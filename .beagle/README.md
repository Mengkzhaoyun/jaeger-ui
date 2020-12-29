# git

```bash
# github
git remote add upstream git@github.com:jaegertracing/jaeger-ui.git

git fetch upstream

git merge v1.12.0

# gitlab
git remote add beagle git@cloud.wodcloud.com:cloud/jaeger-ui.git

git fetch beagle

git push beagle github
```

## build

```bash
docker run --rm \
-v /usr/local/share/.cache/yarn:/usr/local/share/.cache/yarn \
-v $PWD/:/go/src/github.com/jaegertracing/jaeger-ui \
-w /go/src/github.com/jaegertracing/jaeger-ui \
registry.cn-qingdao.aliyuncs.com/wod/devops-node:14.15.0-buster \
bash -c 'yarn install --frozen-lockfile && cd packages/jaeger-ui && yarn build'
```
