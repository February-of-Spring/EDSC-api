---
description: 해당 id를 가진 프로젝트 페이지의 게시물 하나를 불러오는 API입니다

---

# 게시물 한 건 조회하기

## METHOD

```text
GET
```

## URL

```text
/projects/:id
```

* id: 프로젝트 페이지의 읽으려는 게시물 고유 id

## RESPONSE

* id: 게시물 고유 id \(number\)

### RESPONSE EXAMPLE

### success

**HTTP Status code : 200 OK**

```json
{
    "id": 123,
}
```

### fail

**HTTP Status code : 400 Bad Request**

```json
{
    "status": "BAD_REQUEST",
    "message": "존재하지 않는 게시물입니다."
}
```

| name    | type   | description                                                  |
| ------- | ------ | ------------------------------------------------------------ |
| status  | number | HTTP status code(에러 상황에 따라 변할 수 있습니다. )        |
| message | string | 에러 메시지(메시지 내용은 에러 상황에 따라 변할 수 있습니다. ) |