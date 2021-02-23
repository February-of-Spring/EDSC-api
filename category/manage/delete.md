---
description: 특정 카테고리를 삭제하는 API입니다.
---

# 카테고리 삭제하기

## METHOD

```text
DELETE
```

## URL

```text
/category/:level1, /category/:level1/:level2
```

* level1: 상위 카테고리 이름
* level2: 하위 카테고리 이름


## RESPONSE

### success

**HTTP Status code : 204 No Content**

> Response Body는 따로 없습니다.  

### fail

**HTTP Status code : 400 Bad Request**

```json
{
    "status": "BAD_REQUEST",
    "message": "존재하지 않는 카테고리입니다."
}
```

```json
{
    "status": "BAD_REQUEST",
    "message": "하위 카테고리가 존재하는 그룹은 삭제할 수 없습니다."
}
```

```json
{
    "status": "BAD_REQUEST",
    "message": "게시물이 존재하는 카테고리는 삭제할 수 없습니다."
}
```

| name    | type   | description |
| ------- | ------ | ----------- |
| status  | number | HTTP status |
| message | string | 에러 메시지 |

