## Virtual Memory

![Image of Abstraction](https://raw.githubusercontent.com/HlaingTinHtun/Operating-System-For-Programmers/master/images/virtualmemory.PNG)

ကျနော်အရင် article တွေမှာ memory management အကြောင်းကို part 1 2 ခွဲပြီးရေးခဲ့ဖူးပါတယ်။ အခု virtual memory ဆောင်းပါးမှာ memory management တုန်းက အကြောင်းတွေပြန်ပါတဲ့အတွက် အဲ့ဒီ article တွေပြန်ဖတ်ဖို့ recommend လုပ်ပါတယ်။ link တွေကို comment မှာတင်ပေးထားပါတယ်။

ဒါဆိုစလိုက်ကြရအောင်။
Computer တစ်လုံးက သူ့မှာ Physically သွင်းထားတဲ့ memory ထက်ပိုပြီးတော့ သုံးနိုင်ပါတယ်။ ဘာလို့လဲဆိုတော့ virtual memory ကြောင့်ပါ။ virtual memory က hard disk ကိုသုံးပြီးတော့ ram ကို emulate လုပ်ပေးပါတယ်။ အသေးစိတ်ပြောရမယ်ဆိုရင် ဥပမာ program တစ်ခု load လုပ်လိုက်ပြီဆိုပါစို့ ၊ ဒါပေမယ့် run လိုက်တဲ့ program က physical memory RAM ထက်ပိုပြီး memory ကုန်မှာ ၊ ပုံမှန်အတိုင်းဆို virtual memory သာမရှိရင် program က crash ဖြစ်သွားလိမ့်မယ်၊ ဘာလို့ဆို လိုအပ်တဲ့ memory က ရှိနေတဲ့ physical memory(RAM) ထက်ပိုများနေတာကြောင့်။ ဒီနေရာမှာ virtual memory ဆိုတာဝင်လာပြီး Program ရဲ့ လိုအပ်တဲ့ memory ကို hard disk သုံးပြီးတော့ ram ကို emulate လုပ်ရင်းထိန်းပေးသွားတယ်။  တစ်ခုတော့ ရှိတာပေါ့၊ RAM ကမလောက်လို့ disk ထဲက virtual memory နဲ့ run နေတဲ့ အချိန်မှာတော့ program ရဲ့ performance ကအတော်လေးနှေးပါလိမ့်မယ်။ သိတဲ့အတိုင်းပဲ RAM နဲ့ disk နဲ့ speed က အဆတစ်ထောင်လောက်ကွာပါတယ်။

Virtual memory ကိုသုံးရတဲ့ အဓိက အချက်ကတော့ နှစ်ချက်၊ ပထမတစ်ချက်ကတော့ အခုပြောခဲ့တဲ့အတိုင်း disk ကိုသုံးပြီးတော့ physical memory ကို extend လုပ်ပေးနိုင်တယ်၊ နောက်တစ်ချက်က ကျနော် memory management ဆောင်းပါးတွေရေးတုန်းကပြောခဲ့တယ်။ virtual address တွေကို physical address အဖြစ်ပြောင်းပေးတယ်။ (Memory management unit လို့ခေါ်တဲ့ကောင်က ပြောင်းပေးတာ)၊ ပြန်နွေးတဲ့အနေနဲ့ memory management က တစ်ပိုဒ်လောက်ကိုပြန်ထည့်ပေးထားတယ်။

process တစ်ခုက code တွေဆီကနေ reference ယူထားတဲ့ logical address (memory cell, storage element, network host etc.) တွေရှိပါတယ်။ program တစ်ခု memory allocate လုပ်တဲ့အချိန်မှာ OS က logical address တွေကို memory management unit (MMU) ကိုသုံးပြီး physical address အဖြစ် map လုပ်ပါတယ်။ အသေးစိတ်ရှင်းရမယ်ဆို logical address က program တစ်ခု run လိုက်တဲ့အချိန်မှာ CPU က generate လုပ်ပေးထားတာဖြစ်ပြီး physically မရှိဘဲ virtually ပဲရှိပါတယ်။ physical address ကတော့ memory ထဲမှာကို physical location နဲ့ရှိပါတယ်။ MMU ကတစ်ခုနဲ့တစ်ခုကို correspond လုပ်နိုင်ဖို့အတွက် ကြားခံ computation လုပ်ပေးတဲ့အရာတစ်ခုလို့ပြောလို့ရပါတယ်။

အိုကေ ဒါဆို virtual memory ကိုပြန်ဆက်ရအောင်၊ ဒီနေရာမှာ virtual memory နဲ့ physical memory ကိုရောသွားနိုင်ပါတယ်။ ရောစရာမလိုပါဘူး၊ virtual memory က program က သုံးတယ်၊ physical memory RAM ကိုတော့ system ရဲ့ hardware တွေကသုံးပါတယ်။ ဆိုတော့ ပြန်သုံးသပ်ရမယ်ဆိုရင် program ကို run လိုက်ပြီဆို virtual memory ကိုသုံးလိုက်တယ်၊ ပြီးရင် MMU က vm ကို pm အဖြစ်ပြောင်းလိုက်ပြီး system ကို consume လုပ်စေပါတယ်။

virtual memory ကိုတော့ ယေဘုယျအားဖြင့် demand paging technique ကိုသုံးပြီးတော့ ဆောက်ပါတယ်။ demand paging မှာ secondary storage တစ်ခုရှိမယ်၊ disk ပေါ့။ program တစ်ခု run လိုက်လို့ RAM က memory လိုအပ်တဲ့ အချိန်မှသာ disk ကနေယူသုံးတယ်။ swapping technique သုံးတဲ့ paging system နဲ့သွားဆင်ပါတယ်။ (swapping တွေ paging တွေကို memory management article မှာရေးပေးခဲ့ပါတယ်။)

နောက်ထပ်ထပ်ပြီးလေ့လာချင်သေးရင်တော့ virtual memory ကိုတည်ဆောက်တဲ့ demand paging အသေးစိတ်တို့ segmentation အသေးစိတ်တို့ထပ်လေ့လာလို့ရပါသေးတယ်။
