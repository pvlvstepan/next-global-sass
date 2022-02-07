![npm](https://img.shields.io/npm/v/next-global-sass?style=flat-square)
![NPM](https://img.shields.io/npm/l/next-global-sass?style=flat-square)

# next-global-sass

> Import component-level SASS stylesheets anywhere in your [Next.js](https://github.com/vercel/next.js) project, just like in CRA

## Requirements

This package does not include support for SASS automatically, please follow setup instructions on [Next.js official docs](https://nextjs.org/docs/basic-features/built-in-css-support#sass-support)

## Installation

```sh
npm install -S next-global-sass
```

Or if you prefer using Yarn:

```sh
yarn add next-global-sass
```

## Usage

Create a `next.config.js` in the root of your project (if it does not exist yet)

```javascript
// next.config.js

const withGlobalSass = require("next-global-sass");
module.exports = withGlobalSass();
```

Optionally you can add your custom Next.js configuration as a parameter

```javascript
// next.config.js

const withGlobalSass = require('next-global-sass');

/** @type {import('next').NextConfig} */
const nextConfig = {
    reactStrictMode: true,
    ...
};

module.exports = withGlobalSass({ ...nextConfig });
```

Create `SASS/SCSS` stylesheets according to your needs and simply import them in your pages or components

```less
// styles.scss

.sass-container {
    background-color: red;
    color: white;
}
```

```javascript
// MyComponent.jsx

import './styles.scss'

export const MyComponent = () => {
    return (
        <div className="sass-container">
            Hello World
        </button>
    )
}
```

Note that the global styles can still be imported in the `_app.js`

## Credits

Check out [@frattaro](https://github.com/vercel/next.js/discussions/14672#discussioncomment-2052410)'s solution for non-module style imports in Next.js

## License

[MIT License](mit-license.org) © Stepan Pavlov
