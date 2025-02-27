# Arma 3 / Vehicles Overhauling v2.5
>*Dependencies: none.*

Vehicles Overhauling (VO) is a free Arma 3 script that provides a system of repairing, refueling, and rearming vehicles by proximity and with any asset of your choice. Also, the services are divided by doctrine: Ground, Air, and Nautical. Each doctrine and even service is easily turned Off or On, according to the editor's needs. If needed, the editor can allow repairing just for ground vehicles while unavailable for air ones, for example. Triggering or code via Eden Editor is needless. VO is configured through only one file, prioritizing implementation simplicity and quick change management that the mission editor might want.


<img src="vo_mission_example.VR/images/thumb.jpg" />


**What to expect from VO script**

- Set what vehicle type has automatic access to ground, air, or nautical services (rearm, repair, refuel);
- Set what service each station (asset) will provide: repair, refuel, or rearm or all of them (full service);
- Every object/asset on Eden Editor can be traceable as a station automatically, it's up to the mission-editor;
- Once configured which assets are stations, on Eden you just drag and drop the asset and the script will track them;
- All repair, refueling, and rearming of Arma 3 and its DLCs and CDLCs assets are already tracked;
- All repair, refueling, and rearming of RHS and CUP assets are already tracked as well;
- 100% compatible with CBA+ACE.
- No code or triggers are needed on Eden Editor;
- Just one file to set your mission easily: _fn_VO_management.sqf_;
- A parking-helper system for planes/jets, no matter where or what is the plane station (including carriers);
- Script working as gold on hosted and dedicated servers;

_

### HOW TO INSTALL / DOCUMENTATION

Video demo: https://www.youtube.com/watch?v=9wAF2JSfV14

Doc: https://github.com/aldolammel/Arma-3-Vehicles-Overhauling-Script/blob/main/_VO_Script_Documentation.pdf

_

### SCRIPT DETAILS

**Global rules**

- Every object/asset on Eden can be a service provider (service station);
- The vehicle that need a service ("target-vehicle" for better understanding here) must be within the station's range of action;
- At least one player must be close (or inside) to the target-vehicle, except drones if the mission-editor authorized through _fn_VO_parameters.sqf_;
- The target-vehicle must not be completely destroyed;
- To provide the service, the station must not be destroyed or under water or flying (supply containers) or even moving (supply vehicles); 
- Each station can provide only the services that it allowed to;
- The service will be provide just for one player at a time;
- AI won't be able to replace a human player to start one or more services.

**Repairing service rules:**

- The target-vehicle must have some damage;
- The target-vehicle engine must be off.

**Refueling service rules:**

- The target-vehicle must have had some fuel consumption;
- The target-vehicle engine must be off.

**Rearming service rules:**

- The target-vehicle must have on-board weaponry;
- Rearming will be done just for spawned magazines (empties or not) with the target-vehicle, so the Editor should pay attention if they’ll set ammo limitation in the vehicle attributes;
- The target-vehicle must have spent some ammunition.

**Ground vehicles rules:**

- To get a service, the target-vehicle must be a land vehicle, including drones;
- The target-vehicle must have its speed at zero or very close to it.

**Air vehicles rules:**

- To get a service, the target-vehicle must be an air vehicle, including drones;
- The target-vehicle must be touching the ground;
- The target-vehicle must be completely stopped;
- If the target-vehicle is a plane, a parking helper will run automatically.

**Nautical vehicles rules:**

- To get a service, the target-vehicle must be a nautical vehicle, including drones;
- The target-vehicle cannot be submerged, even submarines;
- The target-vehicle must have its speed at zero or very close to it.

_

## Ideas or fixes?

Discussion and known issues: https://forums.bohemia.net/forums/topic/239319-release-vehicles-overhauling-script/

_

## Changelog

**v2.5 - Dec 7th 2024**
- Fixed the "Error Undefined variable" in dedicated servers. Some publicVariables declarations were missing;
- Added support for CDLC Western Sahara fuel, ammo, and repair assets;
- Added support for CDLC Reaction Forces fuel, ammo, and repair assets;
- Added support for CDLC Expeditionary Forces fuel, ammo, and repair assets;
- Performance improvements;
- The 'fn_VO_paremeters.sqf' file was renamed to 'fn_VO_management.sqf';
- New structure of folders to make the installation easier;
- Documentation updated.

**v2.2 - Oct 7th 2022**
- FIXED - when feedback messages On, the messages are shown just for the vehicle owner and not for the whole crew team;
- FIXED - bug where vehicles are rearming even when there's no on-board weaponry;
- FIXED - bug where drones could not get serviced when player wasn't close.

**v2.1 - Sep 27th 2022**
- FIXED - bug that made ground and nautical vehicles with complex weaponry don't rearm properly;
- FIXED - bug where amphibious vehicles were receiving duplicate services when at an asset configured as ground and nautical station simultaneously. 
- FIXED - bug that, after a landing, helicopters were able to rearm if they take off but stay into the service range, even on air;
- Documentation has been updated.

**v2.0 - Sep 23th 2022**
- NEW - Now Aircraft Carrier USS Freedom asset can provide all services exclusively for planes. Others vehicles from air and ground doctrine will need some specific assets on carrier's deck to access their available services;
- NEW - Amphibious vehicles even from Air or Ground doctrine are allowed to get services at stations of Nautical doctrine;
- NEW - When debug is true, the mission editor has now an expanded handling error messages and other alerts to help them to find out misconfiguration;
- FIXED - fixed the rearming issues around vehicle with different amount of magazines and turrets;
- FIXED - fixed the bug (remoteExec) in Dedicated Server with parking helper assets weren't doing correctly the plane manouver inside the hangars;
- PERFORMANCE IMPROVED - more functions, less repeatable code lines;
- PERFORMANCE IMPROVED - duplicated content inside asset arrays are automatically deleted; 
- Documentation has been updated.

**v1.7 - Jul 14th 2022**
- ACE auto-detect improvement (now VO knows if "ace_vehicle_damage_enabled" is running);
- Palliative adjustment for "ace_vehicle_damage_enabled" then it's ON; 
- Documentation updated about "ace_vehicle_damage_enabled";
- Documentation updated about "The stations doesn't meet the conditions...".

**v1.5 - Jul 7th 2022**
- ACE auto-detect;
- RHS and CUP assets tracked by default;
- Some bug fixes and performance improvements; 
- Documentation included.

**v1.0 - Mar 4th 2022**
- Hello world.
