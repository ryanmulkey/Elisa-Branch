## Develop and publish

Requires Node.js 22.13 or newer.

```sh
npm ci
npm run dev
```

After making changes, run `npm run build`. The output is in `docs/`. To update the current flat GitHub deployment, copy the generated JS and CSS to `app.js` and `styles.css` at repository root, update their paths in `index.html`, and copy `docs/models/test-ear.glb` to `test-ear.glb`. Replace `./models/test-ear.glb` with `./test-ear.glb` in the compiled JS. Commit these files along with the updated source archive. Relative asset paths support project hosting and a future custom domain.


## Model credit

“Human Ear” by girts.urbacans, CC BY 4.0, via AiZity. See `public/models/ATTRIBUTION.md`. The application centers, scales, mirrors, and optionally recolors the mesh.
