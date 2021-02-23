---
description: 전체 카테고리 목록을 조회하는 API입니다.
---

# 전체 카테고리 목록 조회하기

## METHOD

```text
GET
```

## URL

```text
/category
```

## RESPONSE

- totalNum: 상위 카테고리 총 개수 (number)
- parentList: 상위 카테고리 리스트 (parentPack 리스트)
  - parentPack
    - `parent`: 상위 카테고리 정보 (object)
      - id: 카테고리 id
      - name: 카테고리 이름
      - level: 카테고리 레벨
      - postNum: 하위 카테고리들의 게시물 개수 합
      - parentCategoryId: 카테고리 id와 동일
    - childNum: 해당 상위 카테고리의 하위 카테고리 개수
    - childList: 하위 카테고리 리스트 (child 리스트)
      - `child`: 하위 카테고리 정보 (object)
        - id: 카테고리 id
        - name: 카테고리 이름
        - level: 카테고리 레벨
        - postNum: 게시물 개수
        - parentCategoryId: 상위 카테고리 id

### RESPONSE EXAMPLE

### success

**HTTP Status code : 200 OK**

```json
{
    "totalNum": 3,
    "parentList": [
        {
            "parent": {
                "id": 1,
                "name": "DSC Ewha Activity",
                "level": 1,
                "postNum": 7,
                "parentCategoryId": 1
            },
            "childNum": 3,
            "childList": [
                {
                    "id": 4,
                    "name": "공지사항",
                    "level": 2,
                    "postNum": 2,
                    "parentCategoryId": 1
                },
                {
                    "id": 5,
                    "name": "정보공유",
                    "level": 2,
                    "postNum": 2,
                    "parentCategoryId": 1
                },
                {
                    "id": 6,
                    "name": "자유게시판",
                    "level": 2,
                    "postNum": 3,
                    "parentCategoryId": 1
                }
            ]
        },
        {
            "parent": {
                "id": 2,
                "name": "개발 파트별 게시판",
                "level": 1,
                "postNum": 3,
                "parentCategoryId": 2
            },
            "childNum": 2,
            "childList": [
                {
                    "id": 7,
                    "name": "프론트엔드",
                    "level": 2,
                    "postNum": 2,
                    "parentCategoryId": 2
                },
                {
                    "id": 8,
                    "name": "백엔드",
                    "level": 2,
                    "postNum": 1,
                    "parentCategoryId": 2
                }
            ]
        },
        {
            "parent": {
                "id": 3,
                "name": "프로젝트별 게시판",
                "level": 1,
                "postNum": 0,
                "parentCategoryId": 3
            },
            "childNum": 1,
            "childList": [
                {
                    "id": 10,
                    "name": "프로젝트팀1",
                    "level": 2,
                    "postNum": 0,
                    "parentCategoryId": 3
                }
            ]
        }
    ]
}
```

