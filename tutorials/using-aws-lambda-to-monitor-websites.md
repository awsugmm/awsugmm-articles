---
description: >-
  A microservice which can be run on AWS Lambda to monitor and check websites
  and metric value of website status code and response time taken per request is
  sent to AWS CloudWatch.
---

# Using AWS Lambda to monitor websites

ဒီတစ်ခေါက်မှာတော့ AWS Lambda ကိုအသုံးပြုပြီး Website Status Monitoring Service လေးတစ်ခုကို အသုံးချပုံလေးကို  ပြောပြသွားမှာဖြစ်ပါတယ်။ 

AWS Lambda Function ကလုပ်ဆောင်ပေးမဲ့ဟာ လေးကတော့ ရိုးရိုးရှင်းရှင်းပါပဲ။ ကျွန်တော်တို့ မြင်တွေ့နေကြ Website Status Check လိုမျိုးပဲ မိမိတို့ Website ရဲ့ Response အပေါ်မူတည်ပြီး Status Code နဲ့ Time Taken တို့ကို output အနေနဲ့ပြန်ပေးမှာဖြစ်ပါတယ်။ Output ကိုမှ ကျွန်တော်တို့ အနေနဲ့ AWS ရဲ့ CloudWatch Service ဆီကို Metric အနေနဲ့ ပို့ဆောင်ပေးမှာပါ။ 

ထိုမှ တစ်ဆင့် ရရှိလာတဲ့ Metric Values တွေကိုကြည့်ပြီး CloudWatch Alarms တွေမှ တစ်ဆင့် AWS Simple Notification Service \( SNS \) တို့ကို ပေါင်းစပ်အသုံးပြုပြီး ကျွန်တော်တို့ရဲ့ Website က အဆင်ပြေနေရဲ့လား မပြေဘူးလားဆိုတာ ကိုသိရှိအောင်ပြုလုပ်နိုင်မှာပဲဖြစ်ပါတယ်။

ဒီ ပို့စ်ရေးဖို့ အတွက် Microservice လေးကို Develop လုပ်ပေးထားတာကတော့ [**ကိုအောင်အေးသန်း** ](https://github.com/AungAyeThan)ပဲဖြစ်ပါတယ်။  

နောက်ပြီးတော့ အသုံးပြုမဲ့ Tech Stack ကလည်းရှင်းပါတယ်။ AWS Lambda Function  

