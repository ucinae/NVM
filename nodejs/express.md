# express

### 설치

```
npm install express
npm install -D @types/express
```

### 설정

typescript 사용 시 추가

```json
// tsconfig.json
{
    "compilerOptions": {
        // ...
        "esModuleInterop": true
    }
}
```

### 시작

```typescript
import express from 'express'

const app = express()
const port = 5000

app.use(express.json())

app.get('/', (req, res) => res.send('Hello World'))

app.listen(port, async () => {
    console.log(`Server running at http://localhost:${port}`)
})
```

### route 추가

```typescript
// 기능.ts
import { Request, Response, Router } from "express"

const 함수 = async (req: Request, res: Response) => {

    try {
        // ~~
        // return res.json()
        // return res.status(400).json()
    } catch (err) {
        return res.status(500).json(err)
    }
}

const router = Router()
router.post('/경로', 함수)

export default router;
```

### route 적용

```typescript
import 라우터이름 from './routes/기능'

// ~~
app.use('/상위경로', 라우터이름)
```