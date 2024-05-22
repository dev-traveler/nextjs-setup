This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app) using below stack.

- Yarn berry
- Typescript
- Eslint
- Prettier
- TailwindCSS

## Getting Started

### Set Yarn Berry

Run:

```zsh
npx create-next-app@latest
asdf local nodejs 20.13.1
yarn set version berry
```

Edit `.yarnrc.yml`

```yml
yarnPath: .yarn/releases/yarn-4.2.2.cjs
nodeLinker: pnp
```

If you're using Zero-Installs, Add it to `.gitignore`

```gitignore
# yarn berry using zero-installs
.yarn/*
!.yarn/cache
!.yarn/patches
!.yarn/plugins
!.yarn/releases
!.yarn/sdks
!.yarn/versions
```

And run:

```zsh
yarn install
```

If you`re using VSCode, run:

```zsh
yarn dlx @yarnpkg/sdks vscode
```

### Add Prettier

Run:

```zsh
yarn add -D prettier eslint-plugin-prettier eslint-config-prettier
```

Edit `.eslintrc.json`

```json
{
  "extends": ["next/core-web-vitals", "plugin:prettier/recommended"],
  "plugins": ["prettier"],
  "rules": {
    "prettier/prettier": "error"
  }
}
```

Add `.prettierrc` to root

```json
{
  "printWidth": 80,
  "tabWidth": 2,
  "singleQuote": true,
  "semi": true,
  "trailingComma": "all",
  "arrowParens": "always"
}
```

Run:

```zsh
yarn dlx @yarnpkg/sdks vscode
```

### Add typescript-eslint

Run:

```zsh
yarn add -D @typescript-eslint/parser @typescript-eslint/eslint-plugin
```

Edit `.eslintrc.json`:

```json
{
  "extends": [
    "next/core-web-vitals",
    "eslint:recommended",
    "plugin:@typescript-eslint/recommended",
    "plugin:prettier/recommended"
  ],
  "parser": "@typescript-eslint/parser",
  "plugins": ["@typescript-eslint", "prettier"],
  "rules": {
    "prettier/prettier": "error"
  },
  "root": true
}
```

Run:

```zsh
yarn dlx @yarnpkg/sdks vscode
```

#### Trouble Shooting

If eslint doesn't work in your VSCode and you have got this alert:

```
The JS/TS language service immediately crashed 5 times. The service will not be restarted.
```

you need to read these issues:

https://github.com/microsoft/vscode/issues/213186
https://github.com/yarnpkg/berry/issues/6270

To reslove this problem (22 May 2024)

- Add `"typescript.tsserver.experimental.useVsCodeWatcher": false` to `.vscode/settings.json` (should work at least until July)
