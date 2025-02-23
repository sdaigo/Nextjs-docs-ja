---
title: httpAgentOptions
description: Next.jsでは、デフォルトでHTTP Keep-Aliveが自動的に使用されます。HTTP Keep-Aliveを無効にする方法については、こちらをご覧ください。
---

Node.js 18 より前のバージョンでは、Next.js は自動的に`fetch()`を[undici](https://nextjs.org/docs/architecture/supported-browsers#polyfills)でポリフィルし、デフォルトで[HTTP Keep-Alive](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Keep-Alive)を有効にしています。

サーバー側のすべての`fetch()`呼び出しで HTTP Keep-Alive を無効にするには、`next.config.js`を開き、`httpAgentOptions`設定を追加します：

```js title="next.config.js"
module.exports = {
  httpAgentOptions: {
    keepAlive: false,
  },
}
```
