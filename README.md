# @zakodium/tsconfig

Shared TypeScript configurations for projects that Zakodium maintains.

## Installation and usage

Install the package:

```console
npm install -D @zakodium/tsconfig
```

Then extend in your own config:

```json
{
  "extends": "@zakodium/tsconfig",
  "compilerOptions": {},
  "include": ["src"]
}
```

## Available configs

### Base config

[`"extends": "@zakodium/tsconfig"`](./configs/tsconfig.base.json)

The base config, suitable for most projects:

- Opinionated defaults for strict type checking
- Ready to compile a library with source maps
- Targets ES2022 for modern and widely supported JS
- Ready for native Node.js TypeScript support

### JSX (React) config

[`"extends": "@zakodium/tsconfig/jsx"`](./configs/tsconfig.jsx.json)

Extends the base config and allows JSX.

## References

- https://www.typescriptlang.org/tsconfig/
- https://2ality.com/2025/01/tsconfig-json.html

## FAQ

### Why compile to `lib` instead of `dist`?

The `lib` is historically used by many Node.js libraries to put their published code.<br>
It's also to avoid clashing with our libraries where `dist` is used to put browser bundles.

### Why `"skipLibCheck": true`?

See https://2ality.com/2025/01/tsconfig-json.html#skipLibCheck.

It also avoids type errors because of broken libraries or when they depend on different tsconfig options.

## License

[MIT](./LICENSE)
