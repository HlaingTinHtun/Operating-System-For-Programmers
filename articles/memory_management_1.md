## Memory Management Part 1

![Image of Abstraction](https://raw.githubusercontent.com/HlaingTinHtun/Operating-System-For-Programmers/master/images/memory_management_1.png)

computer ထဲမှာရှိတဲ့ internal physical memory ကို main memory လို့ခေါ်ပါတယ်။ main memory ဆိုပြီးခေါ်ရတဲ့အကြောင်းရင်းက external memory storage ဖြစ်တဲ့ disk drives တွေနဲ့ ရောသွားမှာဆိုးလို့ အရှေ့မှာ main ထည့်ပြီးခေါ်ရခြင်းဖြစ်ပါတယ်။ main memory ကို RAM လို့လည်းခေါ်လို့ရပါတယ်။ computer က main memory ထဲမှာဖြစ်လာတဲ့ data တွေကိုပဲ manage လုပ်လို့ရပါတယ်၊ ဒါကြောင့်မို့လို့ programs တွေ runလိုက်ပြီဆို storage devices တွေကနေပြီးတော့ main memory ဆီကိုလာရပါတယ်။ ဒါမှသာ computer က အဲ့ဒီ process ကို manage လုပ်လို့ရမှာပါ။

memory management မှာအရေးပါတဲ့ module တစ်ခုခြင်းဆီကိုအောက်မှာထပ်ရေးပေးသွားပါမယ်။

Process Address
process တစ်ခုက code တွေဆီကနေ reference ယူထားတဲ့ logical address  (memory cell, storage element, network host  etc.) တွေရှိပါတယ်။ program တစ်ခု memory allocate လုပ်တဲ့အချိန်မှာ OS က logical address တွေကို memory management unit (MMU) ကိုသုံးပြီး physical address အဖြစ် map လုပ်ပါတယ်။ အသေးစိတ်ရှင်းရမယ်ဆို logical address က program တစ်ခု run လိုက်တဲ့အချိန်မှာ CPU က generate လုပ်ပေးထားတာဖြစ်ပြီး physically မရှိဘဲ virtually ပဲရှိပါတယ်။ physical address ကတော့ memory ထဲမှာကို physical location နဲ့ရှိပါတယ်။ MMU ကတစ်ခုနဲ့တစ်ခုကို correspond လုပ်နိုင်ဖို့အတွက် ကြားခံ computation လုပ်ပေးတဲ့အရာတစ်ခုလို့ပြောလို့ရပါတယ်။ Okay , OS က memory allocate နေရာကိုပြန်သွားရအောင်။ allocate လုပ်တဲ့နေရာမှာ address type ၃ခုကိုသုံးပြီးလုပ်ပါတယ်။

symbolic address
- source code ထဲမှာသုံးတဲ့ address ဖြစ်ပါတယ်။ variable name တို့ constant တို့ အစရှိသဖြင့်ပါပါတယ်။

Relative address
- program ကို compile လုပ်တဲ့အချိန်မှ compiler က symbolic address တွေကို relative address အဖြစ်ပြောင်းလဲပေးလိုက်ပါတယ်။

Physical address
- နောက်ဆုံး program က memory ထဲမှာ load လာလုပ်တဲ့အချိန်မှ loader က physical address တွေကို generate လုပ်ပေးလိုက်ပါတယ်။


Static , Dynamic loading and Static , Dynamic Linking
program တွေက execute လုပ်ဖို့အတွက် main memory ထဲကိုလာလုပ်ကြရပါတယ်။ တစ်ချို့ program တွေက main memory ထဲမှာပဲ completely တစ်ခါတည်း run သွားတယ်။ အဲ့ဒါကို static loading လို့ခေါ်ပါတယ်။ တစ်ချို့ကျတော့ main memory ပေါ်မှာ partially ပဲလာrun ပြီးကျန်တဲ့ libraries တွေ modules တွေကို disk ပေါ်မှာထားထားပါတယ်။ အဲ့ဒီ modules တွေကိုလိုအပ်လာတဲ့အချိန်မှာသာ main memory ထဲမှာ load လုပ်ပါတယ်။ ဒါမျိုးကိုတော့ Dynamic loading လို့ခေါ်ပြီးတော့ system အတွက် efficiency ပိုကောင်းစေတယ်လို့ပြောလို့ရပါတယ်။ main memory ပေါ်မှာ တစ်ခါတည်းနဲ့ completely compile လုပ်သွားတဲ့ program ကို static linking နဲ့လုပ်သွားတယ်လို့ပြောလို့ရပါတယ်။ ဘာလို့လဲဆိုတော့ တစ်ခြား ဘာ modules တွေကိုမှ လှမ်းဆွဲယူစရာမလိုဘဲ single program တည်းနဲ့ပဲ compile လုပ်လို့ရအောင် linking လုပ်ထားတဲ့အတွက်ပါ။ Dynamic loading နဲ့သွားတဲ့ program ကတော့ modules တွေအကုန်လုံး တစ်ခါတည်း link မလုပ်ထားဘဲနဲ့ လိုတဲ့အချိန်မှသာ link လုပ်တဲ့အတွက် dynamic linking လုပ်တယ်လို့ခေါ်ပါတယ်။
