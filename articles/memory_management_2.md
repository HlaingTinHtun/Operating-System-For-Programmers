## Memory Management Part2

![Image of Abstraction](https://raw.githubusercontent.com/HlaingTinHtun/Operating-System-For-Programmers/master/images/memory_management_2.jpg)

Swapping
swapping အကြောင်းကိုတော့ scheduling article မှာလည်းပြောသင့်သလောက်တော့ ပြောထားပြီးပါပြီ။ main memory ထဲမှာလက်ရှိ run နေတဲ့ process ကို secondary storage တစ်ခုထဲကို move လုပ်ထားပြီး အချိန်တစ်ခုကြာမှ main memory ထဲကို ပြန်ထည့်ပြီး run တယ်။ (ဘာလို့ move လုပ်ရလဲဆိုတာကတော့ run ရမယ့် process ရဲ့ memory ကကြီးလို့မဆန့်လို့ခွဲထုတ်တာလိုဖြစ်နိုင်သလို process က စောင့်ရမယ့် task တွေပါလာမယ်ဆိုရင်လဲ secondary storage ထဲကို move လုပ်ပြီးစောင့်ပါတယ်) ။ swapping လုပ်တာက performance ကိုထိခိုက်စေနိုင်ပေမဲ့ တစ်ဖက်ကကြည့်ရင်လည်း multiprocessing ကိုလုပ်နိုင်နေပါတယ်။ တစ်နည်းအားဖြင့် swapping လုပ်တာကို memory compaction လို့လဲခေါ်ပါတယ်။

Memory allocation
main memory မှာ OS ရှိတဲ့ Low memory နဲ့ user processes တွေကိုလုပ်တဲ့ high memory ဆိုပြီး partition နှစ်မျိုးရှိပါတယ်။ Memory allocate လုပ်တဲ့နေရာမှာလည်း single partition နဲ့ multiple partition allocation ဆိုပြီးခွဲထားပါတယ်။

single partition allocation
user processes တွေကြောင့်ဖြစ်လာတဲ့ side effect တွေကြောင့် OS ရဲ့ source code နဲ့ data တွေကို changes လာဖြစ်စေနိုင်ပါတယ်၊ဒါပေမဲ့ OS ကို အဲ့ဒီ threats တွေအတွက် protect လုပ်ထားပြီးသားဖြစ်ပါတယ်။ ထိုနည်းအတူ user processes အချင်းချင်းကိုလည်း changes တွေမဖြစ်အောင် protect လုပ်ထားဖို့လိုပါတယ်။ အဲ့အတွက်ကြောင့်မို့လို့ relocation registers တွေကိုကိုသုံးပါတယ်။ relocation register မှာတော့ အသေးဆုံးဖြစ်တဲ့ physical address ပါမယ်၊ limit register ထဲမှာတော့ logical address range တစ်ခုပါပါမယ်။ relocation နဲ့ limit registers တွေ အရ logical address တိုင်းဟာ limit register ထက်ငယ်နေရပါမယ်။ MMU(memory management unit) က relocation register ထဲက logical address တွေကို map လုပ်ပါတယ်။ map လုပ်ထားတဲ့ address တွေကိုမှ memory ထဲကိုနောက်ဆုံးအနေနဲ့ပို့လိုက်ပါတယ်။

multiple partition allocation (contiguous memory allocation)
memory ကို fixed size partitions လေးတွေအဖြစ်ပိုင်းထားပါတယ်။ contiguous allocation မှာ process တစ်ခုကို အဲ့ဒီ ပိုင်းထားတဲ့ memory block တစ်ခုအပေါ်မှာ allocate လုပ်ပါတယ်။ partition တစ်ခုကို process တစ်ခုပုံစံမျိုးပေ့ါ။ partition တစ်ခုက free ဖြစ်နေတဲ့အချိန်မှာ process တစ်ခုကို queue ထဲကနေ select လုပ်ပြီး allocate လုပ်ပါတယ်။ အဲ့လို free ဖြစ်နေတဲ့ partition block လေးတွေကို holes လို့လဲခေါ်ပါတယ်။ process ပြီးသွားတဲ့အချိန်မှာ partition free up ဖြစ်ပြီးတော့ နောက် process တွေကိုဆက်ပြီး allocate လုပ်သွားပါတယ်။

Fragmentation
Memory ထဲမှာ processes တွေက load လာလုပ်လိုက် remove လုပ်သွားလိုက်လုပ်နေကြပါတယ်။ အဲ့လိုလုပ်ပါများလာတဲ့အခါ free ဖြစ်နေတဲ့ memory space တွေက အပိုင်းသေးသေးလေးတွေအဖြစ် ပြန့်ကျဲသွားပါတယ်။ process တစ်ခု allocate လာလုပ်တော့မယ့်အချိန်မှာ memory block လေးတွေကသေးနေတဲ့အတွက် အသုံးမဝင်တော့တာမျိုးဖြစ်တာကို fragmentation ဖြစ်သွားတယ်လို့ခေါ်ပါတယ်။
fragmentation မှာ နှစ်မျိုးရှိပါတယ်။
Internal fragmentation
process တစ်ခုကို allocate လုပ်ပေးမယ့် memory က လုပ်ပေးရမယ့် memory ထက်ပိုပြီးတော့ ရှိနေပါတယ်။ allocate လုပ်ပြီးတဲ့အခါမှာ memory အပိုတွေထွက်လာပေမဲ့လည်း တစ်ခြား process တွေအတွက် allocate မလုပ်ပေးနိုင်ပါဘူး။

External fragmentation
Process တစ်ခုကို allocate လုပ်ပေးဖို့လုံလောက်ပေမဲ့လည်း contiguous မဖြစ်တဲ့အတွက်ကြောင့်လုပ်ပေးလို့မရပါဘူး။

အဲ့ဒီ fragmentation ဖြစ်တာတွေကိုကာကွယ်နိုင်ဖို့အတွက် Paging ဆိုပြီး technique တစ်ခုရှိပါတယ်။ virtual memory တွေကို ကောင်းကောင်းကစားနိုင်ဖို့အတွက် paging technique ကအရေးပါပါတယ်။ paging က fragmentation ကိုဘယ်လိုကာကွယ်လဲဆိုတော့ process address space ကိုတူညီတဲ့ partition blocks တွေအဖြစ်ခွဲချလိုက်ပါတယ်။ ဥပမာ process တစ်ခုလာပြီဆို တစ်ခါတည်း ပစ်သွင်းလိုက်မယ့်အစား process က 1000 bytes ယူမယ်ဆို 100bytes အဖြစ် block 10 ခုခွဲချလိုက်ပါတယ်၊ ဒါက ဥပမာပြတာပါ။ size က (2 power ဖြစ်ပြီး 512bytes to 8192 bytesအတွင်းရှိနိုင်ပါတယ်)။ အဲ့လိုblocks လေးတွေကို pages တွေလို့ခေါ်ပါတယ်။ process address space အတိုင်းပဲ main memory ကိုလဲ pages တွေအတိုင်းခွဲချလိုက်ပြီးတော့ အလုပ်လုပ်လိုက်ခြင်းအားဖြင့် fragmentation ကို avoid လုပ်ပါတယ်။

Segmentation
Segmentation ဆိုတာကလဲ paging လိုပဲ memory management လုပ်တဲ့ technique နောက်တစ်ခုဖြစ်ပါတယ်။ paging နဲ့မတူတဲ့အချက်က paging က fixed size တွေအဖြစ်ခွဲပေမယ့် segmentation က size တွေက variable ဖြစ်ပါတယ်။ segment တိုင်းမှာလုပ်ဆောင်ရမယ့် program ရဲ့ functions တွေ data structures တွေနဲ့ တစ်ခြား utility functions တွေလဲပါပါတယ်။ segment တိုင်းအတွက်ကို os က segment map table တစ်ခုထားပြီးတော့ အလုပ်လုပ်ပါတယ်။  table ထဲမှာ segment number, segment size, memory location address တွေပါပါတယ်။

အခုပြောသွားတဲ့ paging မှာရော segmentation မှာရောကောင်းတဲ့အချက်တွေရော ဆိုးတဲ့အချက်တွေပါရှိပါသေးတယ်။ အဲ့ဒါကိုတော့ တစ်ချက် research ထပ်လုပ်သင့်ပါတယ်။

အခုလောက်ဆိုရင်တော့ memory management အပိုင်းက module တော်တော်များများကို သိသွားပြီပဲဖြစ်ပါတယ်။ ဒါပေမဲ့ ဒီထက်ပိုပြီးနက်နဲတဲ့အပိုင်းတွေရှိသေးတဲ့အတွက် မိမိဘာသာဆက်လက်ပြီးလေ့လာကြပါဦးလို့ တိုက်တွန်းလိုက်ပါတယ်။
