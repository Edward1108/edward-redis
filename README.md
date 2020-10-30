# edward-redis
ThinkPHP框架的Redis扩展，支持多种Redis使用方法。支持ThinkPHP6.0和ThinkPHP5.x

## 安装
> composer require edward1108/edward-redis

## 配置

ThinkPHP6.0.x 和 ThinkPHP5.1.x
```
config/redis.php
return [
    // 缓存前缀
    'prefix'        => '',
    // 缓存有效期 0表示永久缓存，单位：秒
    'expire'        => 0,
    // redis主机
    'host'          => '127.0.0.1',
    // redis端口
    'port'          => '',
    // 密码
    'password'      => '',
    // 操作库
    'select'        => 0,
    // 超时时间(秒)
    'timeout'       => 0,
    // 是否长连接
    'persistent'    => false,
];
```

ThinkPHP5.0.x
```
config.php
'redis'                  => [
    // 缓存前缀
    'prefix'        => '',
    // 缓存有效期 0表示永久缓存，单位：秒
    'expire'        => 0,
    // redis主机
    'host'          => '127.0.0.1',
    // redis端口
    'port'          => '',
    // 密码
    'password'      => '',
    // 操作库
    'select'        => 0,
    // 超时时间(秒)
    'timeout'       => 0,
    // 是否长连接
    'persistent'    => false,
]
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
