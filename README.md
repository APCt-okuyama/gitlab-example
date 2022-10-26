# gitlab
https://docs.gitlab.com/ee/install/docker.html

## how to use

```
docker pull gitlab/gitlab-ce
```

無料で利用できる ce(community edition)
```
export GITLAB_HOME=/srv/gitlab
sudo docker run --detach \
  --hostname gitlab.example.com \
  --publish 443:443 --publish 80:80 --publish 22:22 \
  --name gitlab \
  --restart always \
  --volume $GITLAB_HOME/config:/etc/gitlab \
  --volume $GITLAB_HOME/logs:/var/log/gitlab \
  --volume $GITLAB_HOME/data:/var/opt/gitlab \
  --shm-size 256m \
  gitlab/gitlab-ce:latest
```
起動に数分かかります。ログを確認してみる
```
docker logs -f gitlab
```
しばらくしてから http://localhost にブラウザからアクセスしてみる
以下のようなログイン画面が表示される
![image](./gitlab_01.PNG)
