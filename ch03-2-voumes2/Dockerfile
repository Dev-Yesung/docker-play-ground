FROM node:14

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 80

# 익명 volume은 컨테이너를 멈췄을 때 제거된다.(--rm 명령에 의해 함께 제거되며, 이 볼륨은 도커에 의해 자동으로 관리된다.)
# 컨테이너를 멈춰도 데이터가 남아있으려면 volume에 이름을 붙여줘야한다.
# docker run -d -p 3000:80 --rm --name feedback-app -v feedback:/app/feedback feedback-node:volumes
# 여기서 feedback:/app/feedback이 핵심 부분 -> volume의 이름은 feedback이고 /app/feedback을 리스닝해서 로컬에 저장하겠다는 의미
VOLUME [ "/app/feedback" ]
CMD [ "node", "server.js" ]

# 하지만 도커화한 파일을 변경할 때마다 빌드를 다시해야한다.
# 왜냐하면 도커는 파일의 스냅샷을 가지고 이미지가 빌드되고 변경되기 때문이다.
# 이러한 문제를 해결할 수 있는 방법은 바인딩 마운트이다.
