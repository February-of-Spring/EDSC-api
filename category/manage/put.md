---
description: 카테고리 정보를 수정하는 API입니다.
---

# 카테고리 수정하기

## METHOD

```text
PUT
```

## URL

```text
/category/:level1, /category/:level1/:level2
```

* level1: 변경하고자 하는 상위 카테고리 이름
* level2: 변경하고자 하는 하위 카테고리 이름

## REQUEST BODY

| name | type   | require | description |
| :--- | :----- | :------ | :---------- |
| name | string | 필수    | 이름        |

### REQUEST BODY EXAMPLE

```json
{
    "name": "찬란한 팀"
}
```

## RESPONSE

### success

**HTTP Status code: 200 OK**

> Response Body는 따로 없습니다.  


### fail

**HTTP Status code: 400 Bad Request**

```json
{
    "status": "BAD_REQUEST",
    "message": "필수항목을 입력해주세요."
}
```

```json
{
    "status": "BAD_REQUEST",
    "message": "존재하지 않는 카테고리입니다."
}
```

```json
{
    "status": "BAD_REQUEST",
    "message": "이미 존재하는 카테고리입니다."
}
```

| name    | type   | description |
| ------- | ------ | ----------- |
| status  | number | HTTP status |
| message | string | 에러 메시지 |

