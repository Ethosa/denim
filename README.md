<p align="center">
  <img src="https://github.com/openpeep/denim/blob/main/.github/denim.png" alt="Denim" width="170px"><br>
  Denim - Native NodeJS addons powered by Nim language<br>👑 Written in Nim language
</p>

<p align="center">
  <code>nimble install denim</code> or <a href="#">Download</a> the latest version 
</p>

<p align="center">
  <a href="https://openpeep.github.io/denim">API reference</a><br>
  <img src="https://github.com/openpeep/denim/workflows/test/badge.svg" alt="Github Actions">  <img src="https://github.com/openpeep/denim/workflows/docs/badge.svg" alt="Github Actions">
</p>

## 😍 Key Features
- [x] Open Source | `MIT` License
- [x] Written in 👑 Nim language

## Example

Here we'll use [nyml package](https://github.com/openpeep/nyml) to build a native nodejs yaml parser

My `yaml.nim`
```nim
import denim/napi/napibindings
import nyml except `%*`

init proc(module: Module) =
  module.registerFn(1, "parse"):
    let yamlContent = args[0].getStr
    return napiCall("JSON.parse", [
      %* yaml(yamlContent).toJsonStr
    ])
```

Magically run
```denim build yaml.nim```

```js
const {parse} = require('./yaml.node')
const sample = "email: test@example.com"

let obj = parse(sample)

console.log(obj)
console.log(obj.email == "test@example.com")
```

### ❤ Contributions & Support
- 🐛 Found a bug? [Create a new Issue](https://github.com/openpeep/denim/issues)
- 👋 Wanna help? [Fork it!](https://github.com/openpeep/denim/fork)
- 😎 [Get €20 in cloud credits from Hetzner](https://hetzner.cloud/?ref=Hm0mYGM9NxZ4)
- 🥰 [Donate via PayPal address](https://www.paypal.com/donate/?hosted_button_id=RJK3ZTDWPL55C)

### 🎩 License
Denim | MIT license. [Made by Humans from OpenPeep](https://github.com/openpeep)<br>
Thanks to [Andrew Breidenbach](https://github.com/AjBreidenbach) and [Andrei Rosca](https://github.com/andi23rosca) for their work.<br>
Copyright &copy; 2023 OpenPeep & Contributors &mdash; All rights reserved.