If you are not happy by the default Vite configuration, then you can set next options:
1. Server Options
To set the exact port write number to the `port` and set `strictPort` to true in the server object
```javascript
server: {
    ...,
    port: 3000,
    strictPort: true,
},
```
2. Preview Options
If build files should run under exact port, then set `port` and set `strictPort` to true
```javascript
...,
preview: {
...,
    port: 3000,
    strictPort: true,
},
```
3. In order to write code in https mode define `@vitejs/plugin-basic-ssl` plugin in the `plugins` array
```javascript
import basicSsl from '@vitejs/plugin-basic-ssl'
```

```javascript
...,
plugins: [..., basicSsl()],
```

`server` and `preview` objects should have defined `https` true value
```javascript
...,
server: {
    ...,
    https: true,
}
```

```javascript
...,
preview: {
    ...,
    https: true,
}
```

4. `open` key with true value will open page in browser once vite is ready to show code
```javascript
...,
server: {
    ...,
    open: true,
}
```

```javascript
...,
preview: {
    ...,
    open: true,
}
```

5. `headers` key will add headers you want

```javascript
...,
server: {
    ...,
    headers: ...,
}
```

```javascript
...,
preview: {
    ...,
    headers: ...,
}
```

6. If sourcemap is needed, then add true `sourcemap` value in the build
```javascript
...,
build: {
    sourcemap: true,
},
```

7. Worker Options
By need service workers plugins can be added to te `worker` object `plugins` array key
```javascript
worker: {
    ...,
    plugins: [...]
}
```

8. Using env variables
Env variables can be called via `import.meta.env`

Note: `strictPort` will not allow to call other port, if needed one is busy.