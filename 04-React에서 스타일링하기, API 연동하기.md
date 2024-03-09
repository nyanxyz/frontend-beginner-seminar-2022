# 4. React에서 스타일링하기, API 연동하기

1. emotion
    1. react
    2. styled
2. [https://junghan92.medium.com/번역-우리가-css-in-js와-헤어지는-이유-a2e726d6ace6](https://junghan92.medium.com/%EB%B2%88%EC%97%AD-%EC%9A%B0%EB%A6%AC%EA%B0%80-css-in-js%EC%99%80-%ED%97%A4%EC%96%B4%EC%A7%80%EB%8A%94-%EC%9D%B4%EC%9C%A0-a2e726d6ace6)
    1. [stitches](https://stitches.dev/)

---

1. REST API란?
    1. Representational State Transfer API
    - **GET**: 데이터 조회
        - 글, id=11999
    - **POST**: 데이터 등록
        - 쓴 글 내용
        - 아이디, 비밀번호
    - **PUT**: 데이터 수정
        - 쓴 글 내용
        - 아이디, 비밀번호
    - **DELETE**: 데이터 제거
        - 글, id=11999
2. axios
    1. axios.get
    2. axios.post
    3. [https://jsonplaceholder.typicode.com/users](https://jsonplaceholder.typicode.com/users)
    
    ```json
    {
      "id": 1,
      "name": "Leanne Graham",
      "username": "Bret",
      "email": "Sincere@april.biz",
      "address": {
        "street": "Kulas Light",
        "suite": "Apt. 556",
        "city": "Gwenborough",
        "zipcode": "92998-3874",
        "geo": {
          "lat": "-37.3159",
          "lng": "81.1496"
        }
      },
      "phone": "1-770-736-8031 x56442",
      "website": "hildegard.org",
      "company": {
        "name": "Romaguera-Crona",
        "catchPhrase": "Multi-layered client-server neural-net",
        "bs": "harness real-time e-markets"
      }
    }[]
    ```