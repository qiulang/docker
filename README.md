For more details about this project visit this [blog post](http://blog.mpayetta.com/node.js/docker/mongodb/2016/09/04/dockerizing-node-mongo-app/)

curl -d 如果是json数据一定要设置 -H "Content-type:application/json”

不然会按照纯文本解析

https://gist.github.com/subfuzion/08c5d85437d5d4f00e58

curl -H "Content-type: application/json" http://localhost:3000/data/into/db \
    -d '[ { "a": 1 }, { "b": 2 }, { "c": 3 } ]'
