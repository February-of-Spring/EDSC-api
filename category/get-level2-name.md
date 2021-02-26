---
description: 글을 쓰거나 수정할 때 선택할 카테고리를 불러오는 API입니다.
---

# 하위 카테고리 이름 조회하기

## METHOD

```text
GET
```

## URL

```text
/category/level2name
```

## RESPONSE

* 카테고리 이름 리스트

### RESPONSE EXAMPLE

### success

**HTTP Status code : 200 OK**

```javascript
[
    "공지사항",
    "정보공유",
    "자유게시판",
    "프론트엔드",
    "백엔드",
    "프로젝트팀1"
]
```

