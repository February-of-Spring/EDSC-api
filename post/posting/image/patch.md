---
description: 게시물에 첨부된 이미지 중 해당 id의 이미지를 수정하는 API입니다.
---

# 게시물 이미지 수정하기

## METHOD

```text
PATCH
```

## URL

```text
/posts/:id/image
```

* id: 게시물에 첨부된 이미지 고유 id

## REQUEST BODY

| name  | type                | require | description            |
| :---- | :------------------ | :------ | :--------------------- |
| image | multipart/form-data | 필수    | 게시물에 첨부할 이미지 |

> 현재 저장가능한 이미지로 `.jpg`, `.jpeg`, `.gif`, `.png`, `.img`, `.tiff`, `.heif` 확장자만 지원합니다.

### REQUEST BODY EXAMPLE

![example on postman](https://user-images.githubusercontent.com/68107000/108875669-c335ce80-7640-11eb-868d-373584a98a61.png)

## RESPONSE

### success

**HTTP Status code: 201 OK**

> Response Body는 따로 없습니다.  
> 대신, Http Location **헤더**에 생성된 자원의 경로를 붙여서 반환합니다. 
> ex\) [https://edsc-s3.s3.ap-northeast-2.amazonaws.com/post-image/1](https://edsc-s3.s3.ap-northeast-2.amazonaws.com/post-image/1)

### fail

**HTTP Status code: 400 Bad Request or 500 Internal Server Error**

```json
{
    "status": "BAD_REQUEST",
    "message": "존재하지 않는 이미지입니다."
}
```

```json
{
    "status": "BAD_REQUEST",
    "message": "파일이 없습니다."
}
```

```json
{
    "status": "INTERNAL_SERVER_ERROR",
    "message": "파일 변환에 실패했습니다."
}
```

```json
{
    "status": "BAD_REQUEST",
    "message": "지원하지 않는 파일 형식입니다."
}
```

| name    | type   | description |
| :------ | :----- | :---------- |
| status  | number | HTTP status |
| message | string | 에러 메시지 |

