# 2024 Crafting

Crafting is going to work like in TF2, with simple recipes that take some number of items and spit out a different item or set of items.

Need to determine the costs for these recipes, but here are the rough ideas:

- ? -> specific strange device/weapon (probably a different recipe for each)
- ? -> crafting prestige medal (upgradable in some way)

Additionally, some behind-the-scenes crafting recipes will work more like a shop (the OCM Gift Shop).

- X common currency -> Y carbon
- X common currency -> Y loose wires
- X common currency -> Y specific common crafting item
- X common currency -> Y specific uncommon crafting item
- X common currency -> Y specific rare crafting item
- X common currency -> Y specific regional crafting item

And after completing some of the quests,

- X rare currency + 1 specific one-time item voucher (hidden item) -> 1 specific rare weapon + 1 one-time item voucher used (hidden item)
- 1 OCM Gift Shop Return Voucher (hidden item) + X crafting item -> 1 OCM Gift Shop Return Voucher (hidden item) + Y common currency

Some recipes get crafted automatically when they are available:

- 5 one-time item voucher used (hidden item) -> 1 rare currency conversion license (hidden item)
- X rare currency + 1 rare currency conversion license (hidden item) -> X common currency + 1 rare currency conversion license (hidden item)

## Drops

Random item drops are earned by simply playing the game. There will be options to opt out of item drops or to opt in to item drops but not receive notifications for crafting materials or to not receive notifications for any drop.

Three recurring item drop timers:

### Main

Determined by mission or marine class (randomly, equal chance). Every 15 minutes of gameplay, up to 5 times per day. Drop pools contain crafting items, with different regional crafting items for each mission group. Very rare chance of strange items, with higher weights for items specific to the currently-played marine class.

*xNUMBER inside parentheses means quantity, outside parentheses means weight. Default weight and quantity is 1.*

*Workshop pools are based on the workshop addon ID containing the mission. A = even number, B = odd number.*

#### Mission pools

- Fallback: (Global Shared)x10;(Regional Crafting Item)
- Workshop Competition: (Global Shared)x10;(Regional Crafting Item)x5;(Non-Common Crafting)x4
- Workshop Campaign A: (Global Shared)x10;(Pile of Red Sand)x2;(Corrosive Fluid Sample)x2;(Retrieved Documents)x2;(Roll of Vent Tape)x2
- Workshop Campaign B: (Global Shared)x10;(Antlion Carapace)x2;(Cooled Volcanic Rock)x2;(Unopened SynUp Cola)x2;(Isotopes)x2
- Workshop Bonus A: (Global Shared)x10;(Pile of Red Sand)x2;(Antlion Carapace)x2;(Retrieved Documents)x2;(Unopened SynUp Cola)x2
- Workshop Bonus B: (Global Shared)x10;(Corrosive Fluid Sample)x2;(Cooled Volcanic Rock)x2;(Roll of Vent Tape)x2;(Isotopes)x2
- Standalone Official Missions: (Global Shared)x10;(Cooled Volcanic Rock)x4;(Pile of Red Sand)x3;(Unopened SynUp Cola)x2
- Endless: (Global Shared)x10;(Regional Crafting Item)x2;(Non-Common Crafting)x2;(Antlion Carapace)x3;(Pile of Red Sand)x2
- Deathmatch: (Global Shared)x10;(Regional Crafting Item)x2;(Non-Common Crafting)x2;(Unopened SynUp Cola)x4
- Jacob's Rest: (Global Shared)x10;(Unopened SynUp Cola)x4;(Roll of Vent Tape)x3;(Cooled Volcanic Rock)x2
- Area 9800: (Global Shared)x10;(Isotopes)x4;(Roll of Vent Tape)x3;(Pile of Red Sand)x2
- Operation Cleansweep: (Global Shared)x10;(Isotopes)x4;(Retrieved Documents)x3;(Roll of Vent Tape)x2
- Research 7: (Global Shared)x10;(Antlion Carapace)x4;(Cooled Volcanic Rock)x3;(Corrosive Fluid Sample)x2
- Tears for Tarnor: (Global Shared)x10;(Pile of Red Sand)x4;(Roll of Vent Tape)x3;(Retrieved Documents)x2
- Tilarus-5: (Global Shared)x10;(Unopened SynUp Cola)x4;(Corrosive Fluid Sample)x3;(Pile of Red Sand)x2
- Lana's Escape: (Global Shared)x10;(Roll of Vent Tape)x4;(Isotopes)x3;(Corrosive Fluid Sample)x2
- Paranoia: (Global Shared)x10;(Retrieved Documents)x4;(Antlion Carapace)x3;(Unopened SynUp Cola)x2
- Nam Humanum: (Global Shared)x10;(Corrosive Fluid Sample)x4;(Retrieved Documents)x3;(Isotopes)x2
- BioGen Corporation: (Global Shared)x10;(Roll of Vent Tape)x4;(Retrieved Documents)x3;(Corrosive Fluid Sample)x2
- Accident 32: (Global Shared)x10;(Isotopes)x4;(Antlion Carapace)x3;(Corrosive Fluid Sample);(Roll of Vent Tape)
- Adanaxis: (Global Shared)x10;(Cooled Volcanic Rock)x4;(Pile of Red Sand)x3;(Retrieved Documents);(Isotopes)
- Reduction: *TODO*
- Dead City: *TODO*
- Telic Corporation: *TODO*
- Escape from Rhea: *TODO*

#### Marine class pools

- Officer: (Common)x1500;(Rare no crafting)x4;(Random Strange Officer Weapon)x4;(Random Strange Grenade Launcher)x1
- Special Weapons: (Common)x1500;(Rare no crafting)x4;(Random Strange Special Weapons Weapon)x4;(Random Strange X-33 Damage Amplifier)x1
- Medic: (Common)x1500;(Rare no crafting)x4;(Random Strange Medic Weapon)x4;(Random Strange CR-18 Freeze Grenades)x1
- Tech: (Common)x1500;(Rare no crafting)x4;(Random Strange Tech Weapon)x4;(Random Strange Chainsaw)x1;(Random Strange Hand Welder)x1

#### Shared pools

- Common: (Loose Wires x100);(Carbon x1000);(Loose Wires x25-50)x4;(Carbon x150-300)x4;(Scrap Metal x2)x2;(Electrical Components x3)x2;(Spare Pipe x2)x2;(Plastics x3)x2;(Coolant x2)x2;(Scrap Metal)x3;(Electrical Components)x3;(Spare Pipe)x3;(Plastics)x3;(Coolant)x3;(Crate)x5;(Battery Pack)x5
- Rare no crafting: (Random Strange Device);(Random Strange All Class Weapon)x2;(Random Strange Weapon)
- Global Shared: (Common)x10000;(Non-Common Crafting)x1500;(Rare no crafting)x50
- Non-Common Crafting: (Alien Chitin)x15;(Biomass Sample)x15;(Glowing Green Acid)x15;(Claw Fragment)x15;(Memory Management Unit);(Arithmetic Logic Unit);(Data Storage Medium)
- Regional Crafting Item: (Pile of Red Sand);(Antlion Carapace);(Corrosive Fluid Sample);(Cooled Volcanic Rock);(Retrieved Documents);(Unopened SynUp Cola);(Roll of Vent Tape);(Isotopes)

### Extended

Every 90 minutes of gameplay, no limit. Contains crafting materials including all regional crafting materials, but without the chance for higher quantities.

- (Common)x10;(Scrap Metal);(Electrical Components);(Spare Pipe);(Plastics);(Coolant);(Crate);(Battery Pack);(Loose Wires x25-50);(Carbon x150-300);(Non-Common Crafting);(Regional Crafting Item)

### Pity

Every 100 hours, max 5 times ever, max 1 time per 90 days.

- Bundle containing 1 random strange weapon (with random strange device installed) and 2 random strange devices

## Materials

Ultra-common:

- Loose Wires (drops in groups of 25-50, 100)
- Carbon (drops in groups of 150-300, 1000)

Common:

- Scrap Metal (drops in groups of 1, 2)
- Electrical Components (drops in groups of 1, 3)
- Spare Pipe (drops in groups of 1, 2)
- Plastics (drops in groups of 1, 3)
- Coolant (drops in groups of 1, 2)
- Crates (drops in groups of 1)
- Battery Pack (drops in groups of 1)

Uncommon:

- Alien Chitin (drops in groups of 1)
- Biomass Sample (drops in groups of 1)
- Glowing Green Acid (drops in groups of 1)
- Claw Fragment (drops in groups of 1)

Rare:

- Memory Management Unit (drops in groups of 1)
- Arithmetic Logic Unit (drops in groups of 1)
- Data Storage Medium (drops in groups of 1)

Regional:

- Pile of Red Sand (drops in groups of 1)
- Antlion Carapace (drops in groups of 1)
- Corrosive Fluid Sample (drops in groups of 1)
- Cooled Volcanic Rock (drops in groups of 1)
- Retrieved Documents (drops in groups of 1)
- Unopened SynUp Cola (drops in groups of 1)
- Roll of Vent Tape (drops in groups of 1)
- Isotopes (drops in groups of 1)
