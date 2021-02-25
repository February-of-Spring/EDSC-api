---
description: 해당 id의 유저가 좋아요를 누른 게시물을 조회하는 API입니다.
---

# 유저의 좋아요 게시물 조회하기

## METHOD

```text
GET
```

## URL

```text
/users/:id/likes
```

* id: 유저 고유 id

## RESPONSE

* totalNum: 좋아요 한 post 객체의 개수 \(number\)
* postList: 좋아요 한 post 리스트 \(`post` List\)
  * `post`: 게시물 정보
    * id: 게시물 고유 id \(number\)
    * `category`: 게시물 카테고리 정보 \(object\)
      * id: 카테고리 id \(number\)
      * name: 카테고리 이름 \(string\)
      * level: 카레고리 level, 항상 2
      * postNum: 카테고리가 가지고 있는 게시물 수 \(number\)
      * parentCategoryId: 상위 카테고리 id, 항상 1
    * `user`: 작성자 정보 \(object\)
      * email: 이메일 \(string\)
      * name: 이름 \(string\)
      * nickname: 별명 \(string\)
      * profileImage: 작성자 프로필 사진 \(이미지 링크 string or base64 encoded string / BLOB\)
    * title: 게시물 제목 \(string\)
    * content: 게시물 내용 \(string\)
    * likeCount: 좋아요 수 \(number\)
    * viewCount: 조회수 \(number\)

### RESPONSE EXAMPLE

### success

**HTTP Status code : 200 OK**

```javascript
{
    "totalNum": 3,
    "postList": [
        {
            "id": 3,
            "category": {
                "id": 6,
                "name": "자유게시판",
                "level": 2,
                "postNum": 3,
                "parentCategoryId": 1
            },
            "user": {
                "email": "hoit1302@ewhain.net",
                "name": "박주은",
                "nickname": "hoit1302",
                "profileImage": "https://edsc-s3.s3.ap-northeast-2.amazonaws.com/profile-image/1"
            },
            "title": "사랑은 거품",
            "content": "모양이 거품",
            "likeCount": 1,
            "viewCount": 5
        },
        {
            "id": 6,
            "category": {
                "id": 6,
                "name": "자유게시판",
                "level": 2,
                "postNum": 3,
                "parentCategoryId": 1
            },
            "user": {
                "email": "hoit1302@ewhain.net",
                "name": "박주은",
                "nickname": "hoit1302",
                "profileImage": "https://edsc-s3.s3.ap-northeast-2.amazonaws.com/profile-image/1"
            },
            "title": "자유게시판",
            "content": "거품의 모양 모양의 거품",
            "likeCount": 2,
            "viewCount": 0
        },
        {
            "id": 7,
            "category": {
                "id": 4,
                "name": "공지사항",
                "level": 2,
                "postNum": 2,
                "parentCategoryId": 1
            },
            "user": {
                "email": "hoit1302@ewhain.net",
                "name": "박주은",
                "nickname": "hoit1302",
                "profileImage": "https://edsc-s3.s3.ap-northeast-2.amazonaws.com/profile-image/1"
            },
            "title": "카테고리 SWIFT post test",
            "content": "day6 💛⛄",
            "likeCount": 1,
            "viewCount": 2
        }
    ]
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

| name | type | description |
| :--- | :--- | :--- |
| status | string | HTTP status |
| message | string | 에러 메시지 |

