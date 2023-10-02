FROM python
WORKDIR /app

COPY . /app
CMD ["python", "rng.py"]

# docker interactive mode + terminal

# 위와 같이 터미널을 이용해 명령을 받는 앱을 사용하고 싶은 경우
# 도커가 STDIN을 입력 받을 수 있도록 옵션을 걸어야 함

# ex) docker run -it DOCKER_IMAGE
# ex) docker start -i DOCKER_CONTAINER
# ex) docker start -a DOCKER_CONTAINER 도 가능