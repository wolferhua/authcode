# authcode
数据打包方法。
# 案例

```
include 'AuthCode.php';

$pack = AuthCode::pack([
    'name' => 'wolferhua',
    'mail' => '358273385@qq.com',
    'sex' => 'man',
    'site'=>'http://www.hashmop.com/'
]);

echo $pack . PHP_EOL;
//e3Z6sGiJJAkhIiIcImlJdHEiOBJObTCwUyN0MEZNTGIwMGUwSWRhbUgwSk5VME16VVkwanh6TVdnMVFsRngwbWp2YnlJczR6NWhiV29pT2lKM2IyY3paWEpv
ZFdFaUxDSnpaWGdpT2lKdFlXNGlMQ0p6YVhSbElqb2lhSFIwY0RwY0wxd3ZkM2QzTG1oaGMyaHRiM0F1WTI5dFhDOGlmUSIsInNpZ24iOiI3OWMwNjM4NzIw
NDJhZmEyNjI3ZDFmYzYwMjhkZmVkNyIsInRpbWVzdGFtcCI6MTUxMDIxMTc2OX0


$data = AuthCode::unpack($pack);
var_dump($data);
/**
array(4) {
  ["appId"]=>
  string(0) ""
  ["data"]=>
  array(4) {
    ["mail"]=>
    string(16) "358273385@qq.com"
    ["name"]=>
    string(9) "wolferhua"
    ["sex"]=>
    string(3) "man"
    ["site"]=>
    string(23) "http://www.hashmop.com/"
  }
  ["sign"]=>
  string(32) "79c063872042afa2627d1fc6028dfed7"
  ["timestamp"]=>
  int(1510211769)
}

*/
$data = AuthCode::getDataByPack($pack);
var_dump($data);
/**
array(4) {
  ["mail"]=>
  string(16) "358273385@qq.com"
  ["name"]=>
  string(9) "wolferhua"
  ["sex"]=>
  string(3) "man"
  ["site"]=>
  string(23) "http://www.hashmop.com/"
}
*/
```