# Delivery Robot State and Event Model

## 1. System States

| State Id | State Name | Description |
| :---: | :--- | :--- |
| S-01 | IDLE | Robot is powered on at the warehouse waiting for orders |
| S-02 | NAVIGATING | Robot is actively moving toward destination or warehouse |
| S-03 | AVOIDING_OBSTACLE | Robot stopped normal movement to steer around an obstacle |
| S-04 | DELIVERING | Robot is at the customer location completing package drop-off |
| S-05 | RETURNING | Robot is traveling back to the warehouse |

---

## 2. System Events / Triggers

| Event Id | Event Name | Description |
| :---: | :--- | :--- |
| E-01 | Delivery Request Received | New order assigned with customer destination |
| E-02 | Obstacle Detected | Sensor detects an object blocking the path |
| E-03 | Obstacle Avoided | Path is clear to continue moving |
| E-04 | Destination Reached | Robot arrives at destination coordinates |
| E-05 | Delivery Successful | Package handoff is completed |
| E-06 | Critical Battery | Battery drops below safe limit during navigation |
| E-07 | Warehouse Reached | Robot arrives back at the warehouse base |
