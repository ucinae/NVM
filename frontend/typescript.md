# Typescript

## react typescript component 만들기

```tsx
interface 컴포넌트Pros {
    키1: 타입1
    키2?: 타입2 // nullable,
    키3: 타입3 | 타입4 // 2가지도 가능
    키4: (a: string) => void // 함수도 가능 
}

const 컴포넌트: React.FC<컴포넌트Props> = ({
    키1,
    키2,
    키3,
    키4
}) => {
    return (
        {/* ~~ */}
    )
}

export default 컴포넌트
```