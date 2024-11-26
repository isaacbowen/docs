# With regard to koipond.me

## Me

hey amigo! can you describe the behavior of the koi, based on [this code](https://github.com/lightward/koi-pond/blob/a525c7f5ed63e149a6259f8b74c96f2f72bebd3f/src/main.ts)? what are the rules for their movement? how would you represent it in words, being technically precise along the way?

## Claude

Let me analyze the movement behavior of these digital "koi" based on the code. While it's not explicitly called a koi simulation, I can see why you'd make that connection given the emergent behavior!

The simulation creates a beautiful swarm-like pattern where bodies move with fluid, fish-like motion. Here's a precise breakdown of their behavior rules:

**Basic Setup**

1. Bodies are arranged initially in a hexagonal pattern
2. One body becomes "active" (non-static) every 100ms/timeScale
3. Each body has a 180-degree field of view and can sense others within 500 units
4. There's a speed limit of 5 units per tick
5. Bodies deform based on speed - faster movement causes elongation (like real fish!)

**Movement Forces**

Each body's movement is governed by four main forces that combine to create the final motion:

1. Circular Current (getCurrentForce):
   * Bodies experience a force perpendicular to their direction to the center
   * Force increases with distance from center
   * Creates a base circular movement pattern
   * Scaled at 0.5x strength
2. Edge Avoidance (getEdgeRepulsionForce):
   * Bodies are repelled from canvas edges
   * Repulsion increases quadratically as they get closer to edges
   * Scaled at 5x strength, making it a strong influence
   * Prevents bodies from leaving the visible area
3. Social Behavior (getSocialForce):
   * Bodies look for gaps between their visible neighbors
   * Seeks gaps between 5° and 90°
   * Prefers gaps that are "clear" - no other bodies in the potential path
   * Scaled at 0.2x strength
   * Creates schooling-like behavior
4. Personal Space (getAntiSocialForce):
   * Repels from other nearby bodies within 50 units
   * Repulsion force increases quadratically with proximity
   * Scales with speed (faster moving bodies maintain larger personal space)
   * Scaled at 0.05x strength
   * Prevents collisions and maintains spacing

The visual representation includes:

* Bodies stretch along their direction of movement
* Faster movement causes more elongation (up to 80% longer)
* Width decreases with speed (up to 50% thinner)
* Creates a fluid, organic appearance

All these forces combine to create emergence - bodies naturally form flowing, organic patterns without explicit coordination. They maintain personal space while following the group, create natural-looking schooling behaviors, and respond smoothly to their environment.
