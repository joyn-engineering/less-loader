<div align="center">
  <a href="https://github.com/webpack/webpack">
    <img width="200" height="200" src="https://webpack.js.org/assets/icon-square-big.svg">
  </a>
</div>

[![npm][npm]][npm-url]
[![node][node]][node-url]
[![deps][deps]][deps-url]
[![tests][tests]][tests-url]
[![cover][cover]][cover-url]
[![chat][chat]][chat-url]
[![size][size]][size-url]

# less-loader-with-js

This is a fork of the official [less-loader](https://github.com/webpack-contrib/less-loader) package. The difference is that here javascript is enabled by default so you don't need to pass this option to enable it. Reason for doing so was to add javascript support for the following import: `import '!style-loader!css-loader!less-loader-with-js!./style.less';`.

Only change done is to add `javascriptEnabled: true` inside of the `getLessOptions` function to `utils.js`.
```
const lessOptions = {
    plugins: [],
    relativeUrls: true,
    // We need to set the filename because otherwise our WebpackFileManager will receive an undefined path for the entry
    filename: loaderContext.resourcePath,
    
    // this line was added
    javascriptEnabled: true,
    
    ...options,
  };
```
