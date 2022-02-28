# Reproduce https://github.com/evanw/esbuild/issues/2065

1. Clone this repo
1. `npm install`
1. `npx esbuild --version` --> verify >= 0.13.9, for me this logs 0.14.23 (currently)
1. `esbuild src/index.ts --bundle` --> Observe the output has the node version:

```
(() => {
  // src/node-web-compat-node.ts
  function doLog() {
    console.log("node");
  }

  // src/index.ts
  doLog();
})();
```
