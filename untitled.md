# A brief History of AWS

## tags: `Fundamental` `AWS` `Introduction`

နိုင်ငံတကာတွင် Cloud Computing ရေစီးကြောင်းတိုးတက်လာသည်နှင့် တပြိုင်နက် Cloud Computing စနစ်ကို ထောက်ပံ့ပေးနေသော provider များပေါ်ထွက်လာခဲ့ပါသည်။ Amazon, Google, Microsoft ကဲ့သို့သော Company ကြီးများနှင့်အတူ IBM, Alibaba, Century Link, Rackspace အစရှိသော Company ကြီးများမှလဲ Cloud Platforms များတည်ဆောက်ပြီး Service Provider အနေဖြင့် ရပ်တည်လျက်ရှိကြပါသည်။ ထို Company ကြီးများအနက် Amazon မှ AWS Cloud သည် 2017 ခုနှစ် Gartner Survey အရ Market Leader Cloud Provider အဖြစ်ထိပ်ဆုံးမှ ရပ်တည်လျှက်ရှိပြီး Public Cloud Service အားအဓိက support ပေးလျှက်ရှိပါသည်။ AWS Cloud သည် 2017 စစ်တမ်းများအရ 17.46 Billion Annual Revenue အဖြစ် ဝင်ငွေအများဆုံး Cloud provider အဖြစ်ရပ်တည်နေပါသည်။ အထူးသဖြင့် လက်ရှိ AWS သည် Public Cloud Computing Provider ဖြစ် IAAS, PAAS, SAAS အစရှိသော Cloud Service များကိုထောက်ပံ့ပေးလျှက်ရှိသော Provider တစ်ခုအဖြစ်သာမက Hybrid Cloud Setup များကို Support ပေးနေသော Service များရှိသော Provider တစ်ခုလည်းဖြစ်ပါသည်။

![](https://i.imgur.com/oR5YqIJ.jpg)

AWS သမိုင်းကြောင်းများအား ပြန်ကြည့်ရမည်ဆိုလျှင် ကနဦး AWS Platform ကို 2002 July တွင် Service အနည်းငယ်မျှဖြင့် စတင်ခဲ့ပြီး 2003 နှောင်းပြီးကာလတွင် Chris Pinkam and Benjamin Black တို့မှစနစ်တကျ Reformulated ပြုလုပ်ခဲ့ပြီး 2004 November တွင် AWS ၏ပထမဦးဆုံး Service ဖြစ်သည့် SQS ကို Public Launch ပြုလုပ်ခဲ့ပါသည်။ ထို့နောက် AWS ၏ဒုတိယမြောက် Service ဖြစ်သည့် Elastic Compute Cloud \(EC2\) ကို တောင်အာဖရိကနိုင်ငံ ကိတ်တောင်းမြို့တွင် Develop ပြုလုပ်ပြီး တရားဝင် Publice Relaunch အား 2006, March14 တွင်

\(1\)S3 \(2\)SQS \(3\)EC2 အစရှိသော Initial Service \(3\) မျိုးဖြင့် စတင်ခဲ့ပါသည်။

Andy Jassy က တော့ 2006 တွင် Vice President အနေဖြင့် တာဝန်ထမ်းဆောင်ခဲ့ပြီး 2016 တွင် CEO အဖြစ်ယနေ့တိုင် ဆောင်ရွက်လျှက်ရှိပါသည်။ ယနေ့ခေတ် Market တွင် Service ပေါင်းတစ်ရာကျော်ဖြင့် Leading Cloud Computing Provider အဖြစ်ရပ်တည်နေပြီးဖြစ်ပါသည်။

![](https://i.imgur.com/jZh3QBj.jpg)

ယနေ့ခေတ် AWS Core Services များတွင်အရေးကြီးပြီးအသုံးများသော Services အချို့အားလေ့လာကြည့်ရမည်ဆိုလျှင် Compute,Storage, Database, Networking, Security and Management များဖြစ်ကြပါသည်။ထို့အပြင် AWS တွင် အခြားသော Services များ၊ နောက်ဆုံးပေါ် Technology Services များလည်းရှိနေပါသေးသည်။ အထူးသတိပြုရမည်ဆိုလျှင် ထို Services အားလုံးကို တပြိုင်နက်ထဲ အသုံးပြုနိုင်ဖို့အတွက် ခက်ခဲကောင်းခက်ခဲနိုင်ပါသည်။ မိမိ Organization, Company ၏ လိုအပ်ချက်အပေါ်မူတည်ပြီး အသုံးပြုသော Services အမျိုးအစားများလည်း ကွဲပြားသွားနိုင်ပါသည်။ ဆိုလိုသည်မှာ Services အားလုံးကိုတပြိုင်တည်းနှင့် အသုံးပြုရန် မလိုအပ်ပါ။ ယေဘူယျအားဖြင့် Services ၏ အလုပ်လုပ်ပုံ၊အသုံးပြုပုံ များကိုသိရှိရန် သာလိုအပ်ပါသည်။ မိမိအသုံးပြုမည့် Services ၏သဘောတရားများကို နားလည်ပါက Services ၏ Documentation များကို အခြေခံ၍ Implement ပြုလုပ်နိုင်ပါသည်။ သို့ရာတွင် AWS Cloud ကိုစတင်အသုံးပြုမည်ဆိုပါက AWS ၏အဓိကအသုံးများဆုံးဖြစ်တဲ့ Core Services များအား သိရှိနားလည်ရန်တော့လိုအပ်ပါသည်။

![](https://i.imgur.com/tKTXptW.jpg)

AWS ၏ အဓိက Core Services များကတော့

**Compute** EC2 \(Elastic Compute Cloud\) ECS \(Elastic Container Service\)

**Storage** S3 \(Simple Storage Service\) EBS \(Elastic Block Storage\) EFS \(Elastic File System\)

**Database** RDS DynamoDB Elasticache Redshift

**Networking** VPC \(Virtual Private Cloud\) Route 53

**Security** IAM \(Identity and Access Management\)

**Management** Cloud Watch Cloud Trail Config

အစရှိသော Service တစ်ခုချင်း၏ ရည်ရွက်ချက် အလုပ်လုပ်ဆောင်ပုံများ ကွဲပြားကြပါသည်။

ကျွန်တော်တို့ နောက်ထပ်ပို့စ်များတွင် တစ်ခုချင်းစီ၏ အလုပ်လုပ်ပုံ၊ ရည်ရွယ်ချက်များကို အချိန်ရရင် ရသလိုတင်ပေးသွားပါမည်။ အခုလောလောဆယ်တော့ AWS ကဘာလဲ? သမိုင်းကြောင်းနှင့် သူ့ရဲ့ Ecosystem/Core Services တွေက ဘာတွေရှိလဲ အစရှိတဲ့ အကြောင်းအရာများကို ဤစာစုကလေးက ပေးနိုင်လိမ့်မယ်လို့ ကျွန်တော်မျှော်လင့်မိပါတယ်။

[AWS User Group Myanmar ](https://www.facebook.com/awsugmm/)

