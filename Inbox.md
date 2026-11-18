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
- **Motorsports**: race cars, race bikes, karts, rally, drag racing; tracks, pit lanes, timing (optional_deps: Automobiles, Motorbikes)
- **Bikes & Boards** (working name): bicycles, BMX, skateboards, kick scooters, roller skates, unicycles; ramps, skateparks
- **Paddle & Sail**: canoes, kayaks, rowing boats, sailboats, surfboards, windsurfing (optional_deps: Watercraft)
- **Snow Sports**: skis, snowboards, sleds, bobsleigh, luge (optional_deps: Ice Sports)
- **Air Sports**: gliders, hang gliders, paragliders, parachutes, skydiving (optional_deps: Aviation)

### Open decisions
- Motorsports: own race vehicles + optional Automobiles/Motorbikes, or layer 3 depending on them directly?
- Final name for Bikes & Boards

## Weapons proposal

Weapons is a layer 1 mod (depends_on: Core) holding shared weapon systems: projectile base, ammo handling, damage/stats (reach, attack speed, armor penetration, knockback, durability), weapon crafting station, weapon racks, stats tooltip.

### Firearms branch
- **Firearms** (layer 2, depends_on: Weapons): shared gun framework: reloading, recoil, calibers, attachments
  - **Handguns** (layer 3, depends_on: Firearms): revolvers, pistols, derringers, machine pistols
  - **Long Guns** (layer 3, depends_on: Firearms): hunting rifles, assault rifles, sniper rifles, shotguns
  - **Heavy Weapons** (layer 3, depends_on: Firearms): machine guns, RPGs, grenade launchers, flamethrowers (optional_deps: Explosives)
  - **Black Powder** (layer 3, depends_on: Firearms): muskets, flintlocks, blunderbusses, hand cannons

### Traditional weapons (layer 2, depends_on: Weapons)
- **Blades**: swords, daggers, sabers, katanas, rapiers
- **Polearms**: spears, lances, halberds, pikes, glaives
- **Axes & Maces**: battleaxes, maces, warhammers, flails, morning stars
- **Bows**: longbows, recurve bows, crossbows, slings
- **Throwing**: javelins, throwing knives and axes, shuriken, boomerangs

### Other (layer 2, depends_on: Weapons)
- **Explosives**: grenades, dynamite, mines, C4
- **Siege**: catapults, trebuchets, ballistas, cannons (optional_deps: Vehicles)

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
