# Requirements Document

## Functional Requirements

| Req-Id | Description | priority |
| :--- | :--- | :---: |
| R-01 | When the robot is powered on, it shall stay idle at the warehouse and wait for a delivery request. | High |
| R-02 | Upon receiving a new delivery request, the robot shall start moving toward the delivery destination. | High |
| R-03 | While moving, the robot shall continuously check surroundings and stop navigation if an obstacle is detected. | High |
| R-04 | When an obstacle is detected, the robot shall switch to obstacle-avoidance mode. | High |
| R-05 | Once the obstacle is cleared, the robot shall resume normal navigation toward the destination. | High |
| R-06 | Upon reaching the destination, the robot shall begin the package delivery process. | High |
| R-07 | After the package is delivered successfully, the robot shall start traveling back to the warehouse. | Medium |
| R-08 | If battery becomes critically low during navigation, the robot shall abort delivery and return to warehouse. | High |
| R-09 | Upon reaching the warehouse, the robot shall return to idle state and wait for the next request. | Medium |
| R-10 | The robot shall not start delivery directly from idle state or while avoiding an obstacle. | High |
