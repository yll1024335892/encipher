# php的免加密文档
## Encipher - the PHP code encode tool ##

php code encode &amp; decode

A simple demo (see ./index.php)

Good luck!



## Encipher - PHP代码加密工具 ##

1.本加密程序是用PHP代码写的。

2.加密后代码无需任何附加扩展，无需安装任何第三方组件，可运行于任何普通 PHP 环境下。

3.加密使用方法详见：./index.php

> 其中：./encoded目录下存放的就是加密后的实例。



## 注意 ##

1.该加密程序未经严格测试，如果使用该加密程序，一切后果作者概不负责。

2.加密后代码无需扩展和第三方组件的加密方式，理论上都是可以破解的。

如有问题，请联系作者（Jacky Yu <jacky325@qq.com>）。
## 使用方法
```
<?php
$app = str_replace('\\', '/', dirname(__FILE__));
require_once($app . '/lib/encipher.min.php');
 
$original = $app . '/original'; //待加密的文件目录
$encoded  = $app . '/encoded';  //加密后的文件目录
$encipher = new Encipher($original, $encoded);
 
/**
 * 设置加密模式 false = 低级模式; true = 高级模式
 * 低级模式不使用eval函数
 * 高级模式使用了eval函数
 */
$encipher->advancedEncryption = true;
 
//设置注释内容
$encipher->comments = array(
    'Encipher - the PHP code encode tool',
    'Version: 1.1.1',
    '',
    'The latest version of Encipher can be obtained from:',
    'https://github.com/uniqid/encipher'
);
 
echo "<pre>\n";
$encipher->encode();
echo "</pre>\n";
```
