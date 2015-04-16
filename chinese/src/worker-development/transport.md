# transport
## 说明:
```php
string Worker::$transport
```

设置当前Worker实例所使用的传输层协议，目前只支持两种，tcp和udp。不设置默认为tcp。


## 范例

```php
use WorkerMan\Worker;
$worker = new Worker('Text://0.0.0.0:8484');
// 使用udp协议
$worker->transport = 'udp';
$worker->onMessage = function($connection, $data)
{
    $connection->send('Hello');
};
```
