---
description: 특정 id 게시물의 해당 id의 댓글을 삭제하는 API입니다.
---

# 댓글 삭제하기

## METHOD

```text
DELETE
```

## URL

```text
/posts/:postId/comments/:commentId
```

* postId: 게시물 고유 id
* commentId: 댓글 고유 id


## RESPONSE

### success

**HTTP Status code : 204 No Content**

> Response Body는 따로 없습니다.  

### fail

**HTTP Status code : 400 Bad Request**

```json
{
    "status": "BAD_REQUEST",
    "message": "존재하지 않는 댓글입니다."
}
```

- 게시물 id와 댓글이 가지고 있는 게시물 id가 다른 경우,

```json
{
    "status": "BAD_REQUEST",
    "message": "잘못된 경로로 접근하셨습니다."
}
```

| name    | type   | description |
| ------- | ------ | ----------- |
| status  | number | HTTP status |
| message | string | 에러 메시지 |

