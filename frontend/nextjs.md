# nextjs

### 시작

`tsconfig.json` 파일 만들기

```
npm install --save-dev typescript @types/react @types/node
npx create-next-app 이름
```

### 폰트 적용 (with tailwindcss)

`_document.tsx` 만들기

```tsx
import Document, { Html, Head, Main, NextScript, DocumentContext } from 'next/document'

class MyDocument extends Document {
  static async getInitialProps(ctx: DocumentContext) {
    const initialProps = await Document.getInitialProps(ctx)
    return { ...initialProps }
  }

  render() {
    return (
      <Html>
        <Head>
            <link rel="preconnect" href="https://fonts.gstatic.com"/>
            <link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Sans:wght@100;200;300;400;500;600;700&display=swap" rel="stylesheet"/>
        </Head>
        <body className="font-body">
          <Main />
          <NextScript />
        </body>
      </Html>
    )
  }
}

export default MyDocument
```
Head tag 안에 link 추가

 `tailwind.config.js` 에 설정 추가

```js
module.exports = {
    // ~~
    theme: {
        fontFamily: {
            body: ['폰트명']
        }
    }
}
```