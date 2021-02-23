---
description: 해당 id의 게시물을 삭제하는 API입니다.
---

# 게시물 삭제하기

## METHOD

```text
DELETE
```

## URL

```text
/posts/:id
```

* id: 게시물 고유 id


## RESPONSE

### success

**HTTP Status code : 204 No Content**

> Response Body는 따로 없습니다.  

### fail

**HTTP Status code : 400 Bad Request**

```json
{
    "status": "BAD_REQUEST",
    "message": "존재하지 않는 게시물입니다."
}
```

| name    | type   | description |
| ------- | ------ | ----------- |
| status  | number | HTTP status |
| message | string | 에러 메시지 |

