# Scenario Specification: Endurance — Full Autonomous Driving with Pedestrian Crossing

## 1. Overview

This scenario evaluates a fully autonomous driving system over a 1 km course. The ego vehicle must navigate the road at a constant speed while avoiding a pedestrian who steps out into the road ahead. Both lateral and longitudinal control must come from the algorithm — this is the combined test for the Endurance event.

---

## 2. Road Geometry

The road is 1002.3 m long and forms a single continuous road with a defined start and end. The ego vehicle must travel the full length of the road within the simulation time window.

- **Total road length:** ~1002 m
- **Lane configuration:** Single driving lane in ego direction
- **Lane markings:** Clearly defined left and right boundaries

---

## 3. Initial Conditions

### Ego Vehicle
- **Model:** SK_Sedan
- **Initial speed:** 30 km/h (8.33 m/s) — vehicle starts moving immediately
- **Initial position:** 10 m from the road start (lane 1)
- **Control:** Full autonomous — both lateral and longitudinal

### Pedestrian (NCAP_Man_Pedestrian)
- **Initial speed:** 0 km/h (stationary at roadside)
- **Initial position:** ~309 m along the road, offset to the side of the carriageway
- **Pedestrian starts moving when:** The ego vehicle comes within **38 m** (Euclidean distance)

---

## 4. Scenario Description

1. The **ego vehicle** starts at 30 km/h and maintains speed along the road.

2. A **pedestrian** (NCAP_Man_Pedestrian) waits stationary at the side of the road at approximately 309 m down the track.

3. When the ego vehicle closes to within **38 m** of the pedestrian, the pedestrian begins walking **across the road** at **6.4 km/h (1.78 m/s)**, moving from the roadside into the driving lane.

4. The pedestrian's trajectory crosses the full width of the carriageway (from offset −1.79 m to the opposite side, a traverse of ~17 m).

5. The autonomous system must:
   - Detect the pedestrian in its path
   - Decide to slow down, stop, or steer around the pedestrian
   - Resume forward progress after the pedestrian has cleared
   - Maintain lane centering throughout the rest of the course

6. The scenario ends when **60 seconds** have elapsed or a **collision** occurs.

---

## 5. Key Parameters

| Parameter | Description | Value |
|---|---|---|
| Road length | Total length of track | ~1002 m |
| Ego vehicle | Vehicle model | SK_Sedan (mass 1000 kg) |
| Ego initial speed | Speed at scenario start | 30 km/h (8.33 m/s) |
| Pedestrian model | NCAP pedestrian | NCAP_Man_Pedestrian (mass 62 kg) |
| Pedestrian trigger distance | Distance at which pedestrian starts moving | 38 m (Euclidean) |
| Pedestrian walking speed | Speed after trigger | 6.4 km/h (1.78 m/s) |
| Pedestrian crossing distance | Traverse across road | ~17 m |
| Pedestrian position (road) | Distance along road | ~309 m |
| Simulation stop condition | Time limit | 60 s |
| Simulation stop condition | Collision | Ego ↔ pedestrian |

---

## 6. Files in this Folder

| File | Format | Use with |
|---|---|---|
| `Endurance.rrscene` | RoadRunner Scene | RoadRunner |
| `Endurance.rrscenario` | RoadRunner Scenario | RoadRunner |
| `Endurance_IPG.xosc` | OpenSCENARIO 1.2 | IPG CarMaker / any OpenSCENARIO tool |
| `Endurance_IPG.xodr` | OpenDRIVE | IPG CarMaker / any OpenDRIVE tool |
| `Endurance_IPG.osgb` | OpenSceneGraph binary (3D mesh) | IPG CarMaker |
| `Endurance_IPG.geojson` | GeoJSON road data | GIS / custom tools |
| `Endurance.mp4` | Video preview | Reference |

> The `.xosc`, `.xodr`, and `.osgb` files must remain in the **same folder** — the scenario file references the others by relative path.

---

## 7. How to Run This Scenario

→ See the [master README](../../README.md) for step-by-step instructions for both **RoadRunner** and **IPG CarMaker**.
