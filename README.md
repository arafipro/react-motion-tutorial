# React Motion Tutorial

## ViteでReactプロジェクトを作成

[vite setup](https://ja.vite.dev/guide/#%E6%9C%80%E5%88%9D%E3%81%AE-vite-%E3%83%95%E3%82%9A%E3%83%AD%E3%82%B7%E3%82%99%E3%82%A7%E3%82%AF%E3%83%88%E3%82%92%E7%94%9F%E6%88%90%E3%81%99%E3%82%8B)

```sh
mkdir react-motion-tutorial
cd react-motion-tutorial
```

```sh
bun create vite ./
✔ Select a framework: › React
✔ Select a variant: › TypeScript
```

```sh
bun install
```

index.htmlを変更

```diff html:index.html
  <!DOCTYPE html>
- <html lang="en">
+ <html lang="ja">
    <head>
      <meta charset="UTF-8" />
      <link rel="icon" type="image/svg+xml" href="/vite.svg" />
      <meta name="viewport" content="width=device-width, initial-scale=1.0" />
-     <title>Vite + React + TS</title>
+     <title>React Motion Tutorial</title>
    </head>
    <body>
      <div id="root"></div>
      <script type="module" src="/src/main.tsx"></script>
    </body>
  </html>
```

## Tailwind CSSを導入

[Tailwind CSS setup](https://tailwindcss.com/docs/guides/vite)

1. Tailwind CSSをインストール

```sh
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

2. tailwind.config.jsにパスを追加

```diff js:tailwind.config.js
  /** @type {import('tailwindcss').Config} */
  export default {
-   content: [],
+ 	content: ["./index.html", "./src/**/*.{js,ts,jsx,tsx}"],
    theme: {
      extend: {},
    },
    plugins: [],
  }
```

3. index.cssに、Tailwindディレクティブを追加

```css:index.css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

4. App.cssを削除

App.cssを削除

5. App.tsxを変更

```diff ts:App.tsx
- import { useState } from "react";
- import "./App.css";
- import reactLogo from "./assets/react.svg";
- import viteLogo from "/vite.svg";

  function App() {
-   const [count, setCount] = useState(0);

-   return (
-     <>
-       <div>
-         <a href="https://vite.dev" target="_blank">
-           <img src={viteLogo} className="logo" alt="Vite logo" />
-         </a>
-         <a href="https://react.dev" target="_blank">
-           <img src={reactLogo} className="logo react" alt="React logo" />
-         </a>
-       </div>
-       <h1>Vite + React</h1>
-       <div className="card">
-         <button onClick={() => setCount((count) => count + 1)}>
-           count is {count}
-         </button>
-         <p>
-           Edit <code>src/App.tsx</code> and save to test HMR
-         </p>
-       </div>
-       <p className="read-the-docs">
-         Click on the Vite and React logos to learn more
-       </p>
-     </>
+     return <h1 className="text-3xl font-bold">React Motion Tutorial</h1>;
    );
  }

  export default App;
```
