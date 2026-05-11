# How to Use SplatTransform with Polycam

## Step 1 — Capture & Export from Polycam

1. Scan your scene in Polycam (LiDAR or photo mode)
2. After processing, tap **Export**
3. Choose **Gaussian Splat** and export as `.ply`
4. Transfer the `.ply` file to your Mac (AirDrop, Files app, etc.)

## Step 2 — Install SplatTransform

```bash
npm install -g @playcanvas/splat-transform
```

Verify it works:

```bash
splat-transform --version
```

## Step 3 — Convert to a shareable HTML file

```bash
splat-transform yourfile.ply output.html
```

- Replace `yourfile.ply` with your actual file name
- The output name can be anything, as long as it ends in `.html`
- The result is a single file anyone can open in a browser — no app or install needed

## Optional — Useful extras

```bash
# Clean up floating artifacts
splat-transform yourfile.ply --filter-nan --filter-floaters output.html

# Reduce file size (keep 50% of Gaussians)
splat-transform yourfile.ply -F 50% output.html

# Shrink further by stripping spherical harmonics
splat-transform yourfile.ply -H 0 output.html
```
