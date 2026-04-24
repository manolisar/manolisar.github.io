# Project Index Landing Page Design

Date: 2026-04-24

## Goal

Replace the current `manolisar.github.io` index page with a polished project landing page for marine engineering tools. The page should feel purpose-built for shipboard fuel and voyage work, not like a generic portfolio page.

The page will present four launch entries:

- Fuel Master
- Voyage Planner
- Voyage Tracker v7
- Voyage Tracker v6, clearly marked as a legacy link

Light mode is the preferred and default theme. Dark mode will be available through a compact toggle.

## Approved Direction

Use the structure of an operational instrument desk with the color and visual language of a nautical chart.

The approved hybrid direction combines:

- A console-like hierarchy that makes the tools feel like launch stations in one working system.
- A light sea-chart surface with subtle grid lines, teal route accents, and warm signal-orange calls to action.
- Gauge, route, and metric motifs that reference fuel conversion, voyage planning, and consumption tracking.
- A secondary dark theme that uses the same layout and accents as a night-watch chart view.

## Content Structure

The page remains a single static HTML document at `index.html`.

The first viewport contains:

- Fixed or sticky navigation with site identity, tool navigation, GitHub link, and a compact theme control.
- Hero copy focused on operational usefulness, with a headline similar to "Plan the leg. Measure the burn."
- A small operational snapshot panel that references the three active domains: fuel, route, and tracking.
- A hint of the tool section below the hero on desktop and mobile.

The tools section contains four launch cards:

- Fuel Master: marine fuel mass-to-volume conversion with density and observed temperature inputs.
- Voyage Planner: speed, power, engine load, sea leg, port, and standby consumption planning.
- Voyage Tracker v7: current local-folder, offline-first voyage fuel tracking.
- Voyage Tracker v6: legacy tracker retained for older workflows and reference access.

The footer stays concise:

- Site identity.
- GitHub link.
- A discreet bottom credit reading `manolisar / dev`, linked to the GitHub account.
- Copyright.
- Optional operational status text.

## Visual Design

The default light theme uses:

- Sea-chart background surface.
- Subtle technical grid lines.
- Deep blue-green text.
- Teal route and system accents.
- Signal-orange launch actions.
- White translucent panels with restrained borders.

The dark theme uses:

- Deep night-chart background.
- Muted teal grid and route accents.
- Light chart-paper text.
- The same signal-orange action color.

Typography should feel editorial and technical:

- A serif display face for the hero and major section headings.
- A compact monospace face for labels, tags, status text, and metadata.
- A readable sans-serif for descriptions.

The visual system should avoid oversized marketing cards, generic gradients, purple-blue styling, and purely decorative blobs. Visual elements should connect back to marine operations: grid, route, gauge, readings, cards as launch stations.

## Interaction

Theme behavior:

- Default to light theme.
- Persist the user's selected theme in `localStorage`.
- Respect the persisted value on reload.
- Provide a visible, compact toggle for light and dark modes.
- If JavaScript fails, the page remains readable in light mode.

Launch behavior:

- Tool cards are ordinary links, so they work without JavaScript.
- Active tools receive primary "Launch App" treatment.
- Voyage Tracker v6 receives "Legacy Link" treatment and a visually quieter card style.

Motion:

- Use restrained CSS transitions for hover and reveal.
- Respect `prefers-reduced-motion`.
- Avoid motion that changes layout dimensions or obscures content.

## Links

Use the existing deployed paths:

- Fuel Master: `/FuelMaster/`
- Voyage Planner: `/voyage-planner/`
- Voyage Tracker v7: `/voyage-tracker-v7/`
- Voyage Tracker v6 legacy: `/VoyageTracker/`
- GitHub: `https://github.com/manolisar`

## Responsive Behavior

Desktop:

- Hero uses a two-column composition: headline/copy and operational snapshot.
- Tool cards sit in a four-column launch grid where space allows.

Tablet:

- Hero stacks if needed.
- Cards become two columns.

Mobile:

- Navigation hides nonessential links and keeps identity plus theme toggle.
- Hero stacks in one column.
- Cards become one column.
- Text must not overflow buttons, cards, or tags.

## Accessibility

- Use semantic HTML: `nav`, `main`, `section`, `article`, and `footer`.
- Cards must be keyboard-focusable links with visible focus states.
- Theme toggle must be a real button with an accessible label and pressed/current state.
- Text contrast must be strong in both themes.
- Decorative visuals should be hidden from assistive technology where appropriate.

## Implementation Scope

The implementation should update only the static site in `manolisar.github.io`, primarily `index.html`.

The current untracked visual companion files under `.superpowers/` and any unrelated untracked files must not be committed as part of this change.

## Testing

Manual and automated checks should cover:

- Open the static file or serve the repo locally and verify the page renders.
- Verify all four tool links point to the intended paths.
- Toggle light/dark mode and reload to confirm persistence.
- Check desktop, tablet, and mobile viewports.
- Confirm text does not overlap or overflow.
- Confirm keyboard focus is visible on cards and the theme toggle.
- Run any available static checks if the repo gains a build step, otherwise validate the HTML/CSS/JS behavior directly in the browser.
