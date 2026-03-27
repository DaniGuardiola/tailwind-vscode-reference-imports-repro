# Tailwind VS Code `@reference` imports repro

This repository reproduces a VS Code navigation issue with Tailwind CSS v4.

## Steps

1. Open this repository in VS Code.
2. Open `src/app.css`.
3. Cmd+Click `#theme.css` in `@reference "#theme.css";`.

## Expected

VS Code resolves the alias from `package.json#imports` and opens `src/theme.css`.

## Actual

VS Code treats `#theme.css` like a literal file path and shows an error saying the file could not be found.

## Notes

- The link is rendered as clickable in the editor.
- The alias is defined in `package.json`:

```json
{
  "imports": {
    "#theme.css": "./src/theme.css"
  }
}
```
