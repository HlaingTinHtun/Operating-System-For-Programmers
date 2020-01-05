## Inter Process Communication

![Image of Abstraction](https://raw.githubusercontent.com/HlaingTinHtun/Operating-System-For-Programmers/master/images/inter_process_communication.png)

Process တစ်ခုကိုခွဲချလိုက်ပြီဆို Independent ဖြစ်တဲ့ process နဲ့ co-operating ဖြစ်တဲ့ Process ဆိုပြီး နှစ်မျိုးရှိပါတယ်။ မှတ်ရတာတော့ လွယ်တယ်၊ independent process က အခြားသော process တွေ execution ဖြစ်နေတဲ့အချိန်မှာသူ့ကိုဘာမှလာ affect မဖြစ်ဘူး၊ co-operating ကတော့ဖြစ်တယ်။ သူ့တို့ရဲ့ သဘောတရားကိုကြည့်ပြီးတော့၊ သြော် independent process က system အတွက်ပိုကောင်းနိုင်တယ်လို့ထင်ရင် မှားမယ်။ တစ်ကယ်တမ်းတော့ co-operating process က ပိုပြီးတော့ system ရဲ့ computation speed အတွက်ရော တစ်ခြားသော efficiencies တွေကိုပါပိုကောင်းစေပါတယ်။ ဘာအကြောင်းတွေကြောင့်လဲဆိုတာ ဆက်ဖတ်ကြည့်ရအောင်။  

IPC လို့ခေါ်တဲ့ inter process communication က process တစ်ခုနဲ့တစ်ခု ချိတ်ဆက်လို့ရအောင် ပြီးတော့ သူတို့ရဲ့ actions တွေကို sync လုပ်လို့ရအောင် ပြုလုပ်ပေးနိုင်တယ်။ အဲ့လို ချိတ်ဆက်တာကို co-operation ရဲ့ method လို့ ယူဆလို့ရတယ်။ Process တွေတစ်ခုနဲ့တစ်ခုချိတ်ဆက်တဲ့နေရာမှာ shared memory နဲ့ message parsing ဆိုပြီး နည်းနှစ်မျိုးနဲ့ ချိတ်ဆက်နိုင်ပါတယ်။

Shared Memory Method
Process 1 နဲ့ process 2 ရှိတယ်ဆိုကြပါစို့။ နှစ်ခုလုံးက တစ်ပြိုင်နက်တည်းမှာ execute လုပ်နေတယ်၊ process တစ်ခုနဲ့ တစ်ခုလည်း resource တွေလည်း share လုပ်ရင်းနဲ့ပေ့ါ။ ဘယ်လိုလုပ်လဲဆိုတော့ Process 1 က သူ execute လုပ်ခဲ့ရတဲ့ အချိန်က resources တွေ၊ computations တွေနဲ့ ပတ်သတ်တဲ့ အချက်အလက်တွေကို generate လုပ်ပြီးတော့ shared memory ထဲမှာ record တွေမှတ်ခဲ့တယ်။ process 2 က အဲ့ဒီ shared လုပ်ထားတဲ့ Information တွေကိုသုံးချင်ပြီဆို shared memory ထဲမှာ record လုပ်ထားတာရှိမရှိကြည့်တယ်၊ ရှိတယ်ဆို လှမ်းယူသုံးလိုက်တယ်။ ဆိုတော့ shared memory method ကတော့ရှင်းတယ်။ process တွေ shared memory ကိုသုံးပြီး information တွေလှမ်းယူလို့ရတယ်။ ကိုယ့်မှာရှိတဲ့ Information တွေကိုလည်း တစ်ခြား process တွေအတွက် shared memory ထဲမှာ record လုပ်ပေးထားလို့ရတယ်။ ပြောရမယ်ဆိုရင် producer နဲ့ consumer လိုပဲပေါ့။ producer ကထုတ်ပေးတယ်၊ consumer ကသုံးပေးတယ်။ သူတို့နှစ်ခုကြားမှာ shared memory ကိုက bridge တစ်ခုအနေနဲ့ လုပ်ဆောင်ပေးတယ်။

Message Parsing Method
အခု method မှာကတော့ shared memory တွေဘာတွေသုံးစရာမလိုတော့ဘဲနဲ့ communicate လုပ်ကြပါတယ်။ ဘယ်လိုလုပ်ကြလဲဆိုတော့ communication link တစ်ခုထုတ်ပေးပါတယ်၊ အဲ့အပေါ်ကတော့ communicate လုပ်ကြပါတယ်။ အဲ့ link ကရှိပြီးသားဆိုရင်တော့ ထပ်ထုတ်စရာမလိုတော့ဘူးပေါ့။ communicate လုပ်တဲ့ ပုံစံကလည်းရှင်းတယ်။ basic primitives ပုံစံလေးတွေပဲသုံးပြီးတော့ လုပ်သွားတာ။ primitive နှစ်ခုရှိမယ်၊ send လုပ်မယ်၊ receive လုပ်မယ်။
Send လုပ်တဲ့အချိန်မှာ param နှစ်ခုထည့်ပြီး send လုပ်လို့ရတယ်။ (message ရယ်၊ ပို့မယ့် destination ရယ်(optional))
Receive လုပ်တဲ့အချိန်မှာလည်း param နှစ်ခုသုံးလို့ရတယ်၊ (message ရယ်၊ လက်ခံရယူမယ့် host name ရယ်(optional))
Message size ကတော့ fixed လည်းဖြစ်နိုင်သလို vary လည်း ဖြစ်နိုင်ပါတယ်။ fixed or variable ပေါ်မူတည်ပြီး OS designer နဲ့ programmer ရဲ့ လုပ်ရမယ့်အပိုင်းတွေကလည်း ကွဲပြားသွားမှာပါ၊ အဲ့အပိုင်းကိုတော့ ကျနော် အကျယ်မချဲ့တော့ပါဘူး။
အိုကေ ဒါဆိုရင် message ကို ထပ်ပြီး analyze လုပ်ကြည့်မယ်ဆို သူ့မှာ header အပိုင်းနဲ့ body အပိုင်းဆိုပြီး ထပ်ကွဲသေးတယ်။ header အပိုင်းမှာတော့ message type,length တို့ source and destination id တို့နဲ့ တစ်ခြား control information တွေလည်းပါပါတယ်။ control information ဆိုတာကတော့ sequence တို့ priority တို့ကိုသိမ်းထားတာပေ့ါ။ body အပိုင်းမှာတော့ ပုံမှန်အတိုင်း message ရဲ့ content ပါတယ်။ ပုံမှန်အားဖြင့်ဆိုရင်တော့ message တွေက FIFO structure နဲ့ အလုပ်လုပ်ပါတယ်။

ဒါဆိုရင်တော့ IPC အကြောင်းတောတော်လေးသိသွားမယ်လို့ထင်ပါတယ်။ တစ်ကယ်တော့ မဟုတ်ပါဘူး :3၊ စတာပါ ယေဘုယျအားဖြင့် လောက်တော့ တော်တော်လေးသိသွားပြီလို့ထင်ပါတယ်။ တစ်ကယ်တမ်း ထပ်ပြီး detail dive လုပ်လို့ရပါသေးတယ်။ ဥပမာ shared memory တို့ message parsing တို့ ရဲ့ အလုပ်လုပ်ပုံ အသေးစိတ်တွေကို ထပ်ပြီးတော့ လေ့လာကြည့်လို့ရပါသေးတယ်။

See ya.
