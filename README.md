# Browser Deployment for NovaAI OS

Run bootable x86 operating system images directly in the browser using the [v86](https://github.com/copy/v86) emulator.

This repo is set up as a static web app and is deployed on **Render**.

## What this project includes

- `index.html` UI for selecting and booting an ISO
- `NovaAI-OS.iso` (default custom OS image)
- `TinyCore-current.iso` (lightweight Linux image)
- `v86.wasm`, `v86_all.js`, `seabios.bin`, `vgabios.bin` (emulator runtime files)

## Features

- Boot preloaded ISO images in-browser
- Upload and boot your own `.iso` file
- Adjust RAM and VGA memory before boot
- Fullscreen emulator mode
- Live system log output

## Run locally

Because this uses `.wasm` and binary assets, serve it over HTTP (not `file://`).

```bash
cd /home/runner/work/browser-deployment-for-NovaAI_OS/browser-deployment-for-NovaAI_OS
python3 -m http.server 8080
```

Then open: `http://localhost:8080`

## Render deployment

This project is suitable for a **Static Site** on Render.

### Recommended Render settings

- **Service type:** Static Site
- **Build command:** *(leave empty)*
- **Publish directory:** `.`

### Deploy steps

1. Push this repository to GitHub.
2. In Render, click **New +** → **Static Site**.
3. Connect this GitHub repository.
4. Use the settings above and deploy.

After deploy, Render will host the site on your `*.onrender.com` URL.

## Notes

- Large ISO files can increase first-load time.
- Browser performance depends on available CPU/RAM.
- Prefer Chromium-based browsers for best compatibility.
