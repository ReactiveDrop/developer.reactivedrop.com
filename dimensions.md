# Mapping Distances

## Architecture

| Object | Dimensions |
|---|---|
| 1 foot | 16 units |
| Maximum Climbable Step | 24 units or 45.573\* degree slope |
| Small Vent | 64×64 |
| Small Hallway | 192 wide |
| Large Hallway | 384 wide |
| Very Large Hallway | 896 wide |
| Standard heavy door | 32×128×160 |
| Vault door | 16×160×160 |

\*The exact maximum slope angle is arccos(0.7).

## Creature Hulls

| Creatures | Dimensions |
|---|---|
| Marine | 32×32×70\* |
| Colonist, all zombies | 26×26×72 |
| Drone (all variants) | 40×40×69 |
| Ranger | 40×40×69 |
| Buzzer | 20×20×20\* |
| Boomer | 60×60×110 |
| Parasite, Xenomite, Grub | 24×24×12 |
| Shieldbug | 80×80×72 |
| Mortarbug | 46×46×69 |
| Harvester | 46×46×69 |
| Shaman | 32×32×64 |
| Queen | 240×240×160 |
| Antlion (both) | 32×32×64 |
| Antlion Guard (both) | 60×60×110 |
| Headcrab (all variants) | 24×24×12 |

\*Marine hulls are biased 2 units south (regardless of camera orientation).
\*Buzzer hulls are vertically centered. All other hulls start at the origin and go up.

## Player View

With `asw_controls 1`, the camera has a fixed angle when moving the mouse. Unless explicitly disabled in `asw_gamerules`, players can rotate the camera's yaw axis in 90 degree increments. For other values of `asw_controls`, the player has full control of the camera angle.

The player can also change the center point of their view on the X and Y axes by moving their mouse. The default values for maximum camera shifting offsets are 300 left/right, 200 forward, and 380 back.

<form id="calculator" class="d-flex">
<fieldset class="flex-item-equal"><legend>Calculator</legend>
<label>Camera Pitch <input type="number" min="0" max="90" id="pitch" value="60" size="5" tabindex="0"></label>
<label>Distance <input type="number" min="0" max="10000" id="dist" value="412" size="5" tabindex="0"></label><br>
<label>Field of View <input type="number" min="20" max="75" id="fov" value="75" size="5" tabindex="0"></label><br>
<label>Aspect Ratio <input type="number" min="1" max="1000" id="aspect_w" value="16" size="5" tabindex="0"></label>
<label>by <input type="number" min="1" max="1000" id="aspect_h" value="9" size="5" tabindex="0"></label><br>
<label>Distance Above Floor <input type="number" min="-8192" max="8192" id="test_z" value="0" size="5" tabindex="0"></label>
</fieldset>
<fieldset class="flex-item-equal"><legend>Result</legend>
<p id="result1"></p>
<p id="result2"></p>
</fieldset>
</form>
<script>
const inputs = {};
["calculator", "result1", "result2", "pitch", "dist", "fov", "aspect_w", "aspect_h", "test_z"].forEach(name => {
	const el = document.getElementById(name);
	inputs[name] = el;
	if (el.nodeName === "INPUT") {
		el.addEventListener("input", recalculate, false);
	}
});
function recalculate() {
	if (!inputs.calculator.reportValidity()) {
		return;
	}
	const pitch = Math.PI - inputs.pitch.valueAsNumber * Math.PI / 180;
	const camOffsetY = -inputs.dist.valueAsNumber * Math.cos(pitch); // camera -> feet
	const camOffsetZ = -inputs.dist.valueAsNumber * Math.sin(pitch); // camera -> feet
	const aspect = inputs.aspect_w.valueAsNumber / inputs.aspect_h.valueAsNumber;
	const halfFOVY = inputs.fov.valueAsNumber * Math.PI / 360;
	const halfFOVX = Math.atan(aspect * Math.tan(halfFOVY));
	const angleTop = pitch + halfFOVY; // +z sin, +y cos
	const angleBottom = pitch - halfFOVY; // +z sin, +y cos
	const testZ = inputs.test_z.valueAsNumber + camOffsetZ; // camera -> floor
	const floorTopY = testZ / Math.tan(angleTop) - camOffsetY;
	const floorBottomY = testZ / Math.tan(angleBottom) - camOffsetY;
	const floorTopX = -testZ * Math.sin(halfFOVX) / Math.sin(angleTop);
	const floorBottomX = -testZ * Math.sin(halfFOVX) / Math.sin(angleBottom);
	if (floorTopY <= floorBottomY) {
		inputs.result1.textContent = "The player cannot see a floor that is " + inputs.test_z.valueAsNumber.toFixed(1) + " units above their feet.";
		inputs.result2.textContent = "";
	} else {
		inputs.result1.textContent = "The player can see a floor that is " + inputs.test_z.valueAsNumber.toFixed(1) + " units above their feet from " + floorTopY.toFixed(1) + " units in front of them to " + (-floorBottomY).toFixed(1) + " units behind them.";
		inputs.result2.textContent = "At the far end, the player can see " + floorTopX.toFixed(1) + " units to the left and right on the floor, and at the near end, the player can see " + floorBottomX.toFixed(1) + " units to the left and right on the floor.";
	}
}
recalculate();
</script>
