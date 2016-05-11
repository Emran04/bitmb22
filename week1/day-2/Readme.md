## গিট পরিচিতি

### গিট কি ?

গিট হচ্ছে ভার্সন কন্ট্রোল সিস্টেম । আমরা প্রোজেক্ট এর বিভিন্ন ভার্সন এর মাধ্যমে খুব সহজে কন্ট্রোল করতে পারি । এটি অনেকটা আমাদের কাজের বিভিন্ন সময়ে স্ক্রিনশট নিয়ে রাখার মত কাজ করে ।

### গিট কেন ব্যাবহার করব ?
আমরা যখন প্রোজেক্ট এ কাজ করি বিভিন্ন ফাইল আর ফোল্ডার নিয়ে কাজ করি, প্রোজেক্ট এর ফাইল আর ফোল্ডার এর পরিবর্তন track করার জন্য আমরা গিট ব্যাবহার করব ।

একটা ছোট উদাহরণ দেখি, ধরি আমরা একটি ওয়েব অ্যাপ্লিকেশান বানাচ্ছি প্রোজেক্ট ফোল্ডার gitbasic  তাতে index.php নামে একটি ফাইল এবং css/ , img/ আর css এর মধ্যে style.css ফাইল আছে । এখন আমরা আমাদের প্রোজেক্ট এ গিট ব্যাবহার করব ।

#### ১। git init
আমরা আগেই আমাদের মেশিন এ গিট ইন্সটল করে নিয়েছি। প্রথমে রুট ফোল্ডার এ গিট initialize করতে হবে mouse এর রাইট বাটন ক্লিক করে start git bash here এ জেতে হবে ,  এর পর git init দিয়ে  initialize হয়ে যাবে এবং রুট ফোল্ডার এ .git নামে একটি হিডেন ফোল্ডার তৈরি হবে।
![Link](https://github.com/Emran04/bitmb22/week1/day-2/screenshots/Screenshot_1.jpg)
#### ২। git add *
এই কমান্ড এর মাধ্যমে আমরা আমাদের সব ফাইলকে track করব ।
![Link](https://github.com/Emran04/bitmb22/week1/day-2/screenshots/Screenshot_2.jpg)
#### ৩। git status
এর মাধ্যমে আমরা প্রোজেক্ট এর বর্তমান আবস্তা সম্পর্কে জানতে পারব।
![Link](https://github.com/Emran04/bitmb22/week1/day-2/screenshots/Screenshot_3.jpg)
#### ৪। git commit -m “First commit”
এর মাধ্যমে আমাদের ফাইল গুলোকে রেকর্ড করব ।
![Link](https://github.com/Emran04/bitmb22/week1/day-2/screenshots/Screenshot_4.jpg)
এই টুকু করলেই আমাদের কাজ অনেটা হয়ে যাবে ।

এখন আমরা প্রোজেক্টকে সার্ভার এ আপলোড করব । এটি করার জন্য আমরা  gitlab ব্যবহার করব।

####  ১। gitlab
এ একটি নতুন প্রোজেক্ট ক্রিয়েট করব এর পর আমরা একটি প্রোজেক্ট url পাব।

####  ২। git remote add origin url
এর পর আমাদের terminal এ গিয়ে git remote add origin url দিতে হবে।
![Link](https://github.com/Emran04/bitmb22/week1/day-2/screenshots/Screenshot_5.jpg)
####  ৩। git push -u  origin master
![Link](https://github.com/Emran04/bitmb22/week1/day-2/screenshots/Screenshot_6.jpg)
এটি দিয়ে আমাদের প্রোজেক্ট সার্ভার এ আপ হয়ে গেল।

আবার আমরা যদি আমাদের প্রোজেক্ট নতুন কোন জায়গায় নামাতে চাই তাহলে আমরা ব্যবহার করব 

- git clone url

নতুন কাজ আপডেট নিতে

- git pull origin master

Summary:

আসলে তিনটা কমান্ড জানলে আমরা মোটামুটি কাজ করতে পারব।
* ১। git commit
* ২। git push
* ৩। git pull

