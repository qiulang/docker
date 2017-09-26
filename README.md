我的第一个docker-compose例子。起了两个container，一个node，一个mongo，网上能找到例子都太老了。 修改这个篇文字的例子 [dockerizing-node-mongo-app](http://blog.mpayetta.com/node.js/docker/mongodb/2016/09/04/dockerizing-node-mongo-app/)

一个关键点在 var uri = **"mongodb://mongo**/dummy-app"; 连接另一个container

测试mongod是不是起了最简单方法连27017端口 nc -zvv localhost 27017

curl -d 如果是json数据一定要设置 -H "Content-type:application/json”

不然会按照纯文本解析 [curl 例子](https://gist.github.com/subfuzion/08c5d85437d5d4f00e58)

	curl -H "Content-type: application/json" http://localhost:3000/data/into/db \
	    -d '[ { "a": 1 }, { "b": 2 }, { "c": 3 } ]'

最简单的docker-compose 模板


	web:
	  image: example/my_web_app:latest
	  links:
	    - db
	    - cache
	
	db:
	  image: postgres:latest
	
	cache:
	  image: redis:latest

两个可以借鉴的文章

	http://blog.mpayetta.com/node.js/docker/mongodb/2016/09/04/dockerizing-node-mongo-app/

    https://medium.com/@sunnykay/docker-development-workflow-node-express-mongo-4bb3b1f7eb1e