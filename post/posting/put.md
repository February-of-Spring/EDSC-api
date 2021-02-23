---
description: 해당 id의 게시물을 수정하는 API입니다.
---

# 게시물 수정하기

## METHOD

```text
PUT
```

## URL

```text
/posts/:id
```

* id: 게시물 고유 id

## REQUEST BODY

| name | type | require | description |
| :--- | :--- | :--- | :--- |
| email | string | 필수 | 작성자 이메일 수정 권한이 있는지 확인하는 용도로, 작성자는 수정되지 않습니다. |
| title | string | 필수 | 게시물 제목 |
| content | string | 필수 | 게시물 내용 |
| categoryName | string | 필수 | 존재하는 하위 카테고리 |

### REQUEST BODY EXAMPLE

```javascript
{
    "email": "example@gmail.com",
    "title": "spring boot 스터디 진행상황 수정",
    "content": "update test",
    "categoryName": "백엔드"
}
```

## RESPONSE

### success

**HTTP Status code: 200 OK**

> Response Body는 따로 없습니다.

### fail

**HTTP Status code: 400 Bad Request or 403 Forbidden**

```javascript
{
    "status": "BAD_REQUEST",
    "message": "필수항목을 입력해주세요."
}
```

```javascript
{
    "status": "BAD_REQUEST",
    "message": "존재하지 않는 게시물입니다."
}
```

```javascript
{
    "status": "BAD_REQUEST",
    "message": "존재하지 않는 카테고리입니다."
}
```

```javascript
{
    "status": "FORBIDDEN",
    "message": "수정할 수 있는 권한이 없습니다."
}
```

| name | type | description |
| :--- | :--- | :--- |
| status | number | HTTP status |
| message | string | 에러 메시지 |

