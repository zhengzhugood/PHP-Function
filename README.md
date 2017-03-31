# -PHP-
## 这些PHP函数你应该惠存，以备不时之需

* ***PHP加密/解密  使用的是base64和md5***

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

// 使用
//Encryption
echo encryptDecrypt('password', 'Helloweba',0); 
//Decryption
echo encryptDecrypt('password', 'z0JAx4qMwcF+db5TNbp/xwdUM84snRsXvvpXuaCa4Bk=',1);
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
// 得到文件扩展名
function getExtension($filename){ 
  $myext = substr($filename, strrpos($filename, '.')); 
  return str_replace('.','',$myext); 
}

// 使用
$filename = 'mydoc.doc'; 
echo getExtension($filename);
```

* 把获取的文件大小结果进行格式化

```php
// 把获取的文件大小结果进行格式化
function formatSize($size) { 
    $sizes = array(" Bytes", " KB", " MB", " GB", " TB", " PB", " EB", " ZB", " YB"); 
    if ($size == 0) {  
        return('n/a');  
    } else { 
      return (round($size/pow(1024, ($i = floor(log($size, 1024)))), 2) . $sizes[$i]);  
    } 
}

// 使用
$thefile = filesize('test_file.mp3'); 
echo formatSize($thefile);
```

* 替换标签

```php
// 替换标签
function stringParser($string,$replacer){ 
    $result = str_replace(array_keys($replacer), array_values($replacer),$string); 
    return $result; 
}

// 使用
$string = 'The {b}anchor text{/b} is the {b}actual word{/b} or words used {br}to describe the link {br}itself'; 
$replace_array = array('{b}' => '','{/b}' => '','{br}' => '
'); 
echo stringParser($string,$replace_array);
```

* 获取文件目录列表

```php
// 获取文件目录列表
function listDirFiles($DirPath){ 
    if($dir = opendir($DirPath)){ 
         while(($file = readdir($dir))!== false){ 
              if(!is_dir($DirPath.$file)) 
              { 
                  echo "filename: $file"; 
              } 
         } 
    } 
}

// 使用
listDirFiles('home/some_folder/');
```

* 获取当前页面的URL

```php
// 获取当前页面的URL
function curPageURL() { 
  $pageURL = 'http'; 
  if (!empty($_SERVER['HTTPS'])) {$pageURL .= "s";} 
  $pageURL .= "://"; 
  if ($_SERVER["SERVER_PORT"] != "80") { 
    $pageURL .= $_SERVER["SERVER_NAME"].":".$_SERVER["SERVER_PORT"].$_SERVER["REQUEST_URI"]; 
  } else { 
    $pageURL .= $_SERVER["SERVER_NAME"].$_SERVER["REQUEST_URI"]; 
  } 
  return $pageURL; 
}
```

* 下载文件

```php
// 下载文件
function download($filename){ 
   if ((isset($filename))&&(file_exists($filename))){ 
     header("Content-length: ".filesize($filename)); 
     header('Content-Type: application/octet-stream'); 
     header('Content-Disposition: attachment; filename="' . $filename . '"'); 
     readfile("$filename"); 
   } else { 
     echo "Looks like file does not exist!"; 
   } 
}

// 使用
download('/down/test_45f73e852.zip');
```

* 获取用户IP

```php
// 获取用户IP
function getIp() { 
  if (getenv("HTTP_CLIENT_IP") && strcasecmp(getenv("HTTP_CLIENT_IP"), "unknown")) 
    $ip = getenv("HTTP_CLIENT_IP"); 
  else
    if (getenv("HTTP_X_FORWARDED_FOR") && strcasecmp(getenv("HTTP_X_FORWARDED_FOR"), "unknown")) 
      $ip = getenv("HTTP_X_FORWARDED_FOR"); 
    else
      if (getenv("REMOTE_ADDR") && strcasecmp(getenv("REMOTE_ADDR"), "unknown")) 
        $ip = getenv("REMOTE_ADDR"); 
      else
        if (isset ($_SERVER['REMOTE_ADDR']) && $_SERVER['REMOTE_ADDR'] && strcasecmp($_SERVER['REMOTE_ADDR'], "unknown")) 
          $ip = $_SERVER['REMOTE_ADDR']; 
        else
          $ip = "unknown"; 
  return ($ip); 
}
```

* 检测参数是否有SQL注入的可能性

```php
// 检测参数是否有SQL注入的可能性
function injCheck($sql_str) {  
  $check = preg_match('/select|insert|update|delete|\'|\/\*|\*|\.\.\/|\.\/|union|into|load_file|outfile/', $sql_str); 
  if ($check) { 
    echo '非法字符！！'; 
    exit; 
  } else { 
    return $sql_str; 
  } 
}

// 使用
echo injCheck('1 or 1=1');
```
