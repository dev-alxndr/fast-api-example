# Fast Api

Facebook 을 보다 [FastAPI 톺아보기 - 부제: python 백엔드 봄은 온다](https://jybaek.tistory.com/890)이러한 글을 보게되었는데, 굉장히 간결하고 좋아보여서 한번 공부해보려합니다.

[Fast Api](https://fastapi.tiangolo.com/ko/)   

공식 사이트에선 Fast Api 특징을 아래처럼 소개하고 있습니다.
![](./images/features.png)

간단한 예제로 살펴보겠습니다.

---
python version : 3.6+
#### 1. Fast Api 패키지 설치
- bash   
  `$pip install fastapi[all]`

### 2. Python Project & main.py 생성
- main.py
    ```python
    from fastapi import FastAPI # 1
    
    app = FastAPI() # 2
    
    @app.get("/") # 3
    async def root(): # 4
        return {"message" : "Hello Fast Api"} # 5
    ```
1. FastApi 임포트
2. Instance 생성
3. 루트 핸들러 생성
    1. Request Methods
    - `@app.post()`
    - `@app.put()`
    - `@app.delete()`
    - `@app.options()`
    - `@app.head()`
    - `@app.patch()`
    - `@app.trace()`
4. 핸들러가 실행할 함수
5. 컨텐츠 반환
    - `dict`, `list` `str`, `int`등 json으로 자동 변환되는 객체들과 모델들이 있습니다.
    
    
### 3. Start Server
- bash   
`$uvicorn main:app --reload`
  1. `--reload` : 코드 변경시 자동 재시작  (개발에서만 사용)
![](./images/start_server.png)
> 참고   
> [About Uvicorn](https://www.uvicorn.org/)   
> [ASGI에 대하여](http://blog.neonkid.xyz/249)

### 4. 만든 API 호출해보기
![](./images/hello_fast_api.png)

### 5. API Docs 확인
Fast API는 API 문서를 자동으로 만들어 줍니다.
`http://localhost:8000/docs` 로 접속해서 확인해봅니다.
![](./images/docs.png)
여기에서 API 목록과 결과 예시를 볼 수 있습니다.
`http://localhost:8000/redoc` 다른 버전의 문서경로입니다.

---
#### Reference
[Fast Api Tutorial](https://fastapi.tiangolo.com/ko/tutorial/)