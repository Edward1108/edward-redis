# edward-redis
ThinkPHP框架Re的Redis扩展，支持多种Redis使用方法。支持ThinkPHP5.0和ThinkPHP5.1

## 安装
> composer require edward1108/edward-redis

## 配置
tp5.0
```
config.php
'redis'                  => [
	'host' => '127.0.0.1', // redis主机
	'port' => '', // redis端口
	'password' => '', // 密码
	'select' => 0, // 操作库
	'expire' => 0, // 有效期(秒)
	'timeout' => 0, // 超时时间(秒)
	'persistent' => true, // 是否长连接
	'prefix' => '', //前缀
]
```

tp5.1
```
config/redis.php
return [
	'host' => '127.0.0.1', // redis主机
	'port' => '', // redis端口
	'password' => '', // 密码
	'select' => 0, // 操作库
	'expire' => 0, // 有效期(秒)
	'timeout' => 0, // 超时时间(秒)
	'persistent' => true, // 是否长连接
	'prefix' => '', //前缀
];
```

## 例子
```
<?php
	namespace app\index\controller;
	use edward-redis\Redis;

	class index
	{
		public function test()
		{
			  Redis::set('name','edward-redis');
			  $res = Redis::get('name');
			  var_dump($res);  //输出edward-redis代表成功
		}
	｝
```
