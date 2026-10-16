# R006 If avatars will enter it, design for them from the first layout

- **Status:** supported (5 project families)
- **Applies when:** The model will be walked through, sat in or ridden, or might be ("make it game ready").
- **Action:** Use the avatar size (default 2 m tall, 0.6 m wide) to set door heights, aisles, stairs, lifts and seats in the first layout. Build collision proxies alongside the mesh. Test visible geometry and collision proxies along every route.
- **Evidence:**
  - Passenger train: "low door headers, a narrow aisle, and solid end walls" found only when made game-ready.
  - High-speed train: two rounds of failures ("Visible geometry clips capsule", "Collision shape obstruction").
  - Walkable cargo spaceship: "nothing is inside them and they aren't reachable" (engines); lift too tight.
  - Three-deck yacht: centre-line route checks passed, then a review with sideways offsets found tight showers, a roof support beside a stair and fittings in the way; headroom measured 1.999 m against a 2 m requirement.
  - Six-deck superyacht: "walls blocking the elevators"; "no colliders until we press enter".
- **Exceptions / counterexamples:** Exterior-only display models.
- **Verify by:** A route check with the agreed avatar passes through every required door, stair and seat.
