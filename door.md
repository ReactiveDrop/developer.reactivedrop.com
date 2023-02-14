# How to make a door for Alien Swarm: Reactive Drop

Doors require a single body group of 5 models:

0. Undamaged (this is the only state where the door can move)
1. Partially damaged from front (toward positive X)
2. Completely damaged from front (toward positive X, `door_rear_fall` can play in this state)
3. Partially damaged from rear (toward negative X)
4. Completely damaged from rear (toward negative X, `door_front_fall` can play in this state)

## Physics

Doors need a collision model. Usually, this can just be a single rectangular solid. The mass should also be set to something reasonable for a giant metal door in case fallen door physics is enabled for a custom challenge. The default door models have a mass of slightly over 12 metric tons.

## Animations

Doors require three animation sequences: an idle animation (which can have any name but must be defined first), `door_rear_fall`, and `door_front_fall`.

The idle animation works like any other model in Source Engine. Opening and closing the door is done by moving the entire entity, so the idle animation can be as short as a single frame.

The fall animations require some events to work properly:

```
{ event AE_CL_PLAYSOUND 0 "ASW_Door.MeleeDown" }
{ event AE_START_SCRIPTED_EFFECT 5 "" }
{ event AE_START_SCRIPTED_EFFECT 10 "" }
{ event AE_START_SCRIPTED_EFFECT 15 "" }
```

The `AE_CL_PLAYSOUND` event is required to make the door play a sound when destroyed. Otherwise, the door will fall silently.

There must be exactly three `AE_START_SCRIPTED_EFFECT` events, which correspond to the [three damage traces](
https://user-images.githubusercontent.com/4257305/200387590-c587b981-48ea-44ed-895c-ff7c82821854.mp4) that a falling door performs. On the second trace, an invisible collision model will be created for the fallen door.

Here are the default values for the damage traces done by a falling door. To visualize the traces performed by the engine, set `ai_show_hull_attacks 1` in the developer console. `wide` and `deep` should be slightly less than half the size of the door, and `tall` should be slightly less than the full height of the door.

```
$keyvalues {
	asw_door {
		wide	60
		deep	10
		tall	140

		crush_offset_1	40
		crush_offset_2	49
		crush_offset_3	99

		crush_length_1	26.64
		crush_length_2	53.28
		crush_length_3	80.00

		hit_sound	"ASW_Door.MeleeHit"
		dent_sound	"ASW_Door.Dented"
	}
}
```
