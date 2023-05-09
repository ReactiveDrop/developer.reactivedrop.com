# 2024 Inventory Management

We have a much more complicated inventory system now than when we first started Heroes of the Interstellar Armed Forces. Accordingly, we need to have a more powerful inventory management interface.

- [ ] Design
- [ ] Style-selectable items
- [ ] Self-serve item deletion
- [ ] Crafting inventory (materials have dedicated slots to make inventory management cleaner)
- [ ] Inventory sorting (items that do not have dedicated slots can be rearranged; client-side only, unless we can find a way to do it in the inventory service)
- [ ] Additional medal slot(s)
- [ ] Swarmopedia items tab

## Overview

The inventory interface is split into multiple screens with narrowly defined purposes.

- [ ] HoIAF Medals (current season expected medal, previous season, other earned hoiaf medals in descending order of recency, equip, delete verbs)
- [ ] Other Medals (detected from item schema, equip, delete verbs)
- [ ] Crafting Material Storage (defined in vdf, delete verb)
- [ ] Other items (equip, attach accessory, delete verbs)
- [ ] Crafting (list of recipes, generated from schema)
- [ ] OCM Gift Shop (generated from schema)
- [ ] Loadout (3 medals, 8 marines, 16 weapons, 8 equipment; can save and load similar to guild wars 1 builds)
- [ ] Loadout Select (shows items that fit into a slot, equip verb, toggle for "show basic items if another version is available" (but need better wording))
- [x] Item showcase (shown when obtaining, creating, upgrading, or inspecting an item)
- [ ] Wait screen

Some items are never shown in inventory lists:

- Currency (shown in OCM Gift Shop and contract campaign screens)
- Hidden items for tracking contract campaign progress

## Verbs

- [ ] Delete (confirmation screen, make it clear that the item will not be returned by support)
- [ ] Equip (sets convar, host_writeconfig; on items that can be equipped in multiple slots, Equip in Slot 1, etc. strings)
- [ ] Attach Accessory (eg. strange weapon + strange device = strange weapon)
- [ ] Change Style: %s1 (on items where style is selectable)
