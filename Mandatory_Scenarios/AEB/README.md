# Scenario Specification: Cut-In and Deceleration Event

## 1. Overview
This scenario describes a dynamic traffic interaction involving an ego vehicle and a target vehicle. The objective is to evaluate the ego vehicle’s response to a cut-in maneuver followed by aggressive deceleration of the target vehicle.

---

## 2. Initial Conditions

### Ego Vehicle
- Initial speed: **0 km/h (at rest)**
- Initial position: **Reference point (0 m)**

### Target Vehicle
- Initial speed: **40 km/h**
- Initial position: **10 m behind the ego vehicle**

---

## 3. Scenario Description

1. The **ego vehicle** begins accelerating from rest and reaches a speed of **30 km/h**.

2. The **target vehicle**, initially traveling faster than the ego vehicle, approaches from behind.

3. Once the target vehicle overtakes the ego vehicle, it performs a **lane cut-in maneuver** into the ego vehicle’s lane.

4. The cut-in is triggered when:
   - The target vehicle is positioned **‘x’ meters ahead** of the ego vehicle (longitudinal gap).

5. Immediately after completing the cut-in maneuver, the target vehicle:
   - **Decelerates uniformly** to a complete stop (**0 km/h**)
   - Applies a constant deceleration of **‘y’ m/s²**

---

## 4. Key Parameters

| Parameter                | Description                                      | Value / Variable        |
|-------------------------|--------------------------------------------------|--------------------------|
| Initial ego speed       | Starting speed of ego vehicle                    | 0 km/h                  |
| Ego target speed        | Final speed after acceleration                   | 30 km/h                 |
| Target initial speed    | Speed of target vehicle                          | 40 km/h                 |
| Initial separation      | Distance between vehicles at start               | 10 m (target behind)    |
| Cut-in trigger distance | Distance ahead of ego when cut-in occurs         | x meters                |
| Target deceleration     | Constant deceleration after cut-in               | y m/s²                  |
| Final target speed      | Speed after deceleration                         | 0 km/h                  |

---
---

## 5. Files in this Folder

| File | Format | Use with |
|---|---|---|
| `AEB.rrscene` | RoadRunner Scene | RoadRunner |
| `AEB.rrscenario` | RoadRunner Scenario | RoadRunner |
| `AEB_IPG.xosc` | OpenSCENARIO 1.2 | IPG CarMaker / any OpenSCENARIO tool |
| `AEB_IPG.xodr` | OpenDRIVE | IPG CarMaker / any OpenDRIVE tool |
| `AEB_IPG.osgb` | OpenSceneGraph binary (3D mesh) | IPG CarMaker |
| `AEB_IPG.geojson` | GeoJSON road data | GIS / custom tools |
| `AEB.mp4` | Video preview | Reference |

> The `.xosc`, `.xodr`, and `.osgb` files must remain in the **same folder** — the scenario file references the others by relative path.

---

## 6. Scenario Parameters (from OpenSCENARIO)

| Parameter | Value |
|---|---|
| Road length | 1000 m (straight) |
| Lanes | 2 driving lanes per direction + shoulders |
| Ego vehicle | Sedan — mass 1500 kg, max speed 65 m/s |
| Ego start speed | 0 km/h |
| Ego acceleration | 4 m/s² → target 30 km/h (8.33 m/s) |
| Traffic vehicle | NCAP_Vehicle — mass 1000 kg |
| Traffic start speed | 40 km/h (11.11 m/s), adjacent lane |
| Cut-in trigger | NCAP_Vehicle ≥ 10 m ahead of Sedan (longitudinal gap) |
| Cut-in distance | 20 m (cubic lane change) |
| Post cut-in deceleration | 15 m/s² → 0 km/h |
| Simulation stop | 60 s elapsed OR collision |

---

## 7. How to Run This Scenario

→ See the [master README](../../README.md) for step-by-step instructions for both **RoadRunner** and **IPG CarMaker**.
