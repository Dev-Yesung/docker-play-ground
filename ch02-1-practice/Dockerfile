FROM node
WORKDIR /app

COPY . /app
RUN npm install
# EXPOSE는 명시적인 표시를 위해 작성(문서화) 필수조건은 아님
EXPOSE 80 
CMD ["node", "server.js"]

# docker run -p 접근포트:컨테이너포트 컨테이너id
# ex) docker run -p 3000:80 503ff6c5e009629...