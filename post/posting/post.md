---
description: 게시물을 생성하는 API입니다
---

# 게시물 생성하기

## METHOD

```text
POST
```

## URL

```text
/posts
```

## REQUEST BODY

| name | type | require | description |
| :--- | :--- | :--- | :--- |
| email | string | 필수 | 작성자 이메일 |
| title | string | 필수 | 게시물 제목 |
| content | string | 필수 | 게시물 내용 |
| categoryName | string | 필수 | 존재하는 하위 카테고리 |

### REQUEST BODY EXAMPLE

```json
{
    "email": "example@gmail.com",
    "title": "리액트 js 스터디 진행상황",
    "content": "router, await, async, etc",
    "categoryName": "프론트엔드"
}
```

## RESPONSE

### success

**HTTP Status code : 201 Created**

> Response Body는 따로 없습니다.  
> 대신, Http Location **헤더**에 생성된 자원의 경로를 붙여서 반환합니다.
> ex) /posts/18

### fail

**HTTP Status code : 400 Bad Request**

```json
{
    "status": "BAD_REQUEST",
    "message": "필수 항목을 입력해주세요."
}
```

```json
{
    "status": "BAD_REQUEST",
    "message": "존재하지 않는 유저입니다."
}
```

```json
{
    "status": "BAD_REQUEST",
    "message": "존재하지 않는 카테고리입니다."
}
```

| name | type | description |
| :--- | :--- | :--- |
| status | string | HTTP status |
| message | string | 에러 메시지 |

