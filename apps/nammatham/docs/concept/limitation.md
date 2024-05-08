---
sidebar_position: 5
---
# Limitation

- Due based on [the official Azure Functions Node.js v4 Programming Model](https://techcommunity.microsoft.com/t5/apps-on-azure-blog/azure-functions-node-js-v4-programming-model-is-generally/ba-p/3929217), there are some limitations that you should be aware of when using Nammatham, which is come from the official Azure Azure Functions Node.js v4 Programming Model
  - It cannot be bundled with any build tools due to it's requires the npm packages to be installed in the runtime, which is `@azure/functions-core`, the package will automatically installed by the Azure Functions runtime in the Azure NPM Private Registry, as you see in the issue [Azure/azure-functions-nodejs-library#201](https://github.com/Azure/azure-functions-nodejs-library/issues/201).
  - And as the same reason above bullet, it cannot be used with monorepo as well.
- Support only Node.js
- Support Azure functions Node.js Runtime
- Strictly based on Azure Functions v2 APIs, cannot still used with general framework like Express.js, or Hono
  - Due to v2 based on [the official Azure Functions Node.js v4 Programming Model](https://techcommunity.microsoft.com/t5/apps-on-azure-blog/azure-functions-node-js-v4-programming-model-is-generally/ba-p/3929217) 
- The project is based on CommonJS


## Next Steps

Most of the limitations are being addressed in the Nammatham v3 (Major Release) as you can see in the [Roadmap](https://github.com/thaitype/nammatham/wiki/V3-Roadmap).

Here is some list the features that will be supported in the Nammatham v3:

- Support both Bun and Node.js, Bun is first-class citizen
- Support Azure Custom Handler instead of Azure Functions node runtime
- Can bundle with bundler and support monorepo 
- `nammatham` command supports to any custom handler using JavaScript/TypeScript both Bun and Node.js runtime.
  - And also support any Web Framework, e.g. Hono, Express.
- Auto create `host.json`, `local.settings.json` and `function.json` files, and provide type-safe for the configuration
- More cleaner the project codebase instead of v1, the v3 will be more cleaner and more maintainable, that can be deployable files into `.nmt` for generated `function.json`, `host.json`, built the bundle files
