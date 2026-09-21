# State Transition Table & Verification

## State Transition Table

| Transition Id | From State | Event | To State | Req-Id |
| :---: | :--- | :--- | :--- | :---: |
| T-01 | IDLE | Delivery Request Received | NAVIGATING | R-02 |
| T-02 | NAVIGATING | Obstacle Detected | AVOIDING_OBSTACLE | R-03, R-04 |
| T-03 | AVOIDING_OBSTACLE | Obstacle Avoided | NAVIGATING | R-05 |
| T-04 | NAVIGATING | Destination Reached | DELIVERING | R-06 |
| T-05 | DELIVERING | Delivery Successful | RETURNING | R-07 |
| T-06 | NAVIGATING | Critical Battery | RETURNING | R-08 |
| T-07 | RETURNING | Warehouse Reached | IDLE | R-09 |
| T-08 | RETURNING | Obstacle Detected | AVOIDING_OBSTACLE | R-03, R-04 |
| T-09 | AVOIDING_OBSTACLE | Critical Battery | RETURNING | R-08 |

