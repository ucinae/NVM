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

## bcrypt

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