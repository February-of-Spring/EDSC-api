---
description: '카테고리 관리 페이지에서 상, 하위 카테고리를 생성하는 api입니다.'
---

# 카테고리 생성하기

## METHOD

```text
POST
```

## URL

```text
/category
```

## REQUEST BODY

| name | type | require | description |
| :--- | :--- | :--- | :--- |
| name | string | 필수 | 카테고리 이름 |
| level | number | 필수 | 상위 카테고리: 1, 하위 카테고리: 2 |
| parentId | number | level이 2일 때 필수 | 상위 카테고리의 id |

### REQUEST BODY EXAMPLE

**상위 카테고리 예시**

```javascript
{
    "name": "자기소개",
    "level": 1
}
```

**하위 카테고리 예시**

```javascript
{
    "name": "spring boot 팀",
    "level": 2,
    "parentId": 3
}
```

## RESPONSE

### success

**HTTP Status code : 201 Created**

> Response Body는 따로 없습니다.

### fail

**HTTP Status code : 400 Bad Request**

```javascript
{
    "status": "BAD_REQUEST",
    "message": "필수 항목을 입력해주세요."
}
```

```javascript
{
    "status": "BAD_REQUEST",
    "message": "이미 존재하는 카테고리입니다."
}
```

```javascript
{
    "status": "BAD_REQUEST",
    "message": "카테고리의 상위 항목이 존재하지 않습니다."
}
```

| name | type | description |
| :--- | :--- | :--- |
| status | string | HTTP status |
| message | string | 에러 메시지 |

