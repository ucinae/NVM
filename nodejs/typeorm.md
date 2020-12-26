# typeorm

TypeScript 기반 NodeJS 용 ORM

[Link](https://typeorm.io/#/)

### 설치

```
npm i -g typeorm
```

### 시작

```
typeorm init --database 사용데이터베이스
typeorm init --database postgres
```

### 설정

`ormconfig.json` 에서 host, port, username, password, database 설정

### 사용

```typescript
// entity
mport {Entity, PrimaryGeneratedColumn, Column, BaseEntity, Index, CreateDateColumn, UpdateDateColumn, BeforeInsert} from "typeorm";

@Entity('users')
export class User Extends BaseEntity {
    constructor(user: Partial<User>) {
        super()
        Object.assign(this, user)
    }

    @PrimaryGeneratedColumn()
    id: number

    @Column()
    username: string

    @Column()
    password: string

    @CreateDateColumn()
    createAt: Date

    @UpdateDateColumn()
    updateAt: Date
}
```