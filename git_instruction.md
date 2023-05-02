![git_logo](git_logo.png)
# Rabota s Git i GitHub

## 1. NASTROYKA I USTANOVKA

 * A) Proverka nalichiya ustanovlennogo Git.
 V terminale nabrat komandu: 
 ```
  git --version 
  ```
 Esli Git ustanovlen - poyavitsa soobsheniye s info o versii programmi, inache vidast oshibku.

 * B) Ustanovka Git
 Zagrujayem poslednuyu versiyu Git s sayta:
  https://git-scm.com/book/ru/v2 
  Ustanavlivayem s nastroykami po umolchaniyu

 * C) Nastoyka Git
  Pri pervom ispolzovanii Git, neobxodimo predstavitsa. Dlya etogo v terminale neobxodimo vipolnit komandi:
  ```
git config --global user.email "your email"
git config --global user.name "your name"
  ```

  ```
  NOTE: 
  dlya proverki etix dannix nujno nabrat komandu:
  git cinfig --global --list
  ```

## 2. OSNOVNIYE KOMANDI Git

* `git init` - инициализация локального репозитория

* `git status` - получить информацию от git о его текущем состоянии

* `git add` - добавить файл или файлы к следующему коммиту

```
NOTE: 
<git add> mojno vipolnyat neskolko raz nakaplivaya izmeneniya pered tem, kak zafiksirovat
s pomoshyu komandi s komentariyem k nemu: <git commit -m"komentariy"> 
```

 * `git commit-m "message"` - создание коммита.

```
NOTE: 
- Fiksaciya dobavlennix izmeneniy posle komandi  "git add", a takje mojno nabrat komandu: 
git commit -a -m "message" (mojno vmeste -am),(etu komandu nelzya ispolzovat pri dobavlenii faila, t.e v samom nachale
nujno ispolzovat otdelno git add i git commit -m) kotoraya vipolyayet 2 komandi:

 1. git add . (s tockoy!)-dlya soxraneniya izmeneniy vo VSEX FAILAX v dannoy papre gde podklyuchen kontrol versiy Git
 
 2. git commit -m"message" dlya fiksacii i komentariy k nim

- Komanda: git commit (bez -m)
(posle komandi git add ...) perevedyot nas vo vstroenniy redaktor (pri zagruzki Git mojno vibrat ili nastoit),
tut dlya vvoda nujno nabrat "i" - insert, i nachat vvodit message dlya commita.
Dlya fiksacii i vixoda nujno najat "ESC" - popadayem na komandnuyu stroku- daleye vvodim ":wq" - gde w - write, q- quit.

Dlya vixoda bez soxraneniya ":q!" ili ":zq"

dlya soxraneniya bez vixoda ":w"

u menya nastroyen drugoy redaktor!!! ya nabral message i v verxnem menyu vibral soxranit i viyti - vse

- Esli vi nepravilno zacommitili posledniy messaj, to komandoy: git commit --amend -a -m 
"ispravlyayem posledniy coomit i message" mojno perezapisat ego
 ```

* `git log` - вывод на экран истории всех коммитов с их хеш-кодами 

```
NOTE: 
"git log --oneline"       dlya bolee korotkogo spiska commit-ov

"git log --oneline -2"    dlya otobrajeniya poslednix 2-x commit-ov

"git log --oneline -2 -p" pokajet s izmeneniyami mejdu etimi poslednimi dvumya commit-ami

"git reflog"     dlya otslejivaniya vsex peremesheniy, vklyuchaya "poteryanniye" commit-i

```

* `git checkout "hachcode"` - переход от одного коммита к другому, a `git checkout name_of_branch` - переход от одной ветки на другую
```
NOTE:
  "git checkout XXXX" gde "XXXX" eto perviye 4 simvola hechcoda, kotoriye mi poluchayem posle comandi "git log"

  "git checkout main" ili "git checkout master" dlya vozvrata na konecho-zafiksirovannoye polojeniye po qlavnoy vetke,
  kotoraya mojet nazivatsa kak "main" tak i "master"

  "git switch" - zamenyayet komandu checkout dlya peremesheniy
```

* `git diff` - увидеть разницу между текущим файлом и закоммиченным файлом

## 3. RABOTA S VETKAMI

* `git branch`-посмотреть список веток в репозитории
```
NOTE:
v spiske tekushaya vetka budet videlena cvetom i oboznachena (*)
````

* `git branch nameOfBranch` - создать ветку "nameOfBranch"

* `git branch -d nameOfBranch` - удалить ветку "nameOfBranch"
```
NOTE:
Komanda git branch -D nameOfBranch udalit etu vetku, esli daje v ney ne bilo fiksacii - commit
```

* `git checkout nameOfBranch` - переход на ветку"nameOfBranch"

* `git checkout -b newNameOfBranch` - создать ветку и сразу переход на нёё "newNameOfBranch"
```
NOTE:
Mojno takje vospolzovatsa novoy rekomendaciyey git i sovershit sozdaniye i momentalniy perexod odnoy komandoy
git switch -c newNameOfBranch
```

* `git merge nameOfBranch` - для слияния ветки
```
NOTE:
- Ne zabivayem pered vixoda iz lyuboy vetki i posle vipolneniya merge vipolnyat komandi fiksacii git add i git commit

- Dlya OTMENI sliyaniya ispolzuem komandu git merge --abort pered fiksaciyey git add i git commit
```

## 4. VARIANTI S KOMANDOY HELP

* `git help`

```
NOTE:
Eta komanda raspechataet vam vse osnovniye komandi.
No esli nabrat git commit -h to git raspechataet vam vse komandi svyazanniye s comandoy commit
```

## 5. IGNORIROVANIYE FAYLOV

Tak kak fayli s izobrajeniyami ne prinyato dobavlyat v kontrol versiy, sozdayom fayl s nazvaniyem:
`.gitignore` (mojno eto sdelat s pomoshyu komandi SVC v terminale nabrav komandu `touch .gitignore`)
I vnosim v etu papku vse ignoriruemiye fayli, mojno s pomoshyu shablona `*.XXX`,
gde XXX- rasshireniye odnotipnix faylov(jpg, png i t.d) 


## 6. STRATEGIYA FAST-FORWARD
Nastroit ili otmenit ego mojno v nastroykax
Esli v otdelnoy vetke proisxodili izmeneniya i fiksirovalis v otlichii ot osnovnoy
vetki - v takom sluchaye pri ix soyedinenii (merge) proisxodit sliyaniye bez dop
soxraneniya otdelnoy vetki v istorii log graph. 

## 7. RAZRESHENIYE KONFLIKTOV
Konfliktami v git nazivayum momenti, kogda pri sliyanii vetok nujno vibrat kakoy variant
nujno soxranit? Ostavit variant v osnovnoy vetke, v kotoruyu mergim vetku?
Prinyat variant iz novoy vetki? Ili ostavit oba i dodelat uje v osnovnoy vetke?
```
NOTE:
V LYUBOM SLUCHAYE NE ZABIVAYTE SDELAT COMMIT DLYA SOXRANENIYA POSLE KOMANDI MERGE!
```

## 8. RABOTA S UDALYONNIM REPOZITORIYEM

```
NOTE:
Git Hub - eto servis kompanii Microsoft kotoraya pozvolyayet integrirovatsa s programmoy Git
(na vashem kompe) i nastroit udalyonnuyu rabotu s vashim repozitoriyem.
```
* A) Neobxodimo zaregistrirovatsa i sozdat svoy account na sayte https://github.com/

* B) Sozsdat udalyonniy repozitoriy 
```
 NOTE:
 - v pravom verxnem uglu (na sayte GitHub) najat "+", zatem vibrat "New repository"
 - v "Repository name*" imenovat ego
 - najat "Createing repository.."
 - Daleye est vibor: 1. "..or create a new repository...." dlya sozdaniya repository cherez terminal".
 2. "...or push an existing repository..." - uje sushestvuyushiy repozitoriy privyazat
 (smotret vishe, kak mojno sozdat local repo. punkt: NASTROYKA I USTANOVKA) k etomu udalyonnomu repozitoriyu
 (s pomoshyu komondi git remote(udalyonniy) svyazali adress origin (imya adresa udalyonnogo repo.)
 i vipolnili komandu git push -u (upstream) origin(nash adress)). 3. "...or import code from another repository"
 importirovat code iz drugogo REPO. 
 Vibiraya eti puti nujno vipolnit te komandi, kotoriye tam ukazani.
 ```

* C) Skachat repo iz GitHub (svoyego ili chujogo accounta) mojno komandoy `git clone`
```
NOTE:
- Eto deystviye mojno proizvodit ne imeya svoyego accounta v GitHub.
- Mesto, kuda budem skachivat luchshe ne podklyuchat version control, t.e. ne ispolzovat komandu git init i t.d.!!!
Na str.GitHub (ili svoyego accaunta) najimayem "CODE", daleye kopiruyem <HTTPS cod>
i s pomoshyu komandi git clone ...kod... U nas doljna poyavitsa papka s imenem iz repo s temi failami chto bili v ney. 
A esli cherez probel posle komandi git clone ...kod... NEW_NAME nabrat, to imya papki izmanitsa na NEW_NAME.
daleye vipolvim "change directory" s pomoshyu komandi "cd nameOfFolder"
daleye OBYAZATELNO sozdayom novuyu vetku "git branch name" i tam uje sozdat fail (prinyato nazivat README.XX)
i sozdat te izmeneniya, kotoriye mi xotim predlojit. daleye git add, git commit, i tak kak novaya vetka yeshe
ne zaregestrirovana nujno nabrat git push --set-upstream origin nameOfNewBranch
ili sokrashenniy variant git push -u origin nameOfNewBranch.
```

* D)  Zalit svoy repozitoriy na GitHub mojno s pomoshyu komandi `git push`
```
NOTE:
etu komandu mojno vipolnit esli vi uje proizveli deystviya ukazanniye vishe "v punkte 8, A) i podpunkt 2."
gde s pomoshyu komondi git remote(udalyonniy) svyazali adress origin (imya adresa udalyonnogo repo.)
i vipolnili komandu git push -u (upstream) origin(nash adress)
```

* E) Vneseniye izmeneniy v fail cherez svoy accaunt mojno pryamo na sayte GitHub 
```
NOTE:
vibirayem nujniy fail i najimayem na risunok karandasha v pravom vernem uglu. 
dobavit commit i najali "Commit changes"
zatem v lokalnom ripo nujno nabrat komandu git pull shtobi styanut vse izmeneniya i vipolnit komandu git merge. 

esli ne xotim vipolnyat komandu git merge, to nujno vipolnit komandu git fetch
```

* F) Uchastvovat v chujom proyekte "Fork"
```
NOTE:
Dlya nachala nujno sozdat polnuyu kopiyu etogo repo na svoyom UDALYONNOM repo
(accaunte na sayte GitHub) i daleye rabotat s nim kak so svoim proyektom.
- Mesto, kuda budem skachivat luchshe ne podklyuchat version control, t.e. ne ispolzovat komandu git init i t.d.!!!
Na str.GitHub najimayem "CODE", daleye kopiruyem <HTTPS cod> i s pomoshyu komandi git clone ...kod...
U nas doljna poyavitsa papka s imenem iz repo s temi failami chto bili v ney.
daleye vipolvim "change directory" s pomoshyu komandi "cd nameOfFolder"
daleye OBYAZATELNO sozdayom novuyu vetku "git branch name" i tam uje sozdat fail (prinyato nazivat README.XX)
i sozdat te izmeneniya, kotoriye mi xotim predlojit. daleye git add, git commit i tak kak novaya vetka yeshe
ne zaregestrirovana nujno nabrat git push --set-upstream origin nameOfNewBranch
ili sokrashenniy variant git push -u origin nameOfNewBranch.

otpravit snachalo v nash repo i daleye najimayem "Compare & pull request"
No, esli ne poyavitsa knopka "Compare & pull request", to mojno v ruchnuyu pereyti 
vo vkladku "Pull requests" v verxney srtoke "<>Code, Pull request, Action..." 
i najimayem na "New pull request" daleye "compare:main" i vibirayem nashu vetku "nameOfNewBranch"- poyavitsa knopka "Create pull request"- najimayem,
daleye mojno dobavit soobsheniye k nashemu kommitu i snovo najat na "Create pull request"
```
