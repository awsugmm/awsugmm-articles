---
description: Introduction to Amazon EKS - Kubernetes on AWS
---

# Amazon EKS Cluster Provisioning

![Introduction to Amazon EKS - Kubernetes on AWS](../.gitbook/assets/screen-shot-2020-04-16-at-01.17.37.png)

ပထမဦးစွာ ဒီ Blog tutorial က [AWS User Group Myanmar](https://www.facebook.com/groups/AWSusergroupmyanmar/) က ကျင်းပမဲ့ Online Meetup မှာ ကျွန်တော်ပြောသွားမဲ့ "**Amazon EKS - Kubernetes on AWS**" Topic လေးနဲ့တူတူ လေ့လာပြီး ကိုယ်ကိုတိုင် AWS EKS cluster ဆောက်ပြီးလိုက်စမ်းနိုင်အောင်ရည်ရွယ်ပြီးရေးထားချင်းဖြစ်ပါတယ်။   
ကျွန်တော်တို.ပွဲလေး ကိုတက်ရောက်ဖို.ဖိတ်ပါရစေ .. ပြီးတော့ Topic များကိုလည်းအောက်မှာဖော်ပြထားတဲ့ Topic Board မှာ ဝင်ရောက်ကြည့်နိုင်ပါတယ်။ 

{% hint style="success" %}
[https://airtable.com/shrGToJczSuy1KZAr](https://airtable.com/shrGToJczSuy1KZAr)
{% endhint %}

အဲ နောက်တစ်ခုက Speaker အဖြစ်နဲ့ Sharing လုပ်ပေးချင်ရင်လည်း ကျွန်တော်တို.က ဝမ်းမြောက်ဝမ်းသာ ဖိတ်ကြားပါရစေ။ အောက်က လင့် လေးကနေ စာရင်းသွင်းလိုရပါတယ်ဗျ။

{% hint style="success" %}
[https://airtable.com/shrV1vefDtNLcAaZ0](https://airtable.com/shrV1vefDtNLcAaZ0)
{% endhint %}

ပွဲအကြောင်းပြောပြီးပြီဆိုတော့ရေးမည့်ဟာလေးကိုဆက်ပါရစေ။ 

Amazon EKS အကြောင်းမပြောခင် ကနဦးအနေနဲ့ Kubernetes ဆိုတာဘာလဲ ဘယ်လို လဲ သူ.ရဲ့ architecture က ဘယ်လိုအလုပ်တွေလုပ်လဲနည်းနည်းအကျဉ်းချုံးကြည့်ရအောင်။ Kubernetes ရဲ့ official documentation မှာတော့အောက်ကအတိုင်းဖော်ပြထားပါတယ်။ အဓိက ကတော့ မြန်မာလိုပြောရရင်တော့ Kubernetes က containerized application တွေကို လွယ်လွယ်ကူကူ စီမံခံခွဲနိုင်အောင်၊ မောင်းနှင်းနိုင်အောင် ပြုလုပ်ထားတဲ့ solution တစ်ခုဖြစ်တယ်ပေါ့။ 

{% hint style="success" %}
Kubernetes is a portable, extensible, open-source platform for managing containerized workloads and services, that facilitates both declarative configuration and automation. It has a large, rapidly growing ecosystem. Kubernetes services, support, and tools are widely available.
{% endhint %}

ဆိုတော့ Kubernetes Cluster ရဲ့ architecture, components တွေကိုလေ့လာကြည့်ရအောင်။Master \(Control Plane\) မှာဘာတွေပါလဲ၊ Worker node \(Minion\) မှာဘာတွေပါဝင်လဲ လေ့လာကြည့်ရအောင်။ ကျွန်တော်ဒီ Blog Post က Amazon EKS cluster provisioning ဆိုတော့ Kubernetes cluster architecture ကိုတော့ မရေးတော့ဘူး ဒါပေမဲ့ မြန်မာလိုပဲရေးထားပြီးနားလည်ရလွယ်ကူတဲ့ Blog content လေးကိုအောက်မှာ link အနေနဲ့ ညွန်းလိုက်ပါတယ်။   

{% hint style="success" %}
[https://blog.k8smm.org/k8s-cluster-achitecture](https://blog.k8smm.org/k8s-cluster-achitecture)
{% endhint %}

Amazon EKS က Amazon Web Services ရဲ. Managed Kubernetes Service တစ်ခုဖြစ်ပါသည်။ အဓိက အားဖြင့် Kubernetes ရဲ့ master control plane ကို AWS ဘက်က managed လုပ်ပေးချင်းကို ဆိုလိုတာပါ။ အဲ့ထက်ပိုပြီး EKS က data plane ဖြစ်တဲ့ worker nodes များပါ managed လုပ်ပေးနိုင်ပြီ ဟုလည်း  AWS က  [announced](https://aws.amazon.com/blogs/containers/eks-managed-node-groups/) လုပ်ထားပါတယ်။ 

အိုကေ .. ဒါဆို လက်တွေ EKS Cluster ကို ဆောက်ကြည့်ကြရအောင်။အရင်ဆုံး EKS Cluster မဆောက်ခင် Official Documentation ကို Share ပါရစေ။  

ပြီးနောက် AWS EKS ရဲ့ Architecture လေးကိုလည်း တစ်ချက်လောက်လေ့လာကြရအောင်။  

![EKS High Level Architecture](../.gitbook/assets/eks.png)

![EKS Consumption Design \(Re-Draw by Wai Yan Min\)](../.gitbook/assets/eks2.png)

Official Documentation here 👇 👇 👇 

{% hint style="success" %}
[https://docs.aws.amazon.com/eks/latest/userguide/what-is-eks.html](https://docs.aws.amazon.com/eks/latest/userguide/what-is-eks.html)
{% endhint %}

CloudFormation Template တွေကိုလည်းတနေရာထဲက Download ချင်ရင်လည်းအဆင်ပြေဖို.တွက်ပြန် Share ပေးထားပါတယ်။  

{% hint style="info" %}
[https://github.com/phyominhtun1990/AWS-EKS-Cluster-Introduction](https://github.com/phyominhtun1990/AWS-EKS-Cluster-Introduction.git)
{% endhint %}

ဆိုတော့ကျွန်တော်တို. EKS Cluster စဆောက်ကြရအောင်။ပထမဆုံးအနေနဲ့ cluster provision မလုပ်ခင် EKS တွက် IAM Role ကို စဆောက်ရပါမယ်။  AWS IAM Console ကို သွားပြီးအောက်မှာဖော်ပြထားတဲ့အတိုင်း IAM Role တစ်ခုကို တည်ဆောက်ပါမယ်။ 

![Creating EKS Role](../.gitbook/assets/eks-role-1.png)

![Creating EKS Role](../.gitbook/assets/eks-role-2.png)

![Creating EKS Role ](../.gitbook/assets/eks-role-3.png)

![](../.gitbook/assets/screen-shot-2020-04-16-at-02.57.52.png)

EKS IAM Role ဆောက်ပြီးပြီ ဆိုတော့ နောက်တစ်ဆင့်အနေနဲ့ EKS Cluster အတွက် VPC ဆောက်ပြီး Networking setting ချပေးရပါမယ်။ VPC ဆောက်ရာတွင် manual ဆောက်တာထက် CloudFormation နဲ့တည်ဆောက်ပါမယ်။ EKS VPC တည်ဆောက်တဲ့ CloudFormation Template ကိုအောက်ကလင့်မှာ Clone or Download လုပ်လို.ရပါတယ်။ \(**Official Link ကနေလဲ Download လုပ်လို.ရပါတယ်**\)။ 

{% hint style="info" %}
[https://github.com/phyominhtun1990/AWS-EKS-Cluster-Introduction.git](https://github.com/phyominhtun1990/AWS-EKS-Cluster-Introduction.git)
{% endhint %}

Download လုပ်ပြီးပြီဆိုရင်ကျွန်တော်တို. တွေ CloudFormation Console ကိုသွားပါမယ်။ပြီးနောက် VPC Create template yml file ကို အောက်ဖော်ပြပါအတိုင်း upload template နေရာမှာ upload တင်ပါမယ်။  

![Upload Template in CF Console](../.gitbook/assets/cf-1.png)

![View in designer in CF console](../.gitbook/assets/cf-2.png)

VPC မဆောက်ခင် တစ်ချက်ကြည့်ကြည့် ရင် VPC က Subnet သုံးခု အကြမ်းဖျဉ်းပါပါတယ်။ ထိုနောက်အောက်ဖော်ပြပါအတိုင်းဆက်လက်တည်ဆောက်ပါမယ်။ကျွန်တော်ကတော့ Template ထဲကအတိုင်း default ထားလိုက်ပြီးတည်ဆောက်ပါမယ်။ 

![VPC Network CIDR ](../.gitbook/assets/cf-3.png)

![VPC Network CIDR](../.gitbook/assets/cf-4.png)

![EKS-VPC](../.gitbook/assets/cf-6.png)

ကျွန်တော်တို. EKS Cluster တွက် VPC ကို CloudFormation Template နဲ့ တည်ဆောက်ပြီးသွားပြီဆိုတော့ ကျွန်တော်တို.ဆက်ပြီး EKS Cluster ကို ဆက်လက်တည်ဆောက်ပါမယ်။ AWS EKS Cluster တည်ဆောက် ရာတွင် ကျွန်တော်တို.သုံးမျိုး တည်ဆောက်လို.ရပါတယ် AWS Management Console , AWS CLI နှင့် eksctl နဲ့တည်ဆောက်လို.ရပါတယ်။ကျွန်တော်ကတော့ AWS CLI သုံးပြီး တော့တည်ဆောက်ပါမယ်။ အောက်မှာဖော်ပြထားတဲ့ Command \(AWS CLI\) နဲ့ EKS Cluster ကို တည်ဆောက်ပါမယ်။ 

{% hint style="info" %}
AWS CLI ကို Configure လုပ်ပေးရပါမယ်။ 
{% endhint %}

```text
#aws configure
```

```text
#aws eks --region region-code create-cluster --name demo-eks-cluster --role-arn arn:aws:iam::111122223333:role/EKS-Role --resources-vpc-config subnetIds=subnet-01,subnet-02,subnet-03,securityGroupIds=[sg-id]
```

![EKS Cluster](../.gitbook/assets/eks-cluster-create-1%20%281%29.png)

EKS Cluster ကိုတည်ဆောက်ပြီးရင် ကျွန်တော်တို. EKS Console ကနေသွားကြည့်ရအောင်။ EKS Cluster ကိုတည်ဆောက်ပြီးရင်ကျွန်တော် တို. Console မှာ တွေ.နိုင်ပါတယ်။ 

![](../.gitbook/assets/screen-shot-2020-04-16-at-00.50.28.png)

အိုခေ ကျွန်တော်တို. EKS Cluster တည်ဆောက် ပြီးပြီဆိုတော့ Worker Nodes တွေ မထည့်ခင် ကျွန်တော်တို. kube config ကို configure လုပ်ကြစို.။ EKS Cluster တွက် kube config ကို configure လုပ်ဖို.တွက်အောက်ဖော်ပြပါ command လေးနဲ့ configure လုပ်ကြရအောင်။ 

```text
#aws eks --region us-east-1 update-kubeconfig --name demo-eks-cluster
```

![](../.gitbook/assets/1%20%286%29.png)

{% hint style="danger" %}
Demo Cluster ဖြစ်တဲ့ အတွက် ပြီးရင် ပြန်ဖျက်မှာပါ။ 
{% endhint %}

demo-eks-cluster တွက် kube config လေး ထွက်လာပါလိမ့်မယ်။ config ရပြီဆိုတော့ကျွန်တော်တို. kubectl command  လေးနဲ့ နည်းနည်း ပါးပါးစမ်းကြည့်ရအောင်။ 

![](../.gitbook/assets/2%20%284%29.png)

ပုံပါအတိုင်းဆို ကျွန်တော်တို. EKS cluster ကတော့ အလုပ်လုပ်နေပါပြီ။ဆိုတော့ကျွန်တော်တို.တွေ Worker nodes တွေ ထည့်ကြည့်ရအောင်။ 

Worker nodes တွေထည့်ဖို. ကျွန်တော်တို. CloudFormation Template ကို အောက်က လင့်မှာ Download လုပ်လို.ရပါတယ်။  \(**Official Link ကနေလဲ Download လုပ်လို.ရပါတယ်**\)။ 

{% hint style="success" %}
[https://github.com/phyominhtun1990/AWS-EKS-Cluster-Introduction.git](https://github.com/phyominhtun1990/AWS-EKS-Cluster-Introduction.git)
{% endhint %}

Download လုပ်ပြီးပြီဆိုတော့ ကျနော်တို. တွေ CloudFormation Template နဲ့ Worker nodes တွေကို  တည်ဆောက်ကြရအောင်။ ပထမဆုံး Download လုပ်ထားတဲ့ CloudFormation Template လေးကို Upload လုပ်ပြီး Run လိုက်ပါမယ်။ Parameters တွေက တော့ အောက်ဖော်ပြပါပုံအတိုင်းထည့်ရပါမယ် တချိူ. parameter တွေကို တော့ default ထားပါမယ်။ 

{% hint style="info" %}
**ami-0c5b63ec54dd3fc38** ကတော့ us-east-1 မှာဆိုရင်တော့ eks node ami ပါ။ 
{% endhint %}

![](../.gitbook/assets/worker1.png)

![](../.gitbook/assets/worker2.png)

Stack Complete ဖြစ်ပြီဆိုရင်ကျွန်တော်တို. EKS Cluster နဲ့ Worker Nodes တွေကို Join ဖို. တွက် အောက်ဖော်ပြပါ ပုံထဲက "**NodeInstanceRole**" ARN ကို မှတ်ထားရပါမယ်။ 

![](../.gitbook/assets/worker3.png)

ထို.နောက် ကျွန်တော်တို. Worker nodes ချိတ်ဆက်ဖို.တွက် Configmap ကို Download လုပ်ပြီး cluster မှာ run ပေးရန်လိုအပ်ပါသည်။ အရင်ဆုံး auth Configmap ကို download 

{% hint style="success" %}
[https://github.com/phyominhtun1990/AWS-EKS-Cluster-Introduction.git](https://github.com/phyominhtun1990/AWS-EKS-Cluster-Introduction.git)
{% endhint %}

ပြီးရင်ကျွန်တော်တို. အပေါ်မှာ မှတ်ထားတဲ့  "**NodeInstanceRole**" ARN ကိုအစားထိုးပြီး  run ပေးရပါမယ်။ 

![](../.gitbook/assets/1%20%281%29.png)

```text
#kubectl apply -f aws-authentation-cm-workers.yaml
```

kubectl apply command နဲ့ Configmap ကို run ပြီးရင် တခဏ လောက်ကြာရင် \#kubectl get nodes command ရိုက်လိုက်ရင် အောက်ဖော်ပြပါပုံအတိုင်း worker nodes တွေ Ready ဖြစ်နေတာကိုတွေ.ရပါလိမ့်မည်။ 

![](../.gitbook/assets/1%20%284%29.png)

![](../.gitbook/assets/1%20%282%29.png)

ထိုအပြင် kube-system namespace ထဲ က pods တွေလည်း running ဖြစ်နေတာကိုတွေ.မြင်ရပါလိမ့်မယ်။အိုခေ 🤩ဒါဆို Node လည်း Ready ဆို ကျန်တာတွေလည်း running ဆိုတော့ EKS Cluster က up and running ဖြစ်နေပြီပေါ့ဗျာ။ သေချာအောင်ကျွန်တော် တို. Application တစ်ခုလောက် run ကြည့်ကြရအောင်ဗျာ။ လွယ်လွယ်ကူကူလေးဖြစ်အောင် 2048 game လေးကို EKS Cluster  မှာ run ကြည့်ရအောင်။ 

2048 yaml file လေးကို အောက်က လင့်လေးမှာ Download လုပ်လို.ရပါတယ်။ Deployment file and service file လေးနှစ်ခုကို Download လုပ်ပြီး terminal ကနေ အောက်ပါ command လေးရိုက်ပြီး run နိုင်ပါတယ်။ 

```text
#kubectl apply -f file.yml
```

{% hint style="success" %}
[https://github.com/phyominhtun1990/AWS-EKS-Cluster-Introduction.git](https://github.com/phyominhtun1990/AWS-EKS-Cluster-Introduction.git)
{% endhint %}

![](../.gitbook/assets/2%20%281%29.png)

အိုခေ ကျွန်တော်တို. Cluster မှာ namespace ဆောက်တယ် deployment ကို replica သုံးလုံး ဆောက်တယ်ပြီးတော့ NodePort service ထုတ်လိုက်တယ်။ ဒါဆို NodePort \(31957\)ကို instance security group မှာ allow လုပ်ပြီး 2048 game ကို access လုပ်ကြည်ကြရအောင်။  

{% hint style="info" %}
[http://34.239.94.225:31957/](http://34.239.94.225:31957/)
{% endhint %}

![](../.gitbook/assets/screen-shot-2020-04-16-at-02.44.48.png)

အိုခေပြီဗျာ .. ကျွန်တော်တို. AWS EKS Cluster က up and running လည်းဖြစ် application ပါတင်ပြီး Run လို.ရနေပါပြီ။ ဒါဆို ကျွန်တော်တို. ဒီ tutorial လေးကို မိတ်ဆွေတို. ကိုယ်တိုင် လိုက်လုပ်ရင်း EKS Cluster ရဲ. feature တွေ kubernetes cluster ရဲ. feature တွေကို ကိုယ်ကိုတိုင် လိုက်လုပ်ကြည့်ရင်း ကိုယ်ပိုင် cluster များ ဆောက်နိုင်ပါစေဟုပြောကြားရင်း နိဂုံးချူပ်ပါရစေ။ 

ကျွန်တော်တို. AWS User Group Myanmar က ပြုလုပ်မဲ့ Online Meetup မှာ ပြန်ဆုံပြီး ထပ်ပြီးဆွေးနွေးကြမယ်။ 

ကျေးဇူးတင်လျက် ...   
AWS User Group Myanmar 

Stay Safe and Healthy!  



