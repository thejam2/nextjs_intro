This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `pages/index.js`. The page auto-updates as you edit the file.

[API routes](https://nextjs.org/docs/api-routes/introduction) can be accessed on [http://localhost:3000/api/hello](http://localhost:3000/api/hello). This endpoint can be edited in `pages/api/hello.js`.

The `pages/api` directory is mapped to `/api/*`. Files in this directory are treated as [API routes](https://nextjs.org/docs/api-routes/introduction) instead of React pages.

This project uses [`next/font`](https://nextjs.org/docs/basic-features/font-optimization) to automatically optimize and load Inter, a custom Google Font.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.

----------------------------------------------------------------------------------------------------------------

Router 필요없음

pages 폴더 안에 있는 파일명에 따라 route가 결정된다.

### css추가방법
1. 모듈생성

작명.module.css 파일 생성후 css 작성
```
.nav{ }
```

사용할 파일에서 import
```
import 작명1 from "./작명2.module.css";

<div className = {작명1.nav}></div>
```

2. styled jsx

해당파일에서 작성 (해당파일에서만 작동)
```
< style jsx>{`
CSS 스타일..
`}< /style>
```

3. Custom App

Next.js는 App 컴포넌트를 사용하여 page를 초기화합니다. 이를 재정의하고 페이지 초기화를 제어할 수 있습니다. 이를 통해 다음과 같은 놀라운 일을 할 수 있습니다.

1. 페이지 변경 간에 레이아웃 유지
2. 페이지 탐색 시 state 유지
3. componentDidCatch를 사용한 Custom 에러 처리
4. 페이지에 추가 데이터 삽입
5. Global CSS 추가

기본 App을 재정의하려면 아래와 같이 ./pages/_app.js 파일을 만듭니다. (파일명 고정)

페이지 렌더링 할때마다 _app.js 실행 후 해당 컴포넌트 실행
```
export default function 함수명({ Component, pageProps }) {
return < Component {...pageProps} />
}
```
https://nextjs.org/docs/advanced-features/custom-app

Custom App (with 타입스크립트)
_app.ts가 아닌 _app.tsx파일을 만들고 아래와 같이 작성
```
import type { AppProps } from 'next/app'

export default function 함수명({ Component, pageProps }: AppProps){
return < Component {...pageProps} />
}
```
https://nextjs.org/docs/basic-features/typescript#custom-app

+ 파일명.module.css 파일 형태를 제외한 모든 나머지 css파일들은 _app.js에서만 import해와서 사용해야 한다. (글로벌 css간의 충돌을 피하기 위해서이다.)
https://nextjs.org/docs/messages/css-global


