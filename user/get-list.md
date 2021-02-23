---
description: 모든 유저의 목록을 조회하는 API입니다.
---

# 유저 목록 조회하기

## METHOD

```text
GET
```

## URL

```text
/users
```

## RESPONSE

* totalNum: 총 유저 수 \(number\)
* userList: 유저 리스트 \(`user` List\)
  * `user`: 유저 정보\(object\)
    * email: 이메일 \(string\)
    * name: 이름 \(string\)
    * nickname: 별명 \(string\)
    * phone: 전화번호 \(string\)
    * profileImage: 작성자 프로필 사진 \(이미지 링크 string or base64 encoded string / BLOB\)
    * postNum: 작성 글 

### RESPONSE EXAMPLE

### success

**HTTP Status code : 200 OK**

```javascript
{
    "totalNum": 2,
    "userList": [
        {
            "email": "hoit1302@ewhain.net",
            "name": "박주은",
            "nickname": "hoit1302",
            "phone": "010-11111-1111",
            "profileImage": "",
            "postNum": 10
        },
        {
            "email": "example@gmail.com",
            "name": "수정",
            "nickname": "수정",
            "phone": "010-1234-5678",
            "profileImage": "https://edsc-s3.s3.ap-northeast-2.amazonaws.com/profile-image/2",
            "postNum": 0
        }
    ]
}
```

