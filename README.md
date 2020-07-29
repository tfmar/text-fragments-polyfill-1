# Text Fragments Polyfill

This is an attempt to polyfill the
[Text Fragments](https://wicg.github.io/scroll-to-text-fragment/) feature for
browsers that don't support it natively.

<div align="center">
  <img width="400" src="https://user-images.githubusercontent.com/145676/79250513-02bb5800-7e7f-11ea-8e56-bd63edd31f5b.jpeg">
  <p>
    <sup>
      The text fragment link
      <a href="https://en.wikipedia.org/wiki/Cat#Size:~:text=This%20article%20is,kept%20as%20a%20pet">
        #:~:text=This%20article%20is,kept%20as%20a%20pet
      </a>
      rendered in Safari on an iOS device, with
      <a href="https://github.com/GoogleChromeLabs/text-fragments-polyfill/blob/master/inject.js">
        <code>inject.js</code>
      </a>
      injected via Web Inspector.
    </sup>
  </p>
</div>

There are still **many** limitations and the code is very hacky, but it serves
well as a proof of concept. This _could_ be used in Chrome for iOS by injecting
the script with
[`WKUserScript`](https://developer.apple.com/documentation/webkit/wkuserscript).

## Installation

```bash
npm install text-fragments-polyfill
```

## Usage

```js
// Only use the polyfill on browser that need it.
if (!('fragmentDirective' in Location.prototype)) {
  import('text-fragments.js');
}
```

## Demo

Try the [demo](https://text-fragments-polyfill.glitch.me/) on a browser that
does not support Text Fragments.

## License

Apache 2.0. This is not an official Google product.
