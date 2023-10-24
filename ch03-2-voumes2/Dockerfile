FROM node:14

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

# 만일 빌드타임에 PORT와 같은 값의 디폴트 값을 동적으로 만들고 싶다면, ARG를 사용한다.
# 이왕이면 변경되었을 때 다른 레이어가 변경되지 않도록 뒷쪽에 배치하는게 좋다.
# 예를 들어 우리는 npm install이 다시 실행되는 걸 원치 않기 때문에...!
ARG DEFAULT_PORT=80

# 환경변수를 제공하는 방법
ENV PORT $DEFAULT_PORT

EXPOSE $PORT

# 익명 volume은 컨테이너를 멈췄을 때 제거된다.(--rm 명령에 의해 함께 제거되며, 이 볼륨은 도커에 의해 자동으로 관리된다.)
# 컨테이너를 멈춰도 데이터가 남아있으려면 volume에 이름을 붙여줘야한다.
# docker run -d -p 3000:80 --rm --name feedback-app -v feedback:/app/feedback feedback-node:volumes
# 여기서 feedback:/app/feedback이 핵심 부분 -> volume의 이름은 feedback이고 /app/feedback을 리스닝해서 로컬에 저장하겠다는 의미
# VOLUME [ "/app/feedback" ]
# CMD [ "node", "server.js" ]

# 노드몬 사용으로 변경
CMD [ "npm", "start" ]

# 하지만 도커화한 파일을 변경할 때마다 빌드를 다시해야한다.
# 왜냐하면 도커는 파일의 스냅샷을 가지고 이미지가 빌드되고 변경되기 때문이다.
# 이러한 문제를 해결할 수 있는 방법은 바인딩 마운트이다.
# 바인딩 마운트는 기존의 도커 컨테이너를 덮어쓰기 때문에 덮어쓰지 않고 싶은 영역은 익명 볼륨을 통해 해결할 수 있다.
# 예를들어 app/node_module의 경우 바인딩 마운트보다 더 구체적인 경로이기 때문에 익명 볼륨에 의해 덮어씌워진다.
