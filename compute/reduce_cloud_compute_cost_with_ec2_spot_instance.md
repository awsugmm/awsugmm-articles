---
description: AWS Spot Instance Introduction with use case
---

# Reduce cloud compute cost with EC2 Spot Instance

![](https://i.imgur.com/jhLoKY2.png)

EC2 Spot Instance လို့ ပြောလိုက်တာနဲ့ တချို့က AWS ရဲ့ Pricing Model တစ်မျိုး or အသုံးမလို ပိုနေတဲ့ Compute Capacity တစ်ခု ခဏလေးသုံး အချိန်မရွေးပြန်ယူမှာ ဆိုတဲ့ အတွေးတွေနဲ့ သုံးဖို့ ဒွိဟဖြစ်နေကြတာတွေ့ရပါတယ် အမှန်တကယ်တော့ Spot instance က သူ့ နေရာသူ Usecase နဲ့ မှန်မှန်ကန်ကန်အသုံးပြု အသုံးချမယ် ဆို မိမိ Infrastructure ရဲ့ compute cost လျော့ချနိုင်မည့်အပြင်မှာ Application HA ပါ တခါ တည်း Setup ချ လို့ ရပါတယ်။ ကဲ ဒါဆို Spot Instance ကို ဘယ်လိုသုံးမလဲ ဘယ်နေရာမှာသုံးမလဲဆိုတာ ကြည့်လိုက်ရအောင်..အဲ့တာတွေ မပြောခင် Spot Instance က ဘာလဲ ဘာလို့ အရမ်းစျေးသက်သာလဲ ဆိုတာ တချက် သုံးသပ်ကြည့်ရအောင်ဗျာ ...

ပထမဦးဆုံး Spot Instance ဆိုတာ AWS ရဲ Spare compute capacity လိုဆိုနိုင်ပါတယ် AWS ရဲ့ ပိုနေတဲ့ compute resource တွေကို လေလံပုံစံနဲ့ ပြန်လည် ငှားရမ်းတဲ့သဘောပါ ဆိုတော့ လေလံပုံစံဆိုတော့ ကိုယ်ပေးတဲ့စျေးက များနေရင် ရမယ် နည်းသွာမယ်ဆို မရတော့ဘူးပေါ့၊ ဒါဆို ဘာဖြစ်မလဲ ပြန်သိမ်းသွားပီး တခြားပိုပေးတဲ့ လူဆီ ကို ငှားရမ်းလိုက်မှာပါ နောက်ပီး EC2 Demand များလာတဲ့အခါပြန်ယူသွားမယ် ဒါပေမဲ့ မစိုးရိမ်ပါနဲ့ ကိုယ်က တခြားကျန်နေတဲ့ resource တွေကို ရယူလို့ရပါသေးတယ်၊ ရရှိခဲ့ရင်လည်း အရမ်းကိုစျေးသက်သာတဲ့ စျေးနဲ့ရမှာ ပါ .Official Documentation မှာ ပြောထားတာ က On-Demand စျေးထက် 90% လောက်ထိသက်သာတယ် ပြောထားပါတယ်။ ဒါဆို Spot instance တွေကို ဘာကြောင့် ဘယ်လိုနေရာမျိုးတွေ မှာ အသုံးပြုရမှာ လဲ မေးစရာရှိလာပါတယ်၊

AWS Spot Instance တွေကို အထူးသဖြင့် အရေးမကြီးတဲ့ Workloads, Compute Capacity များများလိုပီး ခဏပဲ run မည့် Usecase ဥပမာ Bigdata Batch Process တွေ, Stateless Application တွေကို Auto Scale လုပ်တဲ့နေရာ, CI/CD workload နဲ့ အခြားသော Container Cluster Nodes provision workload တွေမှာ အသုံးပြုနိုင်ပါတယ်။ အထူးသဖြင့် ပျက်သွားလည်းမလွမ်းလောက်ပါဘူးဆိုတဲ့ နေရာတွေမှာအသုံးပြုနိုင်ပါတယ်။ နောက်ပီး Microservices ရဲ့ Cattle analogy အတိုင်း Dynamic infrastructure တစ်လုံးမရှိတစ်လုံး ရော့ သွားစမ်း နောက်တစ်လုံးလာဆိုပီး စျေးသက်သက်သာသာနဲ့ ဖောဖောသီသီသုံးချင်တဲ့ သူများ အတွက်ဆို Spot Instance က ကိုက်ညီပါတယ်။

![](https://i.imgur.com/DB7RE3o.png)

ပုံမှာမြင်ရတဲ့ အတိုင်းဆိုရင် EC2 Instance T3.medium ရဲ့ On-demand price က $0.0528/hr ကျသင့်မှာဖြစ်ပြီးတော့ Spot Price နဲ့ဆိုရင်တော့ $0.0158/hr ပဲကျသင့်မှာဖြစ်ပါတယ်။ 70% လောက်ကိုသက်သာပါတယ်။ Instance Size ကိုမူတည်ပြီး စျေးနှုန်းတွေလည်း မတူနိုင်ပါဘူး။ တစ်ချို့ Instance Type တွေဆိုရင် 70%-90% လောက်ထိသက်သာပါတယ်။

![](https://i.imgur.com/mh3MDeQ.png)

ဒီပုံမှာပြထားတာကတော့ Saving Summary ပါ။ ကျွန်တော်သုံးထားတာကတော့ T3.medium instance ၂လုံးကို ၃ရက်လောက်သုံးထားပါတယ်။ On-demand Price ဆိုရင်တော့ $6.49 လောက်ကျသွားမယ်ပေါ့နော်။ Spot Instance နဲ့သုံးမယ်ဆိုရင်တော့ ၃ရက်စာ ၇၂နာရီကို $1.94 လောက်ပဲကျပါတယ်။ ဒါ့အပြင် စျေးအရမ်းသက်သာနေလို့ On-demand Instance တွေလို Performance ကောင်းရဲ့လား၊ Specification ရောလျော့သွားလား ဘာညာစတာတွေ ပူစရာမလိုပါဘူး၊ Spot Instance ကလည်း On-Demand Instance တွေကိုသုံးသလိုပဲ အလွယ်တစ်ကူအသုံးပြုလို့ရပါတယ်။ ပြောင်းလဲလာတဲ့ Spot Instance Pricing Model အရလည်း အရင်လို Bidding တွေအတွက် ခေါင်းရှုပ်စရာမလိုတော့ပါဘူး။

ဒီလောက်ဆိုရင်တော့ EC2 Spot Instance အကြောင်းကို အနည်းနဲ့အများနားလည်သဘောပေါက်လောက်ပြီထင်ပါတယ်။ နောက်ပိုင်း Article တွေမှာလည်း Spot Instance နဲ့ပတ်သက်တဲ့ Spot Block, Spot Fleet နဲ့ Best Practices တွေကိုရေးသားဦးမှာဖြစ်လို့ ဆက်လက်အားပေးကြပါဦးခင်ဗျာ။

လေးစားလျက် [AWS User Group Myanmar](https://www.facebook.com/awsugmm)

