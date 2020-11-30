---
description: >-
  A microservice which can be run on AWS Lambda to monitor and check websites
  and metric value of website status code and response time taken per request is
  sent to AWS CloudWatch.
---

# Using AWS Lambda to monitor websites

ဒီတစ်ခေါက်မှာတော့ AWS Lambda ကိုအသုံးပြုပြီး Website Status Monitoring Service လေးတစ်ခုကို အသုံးချပုံလေးကို  ပြောပြသွားမှာဖြစ်ပါတယ်။ 

AWS Lambda Function ကလုပ်ဆောင်ပေးမဲ့ဟာ လေးကတော့ ရိုးရိုးရှင်းရှင်းပါပဲ။ ကျွန်တော်တို့ မြင်တွေ့နေကြ Website Status Check လိုမျိုးပဲ မိမိတို့ Website ရဲ့ Response အပေါ်မူတည်ပြီး Status Code နဲ့ Time Taken တို့ကို output အနေနဲ့ပြန်ပေးမှာဖြစ်ပါတယ်။ Output ကိုမှ ကျွန်တော်တို့ အနေနဲ့ AWS ရဲ့ CloudWatch Service ဆီကို Metric အနေနဲ့ ပို့ဆောင်ပေးမှာပါ။ 

ထိုမှ တစ်ဆင့် ရရှိလာတဲ့ Metric Values တွေကိုကြည့်ပြီး CloudWatch Alarms တွေမှ တစ်ဆင့် AWS Simple Notification Service \( SNS \) တို့ကို ပေါင်းစပ်အသုံးပြုကာ ကျွန်တော်တို့ရဲ့ Website က အဆင်ပြေနေရဲ့လား မပြေဘူးလားဆိုတာ ကိုသိရှိအောင်ပြုလုပ်နိုင်မှာပဲဖြစ်ပါတယ်။

ဒီ ပို့စ်ရေးဖို့ အတွက် Microservice လေးကို Develop လုပ်ပေးထားတာကတော့ [**ကိုအောင်အေးသန်း** ](https://github.com/AungAyeThan)ပဲဖြစ်ပါတယ်။  

နောက်ပြီးတော့ အသုံးပြုမဲ့ Tech Stack ကလည်းရှင်းပါတယ်။ 

{% embed url="https://github.com/AungAyeThan/monitoring-service" %}

Source Code အနေနဲ့ကတော့ Golang နဲ့ရေးထားတဲ့ monitoring service တစ်ခုဖြစ်ပါတယ်။ Local မှာပဲအသုံးပြုနိုင်သလို  AWS Lambda နဲ့လည်းတွဲဖက်ပြီး အသုံးပြုနိုင်ပါတယ်။ 

AWS ဘက်အခြမ်းမှာ လိုအပ်တဲ့ Service ဆိုရင်တော့ - 

* AWS IAM
* AWS Lambda
* AWS CloudWatch
* AWS EventBridge \( Formerly CloudWatch Event \)
* AWS Simple Notification Service \( SNS \)

တို့ပဲဖြစ်ပါတယ်။ 

ကျွန်တော်တို့အခု ကိစ္စမှာတော့ AWS Lambda Function နဲ့တွဲပြီးအသုံးပြုပါမယ်။ အရင်ဆုံးအနေနဲ့ ကျွန်တော်တို့ Service က Lambda ပေါ်မှာ Run ပြီးတော့ CloudWatch ကို Metric Data တွေနဲ့ Log တွေ ပို့မှာဆိုတော့ Lambda ကနေ CloudWatch ကို Right Access ရှိဖို့လိုပါတယ်။  ဒီတော့ ကျွန်တော်တို့က **AWS IAM Custom Policy** တစ်ခုကို create လုပ်ပြီး IAM Role နဲ့တွဲပါမယ်။ ဒီနေရာမှာ **AWS IAM Role** ကို အသုံးပြုချင်းက မှန်ကန်တဲ့ ရွေးချယ်မှပဲဖြစ်ပါတယ်။ **ဘာလို့လဲဆိုတော့ Best Practices တွေအရ ကျွန်တော်အနေနဲ့ AWS Service တွေအချင်းချင်း communicate လုပ်တဲ့နေရာမှာ access တွေလိုအပ်လာတဲ့ အခါမှာ အကောင်းဆုံးဖြစ်လို့ပါပဲ။** 

**ဒီတော့ AWS IAM Custom Policy တစ်ခု Create လုပ်ဖို့အတွက်** 

```text
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "AllowMeticAlarmCreation",
            "Effect": "Allow",
            "Action": [
                "cloudwatch:PutMetricAlarm",
                "cloudwatch:PutMetricData"
            ],
            "Resource": "*"
        },
        {
            "Sid": "AllowLogCollection",
            "Effect": "Allow",
            "Action": [
                "logs:PutLogEvents",
                "logs:CreateLogStream",
                "logs:CreateLogGroup"
            ],
            "Resource": "arn:aws:logs:*:*:*"
        }
    ]
}
```





 ****

\*\*\*\*

\*\*\*\*

