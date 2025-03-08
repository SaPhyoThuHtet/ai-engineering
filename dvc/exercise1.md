### Exercises
DVC ဖြင့် ဒေတာဗားရှင်းထိန်းချုပ်ခြင်းအတွက် အဆင့်ဆင့်လမ်းညွှန် (Google Drive တွင် သိမ်းဆည်းမည်)

DVC သည် ဒေတာနှင့် မော်ဒယ်များကို ဗားရှင်းထိန်းချုပ်ရန် အသုံးပြုသော ကိရိယာတစ်ခုဖြစ်ပြီး Git နှင့် တွဲဖက်အသုံးပြုနိုင်သည်။ ဤလမ်းညွှန်တွင် Google Drive ကို ဒေတာသိမ်းဆည်းရာနေရာအဖြစ် အသုံးပြုပြီး DVC ကို အသုံးပြုနည်းကို အဆင့်ဆင့်ရှင်းပြပါမည်။

#### လိုအပ်သော ကိရိယာများ
1. **Git** - ကုဒ်နှင့် DVC ဖိုင်များကို ဗားရှင်းထိန်းချုပ်ရန်။
2. **DVC** - ဒေတာနှင့် မော်ဒယ်များကို ဗားရှင်းထိန်းချုပ်ရန်။
3. **Google Drive** - ဒေတာဖိုင်များကို သိမ်းဆည်းရန်။
4. **Python** - DVC သည် Python အခြေခံဖြစ်သည်။

---

### အဆင့် ၁: ပတ်ဝန်းကျင်ပြင်ဆင်ခြင်း
1. **Git ထည့်သွင်းခြင်း**
   - သင့်စက်တွင် Git ထည့်သွင်းပါ။ အောက်ပါ command ဖြင့် စစ်ဆေးနိုင်သည်။
git --version

- မရှိပါက၊ သင့် OS အလိုက် ထည့်သွင်းပါ (ဥပမာ၊ Ubuntu တွင် `sudo apt install git`)။

2. **DVC ထည့်သွင်းခြင်း**
- Python ရှိပါက၊ အောက်ပါ command ဖြင့် DVC ထည့်သွင်းပါ။
  pip install dvc

  - Google Drive အသုံးပြုမည်ဖြစ်သောကြောင့် ထပ်မံထည့်သွင်းပါ။
  - pip install "dvc[gdrive]"
 

3. **Google Drive ပြင်ဆင်ခြင်း**
- Google Drive တွင် ဖိုလ်ဒါတစ်ခု ဖန်တီးပါ (ဥပမာ၊ "DVC_Data")။ ဤဖိုလ်ဒါသည် ဒေတာဖိုင်များကို သိမ်းဆည်းမည့်နေရာဖြစ်သည်။

---

### အဆင့် ၂: Git Repository စတင်ဖန်တီးခြင်း
1. သင့်ပရောဂျက်ဖိုလ်ဒါသို့ သွားပါ။
mkdir my_project
cd my_project
2. Git ကို စတင်အသုံးပြုပါ။
git init

---

### အဆင့် ၃: DVC စတင်အသုံးပြုခြင်း
1. DVC ကို စတင်ပြင်ဆင်ပါ။
dvc init
- ဤအဆင့်တွင် DVC သည် Git နှင့် ချိတ်ဆက်မည်ဖြစ်သည်။
2. Git ဖြင့် ကနဦး commit တစ်ခုပြုလုပ်ပါ။
git commit -m "Initialize DVC"


---

### အဆင့် ၄: Google Drive ကို Remote Storage အဖြစ် ချိတ်ဆက်ခြင်း
1. Google Drive ကို DVC remote အဖြစ် ထည့်သွင်းပါ။
   dvc remote add -d myremote gdrive://<your_folder_id>
   - `<your_folder_id>` သည် Google Drive ဖိုလ်ဒါ၏ URL တွင် ပါသော ID ဖြစ်သည်။ ဥပမာ၊ URL သည် `https://drive.google.com/drive/folders/1a2b3c4d` ဆိုပါက ID မှာ `1a2b3c4d` ဖြစ်သည်။

2. Google Drive ချိတ်ဆက်မှုအတွက် အထောက်အထားစစ်ဆေးခြင်း
- ပထမအကြိမ် run လုပ်သောအခါ၊ DVC သည် Google Drive ချိတ်ဆက်ရန် browser တွင် လင့်ခ်တစ်ခုပြပေးမည်။ ၎င်းကို နှိပ်ပြီး ခွင့်ပြုချက်ပေးပါ။
- ထွက်ပေါ်လာသော code ကို terminal တွင် ထည့်ပါ။

3. Remote ပြင်ဆင်မှုကို Git တွင် သိမ်းပါ။
   git commit .dvc/config -m "Add Google Drive as DVC remote"

   
---

### အဆင့် ၅: ဒေတာဖိုင်ထည့်သွင်းခြင်း
1. သင့်ဒေတာဖိုင်ကို ပရောဂျက်ထဲသို့ ထည့်ပါ (ဥပမာ၊ `data.csv`)။
   dvc add data.csv
   - ဤအဆင့်တွင် `data.csv.dvc` ဖိုင်တစ်ခု ဖန်တီးပေးမည်။

3. Git ဖြင့် ထိန်းချုပ်မှုဖိုင်များကို ထည့်ပါ။
git add data.csv.dvc .gitignore
git commit -m "Add data.csv to DVC"


---

### အဆင့် ၆: ဒေတာကို Google Drive သို့ တင်ခြင်း
1. ဒေတာကို Google Drive သို့ push လုပ်ပါ။
dvc push
- ဒေတာဖိုင်ကြီးများသည် Google Drive သို့ တင်သွားမည်ဖြစ်ပြီး local တွင် မရှိတော့ပါ။

---

### အဆင့် ၇: ဒေတာပြန်ယူခြင်း
1. လိုအပ်ပါက Google Drive မှ ဒေတာကို ပြန်ယူနိုင်သည်။
   dvc pull
   - ဤ command သည် `data.csv` ကို ပြန်လည်ဒေါင်းလုဒ်လုပ်ပေးမည်။

---

### အဆင့် ၈: ဒေတာပြင်ဆင်မှုနှင့် ဗားရှင်းအသစ်ထည့်ခြင်း
1. ဒေတာကို ပြင်ဆင်ပါ (ဥပမာ၊ `data.csv` ကို အသစ်ဖြည့်ပါ)။
2. ပြန်လည် DVC ဖြင့် ထိန်းချုပ်ပါ။
   dvc add data.csv
git add data.csv.dvc
git commit -m "Update data.csv"
dvc push

---

### အဆင့် ၉: ဗားရှင်းများကို ပြန်စစ်ဆေးခြင်း
1. Git log ဖြင့် ဗားရှင်းများကို ကြည့်ပါ။
git checkout <commit_hash>
dvc checkout
