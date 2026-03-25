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