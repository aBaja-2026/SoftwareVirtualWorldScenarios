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
