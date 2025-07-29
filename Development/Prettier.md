Dependencies: 

```shell
npm install --save-dev @trivago/prettier-plugin-sort-imports
```

Code:

`.prettierrc`

```json
{
  "plugins": ["@trivago/prettier-plugin-sort-imports"],
  "printWidth": 80,
  "useTabs": false,
  "tabWidth": 2,
  "semi": true,
  "singleQuote": true,
  "jsxSingleQuote": false,
  "quoteProps": "as-needed",
  "trailingComma": "es5",
  "bracketSpacing": true,
  "arrowParens": "always",
  "proseWrap": "always",
  "endOfLine": "lf",
  "importOrder": ["^@/(.*)$", "^[./]"],
  "importOrderSeparation": true,
  "importOrderSortSpecifiers": true,
  "importOrderCaseInsensitive": true
}
```
 