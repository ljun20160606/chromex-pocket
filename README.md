# Chromex-pocket &middot; [![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/ljun20160606/chromex-pocket/blob/master/LICENSE) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/ljun20160606/chromex-pocket/pull/new)

Chrome extension pocket.

## Installation

```
$ npm i chromex-pocket
```

### Router

Replace chrome.runtime.onMessage

On content page.

```js
const FOO = '/foo';
chrome.runtime.sendMessage({
      path: FOO,
      name: 'foo',
      gender: 'male'
    }, function (response) {

    }
);
```

On Background.

```js
let router = new Router()
router.handle(FOO, ctx => {
    return new Promise((resolve) => {
        let {name, gender} = ctx.request;

        ctx.response = {
            code: 0,
            data: 'ok'
        };
        resolve();
    };
});
```
