## Layer 2 mod proposals

### Vehicles only (depends_on: Vehicles)
- **Automobiles**: cars, vans, trucks, buses; fuel stations, garages
- **Motorbikes**: motorcycles, scooters, mopeds, ATVs, quads
- **Machinery**: tractors, combine harvesters, excavators, cranes, forklifts
- **Rails**: trains, trams, metro; upgraded tracks, stations
- **Watercraft**: motorboats, yachts, jet skis, ferries, submarines
- **Aviation**: planes, helicopters, airships, hot air balloons; runways, hangars

### Sports only (depends_on: Sports)
- **Field Sports**: football (soccer), rugby, American football, baseball, cricket, field hockey, lacrosse
- **Court Sports**: basketball, volleyball, handball, futsal, netball
- **Racket Sports**: tennis, badminton, table tennis, squash, padel
- **Precision Sports**: golf, archery, darts, bowling, billiards, shooting
- **Athletics**: running, hurdles, relay, long/high jump, pole vault, javelin, shot put, discus
- **Combat Sports**: boxing, wrestling, fencing, judo, karate, MMA
- **Gymnastics**: bars, rings, beam, vault, trampoline
- **Climbing**: climbing walls, bouldering, parkour courses
- **Aquatics**: swimming, diving, water polo, synchronized swimming
- **Ice Sports**: ice hockey, curling, figure skating, speed skating
- **Equestrian**: horse racing, show jumping, dressage, polo (vanilla horses)
- **Fitness**: gym equipment, weights, treadmills

### Both (depends_on: Sports, Vehicles)
- **Motorsports**: race cars, race bikes, karts, rally, drag racing; tracks, pit lanes, timing (optionally_depends_on: Automobiles, Motorbikes)
- **Bikes & Boards** (working name): bicycles, BMX, skateboards, kick scooters, roller skates, unicycles; ramps, skateparks
- **Paddle & Sail**: canoes, kayaks, rowing boats, sailboats, surfboards, windsurfing (optionally_depends_on: Watercraft)
- **Snow Sports**: skis, snowboards, sleds, bobsleigh, luge (optionally_depends_on: Ice Sports)
- **Air Sports**: gliders, hang gliders, paragliders, parachutes, skydiving (optionally_depends_on: Aviation)

### Open decisions
- Motorsports: own race vehicles + optional Automobiles/Motorbikes, or layer 3 depending on them directly?
- Final name for Bikes & Boards

## Weapons proposal

Weapons is a layer 1 mod (depends_on: Core) holding shared weapon systems: projectile base, ammo handling, damage/stats (reach, attack speed, armor penetration, knockback, durability), weapon crafting station, weapon racks, stats tooltip.

### Firearms branch
- **Firearms** (layer 2, depends_on: Weapons): shared gun framework: reloading, recoil, calibers, attachments
  - **Handguns** (layer 3, depends_on: Firearms): revolvers, pistols, derringers, machine pistols
  - **Long Guns** (layer 3, depends_on: Firearms): hunting rifles, assault rifles, sniper rifles, shotguns
  - **Heavy Weapons** (layer 3, depends_on: Firearms): machine guns, RPGs, grenade launchers, flamethrowers (optionally_depends_on: Explosives)
  - **Black Powder** (layer 3, depends_on: Firearms): muskets, flintlocks, blunderbusses, hand cannons

### Traditional weapons (layer 2, depends_on: Weapons)
- **Blades**: swords, daggers, sabers, katanas, rapiers
- **Polearms**: spears, lances, halberds, pikes, glaives
- **Axes & Maces**: battleaxes, maces, warhammers, flails, morning stars
- **Bows**: longbows, recurve bows, crossbows, slings
- **Throwing**: javelins, throwing knives and axes, shuriken, boomerangs

### Other (layer 2, depends_on: Weapons)
- **Explosives**: grenades, dynamite, mines, C4
- **Siege**: catapults, trebuchets, ballistas, cannons (optionally_depends_on: Vehicles)

### Cross-family ideas
- Sports + Weapons: archery, fencing, sport shooting (Precision Sports / Combat Sports could optionally depend on Bows / Blades)
- Vehicles + Weapons: tanks, armed planes, warships, vehicle-mounted turrets
- Equestrian + Polearms: jousting with lances

### Open decisions
- Weapons as one L1 with L2/L3 below, or simpler: Firearms and Medieval as two mods (L2 under Weapons, or L1 directly under Core with shared parts in Core)?
- Merge thin mods back if needed (e.g. Axes & Maces into Blades as "Melee")
- One set of bows: Precision Sports optionally depends on Bows instead of adding its own

## Flags proposal

Flags is a layer 1 mod (depends_on: Core) holding shared flag systems: cloth rendering and waving animation, flag poles (multiple designs), mounting (wall, ground, ship mast), possibly wind direction. Also contains general flags like the Jolly Roger.

Placed directly under Core rather than under a "Decoration" L1, since it shares almost no code with furniture, lamps, etc.

### Flag sets (layer 2, depends_on: Flags)
- **National Flags**: flags of countries
- **Naval Flags**: signal flags, ensigns
- **Organization Flags**: international organizations
- **Historical Flags**: flags of former states and eras
- **Regional Flags**: states, provinces, cities
- **Pride Flags**

### Cross-family ideas
- Watercraft / Paddle & Sail + Naval Flags: flags on ship masts
- Weather + Flags: flags wave according to wind direction
- Space + Flags: planting a flag on the moon
- Sports + Flags: team and stadium flags

### Notes
- Some organization symbols are legally protected (Olympic rings, Red Cross symbol, UN emblem), so check before including them. National flags are generally fine.

## Decoration proposal

Decoration is a layer 1 mod (depends_on: Core) holding the shared placement system: wall/floor/ceiling mounting, rotation, multi-block objects, sittable seats, connected textures, color and wood variants, waterlogging.

If its mounting system ends up substantial, Flags could become a layer 2 mod under Decoration instead of a layer 1 mod.

### Organization rule
Three axes coexist, each item has exactly one home:
1. Seasonal or event-specific → **Occasion** mod
2. Mainly belongs in one room or place → that **Room/function** mod
3. Used across many rooms → **Element** mod

Styles (medieval, modern, rustic...) are material/style variants inside mods, not separate mods. Exception: small themed mods for decor that has no other home (ship wheels, thrones).

### By room or function (layer 2, depends_on: Decoration)
- **Living Room**: sofas, armchairs, coffee tables, TV stands
- **Kitchen**: cabinets, counters, sinks, stoves, fridges
- **Dining**: tables, chairs, sideboards, place settings
- **Bedroom**: beds, wardrobes, dressers, nightstands
- **Bathroom**: bathtubs, showers, toilets, sinks, towel racks
- **Office**: desks, office chairs, filing cabinets, whiteboards
- **Library**: bookshelves, reading lamps, ladders, globes
- **Outdoor & Garden**: patio furniture, garden ornaments, birdbaths, hammocks
- **Playground**: swings, slides, sandboxes, climbing frames
- **Street Furniture**: benches, bins, bollards, bus stops (overlaps with a possible Roads mod)
- **Shop Fittings**: counters, display shelves, mannequins, cash registers
- **Café & Restaurant**: bar counters, stools, menu boards, espresso machines
- **Classroom**: school desks, chalkboards, lockers

### By element (layer 2, depends_on: Decoration)
- **Lighting**: lamps, chandeliers, sconces, lanterns, neon signs
- **Wall Décor**: original paintings, mirrors, clocks, shelves, tapestries
- **Textiles**: rugs, carpets, curtains, blinds, cushions
- **Flooring & Walls**: tiles, parquet, wallpaper, wainscoting
- **Windows & Doors**: door styles, window frames, shutters, stained glass
- **Fences & Gates**: picket fences, iron railings, garden walls
- **Plants & Planters**: potted plants, hanging baskets, flower boxes
- **Pottery & Tableware**: vases, urns, plates, cups, bottles
- **Fireplaces**: fireplaces, stoves, chimneys, firewood stacks
- **Statues & Fountains**: sculptures, busts, fountains, columns
- **Signs & Lettering**: placeable letters, shop signs, house numbers
- **Trophies & Displays**: trophies, medals, display cases (ties in with Sports)
- **Toys**: teddy bears, toy trains, dollhouses, building blocks

### By occasion (layer 2, depends_on: Decoration)
- **Holidays**: Christmas, Halloween, Easter, New Year
- **Party**: balloons, bunting, streamers, confetti, banners

### Small themed mods (layer 2, depends_on: Decoration)
- **Medieval Décor**: thrones, banners, torches, weapon racks (ties in with Weapons)
- **Nautical Décor**: anchors, ship wheels, ropes, portholes (ties in with Maritime, Naval Flags)
- **Industrial Décor**: pipes, metal shelving, exposed bulbs
- **Aquariums & Terrariums**: tanks, filters, decorations (ties in with Wildlife)

### Open decisions
- Likely merges: Dining into Kitchen, Classroom into Office
- Whiteboards: Office owns them, Classroom optionally uses them (if both stay)
- Flags: stay layer 1, or move under Decoration?

## Extra decoration mods

Additional room/function mods for Decoration (layer 2, depends_on: Decoration). Many of these are small: a few recognizable items plus some variation of a help/service desk.

### Possible approach
- Shared **Counters & Desks** element mod (reception, service, ticket, teller, check-in desks) so each small mod only adds its signature items
- Merge small ones into grouped mods (see Possible merges)
- Decoration holds props that only look the part; functional versions (healing bed, working lab bench) belong to functional L1 mods (Medicine, Science, Music, Fitness), with optional deps between them

### Public services
- **Medical**: hospital beds, IV stands, curtains, reception desks, pharmacy shelves, wheelchairs
- **Laboratory**: lab benches, fume hoods, glassware, microscopes, safety showers
- **Police Station**: front desks, holding cells, filing cabinets, evidence lockers
- **Fire Station**: gear lockers, hose racks, sliding poles, alarm bells
- **Post Office**: counters, sorting shelves, parcel piles, PO boxes
- **Bank**: teller counters, vault doors, safe deposit boxes, queue barriers
- **Courtroom**: judge's bench, witness stand, gallery seating
- **Places of Worship**: pews, altars, lecterns, candle stands

### Culture and entertainment
- **Museum & Gallery**: plinths, display cases, rope barriers, info plaques
- **Theater & Cinema**: tiered seating, stage curtains, projectors, ticket booths
- **Concert & Stage**: stage platforms, speakers, spotlights, mixing desks (ties in with Music)
- **Nightclub & Bar**: DJ booths, bar shelves, disco balls, booth seating
- **Recording Studio**: sound panels, microphones, mixing consoles
- **Art Studio**: easels, canvases, paint tubes, sculpting stands

### Services and shops
- **Barbershop & Salon**: barber chairs, hair dryers, lit mirrors
- **Laundromat**: washing machines, dryers, folding tables
- **Garage & Workshop**: tool walls, workbenches, car lifts, tire stacks (ties in with Vehicles)
- **Gas Station**: pumps, canopies, air pumps (ties in with Automobiles)
- **Market Stalls**: fruit stands, awnings, crates, scales

### Leisure
- **Gym**: weight racks, mats, lockers, mirrors (decorative counterpart to Fitness)
- **Spa & Sauna**: sauna benches, hot tubs, massage tables
- **Pool & Beach**: loungers, umbrellas, pool ladders, lifeguard chairs (ties in with Aquatics)
- **Hotel**: reception desks, luggage carts, key boards, room service trolleys
- **Tavern & Inn**: barrels, long tables, bar counters, hanging signs

### Transport hubs
- **Airport**: check-in desks, luggage carousels, departure boards (ties in with Aviation)
- **Train Station**: ticket machines, platform benches, station clocks (ties in with Rails)

### Rural and industrial
- **Farm & Barn**: hay bales, troughs, feed bins, tool racks (ties in with Agriculture)
- **Stable**: stalls, saddle racks, hay nets (ties in with Equestrian)
- **Warehouse**: pallets, pallet racks, crates, loading docks
- **Greenhouse**: potting benches, seed trays, misting pipes

### Home extras
- **Nursery & Kids' Room**: cribs, changing tables, toy chests
- **Attic & Basement**: storage boxes, old trunks, water heaters, shelving

### Possible merges
- Police Station + Fire Station + Post Office → **Public Services**
- Theater & Cinema + Concert & Stage + Nightclub & Bar → **Entertainment**
- Airport + Train Station → **Transport Hubs**

## Clothing proposal

Clothing is a layer 1 mod (depends_on: Core) holding the shared wearable system: rendering clothes as layers on the player model, slot handling, dyeing/colors, tailoring/sewing station, wardrobes, mannequins, outfit saving.

Armor is not a separate family: it is clothing with a protective purpose, so it lives in Protective Gear.

### Organization rule
- Split by **purpose only**, not by body part (no Footwear/Headwear/Accessories groups): every hat, shoe or accessory goes to the purpose mod it belongs to
- **Protective Gear** = clothing whose primary purpose is protecting the body from harm (attacks, impact, falls, hazardous materials). In-game test: gives armor points or damage reduction
- Incidental protection (warmth, rain, sturdy fabric) does not count: those items go by their main purpose

### Clothing sets (layer 2, depends_on: Clothing)
- **Everyday Wear**: shirts, jeans, hoodies, dresses, sneakers, boots, caps, beanies, glasses, bags, watches
- **Formal Wear**: suits, ties, gowns, dress shoes, fedoras, top hats
- **Uniforms**: police, medical, firefighter, military, chef (ties in with Emergency Services, Medical)
- **Sportswear**: jerseys, kits, tracksuits, team colors, football boots, ice skates (ties in with Sports)
- **Workwear**: overalls, hi-vis vests, lab coats (ties in with Construction, Laboratory)
- **Seasonal Wear**: winter coats, gloves, scarves, raincoats, winter boots (ties in with Weather)
- **Swimwear**: swimsuits, goggles, wetsuits (ties in with Aquatics, Paddle & Sail)
- **Protective Gear**: plate armor, riot gear, bulletproof vests, hard hats, bike/motorcycle helmets, knee pads, racing suits, hazmat suits, welding and gas masks (ties in with Weapons, Bikes & Boards, Motorsports)
- **Historical Costumes**: medieval, Roman, Victorian, pirate, crowns
- **Traditional Clothing**: folk costumes from different cultures
- **Costumes**: Halloween and party costumes, witch hats (ties in with Holidays)
- **Jewelry**: rings, necklaces, earrings (ties in with Geology gems)

### Open decisions
- Slots: vanilla armor slots vs separate cosmetic/accessory slots via a library (Trinkets on Fabric, Curios on NeoForge, Accessories works on both)
- Jewelry: own mod, or fold into Everyday/Formal Wear?
- Backpacks with extra inventory are functional, not clothing: belong in Camping or a utility mod

## Possible future layer 1 mods

> [!note] Not planned
> These are only possible future expansions, kept so the ideas aren't lost. None of them are planned for now.

Already covered elsewhere: Armor (Protective Gear in Clothing), Jewelry (Clothing), Furniture (Decoration), Stadiums (Sports or Decoration).

### Close to existing families
- **Roads**: roads, lane markings, traffic lights, road signs, bridges, tunnels, street lamps (ties in with Vehicles)
- **Military**: bases, fortifications, camouflage, bunkers (ties in with Weapons)
- **Maritime**: harbors, lighthouses, buoys, docks (ties in with Watercraft, Naval Flags)
- **Emergency Services**: police, fire and rescue stations and equipment (ties in with Vehicles, Uniforms)

### Technology and industry
- **Energy**: generators, solar, wind, hydro, nuclear, power lines (EV charging for Vehicles)
- **Electronics**: computers, TVs, radios, phones, cameras
- **Industry**: factories, conveyors, assembly lines, vehicle factories
- **Construction**: scaffolding, concrete, steel beams, construction cranes
- **Space**: rockets, satellites, space stations, other planets (ties in with Vehicles, Flags)
- **Science**: labs, chemistry, microscopes, observatories
- **Robotics**: robots, drones, automated arms
- **Tools**: power drills, chainsaws, angle grinders, measuring tools, ladders

### Infrastructure and utilities
- **Plumbing & Water**: pipes, water towers, pumps, purification, sewers
- **Oil & Gas**: drilling rigs, pumpjacks, refineries, fuel for Vehicles
- **Mining**: drills, conveyors, mine carts, quarries
- **Waste & Recycling**: bins, garbage trucks, recycling plants, landfills
- **Logistics**: shipping containers, forklifts, cargo cranes, warehouses
- **Security**: locks, keys, safes, alarms, security cameras, keycard doors
- **Communication**: post offices, mailboxes, telephones, radio towers

### Everyday life
- **Food**: cooking appliances, dishes by cuisine, drinks
- **Agriculture**: real crops, orchards, beekeeping, livestock, vineyards (ties in with Machinery)
- **Commerce**: money, shops, vending machines, ATMs, markets
- **Medicine**: hospitals, first aid, pharmacies (functional counterpart to Medical decor)
- **Education**: schools, textbooks, working blackboards

### Leisure and culture
- **Music**: instruments, speakers, stages, jukebox
- **Games**: board games, chess, cards, arcade
- **Amusement Parks**: roller coasters, Ferris wheels, carousels (uses Vehicles ride mechanics)
- **Camping**: tents, campfires, sleeping bags, backpacks with extra inventory
- **Photography**: cameras, photos, frames, albums
- **Hunting & Fishing**: fishing rods, lures, nets, tackle boxes, hunting stands (ties in with Bows, Wildlife)
- **Printing & Writing**: typewriters, printing presses, newspapers, books
- **Navigation**: compasses, GPS, sea charts, globes, sextants
- **Archaeology**: dig sites, fossils, artifacts, dinosaur skeletons

### Nature and world
- **Wildlife**: real-world animals, zoos, aquariums, pets
- **Plants**: real tree species, flowers, gardening
- **Weather**: seasons, storms, wind, temperature (Seasons could merge here; ties in with Flags, Paddle & Sail, Seasonal Wear)
- **Geology**: real minerals, gems, rocks, gem cutting
- **Disasters**: earthquakes, floods, tornadoes, wildfires

### Crafts
- **Workshops**: blacksmithing, woodworking, pottery, glassblowing
- **Textiles**: weaving, dyeing, sewing (Flags and Clothing could build on it)

### Possibly layer 2 instead
- **Fireworks**: under Weapons (next to Explosives) or Decoration (next to Party)

### Outside the real-world theme
- **Magic**, **Mythology**, **Dragons**: would change what "SelfPropelled" stands for, so a conscious decision
