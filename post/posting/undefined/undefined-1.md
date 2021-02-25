---
description: 해당 id의 이미지를 삭제하는 API입니다.
---

# 게시물 이미지 삭제하기

## METHOD <a id="method"></a>

```text
DELETE
```

## URL <a id="url"></a>

```text
/posts/image/:id
```

* id: 게시물의 이미지 고유 id

## RESPONSE <a id="response"></a>

### success <a id="success"></a>

**HTTP Status code : 204 No Content**

> Response Body는 따로 없습니다.

### fail <a id="fail"></a>

**HTTP Status code : 400 Bad Request**

```text
{    "status": "BAD_REQUEST",    "message": "존재하지 않는 이미입니다."}
```

| name | type | description |
| :--- | :--- | :--- |
| status | number | HTTP status |
| message | string | 에러 메시지 |

