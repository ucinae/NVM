# npm

## nodemon

저장하면 바로 다시 node 시작
```
npm install -D nodemon
```

```json
{
    // ~~,
    "scripts": {
        "dev": "nodemon --exec ts-node src/server.ts"
    }
}
```

## morgan

http request 로깅

```
npm install -D @types/morgan morgan
```

express에 적용 

```javascript
app.use(morgan('dev'))
```

---

## bcrypt

암호화

```
npm install bcrypt
npm i -D @types/bcrypt
```

```typescript
import bcrypt from 'bcrypt'

await bcrypt.hash(password, 6)
bcrypt.compare(password, encryptedPassword)
```

---

## class-validator

값 validate 용도

```
npm install class-validator
```

```typescript
import {validate, validateOrReject, Contains, IsInt, Length, IsEmail, IsFQDN, IsDate, Min, Max} from "class-validator";

export class Post {
    @Length(10, 20)
    title: string;
 
    @Contains("hello")
    text: string;
 
    @IsInt()
    @Min(0)
    @Max(10)
    rating: number;
 
    @IsEmail()
    email: string;
 
    @IsFQDN()
    site: string;
 
    @IsDate()
    createDate: Date;
}
```

---

## class-transformer

plain object <-> some class, serialize/deserialize

```
npm install class-transformer
```

```typescript
import { classToPlain, Exclude } from 'class-transformer'

class User {
    // ~~
    @Exclude()
    password: string

    toJSON() {
        return classToPlain(this) // password는 제외됨
    }
}
```

---

## jsonwebtoken

jwt

```
npm install jsonwebtoken
npm i -D @types/jsonwebtoken
```

```typescript
import jwt from 'jsonwebtoken'

//  토근 만들기
const token = jwt.sign(payload, secret)
```

---

## cookie cookie-parser

```
npm install cookie cookie-parser
npm i -D @types/cookie @types/cookie-parser
```

```typescript
import cookie from 'cookie'

const 함수 = async (req: Request, res: Response) => {

    // 개발 시
    res.set('Set-Cookie', cookie.serialize('token', token, {
            httpOnly: true,
            secure: process.env.NODE_ENV === 'production',
            sameSite: 'strict',
            maxAge: 3600,
            path: '/'
        }))
}
```

```typescript
import cookieParser from 'cookie-parser'

app.use(cookieParser())
```

---

## dotenv

```
npm install dotenv
```

.env 파일 만들어 내용 저장

```typescript
import dotenv from 'dotenv'

dotenv.config()

// 사용
process.env.키

```

---

## cors

```
npm install cors
npm install -D @typs/cors
```

```typescript
import cors from 'cors'

app.use(cors())
```

---

## @svgr/webpack

webpack에 svg 사용

```
npm install @svgr/webpack --save-dev
```

```javascript
// next.config.js
module.exports = {
  webpack(config) {
    config.module.rules.push({
      test: /\.svg$/,
      issuer: {
        test: /\.(js|ts)x?$/,
      },
      use: ['@svgr/webpack'],
    });

    return config;
  },
};
// 이제 import ~~Svg from '../**/*.svg' 로 사용 가능
```