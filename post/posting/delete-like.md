---
description: 해당 id의 게시물의 좋아요를 취소하는 API입니다.
---

# 게시물 좋아요 취소하기

## METHOD

```text
DELETE
```

## URL

```text
/posts/:id
```

* id: 게시물 고유 id

아직 로그인/계정 다루는 파트가 개발되지 않아 위의 url 대신 `:userId/posts/:id/likes` 을 사용합니다. 

## RESPONSE

### success

**HTTP Status code : 204 No Content**

> Response Body는 따로 없습니다.  

### fail

**HTTP Status code : 400 Bad Request**

```json
{
    "status": 400,
    "message": "존재하지 않는 게시물입니다. "
}
```

| name    | type   | description |
| ------- | ------ | ----------- |
| status  | number | HTTP status |
| message | string | 에러 메시지 |

