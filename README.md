# Steps to reproduce Node ESM error
1. Run `npm install`
1. Make sure you're using Node 16+ (`nvm use 20`)
1. Run `node test.mjs`
1. See the following error:
```bash
file:///Users/[USERNAME]/amplify-js-v6-node-esm/test.mjs:1
import { signIn } from 'aws-amplify/auth';
         ^^^^^^
SyntaxError: Named export 'signIn' not found. The requested module 'aws-amplify/auth' is a CommonJS module, which may not support all module.exports as named exports.
CommonJS modules can always be imported via the default export, for example using:

import pkg from 'aws-amplify/auth';
const { signIn } = pkg;
```
This would be a regression of the Node ESM module support Amplify JS and UI libraries currently have. Also see: https://github.com/aws-amplify/amplify-ui/issues/3155
