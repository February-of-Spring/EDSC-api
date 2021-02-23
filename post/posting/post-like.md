---
description: 로그인한 유저가 게시물에 좋아요를 누르는 API입니다.
---

# 게시물 좋아요 누르기

## METHOD

```text
POST
```

## URL

```text
/posts/:id/likes
```

* id: 게시물 고유 id

아직 로그인/계정 다루는 파트가 개발되지 않아 위의 url 대신 `:userId/posts/:id/likes` 을 사용합니다.

## REQUEST BODY

> Request body는 따로 없습니다.  
> url의 id 만을 사용합니다.

## RESPONSE

### success

**HTTP Status code : 201 Created**

> Response Body는 따로 없습니다.  
> 대신, Http Location **헤더**에 생성된 자원의 경로를 붙여서 반환합니다. ex\) /posts/18

### fail

**HTTP Status code : 400 Bad Request**

```javascript
{
    "status": "BAD_REQUEST",
    "message": "존재하지 않는 유저입니다."
}
```

```javascript
{
    "status": "BAD_REQUEST",
    "message": "존재하지 않는 게시물입니다."
}
```

| name | type | description |
| :--- | :--- | :--- |
| status | string | HTTP status |
| message | string | 에러 메시지 |

