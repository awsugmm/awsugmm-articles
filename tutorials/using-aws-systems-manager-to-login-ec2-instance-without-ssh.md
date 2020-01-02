# Using AWS Systems Manager to login EC2 instance without SSH

AWS Ec2 instance တစ်လုံး စဆောက်လိုက်ပီးတာနဲ.အဓိကပထမဆုံးလုပ်တာက ဆောက်ထားတဲ့ instance ထဲLogin ဝင်ပီး Manage လုပ်တာပါပဲ။ ဆိုတော့ Login ဝင်မယ်ဆို အဓိက Windows ဆို RDP Protocol , Linux ဆို SSH နဲ့ဝင်ကြရပါတယ်။ခုtutorialလေးက Linux instance ကို လုပ်ပြမှာဆိုတော့ SSH ပေါ့။

AWS Ec2 Linux instance တစ်လုံးကို စတင်ဝင်ရောက်ဖို.ဆိုရင် 1. Pem Key \(Private Key\) တစ်ခု 2. AWS Security Group ကနေ SSH Port 22 ကို Allow လုပ်ပေးဖို.လိုအပ်ပါတယ်။

ခုလုပ်ပြမှာလေးက AWS Ec2 instance တစ်လုံးကို Login ဝင်တဲ့အခါ SSH မလိုပဲ AWS ရဲ့ Service တစ်ခုဖြစ်တဲ့ Systems Manager, Session Manager ကနေ Login ဝင်တဲ့ နည်းလမ်းလေးဖြစ်ပါတယ်။SSH မသုံးပဲ ဘာလို. AWS Systems Manager, Session Manager ကိုသုံးလဲ မေးစရာရှိလာပါတယ် ဘာလိုု.သုံးလဲ ဘာကြောင့်လဲဆိုရင် အဓိက အားဖြင့် ကျနော်အမြင်အရကော Blogs တွေမှာပြောထားတာက -

* SSH bastion Host မလိုတော့ဘူး။ \(စျေးသက်သာတာပေါ့နော်\) 
* SSH Key မလိုတော့ဘူး။
* No need to allow SSH in AWS Security Group \(AWS Security Group မှာ SSH Allow ဖို.မလိုတော့ဘူး\)\(အဲ့တာလေးတော့ကြိုက်တယ်\)
* နောက်ဆုံးတစ်ခုကတော့ Logs တွေကို AWS Cloudwatch Log groups ကနေ Default ကြည့်လို.ရတာပါပဲ။

အိုကေ စကြည့်လိုက်ရအောင် ...

ပထမဆုံးဘာမှ မစခင် ကျနော်တို. Systems Manager, Session Manager တွက် IAM Ec2 Role တစ်ခုဆောက်ပေးဖို.လိုပါတယ် \(Systems Manager ကနေ instance ကို access ရဖို.တွက်\)

ကျနော်တို.အောက်ကပုံမှာပြထားတဲ့အတိုင်း IAM Console ကနေ Role တစ်ခု create လုပ်ပါမယ်။

![](https://i.imgur.com/UqpcX68.png)

![](https://i.imgur.com/ionmWXV.png)

![](https://i.imgur.com/S83dAqE.png)

ထို.နောက် IAM Role Create လုပ်ပီးပီ ဆိုတာနဲ့ ကျနော်တို. Ec2 instance ဆောက်ကြရအောင်.မဆောက်ခင် Ec2 Linux Instance မှာ SSM Agent Install လုပ်ထားဖို.လိုပါတယ်.Amazon Linux AMI တွေမှာ တော့ Default install လုပ်ပြီးသားပါ တခြား Linux AMI တွေမှာ တော့ သွင်းပေးရပါမယ်.အောက်မှာဖော်ပြထားတဲ့ link မှာကြည့်ရှုနိုင်ပါတယ်။

## [https://docs.aws.amazon.com/systems-manager/latest/userguide/sysman-install-ssm-agent.html](https://docs.aws.amazon.com/systems-manager/latest/userguide/sysman-install-ssm-agent.html)

အခုကျွန်တော်က Amazon Linux AMI နဲ့ဆောက်ပြမှာဆိုတော့ ssm agent က default သွင်းပြီးသားပါလာပါလိမ့်မယ်။

![](https://i.imgur.com/udCGVnR.png)

ကျွန်တော်တို. IAM Role နေရာမှာခုနက create လုပ်ထားတဲ့ Role ကိုရွေးချယ်ပေးရပါမယ်။

![](https://i.imgur.com/XJcA5dq.png)

ထို.နောက်အပေါ်မှာ ပြောထားသလို Security Group မှာ ဘာကိုမှ Allow မလုပ်ထားပါဘူး..SSH Key Pair နေရာမှာလဲ ဘာ Key မှ မထည့်ထားပါဘူး။

![](https://i.imgur.com/d3EIp8E.png)

![](https://i.imgur.com/bx8B0qH.png)

နောက်ဆုံးကျနော်တို. Ec2 instance တစ်ခုကို အောင်မြင်စွာဆောက်လို.ရပါပီဗျာ။

![](https://i.imgur.com/CacgR3p.png)

ထို.နောက် ကျွန်တော်တို. AWS Systems Manager ကိုသွားပါမယ်။ကျနော်တို.Ec2 instance ပေါ်နေပီလားသိရအောင် ...

![](https://i.imgur.com/pKMTZJ5.png)

Instance ကို မြင်နေရပါပီဗျာ ...

![](https://i.imgur.com/9I7Dn2K.png)

အိုကေ ကျနော်တို. Session open ပီး instance ထဲ Login ကြည့်ကြရအောင် ...

![](https://i.imgur.com/WzZqkzy.png)

Systems Manager ကနေဝင်လို.ရပါတယ်။ဘာ Pem Key မှမလိုသလို ဘာ Security Group မှာမှ Allow ပေးထားစရာမလိုပါဘူး။ဆိုတော့ကျွန်တော်တို.လုပ်တာ အကုန်မှန်တယ်ပေါ့.. ဒါပေမဲ့ ကျနော်တို.နောက်ဆုံးအနေနဲ့ Logs လုပ်ကြည့်ဖို.လိုပါသေးတယ် AWS CloudWatch ကနေကျွန်တော်ကတော့ ဘာတွေလုပ်သွားလည်းသိဖို.တွက် Logs ကိုလုပ်တာပါ။

Logs တွေကိုထုတ်မယ်ဆို ကျွန်တော်တို. AWS Cloudwatch ကို သွားပါမယ်။ CloudWatch Console ကိုရောက်ရင် _**log groups**_ မှာ လိုချင်တဲ့ နာမည်နဲ့ log group တစ်ခုကို create လုပ်ပါမယ်။ကျွန်တော်ကတော့ _**SSM-Logs**_ ဆိုပီး နာမည်နဲ့တစ်ခုဆောက်လိုက်ပါမယ်။

![](https://i.imgur.com/Oyb4idr.png)

ထို.နောက် Systems Manager Console ကိုပြန်သွားပီး Log group ကို Setting ချပါမယ်။

![](https://i.imgur.com/gZcy6HN.png)

![](https://i.imgur.com/JPE59AX.png)

အထက်ပါပုံအတိုင်း setting ချပီးရင် Save မှတ်ပါမယ်။နောက်ဆုံးအနေနဲ့ Session Login ပြန်ဝင်ပီး Linux မှာ Yum Update နဲ့ တခြား action လုပ်ကြည့်ကြရအောင်..

ပထမဆုံးအနေနဲ့ ကျွန်တော်တို. Yum Update နဲ. Stress Application လေးကိုသွင့်ကြည့်ရအောင်

![](https://i.imgur.com/sxmpI7B.png)

![](https://i.imgur.com/GPO9E1t.png)

ဘာညာနည်းနည်းပါးပါ လျောက် Run ကြည့်မယ်။

![](https://i.imgur.com/ModrT94.png)

ထို.နောက် AWS Cloudwatch Log မှာပေါ်ဖို.စောင့်ရပါလိမ့်မယ်။ချက်ချင်းကြီးတော့မရောက်သေးပါဘူး ခဏတော့စောင့်ပေးရပါတယ်။

ငါးမိနစ်လောက်စောင့်လိုက်ရင် log တွေ Cloudwatch log group ထဲဝင်လာပီး Session event logs များကိုုကြည့်လို.ရပါပီ။

![](https://i.imgur.com/P3euET8.png)

![](https://i.imgur.com/EVr86uQ.png)

နိဂုံးချုပ်ရမယ်ဆိုရင်တော့ဖြင့် မိမိ Ec2 Instance ကို SSH နဲ့သာမက AWS Systems Manager ရဲ့ Session Manager နဲ့လဲ access and management လုပ်နိုင်ပါတယ်၊တစ်ခုနဲ့တစ်ခုမတူတာလေးတွေ အားသာချက်အားနည်းချက်လေးတွေလိုက်ပီး ကိုယ့် usecase အပေါ်မူတည်ပြီးအသုံးပြုနိုင်ပါတယ်။ အခု tutorial လေးကိုနောက်နေ့မှာ ကျွန်တော်တို. Video Record လေးနဲ့ လုပ်နည်းလေးတင်ပေးပါဦးမယ်။

လေးစားလျက် [AWS User Group Myanmar](https://www.facebook.com/awsugmm/)

