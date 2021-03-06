# ল্যাঙ্গুয়েজ ব্যাসিকস

## পিএইচপি কিভাবে কাজ করে?

পিএইচপি ইনজিন পিএইচপি ফাইল পড়ে লাইন বাই লাইন কোড এক্সিকিউট করে এবং আউটপুট দেয় । পিএইচপি ট্যাগের মধ্যে থাকা সব কোডই এই ইনজিনটি প্রসেস করে । প্রত্যেকটি ইনস্ট্রাকশন এর পর সেমিকোলন ব্যবহার করা হয় । সেমিকোলন দেখে পিএইচপি বুঝে নেয় তার বর্তমান কাজটি কোথায় এসে শেষ হবে ।

## পিএইচপি ট্যাগ

যে কোন পিএইচপি ফাইল শুরুই করতে হয় বিশেষ একটি ট্যাগ ব্যবহার করে । এই ট্যাগটি দেখেই পিএইচপি ইনজিন বুঝতে পারে যে এই জায়গা থেকে পিএইচপি কোড শুরু । তখন সে ঐ ট্যাগের মধ্যবর্তী অংশ লাইন বাই লাইন এক্সিকিউট করে । আবার ট্যাগ শেষ হয়ে গেলে সে ধরে নেয় তার কাজ শেষ, আবার ট্যাগ না আসা পর্যন্ত ফাইলে যা আছে তা ঠিক তেমনভাবেই আউটপুট দিয়ে দেয় ।

পিএইচপি ট্যাগ শুরু করতে হয় `<?php` লিখে আর শেষ হয় `?>` লিখে । ফাইলটিতে যদি শুধু পিএইচপি কোডই থাকে তবে ট্যাগ ক্লোজ না করলেও সমস্যা হয় না । তবে যদি আমরা পিএইচপি দিয়ে ডাইনামিক প্রসেসিং এর পাশাপাশি কিছু স্ট্যাটিক অংশও রাখতে চাই সেক্ষেত্রে আমরা পিএইচপি ট্যাগ ওপেন এবং ক্লোজ করে নির্ধারন করে দিতে পারি কোন অংশটুকু ডাইনামিকালি পিএইচপি জেনারেট করবে আর কোন অংশ সবসময়ই একই থাকবে ।

যেমন:

```text
<p>This is going to be ignored by PHP and displayed by the browser.</p>
<?php echo 'While this is going to be parsed.'; ?>
<p>This will also be ignored by PHP and displayed by the browser.</p>
```

এখানে আমরা প্রথমে এইচটিএমএল আউটপুট করলাম, এরপর একটা পিএইচপি ব্লক তারপর আবার আগের মতই এইচটিএমএল ।

## কমেন্টস

কমেন্টস হলো কোড এর সেই অংশ যেটা পিএইচপি ইনজিন ইগনোর করে যায় । কমেন্টস এ কোন ইনস্ট্রাকশন থাকে না । মূলত কোড এ কমেন্ট করা হয় ছোট ছোট নোট আকারে । এই নোটগুলো কোড এর বিভিন্ন বিষয় ব্যখ্যা করে । যেমন একটি ভ্যারিয়েবল কি কাজ করে এটা আমরা ঐ ভ্যারিয়েবল এর পাশে কমেন্ট আকারে লিখে দিতে পারি ।

পিএইচপিতে ৩ ধরনের কমেন্টস করা সম্ভব:

```php
<?php

$name = "masnun"; // সিঙ্গল লাইন কমেন্ট - দুইটা স্ল্যাশ ব্যবহার করা হয় 

/* মাল্টি লাইন কমেন্ট - 
স্ল্যাশ এর পরে স্টার বা এ্যাস্টেরিস্ক দিয়ে শুরু হয় আবার একইভাবে শেষ হয় - শুধু স্ল্যাশ আর স্টারের সিরিয়াল টা বিপরীত */ 

$age = 75; # একটা হ্যাশ ব্যবহার করে শেল স্টাইলে সিঙ্গল লাইন কমেন্ট করা যায়
```

সিঙ্গল লাইন কমেন্ট এর শুরু থেকে লাইনের শেষ পর্যন্ত কমেন্ট হিসেবে বিবেচিত হয় । মাল্টিলাইন কমেন্ট সাধারনত একাধিক লাইন জুড়ে হয় । তবে কমেন্টের শুরু \(`/*`\) আর শেষ \(`*/`\) এক লাইনেও হওয়া সম্ভব ।

