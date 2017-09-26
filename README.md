For more details about this project visit this [blog post](http://blog.mpayetta.com/node.js/docker/mongodb/2016/09/04/dockerizing-node-mongo-app/)


var uri = "mongodb://mongo/dummy-app"; 连接另一个container

测试mongod是不是起了最简单方法连27017端口 nc -zvv localhost 27017

docker-compose up/docker-compose down

curl -d 如果是json数据一定要设置 -H "Content-type:application/json”

不然会按照纯文本解析

https://gist.github.com/subfuzion/08c5d85437d5d4f00e58

curl -H "Content-type: application/json" http://localhost:3000/data/into/db \
    -d '[ { "a": 1 }, { "b": 2 }, { "c": 3 } ]'
