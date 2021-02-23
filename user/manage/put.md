---
description: 해당 id의 유저 정보를 수정하는 API입니다.
---

# 유저 정보 수정하기

## METHOD

```text
PUT
```

## URL

```text
/users/:id
```

* id: 유저 고유 id

## REQUEST BODY

| name     | type   | require | description                                                  |
| :------- | :----- | :------ | :----------------------------------------------------------- |
| email    | string | 필수    | 이메일<br />수정 권한이 있는지 확인하는 용도로, 유저의 email는 수정되지 않습니다. |
| name     | string | 필수    | 이름                                                         |
| nickname | string | 필수    | 별명                                                         |
| phone    | string | 필수    | 핸드폰 번호                                                  |
| password | string | 필수    | 비밀번호                                                     |

### REQUEST BODY EXAMPLE

```json
{
    "name": "김구름",
    "nickname": "화요일",
    "phone": "010-1234-1234",
    "password": "????????"
}
```

## RESPONSE

### success

**HTTP Status code: 200 OK**

> Response Body는 따로 없습니다.  


### fail

**HTTP Status code: 400 Bad Request or 403 Forbidden**

```json
{
    "status": "BAD_REQUEST",
    "message": "필수항목을 입력해주세요."
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
    "status": "FORBIDDEN",
    "message": "수정할 수 있는 권한이 없습니다."
}
```

| name    | type   | description |
| ------- | ------ | ----------- |
| status  | number | HTTP status |
| message | string | 에러 메시지 |

