# Deploying Wordpress Website with Amazon Lightsail

အခုပြောပြပေးချင်တာကတော့ WordPress ဆိုဒ်တခုကို AWS မှာ စျေးသက်သက်သာသာနဲ့ Host ဘယ်လိုလုပ်မလဲဆိုတာမျိုးပဲ ဖြစ်ပါတယ်။ Server Configuration တွေသိစရာမလိုပဲ အလွယ်တကူ Build လုပ်လို့ရတဲ့ services တမျိုးပါ။ နောက်ကျရင် Pros & Cons လည်း သီးသန့်ရေးပေးပါအုံးမယ် အချိန်ရတာနဲ့အမျှ အခုတော့ setup လုပ်တာလေးကိုပဲ အဆင်ပြေရင်လိုက်စမ်းကြည့်ပီး သုံးကြည့်ကြပါလို့ပြောချင်ပါတယ်။

ပထမဆုံးအနေနဲ့ AWS Lightsail \([https://lightsail.aws.amazon.com/ls/webapp/home/instances](https://lightsail.aws.amazon.com/ls/webapp/home/instances)\) ရဲ့ Console ကိုအရင် ၀င်လိုက်ပါ ပုံမှာပြထားတဲ့အတိုင်းမြင်ရပါလိမ့်မယ်

![](https://leetdev.net/wp-content/uploads/2019/10/Screenshot-from-2019-10-22-14-16-40-700x376.png)

Create Instance ကနေ မိမိ အသုံးပြုလိုသော Application အမျိုးအစားတွေအလိုက် ရွေးလို့ရပါတယ်။ ကျွန်တော်ကတော့ WordPress ကိုအဓိက ပြောမှာ ဖြစ်လို့ WordPress ကိုပဲ ရွေးလိုက်ပါတယ်။ WordPress site အများကြီးလုပ်ချင်ရင်လည်း ရပါတယ် ဘေးက တခုကို ရွေးပေးပီး လုပ်လို့ရပါတယ်။

![](https://leetdev.net/wp-content/uploads/2019/10/Screenshot-from-2019-10-22-14-19-57-700x485.png)

နောက်တဆင့်ကတော့ ကိုယ်သုံးမယ့် WordPress site အတွက်လိုအပ်မယ် Specification လေးတွေ ရွေးပေးလို့ရပါတယ် ကိုယ့်ဆိုဒ်ရဲ့ User ဘယ်လောက်ထိရှိမယ် Request များလား Response များလားပေါ်မူတည်ပီး ကိုယ်စိတ်ကြိုက် memory\(RAM\) တွေရော storage ရော ရွေးပေးလို့ရပါတယ်။ အောက်က ပုံမှာ မြင်နိုင်ပါတယ်။ default ssh key pair မသုံးပဲ မိမိစိတ်ကြိုက်လည်း ပြောင်းရွေးပေးခဲ့လို့ရပါတယ်။

![](https://leetdev.net/wp-content/uploads/2019/10/Screenshot-from-2019-10-22-14-23-32-700x529.png)

 ကိုယ်ပေးခြင်တဲ့ နာမည်နဲ့ Create Instance ရသွားပီးဆိုရင် WordPress site လေးတော့ ပီးသွားပီလို့ ယူစလို့ရပါတယ်။

![](https://leetdev.net/wp-content/uploads/2019/10/Screenshot-from-2019-10-22-14-24-45-700x414.png)

Running ဖြစ်နေတဲ့ WordPress လေးကို ခဗျားတို့ တွေ့ရမှာ ဖြစ်ပါတယ်

![](https://leetdev.net/wp-content/uploads/2019/10/Screenshot-from-2019-10-22-14-26-01-700x304.png)

နောက်တခုကတော့ ကျွန်တော်တို့ အနေနဲ့ Create လုပ်ထားတဲ့ WordPress ကို public ip နဲ့ခေါ်လို့ရအောင် elastic ip \(static ip\) တခု Attach လုပ်ပေးဖို့လိုပါတယ်။ Networking ဆိုတဲ့ tag ကနေသွားလုပ်ရမှာပါ ပုံမှာပါတဲ့အတိုင်း Create Static IP လုပ်ရမှာပါ။

![](https://leetdev.net/wp-content/uploads/2019/10/Screenshot-from-2019-10-22-14-28-40-700x454.png)

Create Static IP လုပ်တဲ့အခါမှာ ဘယ်အလုံးကို Attach လုပ်မလဲရွေးပေးရပါတယ် ကျွန်တော်တို့ အနေနဲ့ WordPress Leetdev ကို ရွေးပေးလိုက်ပါပြီ Create လိုက်ရင် ရပါပြီ။ သူအစကတည်းက ပေးထားတဲ့ Public IP သုံးလို့လည်းရပါတယ်။

![](https://leetdev.net/wp-content/uploads/2019/10/Screenshot-from-2019-10-22-14-30-26-700x544.png)

အခုဆိုရင် ကျွန်တော်တို့ wordpress ဆိုဒ်ကို ခေါ်လို့ရမယ့် Public IP တခုရလာပါပြီ AWS Route53 နဲ့ Domain ဘယ်လို Point မလဲဆိုတာကိုတော့ ကျွန်တော်နောက် အချိန်ရရင် ရေးပေးပါအုံးမယ်။

![](https://leetdev.net/wp-content/uploads/2019/10/Screenshot-from-2019-10-22-14-32-03-700x385.png)

အောက်ကပုံကတော့ WordPress setup လုပ်ထားပီးသား Default ဆိုဒ်တခုရလာပါပြီ ကျွန်တော်တို့အနေနဲ့ မိမိတို့သုံးလိုတဲ့ Themes တွေ Plugin တွေတော့ ထည့်ပီး လုပ်ဖို့တော့လိုပါအုံးမယ်။

![](https://leetdev.net/wp-content/uploads/2019/10/Screenshot-from-2019-10-22-14-34-10-700x357.png)

နောက်တခုကတော့ wp-login ကနေ ၀င်ဖို့ ကျွန်တော်တို့ အနေနဲ့ username နဲ့ password ရဖို့လိုပါသေးတယ်။ ဘယ်ကနေရမလဲဆိုတော့ ကျွန်တော်တို့ အနေနဲ့ WordPress Lighsail server ထဲကို ssh login ၀င်ရမှာပါ ကျွန်တော်ကတော့ သူ့ Console ကနေပဲ Login ၀င်လိုက်ပါတယ်။

![](https://leetdev.net/wp-content/uploads/2019/10/Screenshot-from-2019-10-22-14-37-27-700x327.png)

ls ခေါ်ကြည့်လိုက်ပါ credentials တွေပေးထားတာ တွေ့ရပါလိမ့်မယ်။ cat နဲ့ ဖတ်ကြည့်လိုက်တဲ့အခါ wp-login အတွက် username & password တွေ့ရပါလိမ့်မယ်။

![](https://leetdev.net/wp-content/uploads/2019/10/Screenshot-from-2019-10-22-14-39-47.png)

ကဲရလာတဲ့ Credential တွေကိုသုံးပြီး wordpress site ကို login ၀င်လို့ရပါပြီ မိမိစိတ်ကြိုက် wordpress site တခုကို အမြန်ဆုံး develop လုပ်နိုင်သွားပီ ဖြစ်ပါတယ်။

![](https://leetdev.net/wp-content/uploads/2019/10/Screenshot-from-2019-10-22-14-42-47-700x338.png)

အားလုံးပဲ အဆင်ပြေကြမယ်လို့ထင်ပါတယ် ဖတ်ပေးကြသူအားလုံးကို ကျေးဇူးတင်ပါတယ်။

ကောင်းသန့်လွင်

AWS User Group Myanmar \|\| LeetDev

 

