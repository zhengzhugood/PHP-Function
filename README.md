# -PHP-
## 这些PHP函数你应该惠存，以备不时之需

* PHP加密/解密  使用的是base64和md5

```php
// PHP加密/解密  使用的是base64和md5
function encryptDecrypt($key, $string, $decrypt){ 
  if($decrypt){ 
    $decrypted = rtrim(mcrypt_decrypt(MCRYPT_RIJNDAEL_256, md5($key), base64_decode($string), MCRYPT_MODE_CBC, md5(md5($key))), "12"); 
    return $decrypted; 
  }else{ 
    $encrypted = base64_encode(mcrypt_encrypt(MCRYPT_RIJNDAEL_256, md5($key), $string, MCRYPT_MODE_CBC, md5(md5($key)))); 
    return $encrypted; 
  } 
}
```

* 生成随机字符串

```php
// 生成随机字符串
function generateRandomString($length = 10) { 
  $characters = '0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ'; 
  $randomString = ''; 
  for ($i = 0; $i < $length; $i++) { 
    $randomString .= $characters[rand(0, strlen($characters) - 1)]; 
  } 
  return $randomString; 
}
```

* 得到文件扩展名

```php
// PHP加密/解密  使用的是base64和md5
function encryptDecrypt($key, $string, $decrypt){ 
  if($decrypt){ 
    $decrypted = rtrim(mcrypt_decrypt(MCRYPT_RIJNDAEL_256, md5($key), base64_decode($string), MCRYPT_MODE_CBC, md5(md5($key))), "12"); 
    return $decrypted; 
  }else{ 
    $encrypted = base64_encode(mcrypt_encrypt(MCRYPT_RIJNDAEL_256, md5($key), $string, MCRYPT_MODE_CBC, md5(md5($key)))); 
    return $encrypted; 
  } 
}
```

* 把获取的文件大小结果进行格式化

```php
// PHP加密/解密  使用的是base64和md5
function encryptDecrypt($key, $string, $decrypt){ 
  if($decrypt){ 
    $decrypted = rtrim(mcrypt_decrypt(MCRYPT_RIJNDAEL_256, md5($key), base64_decode($string), MCRYPT_MODE_CBC, md5(md5($key))), "12"); 
    return $decrypted; 
  }else{ 
    $encrypted = base64_encode(mcrypt_encrypt(MCRYPT_RIJNDAEL_256, md5($key), $string, MCRYPT_MODE_CBC, md5(md5($key)))); 
    return $encrypted; 
  } 
}
```

* 替换标签

```php
// PHP加密/解密  使用的是base64和md5
function encryptDecrypt($key, $string, $decrypt){ 
  if($decrypt){ 
    $decrypted = rtrim(mcrypt_decrypt(MCRYPT_RIJNDAEL_256, md5($key), base64_decode($string), MCRYPT_MODE_CBC, md5(md5($key))), "12"); 
    return $decrypted; 
  }else{ 
    $encrypted = base64_encode(mcrypt_encrypt(MCRYPT_RIJNDAEL_256, md5($key), $string, MCRYPT_MODE_CBC, md5(md5($key)))); 
    return $encrypted; 
  } 
}
```

* 获取文件目录列表

```php
// PHP加密/解密  使用的是base64和md5
function encryptDecrypt($key, $string, $decrypt){ 
  if($decrypt){ 
    $decrypted = rtrim(mcrypt_decrypt(MCRYPT_RIJNDAEL_256, md5($key), base64_decode($string), MCRYPT_MODE_CBC, md5(md5($key))), "12"); 
    return $decrypted; 
  }else{ 
    $encrypted = base64_encode(mcrypt_encrypt(MCRYPT_RIJNDAEL_256, md5($key), $string, MCRYPT_MODE_CBC, md5(md5($key)))); 
    return $encrypted; 
  } 
}
```

* 获取当前页面的URL

```php
// PHP加密/解密  使用的是base64和md5
function encryptDecrypt($key, $string, $decrypt){ 
  if($decrypt){ 
    $decrypted = rtrim(mcrypt_decrypt(MCRYPT_RIJNDAEL_256, md5($key), base64_decode($string), MCRYPT_MODE_CBC, md5(md5($key))), "12"); 
    return $decrypted; 
  }else{ 
    $encrypted = base64_encode(mcrypt_encrypt(MCRYPT_RIJNDAEL_256, md5($key), $string, MCRYPT_MODE_CBC, md5(md5($key)))); 
    return $encrypted; 
  } 
}
```

* 下载文件

```php
// PHP加密/解密  使用的是base64和md5
function encryptDecrypt($key, $string, $decrypt){ 
  if($decrypt){ 
    $decrypted = rtrim(mcrypt_decrypt(MCRYPT_RIJNDAEL_256, md5($key), base64_decode($string), MCRYPT_MODE_CBC, md5(md5($key))), "12"); 
    return $decrypted; 
  }else{ 
    $encrypted = base64_encode(mcrypt_encrypt(MCRYPT_RIJNDAEL_256, md5($key), $string, MCRYPT_MODE_CBC, md5(md5($key)))); 
    return $encrypted; 
  } 
}
```

* 获取用户IP

```php
// PHP加密/解密  使用的是base64和md5
function encryptDecrypt($key, $string, $decrypt){ 
  if($decrypt){ 
    $decrypted = rtrim(mcrypt_decrypt(MCRYPT_RIJNDAEL_256, md5($key), base64_decode($string), MCRYPT_MODE_CBC, md5(md5($key))), "12"); 
    return $decrypted; 
  }else{ 
    $encrypted = base64_encode(mcrypt_encrypt(MCRYPT_RIJNDAEL_256, md5($key), $string, MCRYPT_MODE_CBC, md5(md5($key)))); 
    return $encrypted; 
  } 
}
```

* 检测参数是否有SQL注入的可能性
