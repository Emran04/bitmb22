# PHP বেসিক
### 1. PHP Tags
Php তে কোড লেখার সময় পিএইচপি tag এর ভিতরে লিখতে হয়। পিএইচপি তে চার ধরনের tag আছে ।

* Procedural tag `<?php ?>`
* ASP tag `<% %>`
* Short open tag `<? ?>`
* Script tag `<script language=”php”> </script>`


### 2. Comments
Php তে তিন ভাবে কমেন্ট লিখা যায় ।
* `// single line comment`
* `/* multiple line comment */`
* `# shell style comment`


### 3. Escaping from HTML
Php tag এর বাহিরে html কোডকে পিএইচপি পারসার বিবেচনা করেনা । তাই html এর ভিতরে পিএইচপি কোড লেখা যায় ।
```html
<p>This is going to be ignored by PHP and displayed by the browser.</p>

<?php echo 'While this is going to be parsed.'; ?>

<p>This will also be ignored by PHP and displayed by the browser.</p>
```

### 4. Instruction separation
Php তে প্রতিটা ইন্সট্রাকশন আলাদা করা হয় সেমিকোলন “;” দিয়ে।
শেষ লাইন এ সেমিকোলন না দিলেও চলবে । শেষ tag ক্লোজ না করলেও হবে।

### Types
Php ৮ প্রকার প্রিমিটিভ টাইপ সাপোর্ট করে ।

চার প্রকার স্কেলার টাইপঃ

* Boolean , এটি ট্রুথ ভেলু প্রকাশ করে । এটি শুধু true আথবা false হতে পার যেমন` $foo = true;`
* Integers, বিভিন্ন সংখ্যা এই টাইপে প্রকাশ করা হয়। যেমন` $a = 30;`
* Float, ভগ্নাংশ এই টাইপ এ প্রকাশ করা হয়। যেমন `$a = 1.234;`
* String, characters এর সমষ্টি হচ্ছে string । যেমন `$name = “abul”;`

দুই প্রকার কমপাউন্ড টাইপঃ
* Array, array হচ্ছে ভেরিএবল এর সমষ্টি । যেটি key এবং value আকারে সাজানো থাকে । যেমন `array(“color” => “red”);`
*  Object, class এর blueprint । এটিতে propertise এবং method থাকতে পারে । যেমন 
`class Foo {
};
new Foo();`

বাকি দুই প্রকারঃ
* Resources, এটি special variable, যা বাহিরের কোন resources এর রেফারেন্স রাখে।
* Null, কোন ভেলু না থাকলে সেটা নাল হিসেবে থাকে।

### Type juggling
ভেরিএবল এর এক টাইপের ভেলু কে অন্য টাইপের ভেলুতে রূপান্তর করতে type juggling ব্যবহার করা হয়।
যেমন 
```php
<?php
$foo = 10;
$bar = (boolean) $foo;
```

### Variables
পিএইচপিতে ডলার সাইন ব্যবহার করে ভেরিএবল লিখতে হয়। ভেরিএবল এর নাম case-sensitive ।
যেমন  `$name = “motin”;`

### Variable scope
Variable scope হচ্ছে যেখানে ভেরিএবল ডিক্লার করা হয়েছে সেটি কোথায় এবং এটি কোথায় কোথায় ব্যবহার করা যাবে ।

যেমন 
```php
<?php
$a = 1; // global scope

function test () {
	global $a;
	$b = 2; // local scope
	echo $a . $b;
}
test();
?>
```