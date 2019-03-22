# Chromex-pocket

chrome extension pocket

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
