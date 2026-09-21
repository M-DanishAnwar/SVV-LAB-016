# Delivery Robot State and Event Model

## 1. System States

| State Id | State name | Description | Entry Condition | Exit Condition |
| :---: | :--- | :--- | :--- | :--- |
| S-01 | IDLE | Robot is stationary at the warehouse waiting for orders | Power ON or Warehouse Reached | Delivery Request Received |
| S-02 | NAVIGATING | Robot is actively moving along the planned route | Delivery Request Received or Obstacle Avoided | Obstacle Detected, Destination Reached, or Critical Battery |
| S-03 | AVOIDING_OBSTACLE | Robot pauses normal transit to steer around an obstacle | Obstacle Detected | Obstacle Avoided or Critical Battery |
| S-04 | DELIVERING | Robot is at destination handing over package | Destination Reached | Delivery Successful |
| S-05 | RETURNING | Robot is traveling back to warehouse | Delivery Successful or Critical Battery | Warehouse Reached or Obstacle Detected |

---

## 2. System Events / Triggers

| Event Id | Event Name | Description |
| :---: | :--- | :--- |
| E-01 | Delivery Request Received | New order assigned with target destination |
| E-02 | Obstacle Detected | Sensor detects an object blocking path |
| E-03 | Obstacle Avoided | Path is cleared around obstacle |
| E-04 | Destination Reached | Robot arrives at delivery destination |
| E-05 | Delivery Successful | Package handoff is completed |
| E-06 | Critical Battery | Battery drops below safe limit during transit |
| E-07 | Warehouse Reached | Robot docks back at warehouse base |
