# Scenario Specification: Lane Keeping Assist (LKA) on Curved Road

## 1. Overview
This scenario evaluates the performance of a Lane Keeping Assist (LKA) system on a road with varying curvature. The objective is to assess the ego vehicle’s ability to maintain lane centering and stability while traversing curved and near-straight segments.

---

## 2. Road Geometry

The road consists of two primary segments:

- Segment 1:
  - Radius: **127.48 m**
  - Central angle: **22.62°**
  - Direction: Left curve

- Segment 2:
  - Type: **Near-straight / very low curvature segment**

- Lane configuration:
  - Single lane in ego direction
  - Clearly marked left and right lane boundaries

---

## 3. Initial Conditions

### Ego Vehicle
- Initial position: **Centered in lane**
- Initial speed: **0 km/h (at rest)**
- Control: **LKA system enabled**

---

## 4. Scenario Description

1. The ego vehicle starts from rest, centered within its lane.

2. The vehicle accelerates smoothly from **0 km/h to 30 km/h**.

3. As the vehicle encounters the **left curved segment**, the LKA system must:
   - Detect lane boundaries
   - Apply appropriate steering corrections
   - Maintain lane centering

4. The vehicle then transitions into a **near-straight segment**, where:
   - Minimal steering correction is expected
   - Stability and smoothness of control are evaluated

---

## 5. Key Parameters

| Parameter           | Description                               | Value / Variable     |
|--------------------|-------------------------------------------|----------------------|
| Curve radius       | Radius of curved segment                  | 127.48 m             |
| Curve angle        | Angle of curved segment                   | 22.62°               |
| Vehicle speed      | Speed profile of ego vehicle              | 0 → 30 km/h          |
| Lane width         | Width of lane                             | Configurable         |
| Lateral deviation  | Offset from lane center                   | Measured output      |
| Steering input     | Steering command from LKA                 | Measured output      |

---

---

## 6. Files in this Folder

| File | Format | Use with |
|---|---|---|
| `LKA.rrscene` | RoadRunner Scene | RoadRunner |
| `LKA.rrscenario` | RoadRunner Scenario | RoadRunner |
| `LKA_IPG.xosc` | OpenSCENARIO 1.2 | IPG CarMaker / any OpenSCENARIO tool |
| `LKA_IPG.xodr` | OpenDRIVE | IPG CarMaker / any OpenDRIVE tool |
| `LKA_IPG.osgb` | OpenSceneGraph binary (3D mesh) | IPG CarMaker |
| `LKA_IPG.geojson` | GeoJSON road data | GIS / custom tools |
| `LKA.mp4` | Video preview | Reference |

> The `.xosc`, `.xodr`, and `.osgb` files must remain in the **same folder**.

---

## 7. Road Geometry (from OpenDRIVE)

The road is 1002.3 m long and consists of the following segments in sequence:

| Segment | Type | Length | Notes |
|---|---|---|---|
| 1 | Straight | 24.5 m | Entry straight |
| 2 | Left arc | 50.8 m | Curvature −0.00388 rad/m |
| 3 | Right arc | 50.3 m | Curvature +0.00784 rad/m |
| 4 | Straight | 51.0 m | Mid straight |
| 5 | Left arc | 50.3 m | Curvature −0.00784 rad/m |
| 6 | Right arc | 50.8 m | Curvature +0.00388 rad/m |
| 7 | Straight | 724.5 m | Long exit straight |

The S-curve section (segments 2–6) spans ~253 m and forms a symmetric chicane. The LKA system must handle continuous lane-centering corrections through this section before stabilising on the long straight.

---

## 8. Scenario Parameters (from OpenSCENARIO)

| Parameter | Value |
|---|---|
| Road length | 1002.3 m |
| Ego vehicle | Sedan — mass 1500 kg |
| Ego start speed | 0 km/h |
| Ego acceleration | 4 m/s² → target 30 km/h (8.33 m/s) |
| Traffic | None |
| Simulation stop | 60 s elapsed OR collision |

---

## 9. How to Run This Scenario

→ See the [master README](../../README.md) for step-by-step instructions for both **RoadRunner** and **IPG CarMaker**.
