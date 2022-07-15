# next image

220521

## Importing SVGs to Next.js

There are few different ways to approach.

### Including directly

`<svg>` is a standard HTML tag that can be directly used in JSX.

### Using the `<img>` tag

You need to place the image in the /public directory and reference it relative to that. This file would be in the root of the public directory.

### Use next/image

The <Image /> component requires the following properties. => src, width, height
It means the only thing to be aware here is that this component requires the height and width to be passed through as props.

```javascript
import Image from "next/image";

<Image src="/images/home.svg" alt="home" width={10} height={10} />;
```

### As a component

Once you have your SVG as a component, you can pass it props to alter it's appearance. You receive the props and then use them directly on your SVG.

### Importing as a file - svgr/webpack

```
npm install -D @svgr/webpack
or
yarn add -D @svgr/webpack
```

install @svgr/webpack to your project. Then, add to your next.config.js in the root of your project.

```javascript
module.exports = {
  webpack(config) {
    config.module.rules.push({
      test: /\.svg$/,
      use: ["@svgr/webpack"],
    });

    return config;
  },
};
```

물론 config 파일을 수정했으니 서버를 재시작 해야한다.
