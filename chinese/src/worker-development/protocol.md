# protocol

## 说明:
```php
string Connection::$protocol
```

设置此链的应用层协议打包解包所使用的类


## 范例


```php
use WorkerMan\Worker;
$worker = new Worker('tcp://0.0.0.0:8484');
$worker->onConnect = function($connection)
{
    $connection->protocol = 'Workerman\\Protocols\\Http';
};
$worker->onMessage = function($connection, $data)
{
    var_dump($_GET, $_POST);
    // send 时会自动调用$connection->protocol::encode()，打包数据后再发送
    $connection->send("hello");
};
```
