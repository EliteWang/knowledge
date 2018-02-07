## Elastic Search

### es设置最大查询数量，默认只能查10000条  
	
	curl -XPUT http://127.0.0.1:9200/projects/_settings -d '{ "index" : { "max_result_window" : 100000000}}'


### 查询的结果不一样

	这是由于每次查询的节点是随机的。所以在查询的时候可以指定preference

	Controls a preference of which shard replicas to execute the search request on. 