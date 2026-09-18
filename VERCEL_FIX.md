# Vercel build fix

If Vercel previously showed `vite: command not found`, the project was being built without the local dev dependencies available (or the dashboard Build Command was bypassing the package script).

This version explicitly installs dev dependencies and uses `npx` for Vite and esbuild.

In Vercel Project Settings:
- Framework Preset: Vite (or Other)
- Build Command: `npm run build`
- Output Directory: `dist`
- Install Command: `npm install --include=dev`

Do not set the Build Command to `vite build` manually; leave it as `npm run build`.
