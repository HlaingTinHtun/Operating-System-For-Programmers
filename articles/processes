## Processes

![Image of Abstraction](https://raw.githubusercontent.com/HlaingTinHtun/Operating-System-For-Programmers/master/images/processes.jpg)

Process ဆိုတာနဲ့ မိတ်ဆက်ပေးစရာတော့ တကူးတက မလိုလောက်ဘူးထင်ပါတယ်။ ရှင်းရှင်းနဲ့ ပြောရရင် program တစ်ခုကို run လိုက်တယ်ဆို process ဆိုတာဖြစ်လာတာပါပဲ။ code တွေရေးလိုက်တယ်၊ ပြီးရင် execute လုပ်လိုက်တယ်၊ အဲ့ကနေ process ဆိုတာဖြစ်လာပြီးတော့ ရေးထားတဲ့ program တွေထဲက code တွေအတွက် အလုပ်လိုက်လုပ်ပေးသွားတယ်။

တစ်ကယ်တန်းတော့ ဒီထက်ပိုနက်နဲပါတယ်။ system memory ထဲကနေ program တစ်ခု run လိုက်လို့ process ဆိုတာဖြစ်လာတာနဲ့အတူ အဲ့ဒီ process က memory ထဲမှာ Stack, Heap, Text, Data ဆိုပြီး အပိုင်း ၄ ပိုင်းခွဲပြီး အလုပ်လုပ်ပါတယ်။

Stack က temporary data တွေအတွက် (ဥပမာ function ထဲမှာ သိမ်းထားတဲ့ variable တို့, parameters တို့)။
Heap ကတော့ process run နိုင်ဖို့အတွက် allocate လုပ်ထားတဲ့ dynamic memory. Heap အကြောင်းကို data structures series မှာ ရေးထားပါတယ်။
Text ဆိုတာကတော့ program counter နဲ့ cpu registers တွေရဲ့ လက်ရှိလုပ်နေတဲ့ activity value တွေအတွက်ဖြစ်ပါတယ်။
Data section ကတော့ global variable တွေနဲ့ static variables တွေအတွက်ဖြစ်ပါတယ်။

၄ပိုင်းခွဲပြီးအလုပ်လုပ်တာက ဟုတ်ပါပြီ။ ဘယ်လိုအလုပ်လုပ်လဲဆိုတာကရှိသေးတယ်။ program တစ်ခု run လိုက်ပြီးဆိုတာနဲ့ အလုပ်လုပ်သွားတဲ့ အဆင့် ၅ ဆင့်ရှိပါတယ်။ OS ပေါ်လိုက်ပြီး အစဉ်လိုက်က ကွဲပြားနိုင်တယ် ဆိုပေမဲ့လို့ အကြမ်းဖျင်းအားဖြင့်တော့ ဒီအစဉ်လိုက်ပါတယ်။

Start - process တစ်ခုကစမှတ် (process ဆိုပြီးဖြစ်လာတဲ့အချိန်ပေါ့)။

Ready – ဒီ stage မှာတော့ process က သူ့ကိုလာ assign လုပ်မယ့် processor ကိုစောင့်နေပါတယ်။ ပြီးတာနဲ့ allocate လုပ်ပြီး run လို့ရပြီပဲဖြစ်ပါတယ်။ ready stage ကိုရောက်လာရတဲ့ အကြောင်းအရင်းက နှစ်မျိုးရှိနိုင်ပါတယ်။ start stage ပြီးလို့ရောက်လာတာရယ်၊ ဒါမှမဟုတ် process က running ဖြစ်နေပြီးတော့ scheduler တစ်ခုခုကြောင့် CPU က တစ်ခြား process တွေသွား run နေတဲ့အချိန် interrupt ဖြစ်သွားပြီး ready stage ပြန်ရောက်သွားတာမျိုးလဲဖြစ်နိုင်ပါတယ်။

Running – OS ရဲ့ scheduler တွေက processor ကနေ process တွေကို assign လုပ်လိုက်တဲ့အချိန်မှာ ဒီ stage ကိုရောက်ပါတယ်။

Waiting – process တွေက execute ထပ်လုပ်ဖို့အတွက်စောင့်ဖို့လိုလာတဲ့အချိန်ဆိုဒီနေရာရောက်ပါတယ်။ (ဥပမာ file တစ်ခုခုကိုလှမ်းဖတ်နေတာပဲဖြစ်ဖြစ်၊ user input ကိုစောင့်နေတာပဲဖြစ်ဖြစ်ပေ့ါ)။

Terminated -  process ကသူ့ဘာသာ ပြီးသွားတာပဲဖြစ်ဖြစ်၊ OS က terminate လုပ်ပစ်လိုက်တာပဲဖြစ်ဖြစ် ဒီအဆင့်ကိုရောက်လာပါတယ်။ ပြီးတာနဲ့ main memory က process ကို remove လုပ်သွားပါတယ်။

Process တွေကို run တိုင်းမှာ OS က PCB (Process Control Block) ဆိုတဲ့ data structure တစ်ခုနဲ့ process တွေကို track လုပ်ပါတယ်။ PCB ကိုတော့ integer value တွေနဲ့ identify လုပ်ထားပါတယ်။ PCB ထဲမှာဘာတွေပါလဲဆိုတော့

Process state - လက်ရှိ process က အပေါ်ကပြောထားတဲ့ ၅ ချက်ထဲကဘယ်အဆင့်ဆိုတာ။
Process privileges – system resources တွေကို allow လုပ်မှာလား။ disallow လုပ်မှာလား။
Process ID – unique ဖြစ်တဲ့ process id။
Pointer – parent process ကို link ထားတဲ့အရာ။
Program counter - လာမယ့် instruction အတွက်ထောက်ထားတဲ့ pointer တစ်ခု။
CPU Scheduling info – process ရဲ့ priority level နဲ့ schedule လုပ်ရမယ့် အချက်အလက်တွေ။
CPU Registers – running stage မှာ process တွေကို store လုပ်ပေးမယ့် CPU registers တွေ။
Memory Management info – system memory ပေါ်မူတည်ပြီးတော့ OS ကအသုံးပြုသွားမယ့် memory limit တွေ page & segment table တွေ။
Accounting Information - လက်ရှိ process အတွက် အသုံးပြုမယ့် CPU amount နဲ့ execute လုပ်တဲ့ ID တွေ နဲ့
Input Output devices တွေရဲ့ status တွေစုထားတဲ့  IO status information တွေ ပါမှာဖြစ်ပါတယ်။

ဒီလောက်ဆိုရင်တော့ process တစ်ခုရယ်လို့ဖြစ်လာပြီဆို OS ကဘယ်လိုကိုင်တွယ်သွားလဲဆိုတာ ကောင်းကောင်းနားလည်သွားပြီပဲဖြစ်ပါတယ်။
