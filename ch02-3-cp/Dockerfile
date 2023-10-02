FROM node
WORKDIR /app

COPY . /app
RUN npm install
# EXPOSE는 명시적인 표시를 위해 작성(문서화) 필수조건은 아님
EXPOSE 80 
CMD ["node", "server.js"]

# 로컬 -> 도커 : 파일 복사
# 경로와 복사할 구체적인 파일이 있는 경우
# ex) docker cp dummy/test.txt CONTAINER:/test

# # 경로와 그 경로의 모든 파일을 복사할 경우
# ex) docker cp dummy/. CONTAINER:/test

# 여기서 :/test는 복사된 파일이 들어갈 특정 컨테이너의 경로를 지칭

# 도커 -> 로컬 : 파일 복사

# 위의 명령어를 반대로 입력하면 됨
# ex) docker cp CONTAINER:/test dummy

# 구체적인 파일만 복사하고 싶을 경우
# ex) docker cp CONTAINER:/test/test.txt dummy