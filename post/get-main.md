---
description: 지정된 카테고리의 최근 게시물을 한 건씩 불러오는 API입니다.
---

# 메인 페이지의 게시물 조회하기

## METHOD

```text
GET
```

## URL

```text
/posts/main
```

## RESPONSE

> category_id 4, 5, 6에 해당하는 글 중 최신 글 1개씩 조회합니다.
>
> parent_category_id 로 1을 가지고 있는 category_id 4, 5, 6 에 해당하는 카테고리는 정보(이름)가 수정될 수 있지만, 삭제할 수 없습니다.
> 각각의 카테고리에 글이 하나도 없을 경우, 해당하는 하나의 post 객체를 불러오지 않습니다.

* totalNum: post 객체의 개수 (number)
* postList: post 리스트 (`post` List)
  * `post`: 게시물 정보
    * id: 게시물 고유 id (number)
    * `category`: 게시물 카테고리 정보 \(object\)
      * id: 카테고리 id \(number\)
      * name: 카테고리 이름 \(string\)
      * level: 카레고리 level, 항상 2
      * postNum: 카테고리가 가지고 있는 게시물 수 (number)
      * parentCategoryId: 상위 카테고리 id, 항상 1
    * `user`: 작성자 정보 (object)
      * email: 이메일 (string)
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

```json
{
    "totalNum": 3,
    "postList": [
        {
            "id": 9,
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
                "profileImage": ""
            },
            "title": "카테고리 SWIFT 2번째 post test",
            "content": "day6 💛⛄",
            "likeCount": 0,
            "viewCount": 2
        },
        {
            "id": 16,
            "category": {
                "id": 5,
                "name": "정보공유",
                "level": 2,
                "postNum": 2,
                "parentCategoryId": 1
            },
            "user": {
                "email": "hoit1302@ewhain.net",
                "name": "박주은",
                "nickname": "hoit1302",
                "profileImage": ""
            },
            "title": "수정 test",
            "content": "수정되었습니다. 💛⛄🙄",
            "likeCount": 0,
            "viewCount": 7
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
                "profileImage": ""
            },
            "title": "자유게시판",
            "content": "거품의 모양 모양의 거품",
            "likeCount": 2,
            "viewCount": 0
        }
    ]
}
```

