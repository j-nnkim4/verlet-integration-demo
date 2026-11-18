## verlet integration

**verlet integration** is a numerical method used to integrate Newton's equations of motion, widely used in real-time physics simulations, particle systems, and cloth or soft-body dynamics.

### how it works
* **position-based updates:** unlike standard Euler integration, which tracks explicit velocity vectors, Verlet integration calculates a particle's next position using its current position, its previous position, and current acceleration.
* **implicit velocity:** velocity is derived naturally from the difference between the current and previous positions (`velocity = current_pos - previous_pos`), making it easy to handle collisions and position adjustments directly.
* **distance constraints:** rigid sticks, ropes, and cloth meshes are simulated by iteratively pushing or pulling connected particles back toward their target rest lengths after each position update.

### key characteristics
* **high stability:** offers strong numerical stability and better energy conservation than explicit Euler integration, especially when simulating stiff constraints or interconnected particle networks.
* **simple constraint solving:** moving a particle directly to resolve a collision or satisfy a distance constraint automatically updates its trajectory on the next frame without manual velocity recalculations.
* **fixed timestep sensitivity:** works best with a fixed timestep (`dt`); variable framerates require time-corrected Verlet formulas to prevent unstable forces or drifting velocities.
