---
description: Auto Scaling and Spot Instance with auto assign EIP use case
---

# Feel the power of AutoScaling and Spot Instances

ဒီသင်္ကြန်ပိတ်ရက်မှာ အပြင်လည်းမထွက်ရတော့ ပျင်းပျင်းနဲ့ ဂိမ်းဆာဗာလေးတစ်ခုလုပ်ဖို့ စဉ်းစားမိရင်ကနေ ကိုယ့်ပိုက်ဆံနဲ့ကိုယ်လုပ်မှာဆိုတော့ တွက်ချေလည်းကိုက်ရမယ် Server ကိုလည်း [**Uptime 99.5%** ](https://uptime.is/99.5) ****လောက်ပေးချင်တယ်ဆိုပြီး Infra ပိုင်းလေးနည်းနည်းစဉ်းစားကြည့်ပြီး လုပ်ဖြစ်တာလေးကို ဝေမျှလိုက်ရပါတယ်။ 

ဒီနေရာမှာ ကျွန်တော့်အနေနဲ့ က လိုအပ်တာတွေရှိတယ်။ အဲ့ဒါတွေကို အရင်စဉ်းစားလိုက်တယ်။ ဘာလိုမလဲဆိုရင် ထုံးစံအတိုင်း အရင်ဆုံး Infrastructure requirement  အရ Virtual Private Cloud \( VPC \) တစ်ခုကို Public / Private Subnets တွေနဲ့ တည်ဆောက်လိုက်တယ်။ Public / Private Subnets ဆောက်တာက ဘာအတွက်လဲဆိုတော့ အရင်ဆုံးဘာမှမရှိသေးတဲ့ Infrastructure မှာ Network လိုလို့ပါ။ Network Diagram အရဆိုရင်တော့ အောက်မှာပြထားတဲ့ပုံထဲကလိုမျိုးပေါ့ဗျာ ။ ပြီးတော့ Web Server နဲ့ Application Server အပြင် ကျွန်တော်သုံးချင်တဲ့ထဲမှာ Database Server တစ်ခုသုံးဖို့လိုလို့။ Best Practices ဆိုတာထပ်လည်း Database Server လိုမျိုးက Public Subnet မှာမထားသင့်ထဲမှာပါတယ်။  Best Practices အရလည်း အဆင်ပြေတယ်။  အဆင်မပြေတာက တစ်ခုပဲ။ ဘာလဲဆိုတော့ NAT Gateway အတွက်ပိုက်ဆံထပ်ကုန်တာပါ။ အဲ့နေရာမှာ Private Subnet က Internet ကို ထွက်ဖို့အတွက် [NAT Gateway](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html#nat-gateway-basics) လိုတယ်။ ဒီနေရာမှာ စျေးသက်သာချင်ရင် Web , App, Database သုံးခု စလုံးကို Public Subnet မှာထားပြီးလုပ်လိုက်ရင်လည်း အဆင်ပြေတယ်။ အဲ့ကြရင် NAT Gateway ဖိုးမကုန်တော့ဘူး။ ဘယ်လိုမှဖြစ်မယ်ဆိုတာမျိုးတော့ မရှိပါဘူး ။ 

![Network Diagram with NAT Gateway ](../.gitbook/assets/nat-gateway-diagram.png)

ကျွန်တော်ကတော့ Web နဲ့ Application Server ကို Public Subnet မှာထားပြီးတော့ Database ကိုတော့ Private Subnet ထဲပို့လိုက်တယ်။ VPC Setup ပြီးပြီဆိုရင်တော့ ကျွန်တော်တို့လိုချင်တဲ့ Game Server လုပ်ဖို့ Compute Instances \( EC2 \) ဘက်အပိုင်းကိုသွားလိုက်ရအောင်။  ကိုယ်သုံးချင်တဲ့  Tier ပုံစံကို တစ်ခုထပ်စဉ်းစားဖို့လိုပါမယ်။ ဘယ်ဟာကို ဘယ်လိုထားမှာလဲ 2 Tier လား 3 Tier လား ၊ ဘယ်နေရာမှာ ဘာသုံးမယ် စသည်ဖြင့်ပေါဗျာ။ ကျွန်တော်ကတော့ Web, App, Database သုံးခုမှာ Web နဲ့ App ကို Instance တစ်ခုတည်းသုံးလိုက်တယ်။ ပိုက်ဆံကုန်သက်သာအောင်လို့ပါ ;\)  Database Server ကိုတော့ AWS ရဲ့ Managed RDS ကိုမသုံးတော့ဘူး ဒီနေရာမှာ ကိုယ်တိုင် EC2 ကို Setup လုပ်ပြီး Manage လုပ်ပါမယ်။ အဲတော့ စုစုပေါင်းမှ EC2 Instance ၂ ခုပဲလိုပါတယ်။ 

အိုကေ အဲ့တော့ Application Server အတွက် အမြဲတမ်း Run နေအောင် နဲ့ အကုန်အကျလေးတော်တော်သက်သာအောင် EC2 AutoScaling နဲ့ Spot Instance ကိုတွဲသုံးပါမယ်။ အပေါ်မှာပြောခဲ့သလို ပဲ Uptime က 99.5% ရှိနေရမှာဖြစ်တဲ့အတွက် Server ကတစ်ခုခုဖြစ်သွားရင် ချက်ချင်းဆိုသလိုပြန်တက်လာပြီး Up and Running ဖြစ်နိုင်ဖို့ လိုပါတယ်။ အဲ့အတွက် AWS ရဲ့ [EC2 Auto Scaling ](https://aws.amazon.com/ec2/autoscaling/) သုံးရတာပါ။  စျေးသက်ဖို့အတွက်  နောက်တစ်ခုက [EC2 Spot Instance](https://aws.amazon.com/ec2/spot/) ပါ။ Spot Instance အကြောင်းကို အောက်က လင့် မှာလည်းလေ့လာလို့ရပါတယ်။ 

{% page-ref page="reduce\_cloud\_compute\_cost\_with\_ec2\_spot\_instance.md" %}



သူကတော့ EC2 Instance ရဲ့ Purchase Option တစ်ခုပါ ပုံမှန် Instance \( On-demand \) ထပ်များသောအားဖြင့် Average စျေးက 60-70% လောက်သက်သာပါတယ်။ နောက်တစ်ခုလိုအပ်တာကတော့ [Elastic IP](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html#eip-basics) ပါ။ သူကတော့ Auto Scaling မှာ EC2 Instance က တစ်ခုခုဖြစ်ပြီး Down သွားရင်သော်လည်းကောင်း Spot Instance နဲ့တွဲသုံးမှာဖြစ်တဲ့အတွက် Spot Instance ရဲ့ သဘောတရားအရ Spare Resource တွေမလောက်တော့ရင်ဖြစ်ဖြစ် ကိုယ့် EC2 Instance ကပျက်သွားမှာပါ။ အဲ့ဒီအခါကြရင် Auto Scaling နဲ့ EC2 Instance အသစ်တစ်ခုပြန်တက်လာတဲ့ အခါမှာ အရင်ကရှိခဲ့တဲ့ EC2 Instance ရဲ့ IPv4 IP Address ကပျက်သွားပြီးတော့ IP Address အသစ်တစ်ခုနဲ့ပြန်တက်လာမှာပါ။

{% hint style="info" %}
 ဒီမှာ ပြဿနာက အရင် EC2 Instance ရဲ့ IP Address ကသာ Domain နဲ့တွဲထားမယ်ဆိုရင် Instance အသစ်ပြန်တက်လာတဲ့အခါ်မှာ IP ပြောင်းသွားတဲ့အတွက် Access လုပ်တဲ့အခါမှာ အခက်တွေ့စေမှာဖြစ်ပါတယ်။ 
{% endhint %}

Elastic IP သုံးထားတဲ့အတွက် Auto Scaling Group မှာ EC2 Instance က အပေါ်မှာပြောခဲ့တဲ့ Case တစ်ခုခုကြောင့်က Down သွားတယ်ဆိုရင် အသစ်တက်လာမဲ့ EC2 Instance မှာ Elastic IP က auto assign လုပ်သွားမှာဖြစ်တဲ့အတွက် စိတ်ပူစရာမလိုတော့ပါဘူး။ ထပ်ဆောင်းပြောရရင် ကျွန်တော်တို့ အခု use case မှာဆိုရင် Spot Instance သုံးထားတဲ့အတွက် ပိုတောင်လိုအပ်ပါသေးတယ်။ 







