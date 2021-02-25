---
description: 해당 id의 유저가 작성한 게시물을 조회하는 API입니다.
---

# 유저의 게시물 조회하기

## METHOD

```text
GET
```

## URL

```text
/users/:id/posts
```

* id: 유저 고유 id

## RESPONSE

* totalNum: post 객체의 개수 \(number\)
* postList: post 리스트 \(`post` List\)
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
    "totalNum": 2,
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
            "id": 4,
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
            "title": "love is an bubble",
            "content": "bubble is made of!!",
            "likeCount": 0,
            "viewCount": 4
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

