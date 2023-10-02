FROM node
WORKDIR /app

COPY . /app
RUN npm install
# EXPOSE는 명시적인 표시를 위해 작성(문서화) 필수조건은 아님
EXPOSE 80 
CMD ["node", "server.js"]

# 도커 컨테이너에 이름 붙이기
# ex) docker run -p 3000:80 -d --name CONTAINER_NAME IMAGE

# 도커 이미지에 이름 붙이기 ( name(repository):tag )
# name을 통해서는 여러 개의 이미지 그룹을 만들 수 있음
# tag는 이미지 그룹 내의 특정한 버전,이름을 지칭할 때 사용
# ex) docker build -t goals:latest .

# 태그된 이미지를 포함하여 사용하지 않는 모든 이미지를 삭제
# docker image prune -a