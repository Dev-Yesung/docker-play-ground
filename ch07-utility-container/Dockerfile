FROM node:14-alpine
# alpine 이미지는 경량버전이다.
WORKDIR /app
# CMD 명령에 관한 설정을 하지 않고 이미지를 run할 때 명령을 전달한다.
# 또한 바인드 마운트 볼륨을 사용하는 것으로 컨테이너와 데이터를 공유할 수 있다.
# 이 방법을 통해 호스트 컴퓨터에 node를 직접 설치하지 않고 컨테이너에 설치하는 것으로
# 노드가 있어야만 만들 수 있는 것을 호스트 컴퓨터에서 만들어 낼 수 있다.
# docker run -it -v 'myPath':/app node-util npm init

# ENTRYPOINT를 활용하면 좀 더 유연하게 활용할 수 있다.
# 예를 들어 현재 ENTRYPOINT가 npm이기 때문에,
# docker run -it -v 'myPath':/app node-util npm init
# 대신에
# docker run -it -v 'myPath':/app node-util init
# 혹은
# docker run -it -v 'myPath':/app node-util install
# 과 같은 명령어를 사용하여 실제 호스트 컴퓨터에는 npm을 설치하지 않고 기능을 사용할 수 있다.
ENTRYPOINT [ "npm" ]