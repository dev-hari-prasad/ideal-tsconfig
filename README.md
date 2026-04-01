<h1 align="center">Ideal TS tsconfig.json settings</h1>

This project is a simple reference for a practical and strict TypeScript setup.
It helps you start new projects with safer defaults and cleaner code checks. Simply copy the `tsconfig.json` file into your project or copy the relevant options into your existing configuration.

---


## Options Explained

### File Layout

- `rootDir: "./src"`: Tells TypeScript where your source files live.
- `outDir: "./dist"`: Sends compiled output to `dist`.

### Environment

- `module: "nodenext"`: Uses modern Node.js module behavior (ESM/CJS aware).
- `target: "esnext"`: Emits modern JavaScript.
- `types: []`: Includes no global `@types/*` packages by default (cleaner type environment).

### Build Output

- `sourceMap: true`: Generates source maps for easier debugging.
- `declaration: true`: Creates `.d.ts` files for exported types.
- `declarationMap: true`: Creates maps for declaration files for better editor navigation.

### Safety And Correctness

- `strict: true`: Enables TypeScript strict mode (stronger type checking overall).
- `noUnusedLocals: true`: Reports local variables that are never used.
- `noUnusedParameters: true`: Reports function parameters that are never used.
- `allowUnusedLabels: false`: Disallows labels that are not used.
- `allowUnreachableCode: false`: Reports code that can never run.
- `noFallthroughCasesInSwitch: true`: Prevents accidental fallthrough in `switch` cases.
- `noUncheckedSideEffectImports: true`: Helps catch side-effect-only imports that are not resolved correctly.
- `noUncheckedIndexedAccess: true`: Adds `undefined` when reading via index access (safer array/object indexing).
- `exactOptionalPropertyTypes: true`: Treats optional properties more precisely instead of loosely accepting `undefined`.
- `noPropertyAccessFromIndexSignature: true`: Forces safer access for index-signature-based objects.
- `noImplicitOverride: true`: Requires `override` when overriding base class members.
- `erasableSyntaxOnly: true`: Restricts syntax to erasable TypeScript-only constructs.

### Runtime And Tooling Behavior

- `jsx: "react-jsx"`: Uses the modern React JSX transform.
- `verbatimModuleSyntax: true`: Keeps import/export syntax as written for predictable module output.
- `isolatedModules: true`: Makes each file safe for single-file transpilers and faster toolchains.
- `moduleDetection: "force"`: Treats files as modules consistently.
- `skipLibCheck: true`: Skips type-checking `.d.ts` files for faster builds.
- `noErrorTruncation: false`: Keeps error messages shorter by default.

## Quick Notes

- If you are building a Node.js app, set `types` to `["node"]` and install `@types/node` with `npm install -D @types/node`.
- If you need full, long TypeScript diagnostics while debugging, temporarily set `noErrorTruncation` to `true`.
- For faster local builds, keep `skipLibCheck: true`; for stricter CI checks, some teams run CI with it set to `false`.
