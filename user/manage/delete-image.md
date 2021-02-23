---
description: 해당 id의 유저 프로필 이미지를 삭제하는 API입니다.
---

# 유저 프로필 이미지 삭제하기

## METHOD

```text
DELETE
```

## URL

```text
/users/:id/image
```

* id: 유저 고유 id

## RESPONSE

### success

**HTTP Status code: 204 No Content**

> Response Body는 따로 없습니다.

### fail

**HTTP Status code: 400 Bad Request**

```javascript
{
    "status": "BAD_REQUEST",
    "message": "존재하지 않는 유저입니다."
}
```

| name | type | description |
| :--- | :--- | :--- |
| status | number | HTTP status |
| message | string | 에러 메시지 |

