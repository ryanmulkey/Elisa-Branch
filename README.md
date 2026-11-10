# Elisa Planner

A personal 3D ear-piercing planner, with sixteen named piercing presets and adjustable jewelry.

## Website

Published at https://ryanmulkey.github.io/Elisa-Branch/ from the `main` branch, repository root.

Desktop decoration appears above 1100 px with a fine pointer and hover support. The sidebars use the approved Gothic cathedral study at subdued opacity, with rose-window tracery, quatrefoils, and foliate piers. The bottom displays only the original rose petal lace; it has no click switch. Phones and touch-only tablets retain the plain layout.

The interface uses three steps: choose a piercing, choose a jewelry style, and jewelry settings. Scrollbars are hidden while scrolling remains enabled; new sessions start with an empty ear.

Panels can be collapsed independently with their header buttons, or hidden together using Focus view. The ear viewport expands without changing the arrangement. Use the edge buttons or Show panels to restore them. The interface uses a black rose favicon and rose motifs. The header pairs a bundled UnifrakturCook blackletter wordmark with a rose stem that wraps underneath as an underline. The font is licensed under SIL OFL 1.1; see `FONT-LICENSE.txt`.

Choose Skin tone in the footer to open Ear appearance. Six presets and a custom color picker recolor the ear material. The chosen color is included in saved looks and exported JSON plans; Brown is the starting color when no skin tone is saved; existing saved color choices are preserved. Original textures remain available on supported renderers.

## Features

- A rotatable 3D test ear, mirrored for left/right arrangements.
- Sixteen starting locations: four lobe positions; upper, mid, lower and floating helix; flat; two forward helix positions; rook; daith; snug; conch; tragus.
- Ball studs, gem studs, hoops, barbells, and lobe gauge/plug jewelry with dimensions, finish, and six degrees of freedom: X/Y/Z position and X/Y/Z rotation. Nominal gauge labels are shown alongside millimeters.
- One piece per location; changing jewelry at an occupied location updates the piece.
- Linked chains between two visible stud, gem, hoop, or barbell pieces on the same ear, with adjustable drop, wire thickness, and finish. Endpoint positions follow jewelry changes. Deleting an endpoint or changing it to a plug removes its connections. Chains are visual drapes, without modeled clasps or physical fit simulation.
- Saved looks in this browser, JSON plan import/export, and PNG image export, including chains and plug sizes.
- Self-contained GLB import with a reference-height control. Models must be cropped to the ear, Y-up, front facing +Z.
- WebGL rendering with a CPU canvas fallback. Photo textures require WebGL.

## Develop and publish

Requires Node.js 22.13 or newer.

```sh
npm ci
npm run dev
```

After making changes, run `npm run build`. The output is in `docs/`. To update the current flat GitHub deployment, copy the generated JS and CSS to `app.js` and `styles.css` at repository root, update their paths in `index.html`, and copy `docs/models/test-ear.glb` to `test-ear.glb`. Replace `./models/test-ear.glb` with `./test-ear.glb` in the compiled JS. Commit these files along with the updated source archive. Relative asset paths support project hosting and a future custom domain.

All arrangements and imported models stay in the visitor's browser. No backend or ChatGPT sign-in is required. Browser storage can be cleared; retain exported plans and original model files as backups. Data saved at a different website origin does not automatically transfer here.

Position controls translate jewelry along the ear model’s X/Y/Z axes (left/right, up/down, in/out), from −100 to +100 mm relative to its starting placement. Rotation controls cover −180° to +180° about the jewelry’s starting local axes in XYZ order. Numeric inputs allow fine adjustments. Reset clears all six offsets; moving to another preset starts from that template’s orientation. Saved looks, JSON import/export, reload, and style changes preserve free placement. Chains follow the adjusted endpoints. Existing rotation/tilt/depth values are retained as the starting pose for older plans. New jewelry defaults to silver; existing saved finishes are preserved.

## Limits

Preset locations are approximate landmarks for visual planning. They do not assess anatomical feasibility, tissue thickness, healing, or certified jewelry fit. The test ear is a surface model and the opposite ear is mirrored geometry. Photo reconstruction is not included.

## Model credit

“Human Ear” by girts.urbacans, CC BY 4.0, via AiZity. See `public/models/ATTRIBUTION.md`. The application centers, scales, mirrors, and optionally recolors the mesh.
