# An Uphill Battle

A simple 2D inclined-plane teaching game with a warm cartoon look.

Repository: `UphillBattle`.

## Design Brief

**Status:** Initial concept documentation. This brief records the requested direction and separates it from proposals and decisions still to make. It does not implement a game, select an engine, or commission assets.

### Teaching Goal

Give students an inviting way to explore an inclined plane by changing a few visible variables and observing what happens. Keep the scene and controls simple enough that students can compare trials without a complicated game system getting in the way.

The precise lesson, grade-level vocabulary, and physics model remain to be chosen. The visual concept can be preserved while those choices are refined.

### Approved Concept

- A single 2D scene with a blue sky and gently drifting clouds.
- A green foreground hill, low on the left and peaking on the right.
- A cannon at the lower-left foot of the hill, with a small stick figure beside it.
- Controls along the bottom for **Blast Power**, **Cannonball Size**, **Hill Height**, and **Hill Steepness**.
- A warm, friendly cartoon art style.
- Stronger blasts produce visibly larger cannon recoil and a larger explosion/smoke puff.
- Changing hill steepness must not relocate the cannon. Expanding the hilltop is a suggested way to accommodate the changing hill shape.

### Screen Composition

The sky forms a calm backdrop, while the hill and cannon carry the action. Keep the cannon, stick figure, and lower end of the slope easy to distinguish. Leave the bottom control area separate from the playfield so it does not obscure the cannonball or terrain.

The cannon has a fixed resting position. Its brief recoil animation should read as a firing effect around that position, rather than permanently moving the launcher. A proposed approach is for it to settle back after each shot.

### Controls and Feedback

- **Blast Power:** Changes the strength of the shot. The recoil and explosion/smoke puff become visibly larger as this setting increases. The physical quantity behind this classroom-friendly label is still open.
- **Cannonball Size:** Changes the visible size of the cannonball. Whether it also changes mass is a future physics decision.
- **Hill Height:** Changes the hill's vertical rise. Its interaction with steepness needs an explicit rule.
- **Hill Steepness:** Changes the incline while preserving the cannon's location. Terrain should visibly change rather than moving the cannon to fit it.

Proposed interaction: students adjust a setting, fire, observe, and repeat. A simple **Fire** action and **Reset** action would support this loop; their exact behavior and any measurements are not yet settled. Labels and current settings should be easy to read.

### Proposed Hill Geometry

This is a candidate solution, not an approved implementation rule.

Keep the slope's foot fixed beside the cannon. Give the hill a straight inclined face leading to a right-side plateau, with the plateau's far-right edge fixed.

- At a fixed height, increasing the incline angle shortens the ramp's horizontal run. Its upper endpoint moves left, broadening the right-side plateau.
- At a fixed height, decreasing the incline angle lengthens the horizontal run and narrows the plateau.
- For independent height and steepness controls, one proposal is to let a height change preserve the selected angle and recompute the horizontal run. Raising the hill would then lengthen the ramp and narrow the plateau.

For a straight incline, the proposed relationship is horizontal run = height / tan(angle). The available space imposes limits: very shallow angles or large heights may not fit. Valid ranges and how to communicate limits should be decided before implementation, without silently changing the other selected control.

This proposal preserves the fixed cannon and develops the suggested expanding hilltop. Other geometry choices remain possible.

### Open Design Questions

1. **Motion and Contact:** Does the cannonball roll along the incline, launch through the air and then contact it, or use another clearly explained model? Choose this before claiming the game demonstrates a particular inclined-plane principle. Launch direction, friction, rolling behavior, and impacts follow from that choice.
2. **Size and Mass:** Does size mean radius only, or does mass change too? Larger appearance should not imply an unstated physical relationship.
3. **Blast Terminology:** Does the control represent an impulse, an energy input, or actual power applied over time? These are different quantities. Keep the friendly label provisional until the model and teaching language agree.
4. **Height and Steepness:** Should the proposed independent-control geometry be adopted? What ranges fit the scene while keeping the cannon fixed?
5. **Learning Feedback:** Which observation matters most: reaching the top, distance traveled, maximum height, or another outcome? Decide whether measurements are needed and what resets between trials.

These questions are future design decisions, not blockers to documenting the concept.

### Scope for Now

Documentation only. No game code, generated artwork, engine setup, scoring system, levels, accounts, or other feature expansion is included.
