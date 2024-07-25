# tsconfig-includes-test

## Environment

- Node.js: 22.0.0
- typescript: 5.5.4

## Test results

### `"includes": ["src/main.ts"]`

```console
$ npx tsc --listFilesOnly | grep -v node_modules
/Users/mizdra/src/github.com/mizdra/tsconfig-includes-test/src/math.ts
/Users/mizdra/src/github.com/mizdra/tsconfig-includes-test/src/main.ts
```

### `"includes": ["src/*"]`

```console
$ npx tsc --listFilesOnly | grep -v node_modules
/Users/mizdra/src/github.com/mizdra/tsconfig-includes-test/src/collection.ts
/Users/mizdra/src/github.com/mizdra/tsconfig-includes-test/src/log.ts
/Users/mizdra/src/github.com/mizdra/tsconfig-includes-test/src/math.ts
/Users/mizdra/src/github.com/mizdra/tsconfig-includes-test/src/main.ts
```

### `"includes": ["src/**/*"]`

```console
$ npx tsc --listFilesOnly | grep -v node_modules
/Users/mizdra/src/github.com/mizdra/tsconfig-includes-test/src/collection.ts
/Users/mizdra/src/github.com/mizdra/tsconfig-includes-test/src/log.ts
/Users/mizdra/src/github.com/mizdra/tsconfig-includes-test/src/math.ts
/Users/mizdra/src/github.com/mizdra/tsconfig-includes-test/src/main.ts
```

### `"includes": ["src/**"]`

```console
$ npx tsc --listFilesOnly | grep -v node_modules
error TS18003: No inputs were found in config file '/Users/mizdra/src/github.com/mizdra/tsconfig-includes-test/tsconfig.json'. Specified 'include' paths were '["src/**"]' and 'exclude' paths were '[]'.
tsconfig.json(2,15): error TS5010: File specification cannot end in a recursive directory wildcard ('**'): 'src/**'.
```

### `"includes": ["src"]`

```console
$ npx tsc --listFilesOnly | grep -v node_modules
/Users/mizdra/src/github.com/mizdra/tsconfig-includes-test/src/collection.ts
/Users/mizdra/src/github.com/mizdra/tsconfig-includes-test/src/log.ts
/Users/mizdra/src/github.com/mizdra/tsconfig-includes-test/src/math.ts
/Users/mizdra/src/github.com/mizdra/tsconfig-includes-test/src/main.ts
```

### `includes` option is not set

```console
$ npx tsc --listFilesOnly | grep -v node_modules
/Users/mizdra/src/github.com/mizdra/tsconfig-includes-test/src/collection.ts
/Users/mizdra/src/github.com/mizdra/tsconfig-includes-test/src/log.ts
/Users/mizdra/src/github.com/mizdra/tsconfig-includes-test/src/math.ts
/Users/mizdra/src/github.com/mizdra/tsconfig-includes-test/src/main.ts
```
