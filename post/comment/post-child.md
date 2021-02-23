---
description: 해당 id 게시물에 대댓글을 생성하는 API입니다.
---

# 대댓글 작성하기

## METHOD

```text
POST
```

## URL

```text
/posts/:postId/comments
```

* postId: 게시물 고유 id

## REQUEST BODY

| name | type | require | description |
| :--- | :--- | :--- | :--- |
| email | string | 필수 | 작성자 이메일 |
| content | string | 필수 | 댓글 내용 |
| parentId | number | 필수 | 상위 댓글의 id |
| isPublic | boolean | 필수 X, default: true\(1\) | 공개 여부, 아직 작동 X |

```javascript
{
    "email": "example@gmail.com",
    "content": "LGTM ✨💖",
    "parentId": "",
    "isPublic": 1
}
```

## RESPONSE

### success

**HTTP Status code : 201 Created**

> Response Body는 따로 없습니다.  
> 대신, Http Location **헤더**에 생성된 자원의 경로를 붙여서 반환합니다. ex\) /posts/4/comments/17

### fail

**HTTP Status code : 400 Bad Request**

```javascript
{
    "status": "BAD_REQUEST",
    "message": "필수 항목을 입력해주세요."
}
```

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

```javascript
{
    "status": "BAD_REQUEST",
    "message": "상위 댓글이 존재하지 않습니다."
}
```

| name | type | description |
| :--- | :--- | :--- |
| status | string | HTTP status |
| message | string | 에러 메시지 |

