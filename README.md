# parcel-resolver-tspaths


Parcel does not make use of `tsconfig.json` to resolve path aliases, and instead uses `package.json` ([reference](https://v2.parceljs.org/features/module-resolution/#typescript-~-resolution)). This Parcel v2 plugin enables typescript path alias resolution as you would normally expect with webpack or otherwise. As a bonus, intellisense will continue to provide suggestions from your tsconfig.

**This plugin is experimental until Parcel V2 is released.** Use in production with heavy caution.

## Installation

`yarn add -D parcel-resolver-tspaths`

or


`npm install --save-dev parcel-resolver-tspaths`

Now if you have a [.parcelrc](https://v2.parceljs.org/configuration/plugin-configuration/) (skip if you don't), drop in the plugin to your resolvers like so:

```json
"resolvers": ["parcel-resolver-tspaths"],
```

No need to configure which filetypes to resolve (`.ts`/`.tsx` only).

## Known Limitations

- This plugin is not currently compatible with importing [non-code assets](https://v2.parceljs.org/getting-started/migration/#importing-non-code-assets-from-javascript), but this is being considered for future development. 

  For example:

  ```typescript
  import logo from 'url:@myassets/image/logo.svg'
  ```

- ## **Please file an issue if you notice any bugs. Thanks!**

## Development

Clone this repo anywhere, then run `yarn && yarn link` in the project root.

In `test/testapp`, run `yarn && yarn link parcel-resolver-tspaths`. Run `yarn dev` to start the typscript compiler in watch mode.

Test app WIP.

If you run into issues viewing debug output, you can see all raw output by running `yarn test |& cat` (Mac/Linux users only).
