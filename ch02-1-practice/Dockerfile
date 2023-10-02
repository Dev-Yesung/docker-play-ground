FROM node
WORKDIR /app

COPY . /app
RUN npm install
# EXPOSE는 명시적인 표시를 위해 작성(문서화) 필수조건은 아님
EXPOSE 80 
CMD ["node", "server.js"]

# docker run -p 접근포트:컨테이너포트 컨테이너id
# ex) docker run -p 3000:80 503ff6c5e

# docker 컨테이너의 로그를 출력
# ex) docker logs 503ff6c5e

# docker run --rm 을 사용하면 도커 컨테이너의 실행이 멈췄을 때 컨테이너가 삭제됨
# ex) docker run -d -p 3000:80 --rm 503ff6c5e

# 사용하지 않는 컨테이너 모두 삭제
# docker container prune