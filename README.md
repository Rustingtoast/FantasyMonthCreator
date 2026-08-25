# Fantasy Calendar Creator (Tauri 2 + Svelte 5 + DaisyUI)

This project now runs on:

- **SvelteKit (Svelte 5)**
- **DaisyUI + Tailwind CSS v4**
- **Tauri 2**

## Development (Deno)

```bash
deno task dev
```

## Tauri

```bash
deno task tauri:dev
```

## Build

```bash
deno task build
deno task tauri:build
```

### Windows installer (.exe, NSIS)

Build on Windows (recommended):

```bash
deno task tauri:build --target x86_64-pc-windows-msvc
```

Cross-build from Linux (experimental):

```bash
deno task tauri:build --target x86_64-pc-windows-gnu
```

Output path example:

```text
src-tauri/target/x86_64-pc-windows-gnu/release/bundle/nsis/<app>_<version>_x64-setup.exe
```

### macOS app bundle (.app/.dmg)

Build on macOS host:

```bash
# Apple Silicon Macs
deno task tauri:build --target aarch64-apple-darwin

# Intel Macs
deno task tauri:build --target x86_64-apple-darwin
```

Output path example:

```text
src-tauri/target/<target-triple>/release/bundle/
```

Note: Cross-platform packaging is limited. For best compatibility and
signing/notarization, build each installer on its matching host OS.

## Project structure

- `src/lib/components`: Svelte UI components
- `src/lib/types`: shared TypeScript types
- `src/routes`: SvelteKit routes/layout
- `src-tauri`: Rust/Tauri backend
