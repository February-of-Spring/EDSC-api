---
description: 계정 한 개의 유저 정보를 조회하는 API입니다.
---

# 유저 정보 조회하기

## METHOD

```text
GET
```

## URL

```text
/users/:id
```

* id: 유저 고유 id

## RESPONSE

* email: 이메일 \(string\)
* name: 이름 \(string\)
* nickname: 별명 \(string\)
* phone: 전화번호 (string)
* profileImage: 작성자 프로필 사진 \(이미지 링크 string or base64 encoded string / BLOB\)

### RESPONSE EXAMPLE

### success

**HTTP Status code : 200 OK**

```javascript
{
    "email": "example@gmail.com",
    "name": "김구름",
    "nickname": "구름빵",
    "phone": "010-1234-5678",
    "profileImage": "https://edsc-s3.s3.ap-northeast-2.amazonaws.com/profile-image/2"
}
```

### fail

**HTTP Status code : 400 Bad Request**

```javascript
{
    "status": "BAD_REQUEST",
    "message": "존재하지 않는 유저입니다."
}
```

| name    | type   | description |
| :------ | :----- | :---------- |
| status  | string | HTTP status |
| message | string | 에러 메시지 |



```json
{
    "email": "example@gmail.com",
    "name": "수정",
    "nickname": "수정",
    "phone": "010-1234-5678",
    "profileImage": "https://edsc-s3.s3.ap-northeast-2.amazonaws.com/profile-image/2"
}
```

