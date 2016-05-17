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

### $_GET

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

এখন আমরা যদি captureGet.php এ $_GET['username'] কে echo করি তাহলে অউটপুট এ emran প্রিন্ট হবে।


captureGet.php
```php
<?php
echo $_GET['username'];
```

### $_POST

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



### $_SESSION

Session ইউজার সম্পর্কিত ডেটা সার্ভার এ পাঠায় ।

Session ব্যবহার করার জন্য আমরা ফাইল এর প্রথমেই session_start() ফাংশন ব্যবহার করতে হবে।
এটি ব্রাউজার এ PHPSESSID নামে একটি cookie তৈরি করবে এবং এর ডেটা সার্ভার এ পাঠাবে ।
ইউজার যখন ওয়েবসাইট এ ঢুকবে তখনি সেশন ক্রিয়েট হবে এবং যখন ব্রাউজার ক্লোজ করবে তখন সেশন শেষ হবে। 

`session_start()` ফাংশন এর পর আমরা যদি `$_SESSION['username'] = "emran" `
সেট করি তাহলে এই ভেলুটি session থাকা পর্যন্ত আমরা অ্যাক্সেস করতে পারব। 


session.php
```php
<?php
session_start();

$_SESSION['username'] = "emran";
```

আমরা যদি ব্রাউজার এর ডেভেলপার টুল ব্যবহার করে Resources টেব এর Cookies > localhost এ দেখি তাহলে PHPSESSID নামের
cookie দেখতে পাব।

![Image of Project1](/week2/day-1/screenshots/Screenshot_1.jpg)


এখন আমরা যদি অন্য কোন পেইজ এ $_SESSION['username'] কে দেখি তাহলে emran আউটপুট দেখাবে ।
তবে এর আগে অবশ্যই session_start() করে নিতে হবে।


captureSession.php
```php
<?php
session_start();

echo $_SESSION['username'];
```

আমরা চাইলে `session_destroy()` ফাংশন দিয়ে সেশন শেষ করতে পারি।


sessionDestroy.php
```php
<?php
session_start();

$_SESSION['username'] = array();

session_destroy();
```

### $_COOKIE

Cookie হচ্ছে ইউজার সম্পর্কিত ডেটা যা ব্রাউজার এ সেভ করা থাকে এবং http হেডার এর মাধ্যমে সার্ভার এ পাঠায় ।

cookie ব্যবহার করার জন্য আমরা `setcookie()` ফাংশন টা ব্যবহার করব ।
এটি তিনটি প্যারামিটার নিবে name, value, expire ।


cookie.php
```php
<?php
$name = "user";
$value = "Emran Hossen";
$expire = time() + (60*60*24);

setcookie($name, $value, $expire);
```

আমরা যদি আবার ব্রাউজার এর ডেভেলপার টুল ব্যবহার করে Resources টেব এর Cookies > localhost এ দেখি তাহলে user নামের
cookie দেখতে পাব।

![Image of Project2](/week2/day-1/screenshots/Screenshot_2.jpg)
