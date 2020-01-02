---
description: Elastic Compute Cloud Introduction
---

# Elastic Compute Cloud \(or\) EC2 - Episode \(1\)

![](https://i.imgur.com/dRgLosS.jpg)

ဒီနေ့မှာတော့ AWS မှာရှိတဲ့ Service တွေထဲကမှ တစ်ခုအပါအဝင်ဖြစ်ပြီး လူသုံးအများဆုံး Core Service တစ်ခုလည်းဖြစ်တဲ့ EC2 \(Elastic Compute Cloud\) Instance အကြောင်းကိုပြောပြပေးသွားမှာဖြစ်ပါတယ်။ ဆိုတော့ကာ ကျွန်တော်တို့ကြားဖူးနေတဲ့ AWS က EC2 Instance ဆိုတာဘယ်လို Service လဲဆိုရင်တော့ဖြင့် အနီးစပ်ဆုံးပြောရင် Virtual Private Server \( VPS \) တွေလိုပါပဲ။ EC2 ကအဓိကအားဖြင့် Cloud Compute ပိုင်းကိုလုပ်ဆောင်ပါတယ်။ Compute ဆိုတဲ့ထဲမှာအများကြီးပါဝင်ပါတယ်။ လွယ်လွယ်ပြောရရင် ကျွန်တော်တို့သုံးချင်တဲ့ Web Server, Application Server, Database Server စတာတွေအတွက် Cloud ပေါ်မှာတင်ပြီးအသုံးပြုလို့ရနိုင်အောင်လုပ်ပေးတယ်ပေါ့ဗျာ။ EC2 Instance တွေဟာ သေချာမွန်းမံထားတဲ့ Xen Virtualization ပေါ်မှာအခြေခံထားတာဖြစ်ပြီး 2017 နောက်ပိုင်း Instance Class တစ်ချို့ကိုတော့ KVM Based Virtualization \( [Nitro](http://www.brendangregg.com/blog/2017-11-29/aws-ec2-virtualization-2017.html) \) ပေါ်မှာအခြေခံထားတာဖြစ်ပါတယ်။ EC2 \( Elastic Compute Cloud \) ပေါ်မှာ Linux Distro တော်တော်များများ၊ BSD ၊ Windows Operating System စတာတွေ Run လို့ရပါတယ်။On-Premise မှာ ကိုယ်တိုင် OS Install/Setup လုပ်ရမဲ့ အချိန်တွေကို Cloud ပေါ်မှာဆိုရင်တော့ မိနစ်ပိုင်းအတွင်းပြီးမှာဖြစ်တဲ့ အတွက်အချိန်ကုန်သက်သာစေပြီး Future Plan အတွက် Scaling \( Horizontal/Vertical \) ပြုလုပ်ရာမှာလည်းအလွယ်တကူပြုလုပ်နိုင်မှာဖြစ်ပါတယ်။

**Amazon EC2 \( Elastic Compute Cloud \)** တွင် Virtual Server အပြင် ၎င်းမှ Supporting ပေးထားသော Features များကိုမိတ်ဆက်ပေးပါရစေ။

### Basics

* Instances and AMIs
* Regions and Availability Zones
* Instance Types
* Tags

### Networking and Security

* Amazon EC2 Key Pairs
* Security Groups
* Elastic IP Addresses
* Amazon EC2 and Amazon VPC

### Storage

* Amazon EBS
* Instance Store

## Guide

* အရင်ဆုံး Naming အနေနဲ့ AWS မှာ EC2 ကို _**Instance**_ လို့လည်းခေါ်ကြပါတယ်။
* Resources များအတွက် Multiple Physical Locations ခေါ်  _**Regions, Availability Zones \( AZs \)**_
* CPU, Memory, Storage, Networking Capacity ဘယ်လောက်သုံးမယ်ကိုရွေးချယ်နိုင်မယ့် _**Instance Types**_
* Instance အတွင်း Additional Software များကိုအချိန်တိုအတွင်းရွေးချယ်ပြီး Install/Setup လုပ်နိုင်သော Pre-configure Template ခေါ် _**AMIs \( Amazon Machine Images \)**_ 
* Instance များကို လုံခြုစွာ Remote Login ပြုလုပ်နိုင်ရန်အတွက်  _**Key Pair \( Public/Private Key \)**_
* Instance ကို Stop or Terminate လုပ်ရင်ပျက်သွားမဲ့ Temporary Storage Volume အတွက် _**Instance Store Volumes**_ 
* Persistent/Permanent Storage Data Volume အတွက် _**Amazon Elastic Block Storages \( Amazon EBS Volumes \)**_
* Instances များအတွက်  _**Security Groups**_   ခေါ် Firewall \( Specify the protocols, ports, and source IP range \) 
* _**Elastic IP**_ Addresses ခေါ် Instance များအတွက် Static Public IPv4 Addresses
* EC2 Instances များအတွက်လိုအပ်သော Virtual Network များကို AWS Cloud အတွင်း Logically Isolated ဖြစ်ရန်အတွက်သတ်မှတ်နိုင်သော _**Amazon Virtual Private Clouds \( Amazon VPCs\)**_
* AWS အတွင်းရှိ Instances, Amazon Machine Images \( AMI \) နှင့် အခြားသော Resources များကို Manage လုပ်ရလွယ်ကူစေရန်အတွက် _**Tags**_

သည်လောက်ဆိုရင်တော့ **Amazon EC2** ရဲ့ အခြေခံ Concepts နဲ့ သူရဲ့နာမည်အခေါ်အဝေါ်လေးတွေကို အကြမ်းဖျင်းသဘောပေါက်လိမ့်မယ်ထင်ပါတယ်။ Episode \(1\) ပဲရှိသေးတဲ့အတွက်နောက်ထပ် Episodes တွေမှာ Feature တစ်ခုချင်းစီရဲ့ Use Case နဲ့ Details လေးတွေရေးသားသွားဦးမှာမို့ ဆက်လက်အားပေးကြပါဦး ခင်ဗျာ။

လေးစားလျက်

 [AWS User Group Myanmar](https://www.facebook.com/awsugmm/)

