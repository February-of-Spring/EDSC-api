---
description: 해당 id를 가진 게시물 한 건을 조회하는 API입니다.
---

# 게시물 조회하기

## METHOD

```text
GET
```

## URL

```text
/posts/:id
```

* id: 게시물 고유 id

## RESPONSE

* id: 게시물 고유 id \(number\)
* `user`: 게시물 작성자 정보\(object\)
  * email: 이메일 \(string\)
  * name: 이름 \(string\)
  * nickname: 별명 \(string\)
  * profileImage: 작성자 프로필 사진 \(이미지 링크 string or base64 encoded string / BLOB\)
* title: 게시물 제목 \(string\)
* content: 게시물 내용 \(string\)
* likeCount: 좋아요 수 \(number\)
* viewCount: 조회수 \(number\)
* createdAt: 게시물 작성 날짜 \(string / DATETIME\)
* modifiedAt: 게시물 수정 날짜 \(string / DATETIME\)
* `category`: 게시물 카테고리 정보 \(object\)
  * id: 카테고리 id \(number\)
  * name: 카테고리 이름 \(string\)
  * level: 카레고리 level, \(1: 상위 카테고리, 2: 하위 카테고리\)
  * postNum: 카테고리가 가지고 있는 게시물 수
  * parentCategoryId: 카테
* images: 게시물 이미지 정보 \(image 배열\)
  * `image`: 이미지 정보\(object\)
    * id: 이미지 id \(number\)
    * path: 이미지 URI 경로 \(string\)
* files: 게시물 첨부파일 \(file 배열\)
  * `file`: 파일 정보\(object\)
    * id: 파일 id \(number\)
    * path: 이미지 URI 경로 \(string\)
* commentNum: 댓글 수 \(number\)
* comments:
  * `comment`:
    * createdAt: 댓글 작성 날짜 \(string / DATETIME\)
    * modifiedAt: 댓글 수정 날짜 \(string / DATETIME\)
    * id: 댓글 고유 id \(number\)
    * content: 댓글 내용 \(string\)
    * `user`: 댓글 작성자 정보\(object\)
      * email: 이메일 \(string\)
      * name: 이름 \(string\)
      * nickname: 별명 \(string\)
      * profileImage: 작성자 프로필 사진 \(이미지 링크 string or base64 encoded string / BLOB\)



### RESPONSE EXAMPLE

### success

**HTTP Status code : 200 OK**

```javascript
{
    "id": 4,
    "user": {
        "email": "example@gmail.com",
        "name": "김애용",
        "nickname": "애용",
        "profileImage": "example.png"
    },
    "title": "Love is all bubbles",
    "content": "Bubbles are made of⛅",
    "likeCount": 0,
    "viewCount": 3,
    "createdAt": "2021-02-20T03:35:20.000+00:00",
    "modifiedAt": "2021-02-22T00:31:52.000+00:00",
    "category": {
        "id": 6,
        "name": "자유게시판",
        "level": 2,
        "postNum": 3,
        "parentCategoryId": 1
    },
    "images": null,
    "files": null
}
```

### fail

**HTTP Status code : 400 Bad Request**

```javascript
{
    "status": "BAD_REQUEST",
    "message": "존재하지 않는 게시물입니다."
}
```

| name | type | description |
| :--- | :--- | :--- |
| status | string | HTTP status |
| message | string | 에러 메시지 |



