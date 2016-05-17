# PHP Superglobal variables
সব স্কুপ এ কাজ করে এমন কিছু বিউল্ট ইন ভেরিয়েবল হচ্ছে সুপার গ্লোবাল ভেরিয়েবল ।
এরা হচ্ছে
- $GLOBALS
- $_SERVER
- $_GET
- $_POST
- $_COOKIE
- $_SESSION
- $_FILES
- $_REQUEST
- $_ENV

এই ভেরিয়েবল গুলো নিয়ে কাজ করতে এদের আগে global লিখতে হয়না।

### GET

এটি অ্যারে আকারে url এর মাধ্যমে বর্তমান স্ক্রিপ্ট এ ভেরিয়েবল গুলো পাঠায় ।

একটা উদাহরণ দেখি

আমরা get.php নামে ফাইল এ ফর্ম এর মাধ্যমে একটা ইনপুট নিই এবং মেথড হবে get ।

get.php
```html
<form action="captureGet.php" method="get">
    <label for="username">Enter your name</label>
    <input type="text" name="username"/>
    <input type="submit" value="Submit"/>
</form>
```

এখানে আমরা ফর্ম এর অ্যাকশান দিয়েছি captureGet.php, তার মানে ফর্মটা সাবমিট হলে আমাদের get রিকুয়েস্টটা যাবে captureGet.php তে,
এবং ওই ফাইলে আমরা $_GET এর মাধ্যমে ফর্ম এর ভেলু গুলো পাব ।


get রিকুয়েস্ট এ ভেলুগুলো পাঠায় কুয়েরি স্ট্রিং এর মাধ্যমে । আমাদের ক্ষেত্রে এটা হবে অ্যাকশান এর পর , এর পর ভেলুগুলো দেখাবে। 
যেমন আমরা যদি ইনপুট এ emran দিয়ে সাবমিট করি তাহলে যাবে`captureGet.php?username=emran`

এখন আমরা যদি captureGet.php তে ` $_GET['username'] ` কে echo করি তাহলে অউটপুট এ emran প্রিন্ট হবে।

captureGet.php
```php
<?php
echo $_GET['username'];
```

### POST

Post রিকুয়েস্ট অ্যারে আকারে যাবে কিন্তু url এ দেখাবেনা। তাই এটি সিকিউর ডাটা পাঠাতে বেশি ব্যবহার করা হয়।

আগের মতই আমরা আর একটি ফর্ম নিই কিন্তু এইবার মেথড হিসেবে নিব post আর অ্যাকশান দিব capturePost.php ।


post.php
```html
<?php

<form action="capturePost.php" method="post">
    <label for="username">Enter your name</label>
    <input type="text" name="username" id="username" />
    <input type="submit" value="Submit"/>
</form>
```

এ ক্ষেত্রে পোস্ট রিকুয়েস্ট যাবে capturePost.php তে এবং ওই ফাইলে $_POST ভেরিয়েবল দিয়ে আমরা ফর্ম এর ডাটা এক্সেস করতে পারব ।
capturePost.php
```php
<?php
echo $_POST['username'];
```


