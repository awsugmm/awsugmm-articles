---
description: Overview of AWS Services' Pricing and Cost Optimization
---

# Cost Optimization on AWS Cloud

ဒီနေ့မှာတော့ကျွန်တော်တို့ Amazon Web Services အသုံးပြုနေကြတဲ့သူတွေအတွက် အသုံးဝင်လောက်မဲ့ articleလေး တစ်ခုကိုရေးပေးချင်ပါတယ်။ ကျွန်တော်တို့ ရုံးတွေမှာ AWS သုံးကြတယ် Costတွေ ကလည်း တော်တော်လေးကုန် ကျနေတယ် ဘာတွေကကုန်နေမှန်းလည်း မသိဘူး Billing Console မှာတော့ပြနေတယ် ဘာတွေအတွက်ကဘယ်လောက် ဘယ်လောက်ကုန်နေတယ် ဒါပေမယ့် သူတို့ဘယ်လိုဘယ်လိုတွက်လိုက်လဲ မသိဘူးဖြစ်နေတယ်ဆိုရင် ၊ Cost တွေ ကအဆမတန်ကုန်ကျနေတယ်ဆိုရင်  အခု article လေး က သင့်အတွက် လက်ရှိကုန်ကျနေတဲ့ Cost တွေရဲ့ တွက်ချက်ပုံ အကြမ်းဖျင်းနဲ့ Optimization သဘောတရား များကို အနည်းနဲ့အများ နားလည် သဘောပေါက်ပြီး အထောက်အကူပြုလိမ့်မယ်လို့ ယုံကြည်ပါတယ်။ ဟုတ်ပြီ အဲ့တော့ စလိုက်ကြရအောင်။

ကျွန်တော်တို့ အနေနဲ့ ဘယ်လိုစလုပ်မလဲ

* အရင်ဆုံးကိုယ်က AWS ရဲ့ ဘယ် service တွေကို သုံးထားလဲသိရပါမယ်   
  ဥပမာ - ဘယ် Region မှာ ဘာ service ကိုသုံးထားလဲပေါ့ ၊ North Virginia \( us-east-1 \)

   မှာ EC2 သုံးထားတာလား Europe \( Paris - eu-west-3 \)မှာ RDS သုံးထားတာလား စသဖြင့်ပေါ့   

* ပြီးတော့ ကိုယ်သုံးထားတဲ့ service တွေရဲ့ pricing ကိုသေချာသိရပါမယ် ၊ ဒီမှာဘာပြသနာရှိလဲဆိုတော့ AWS က သူရဲ့ Region အလိုက် Service Pricing တွေက အများကြီးရှိတဲ့ အတွက်အကုန်တော့ ထည့်မပြောနိုင်တော့ပါဘူး။  ဥပမာအနေနဲ့ မြင်သာအောင်ပြောရမယ်ဆိုရင် North Virginia \( us-east-1 \) မှာ ရှိတဲ့ EC2 Pricing နဲ့ Singapore \( ap-southeast-1 \) မှာရှိတဲ့ EC2 Pricing က မတူပါဘူး။ 

![US East \( N. Virginia\) EC2 t3.medium price per hour](../.gitbook/assets/screenshot-from-2020-01-14-00-14-14.png)

![Asia Pacific  \( Singapore \) EC2 t3.medium price per hour](../.gitbook/assets/screenshot-from-2020-01-14-00-14-47.png)

ဒီပုံမှာကြည့်မယ်ဆိုရင် US East \( N. Virginia\) EC2 t3.medium price per hour က **$​0.0416** ပဲကျသင့်မှာဖြစ်ပြီးတော့ Asia Pacific \( Singapore \) EC2 t3.medium price per hour က **$0.0528** ကျသင့်မှာပါ။  တစ်ခြားသော Instance Type တွေလည်း ထိုနည်းလည်းကောင်းပါပဲ။ US East \( N. Virginia \) ကပိုသက်သာပါတယ်။ ဆိုလိုတာကတော့ ကျွန်တော်တို့တွေအနေနဲ့ ကိုယ်ရဲ့ company requirement  အရ Region အလိုက်စျေးနှုန်းတွေကို အကြမ်းဖျင်နားလည်ထားရပါမယ်။ ဒါဆိုဘာလို့ US East \( N. Virginia \) ကပိုသက်သာတာလဲဆိုရင် AWS ရဲ့ Default Region ဖြစ်တာလည်း တစ်ကြောင်း၊ များပြားတဲ့ Customer တွေကို Service ပေးနိုင်ဖို့ Resource များများရှိတာရယ်၊ Physical Datacenter တွေအတွက် လိုအပ်တဲ့ Electrical Power ရပုံခြင်းမတူတာရယ် နိုင်ငံရဲ့ Tax rule ဘာညာအနေအထားတွေ မတူညီတာရယ်ကြောင့်လို့ ယေဘုယျ ဆိုနိုင်ပါတယ်။

* 




