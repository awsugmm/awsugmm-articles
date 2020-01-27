---
description: Overview of AWS Services' Pricing and Cost Optimization
---

# Cost Optimization on AWS Cloud - Part 2

ကျွန်တော်တို့ အရင် [**article**](https://blog.awsugmm.org/cost_and_billing/cost_optimization) မှာတော့ Cost Optimize လုပ်ဖို့လိုအပ်တဲ့ အရာလေးတွေနဲ့ Billing သဘောတရားများကို အကြမ်းဖျင်းအနေနဲ့ ပြောပြီးပြီဆိုတော့ ဒီ Part 2 မှာနောက်ထပ် အကြောင်းအရာလေးတွေ ကိုထပ်ပြီးဆွေးနွေးကြရအောင်ဗျာ။ 

{% hint style="info" %}
Cost Optimization နဲ့ ပတ်သက်တဲ့ ဆက်စပ်နေတဲ့ နောက်ထပ်အကြောင်း အရာတစ်ခုက တော့ Right Sizing   ပါ။ Right Sizing ပြုလုပ်တာက ကိုယ့် ရဲ့ infrastructure cost ကို သိသိသာသာသက်သာစေပါတယ်။ 
{% endhint %}

AWS မှာ Right Sizing လုပ်မယ်ဆိုရင်တော့ ကျွန်တော်တို့ အနေနဲ့ ရှေ့ article မှာပြောခဲ့သလိုတွေပြုလုပ်နိုင်ပါတယ်။ နောက်ပြီးတော့ ကျွန်တော်တို့ အနေနဲ့ AWS က သူ Ecosystem မှာ Right Sizing ပြုလုပ်နိုင်ဖို့ ထုတ်ပေးထားတဲ့ Tools တွေကို သုံးပြီးလည်းပြုလုပ်နိုင်ပါတယ်။ 

* ပထမဆုံးတစ်ခုက **AWS Cost Explorer** ပါ။ ဒီကောင်လေးကတော့ ကိုယ်သုံးနေတဲ့ ဘယ် resource တွေက ဘယ်လောက်တော့ ကုန်ကျနေတယ်ဆိုတာကိုပြန်ကြည့်လို့ရပါတယ်။ နောက်ပြီး လွန်ခဲ့တဲ့ ၇ရက် ၁လ ၂လ ကကိုယ်သုံးခဲ့တဲ့ resource တွေရဲ့ utilization ကိုအခြေခံပြီး ဘယ် resource တွေကတော့ reserved လုပ်သင့်တယ် တစ်ချို့ဆိုလည်း Down Sizing လုပ်သင့်တယ် ဘာညာစတာတွေကို ပြပေးထားတဲ့ အတွက် ကျွန်တော့်တို့ က သူ့ tools က ထုတ်ပးတဲ့ Data တွေနဲ့ ကိုယ့် environment , organization ကလိုချင်တဲ့ လိုအပ်တဲ့အရာတွေနဲ့ ကိုက်ညီတယ်ဆိုရင် ကျွန်တော်တို့က လွယ်လွယ်ကူကူပဲ Cost Optimize ပြုလုပ်နိုင်မှာပါ။ 

![AWS Cost Explorer](../.gitbook/assets/screenshot-from-2020-01-27-16-59-31.png)

* နောက်ထပ်တစ်ခုကတော့ AWS Trusted Advisor ပါ။ **သူကတော့ ကိုယ့် AWS account ရဲ့ Support Plan ပေါ်မူတည်ပြီး သုံးလို့ရတဲ့ Features တွေတော့ ကွာခြားချက်ရှိပါတယ်။** ကိုယ်တော်တို့ ကတော့ Business Plan ယူထားတဲ့ အတွက် Feature အစုံသုံးလို့ရနေပါတယ်။ Trusted Advisor ထဲက Cost Optimization Checks ဆိုတဲ့ feature ရဲ့ အကူအညီနဲ့လည်း Low utilization EC2 Instance တွေ Idle ဖြစ်နေတဲ့ RDS Instance တွေ မသုံးပဲ ထားမိနေတဲ့ Resources တွေကို ပြပေးပါတယ်။ 

![AWS Trusted Advisor](../.gitbook/assets/screenshot-from-2020-01-27-17-10-47.png)

* နောက်ထပ်တစ်ခုကတော့ AWS Compute Optimizer ဆိုတဲ့ Tools လေးပါ။ သူကတော့ AWS ရဲ့ Service တစ်ခုအနေနဲ့ဖြစ်လာတာတော့ မကြာသေးပါဘူး။ ဒါပေ့မယ် တော်တော်လေးအသုံးဝင်တဲ့ Tool တစ်ခုပါ။ Compute Optimizer ဆိုတဲ့ အတိုင်းပဲ လက်ရှိမှာတော့ Compute Resource တွေထဲကမှာ AWS EC2 Instance နဲ့ Autoscaling Group တွေအတွက်ပဲ အသုံးပြုလို့ရနိုင်ပါသေးတယ်။ နောက်ထပ်တစ်ခုက အခုအချိန်မှာတော့ AWS Region ၅ ခုမှာပဲ အသုံးပြုနိုင်ပါသေးတယ်။ 

![AWS Compute Optimizer](../.gitbook/assets/screenshot-from-2020-01-27-17-27-29.png)

ကျွန်တော့်ကိုယ်ပိုင် အမြင်နဲ့ပြောရရင်တော့ ဒီ tools လေးတွေကတော်တော် အထောက်အကူပြုပါတယ်။ ကျွန်တော်တို့အနေနဲ့ Instance တစ်လုံး နှစ်လုံးဆိုရင်တော့ tools တွေ အကူအညီမယူပဲ ကိုယ့်ဘာသာကိုယ်တွက်လို့ရနိုင်ပါတယ်။ Server အလုံး တစ်ဆယ် နှစ်ဆယ် တစ်ရာ နှစ်ရာဖြစ်လာပြီဆိုရင်တော့ ဒီ tools တွေရဲ့ အကူအညီနဲ့ မြန်မြန်ဆန်ဆန် Cost Optimized ပြုလုပ်နိုင်မှာဖြစ်ပါတယ်။ 

#### Reserved Instance

နောက်ထပ် Cost Optimize လုပ်နိုင်မဲ့ အချက်ကတော့ Reserved လုပ်ခြင်းပါ။ ဥပမာ ကျွန်တော်တို့ Gym မှာပိုက်ဆံပေးပြီးသွားဆော့သလိုပဲ တစ်နေ.ဆော့ရင် \( On-Demand \) ဆိုရင် စျေးတစ်မျိုး ၁နှစ်စာကြိုပေးပြီးဆော့မယ်ဆိုရင်စျေးတစ်မျိုး \(  AllUpFront \) ၁ နှစ်တော့ဆော့မယ် တစ်လချင်တစ်မျိုး \( NoUpfront \) ၁နှစ်တော့ ဆော့မယ် ၆လတစ်ဖြတ်ပေးမယ် \( PartialUpFront \) ဆိုတဲ့ သဘောတရားပါပဲ။ ဆိုလိုတာက ကိုယ့်ရဲ့ Infra အနေအထား မြွေဖားက ပြောင်းဖို့မရှိဘူး ဒါမှမဟုတ် တစ်နှစ်အတွင်းဒီ ဟာကို အပြီပြင်သုံးမယ်ဆို Reserved Instance က On Demand ထက်ပို စျေးသက်သာပါတယ်။ 









