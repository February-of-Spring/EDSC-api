---
description: 해당 id 게시물의 해당 id의 댓글을 수정하는 API입니다.
---

# 댓글 수정하기

## METHOD

```text
PUT
```

## URL

```text
/posts/:post_id/comments/:comment_id
```

* post\_id: 게시물 고유 id
* comment\_id: 댓글 고유 id

## REQUEST BODY

| name | type | require | description |
| :--- | :--- | :--- | :--- |
| email | string | 필수 | 작성자 이메일  수정 권한이 있는지 확인하는 용도로, 작성자는 수정되지 않습니다. |
| content | string | 필수 | 게시물 내용 |
| parentId | string | 필수 | 대댓글이면 연관된 상위의 댓글 id, 아니면 자기 자신의 id |
| isPublic | string | 필수 | 공개 여부 |

### REQUEST BODY EXAMPLE

```javascript
{
    "email": "example@gmail.com",
    "content": "update test",
    "parentId": 3,
    "isPublic": 0
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

