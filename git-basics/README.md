### General Knowledge

Git ဆိုတာက version control system တစ်ခုဖြစ်ပြီး၊ software development မှာ code တွေကို စီမံခန့်ခွဲဖို့၊ ပူးပေါင်းလုပ်ဆောင်ဖို့နဲ့ changes တွေကို ခြေရာခံဖို့အတွက် အသုံးပြုပါတယ်။ ဒီမှာတော့ Git ကို ဘယ်လို အသုံးပြုရမလဲဆိုတာကို လွယ်ကူရှင်းလင်းစွာ ရှင်းပြပေးသွားမှာပါ။

Git ကို Install လုပ်နည်း
1. Windows မှာ Git Install လုပ်နည်း
Git ကို Git ရဲ့ official website မှာ download လုပ်ပါ။

Download လုပ်ထားတဲ့ installer ကို run ပါ။

Installation လုပ်နေစဉ်မှာ default settings တွေကို သုံးပြီး Next ကို နှိပ်သွားပါ။

Installation ပြီးသွားရင် Git Bash ကို ဖွင့်ပြီး အောက်ပါ command ကို run ပါ:

git --version
ဒါက Git version ကို ပြသပါလိမ့်မယ်။

2. macOS မှာ Git Install လုပ်နည်း
Terminal ကို ဖွင့်ပါ။

Homebrew ကို အသုံးပြုပြီး Git install လုပ်ပါ:

brew install git
Installation ပြီးရင် အောက်ပါ command ကို run ပါ:

git --version
Git version ကို ပြသပါလိမ့်မယ်။

3. Linux (Ubuntu/Debian) မှာ Git Install လုပ်နည်း
Terminal ကို ဖွင့်ပါ။

အောက်ပါ command ကို run ပါ:

sudo apt update
sudo apt install git
Installation ပြီးရင် အောက်ပါ command ကို run ပါ:


git --version
Git version ကို ပြသပါလိမ့်မယ်။

#### Git ကို စတင်အသုံးပြုနည်း
1. Git Configuration (ပြင်ဆင်ခြင်း)
Git ကို စတင်သုံးဖို့အတွက် သင့်ရဲ့ username နဲ့ email ကို သတ်မှတ်ပေးရပါမယ်။ Terminal (သို့) Git Bash မှာ အောက်ပါ commands တွေကို run ပါ:

git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
2. Repository စတင်ခြင်း
Project folder ထဲမှာ Git repository စတင်ဖို့အတွက် အောက်ပါ command ကို run ပါ:

git init
ဒါက .git folder တစ်ခုကို ဖန်တီးပေးပါလိမ့်မယ်။

3. File တွေကို Track လုပ်ခြင်း
File တွေကို Git မှာ track လုပ်ဖို့အတွက် git add command ကို အသုံးပြုပါ:

git add filename.txt
ဒါမှမဟုတ် ဖိုင်အားလုံးကို track လုပ်ချင်ရင်:


git add .
4. Changes တွေကို Commit လုပ်ခြင်း
Track လုပ်ထားတဲ့ changes တွေကို commit လုပ်ဖို့အတွက်:


git commit -m "Your commit message"
Commit message က changes တွေရဲ့ အကျဉ်းချုပ်ဖြစ်ပါတယ်။

5. Repository Status ကို ကြည့်ရှုခြင်း
Repository ရဲ့ status ကို ကြည့်ဖို့အတွက်:


git status
6. Branch များကို စီမံခန့်ခွဲခြင်း
New branch တစ်ခုဖန်တီးဖို့:


git branch new-branch-name
Branch တစ်ခုကနေ အခြား branch တစ်ခုကို ပြောင်းဖို့:


git checkout branch-name
Branch တွေကို စာရင်းကြည့်ဖို့:


git branch
7. Remote Repository နဲ့ ချိတ်ဆက်ခြင်း
GitHub (သို့) အခြား remote repository နဲ့ ချိတ်ဆက်ဖို့:

git remote add origin https://github.com/username/repository-name.git
Local repository ကို remote repository ဆီ push လုပ်ဖို့:

git push -u origin main
8. Remote Repository ကနေ Code ကို Pull လုပ်ခြင်း
Remote repository က code တွေကို local မှာ update လုပ်ဖို့:


git pull origin main
#### အသုံးဝင်တဲ့ Git Commands များ
Log ကြည့်ခြင်း:


git log
Changes တွေကို ပြန်ဖျက်ခြင်း:

git reset filename.txt

Staged changes တွေကို ပြန်ဖျက်ခြင်း:
git restore --staged filename.txt
Branch ကို Delete လုပ်ခြင်း:

git branch -d branch-name

#### Git ကို အသုံးပြုရာမှာ အကြံပြုချက်များ
Commit Messages တွေကို ရှင်းလင်းစွာရေးပါ:

Changes တွေကို နားလည်လွယ်အောင် commit messages တွေကို ရှင်းရှင်းလင်းလင်း ရေးပါ။

Branch တွေကို မကြာခဏသုံးပါ:

Feature တစ်ခုချင်းစီအတွက် branch တွေခွဲပြီး လုပ်ဆောင်ပါ။

Remote Repository ကို မကြာခဏ Sync လုပ်ပါ:

git pull နဲ့ git push တွေကို မကြာခဏလုပ်ပြီး code တွေကို update လုပ်ပါ။

.gitignore ဖိုင်ကို အသုံးပြုပါ:

မလိုအပ်တဲ့ files တွေ (ဥပမာ - .env, node_modules) ကို track မလုပ်မိအောင် .gitignore ဖိုင်မှာ ထည့်သွင်းပါ။


### Practical Exercises

