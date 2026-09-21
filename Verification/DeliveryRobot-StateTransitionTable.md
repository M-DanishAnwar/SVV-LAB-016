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

---

## Verification Activity

### Check 1 — Invalid Transition: IDLE -> DELIVERING
* **Can this happen?** No.
* **Requirement Violated:** R-10 (and R-02).
* **Explanation:** A robot in IDLE is physically at the warehouse. Allowing it to jump directly to DELIVERING means the package door opens at the warehouse without traveling to the customer.

---

### Check 2 — Missing Transition: NAVIGATING -> AVOIDING_OBSTACLE with no return path
* **What happens?** The robot enters a deadlock (trap state).
* **Can the robot continue its delivery?** No.
* **Explanation:** Without transition T-03 (Obstacle Avoided -> NAVIGATING), the robot will stay stuck in obstacle mode forever until its battery dies.

---

### Check 3 — Obstacle During Delivery: AVOIDING_OBSTACLE -> DELIVERING
* **Can this happen?** No, direct transition is prohibited.
* **Requirement Violated:** R-10.
* **Explanation:** The robot cannot deliver while still performing avoidance maneuvers. It must first clear the obstacle, return to NAVIGATING, reach a stable stop at the destination, and only then start DELIVERING.
