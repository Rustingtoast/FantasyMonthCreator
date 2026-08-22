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

## Project structure

- `src/lib/components`: Svelte UI components
- `src/lib/types`: shared TypeScript types
- `src/routes`: SvelteKit routes/layout
- `src-tauri`: Rust/Tauri backend
