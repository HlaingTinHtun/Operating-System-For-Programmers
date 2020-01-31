## I/O Management

![Image of Abstraction](https://raw.githubusercontent.com/HlaingTinHtun/Operating-System-For-Programmers/master/images/iomanagement.png)

I/O devices တွေကို manage လုပ်ဖို့ဆိုတာကလည်း OS ရဲ့ အရေးကြီးတဲ့ အပိုင်းတစ်ခုဖြစ်ပါတယ်။ I/O device ဆိုတာကတော့ အားလုံးသိတဲ့အတိုင်း keyboard , mouse , drivers, usb devices စတာတွေပေါ့။ စဉ်းစားကြည့်မယ်ဆို I/O system ရဲ့ အလုပ်လုပ်ပုံက အရမ်းမရှုပ်ပါဘူး။ 
-	I/O request တွေကို system ကနေယူမယ်။
-	ရလာတာတွေကို I/O device တွေဆီကိုပို့ပေးမယ်။
-	Device တွေကနေပြန်ရလာတဲ့ response ကိုယူပြီး application level ဆီကိုပို့ဖို့ အလုပ်လုပ်မယ်။
I/O devices တွေထဲမှာ data တွေကို block လိုက်ပို့တဲ့ block device နဲ့ character တစ်ခုခြင်းဆီလိုက်ပို့တဲ့ character device ဆိုပြီးကွဲပါသေးတယ်။ block device ဆိုရင် data တွေ communicate လုပ်တဲ့အချိန် block လိုက်ပို့တဲ့ကောင်တွေ၊ ဥပမာ hard drive တို့ ဘာတို့ ၊ character လိုက်ပို့တဲ့ကောင်တွေကတော့ system ထဲမှာရှိတဲ့ console devices တွေ serial devices တွေပေါ့။

နောက်ပြီးတော့ ကျနော်တို့ driver တွေအကြောင်းကြားဖူးမယ်ထင်တယ်။ laptop ဝယ်ရင် driver ခွေတွေဘာတွေပေးတာတို့ ဒါမှမဟုတ် driver လိုနေလို့ driver သွင်းရတာတို့။ I/O device တိုင်းမှာလည်း driver တွေလိုတယ်။ ဥပမာ touch pad driver မရှိဘူးဆို touch pad ကသုံးလို့ရမှာမဟုတ်ဘူး။ ဒါကြောင့် OS က I/O devices တွေကို handle လုပ်ဖို့ဆိုရင် driver တွေရဲ့ အကူအညီကိုသုံးပြီး handle လုပ်ပါတယ်။

ကျနော်အပေါ်မှာ data communicate လုပ်တဲ့ဆိုတဲ့အကြောင်းလေးပါခဲ့တယ်။ ဆိုတော့ system CPU က အဲ့ဒီ I/O devices တွေဆီကို ဘယ်လိုနည်းတွေနဲ့ communicate လုပ်လဲဆိုတာမေးစရာရှိပါတယ်။ communicate လုပ်တဲ့ instructions ပုံစံသုံးမျိုးရှိပါတယ်။

Special Instruction I/O
သူ့ကိုဘာလို့ special instruction လို့ခေါ်လည်းဆိုတော့ I/O devices တွေကို control လုပ်ဖို့ကို CPU ဆီက Instructions တွေနဲ့တိုက်ရိုက်သုံးပြီးလုပ်လို့ပဲ။ အဲ့ဒီ Instructions တွေအတိုင်း I/O devices တွေဆီကနေ data တွေ communicate လုပ်ဖို့ကိုဆောင်ရွက်ပါတယ်။

Memory-mapped I/O
ဒီအပိုင်းမှာတော့ data communication လုပ်ဖို့ကို CPU ကနေတိုက်ရိုက်မသွားတော့ဘူး၊ သတ်မှတ်ပေးထားတဲ့ memory space ပေါ်ကနေပဲ communicate လုပ်သွားတယ်။ အဲ့ဒီ memory space အတွက်ကိုလည်း OS က allocate လုပ်ပေးထားတာ၊ ဆိုလိုချင်တာက CPU နဲ့ I/O devices တွေကြားထဲမှာ memory space တစ်ခုခံထားပြီး data တွေ transfer လုပ်တယ်။ အဲ့လို transfer လုပ်တဲ့အချိန်မှာလည်း I/O devices တွေက CPU နဲ့ကို async ပုံစံနဲ့ communicate လုပ်တယ်။ process ပြီးပြီဆိုရင် CPU လည်း stop ဖြစ်သွားတယ်။ memory-mapped I/O ကို high speed transfer လုပ်တဲ့ devices တွေမှာသုံးတယ်၊ ဥပမာ disk drives တွေလိုကောင်တွေ။

Direct Memory Access
DMA လို့လည်းခေါ်တယ်။ အပေါ်မှာကျနော်ပြောထားတဲ့ memory-mapped က high speed devices တွေအတွက်ဆိုပေမယ့် စဉ်းစားစရာရှိတာက keyboard တို့လို slow speed devices တွေကျတော့ ဘယ်လိုလုပ်မလဲပေါ့၊ သူတို့က byte တစ်ခုခြင်းဆီလွှတ်နေတာ၊ ဆိုတော့ CPU ကအဲ့ဒါကိုထိုင်စောင့်ပြီး အလုပ်လုပ်နေရင် waste အများကြီးဖြစ်သွားတယ်။ အဲ့နေရာမှာ အခုပြောမယ့် DMA ဆိုတာဝင်လာတာပဲ။ CPU က I/O devices တွေနဲ့ communicate လုပ်ဖို့အတွက် DMA ကို ခွင့်ပေးလိုက်တယ်။ communication လုပ်တဲ့အချိန်မှာ devices တွေနဲ့ DMA တိုက်ရိုက်လုပ်ပစေ၊ သူဝင်မပါတော့ဘူးဆိုတဲ့ သဘော (include main memory between DMA and devices tho)။ လိုအပ်တဲ့ authorities မှန်သမျှကိုလဲ DMA ကို grant လုပ်ပေးထားတယ်။ သူဝင်ပါမယ့်အချိန်က communication စလုပ်မယ့်အချိန်ရယ် အကုန်လုပ်ပြီးသွားလို့ end ဖြစ်သွားတဲ့အချိန်ပဲဝင်ပါတော့မယ်။ 
DMA ကလည်း data transfer လုပ်တဲ့နေရာမှာ manage လုပ်နိုင်ဖို့အတွက် DMA controller ဆိုတာကိုသုံးသေးတယ်။ အဓိက ကတော့ data transfer လုပ်တဲ့နေရာမှာ handle လုပ်နိုင်ဖို့ပဲ၊ ဥပမာ data transfer လုပ်တဲ့နေရာမှာ source & destinations သတ်မှတ်တာတို့၊ transfer ဖြစ်သွားတဲ့ bytes တွေ count ထားတာတို့ စသည်ဖြင့် transfer လုပ်တဲ့နေရာမှာ လိုအပ်တာတွေကို handle လုပ်ပေးတယ်။

ဒီလောက်ဆိုရင်တော့ I/O devices တွေ OS ပေါ်မှာဘယ်လိုအလုပ်လုပ်နေလဲဆိုတဲ့ အကြောင်းကို general abstraction ကောင်ကောင်းရသွားပါပြီ၊ ထပ်ပြီးလေ့လာချင်သေးတယ်ဆိုရင် DMA Controller တွေရဲ့ အလုပ်လုပ်ပုံတွေ၊ data တွေ transfer ဘယ်လိုလုပ်သွားလဲဆိုတဲ့ အသေးစိတ်တွေထပ်လေ့လာလို့ရပါသေးတယ်။

See ya.



