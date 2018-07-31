[![Latest Stable Version](https://poser.pugx.org/zoujingli/ip2region/v/stable)](https://packagist.org/packages/zoujingli/ip2region)
[![Total Downloads](https://poser.pugx.org/zoujingli/ip2region/downloads)](https://packagist.org/packages/zoujingli/ip2region)
[![Latest Unstable Version](https://poser.pugx.org/zoujingli/ip2region/v/unstable)](https://packagist.org/packages/zoujingli/ip2region)
[![License](https://poser.pugx.org/zoujingli/ip2region/license)](https://packagist.org/packages/zoujingli/ip2region)


本库基于 [lionsoul2014/ip2region](https://github.com/lionsoul2014/ip2region) 和 [zoujingli/ip2region](https://github.com/zoujingli/ip2region) ，整合使用`composer`来管理。

同时重新打包了`ip2region.db`文件，使用`GBT2260`国家行政区域划分代码作为city_id的返回值。

--

[ip2region](https://github.com/lionsoul2014/ip2region) - 最自由的ip地址查询库，ip到地区的映射库，提供Binary,B树和纯内存三种查询算法，妈妈再也不用担心我的ip地址定位。

### 1. 99.9%准确率，定时更新：

数据聚合了一些知名ip到地名查询提供商的数据，这些是他们官方的的准确率，经测试着实比纯真啥的准确多了。<br />
每次聚合一下数据需要1-2天，会不定时更新。

### 2. 标准化的数据格式：

每条ip数据段都固定了格式：_城市Id|国家|区域|省份|城市|ISP_

只有中国的数据精确到了城市，其他国家只能定位到国家，后前的选项全部是0，已经包含了全部你能查到的大大小小的国家。

### 3. 体积：

数据库文件`ip2region.db`重新打包后大小为3.3M

### Composer 安装

```
composer require shaojjjin/ip2region
```

### ip2region 使用
```php

$ip2region = new Ip2Region();

$ip = '101.105.35.57';

$info = $ip2region->btreeSearch($ip);

var_export($info, true);

// array (
//     'city_id' => 440300,
//     'region' => '中国|华南|广东省|深圳市|鹏博士',
// )

```
