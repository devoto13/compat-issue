This repository demonstrates that `@fortawesome/fontawesome-svg-core` 1.3.x line contains breaking changes compared to the 1.2.x line because it exposes types from the `@fortawesome/fontawesome-common-types` which contains breaking changes in the supported icon names (some names are removed).

To reproduce the problem run `npm run build`. Observe that v5 `IconDefinition` is rejected by the v6 SVG core implementation.

```
$ npm run build

> compat-issue@1.0.0 build /Users/devoto13/Projects/trash/compat-issue
> tsc index.ts

index.ts:4:13 - error TS2345: Argument of type 'IconDefinition' is not assignable to parameter of type 'IconDefinitionOrPack'.
  Type 'IconDefinition' is not assignable to type 'IconPack'.
    Index signature for type 'string' is missing in type 'IconDefinition'.

4 library.add(faTwitter);
              ~~~~~~~~~
```
