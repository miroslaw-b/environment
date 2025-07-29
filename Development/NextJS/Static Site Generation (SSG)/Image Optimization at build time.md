Dependencies:

```shell
npm install --save-dev next-export-optimize-images
```

Code:

`next.config.ts`

```typescript
import type { NextConfig } from "next";
import withExportImages from "next-export-optimize-images";

const nextConfig: NextConfig = withExportImages({
  output: "export",
  images: {
    qualities: [100],
    loader: "custom",
    loaderFile: "./image-loader.js",
  },
});

export default nextConfig;
```

`image-loader.js`

```javascript
export default function imageLoader({ src, width, quality }) {
  const newSrc = src.replace(/\.([a-z]+)$/g, `_${width}.$1`);
  return `/_next/static/chunks/images/${newSrc}`;
}
```

`package.json`

```json
{
  // ...
  "scripts": {
	// ...
    "build": "next build && next-export-optimize-images",
    // ...
  },
  // ...
}
```