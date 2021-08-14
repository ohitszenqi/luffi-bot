# Variables:
```
beli: 0
level: 0
exp: 0
hh:
```
# Economy
### -adventure
```
$nomention
$title[Adventure!]
$color[ff6000]
$authorIcon[$userAvatar[$botID]]
$author[$username[$botID]#$discriminator[$botID]]
$description[You got $random[1;500]<:beri:872492755027370054> from your adventure.]
$setUserVar[beli;$sum[$getUserVar[beli];$random[1;500]]]
$setUserVar[exp;$sum[$getUserVar[exp];1]]
$if[$getUserVar[level]>=1]
$title[Adventure!]
$color[ff6000]
$authorIcon[$userAvatar[$botID]]
$author[$username[$botID]#$discriminator[$botID]]
$description[You got $numberSeparator[$random[1;1000]]<:beri:872492755027370054> from your adventure.]
$setUserVar[beli;$sum[$getUserVar[beli];$random[1;1000]]]
$setUserVar[exp;$sum[$getUserVar[exp];1]]
$footer[Money Multiplier 2x]
$if[$getUserVar[level]>=2]
$title[Adventure!]
$color[ff6000]
$authorIcon[$userAvatar[$botID]]
$author[$username[$botID]#$discriminator[$botID]]
$description[You got $numberSeparator[$random[1;1500]]<:beri:872492755027370054> from your adventure.]
$setUserVar[beli;$sum[$getUserVar[beli];$random[1;1500]]]
$setUserVar[exp;$sum[$getUserVar[exp];1]]
$footer[Money Multiplier 3x]
$if[$getUserVar[level]>=3]
$title[Adventure!]
$color[ff6000]
$authorIcon[$userAvatar[$botID]]
$author[$username[$botID]#$discriminator[$botID]]
$description[You got $numberSeparator[$random[1;2000]]<:beri:872492755027370054> from your adventure.]
$setUserVar[beli;$sum[$getUserVar[beli];$random[1;2000]]]
$setUserVar[exp;$sum[$getUserVar[exp];1]]
$footer[Money Multiplier 4x]
$if[$getUserVar[level]>=4]
$title[Adventure!]
$color[ff6000]
$authorIcon[$userAvatar[$botID]]
$author[$username[$botID]#$discriminator[$botID]]
$description[You got $numberSeparator[$random[1;2500]]<:beri:872492755027370054> from your adventure.]
$setUserVar[beli;$sum[$getUserVar[beli];$random[1;2500]]]
$setUserVar[exp;$sum[$getUserVar[exp];1]]
$footer[Money Multiplier 3x]
$if[$getUserVar[level]>=5]
$title[Adventure!]
$color[ff6000]
$authorIcon[$userAvatar[$botID]]
$author[$username[$botID]#$discriminator[$botID]]
$description[You got $numberSeparator[$random[1;3000]]<:beri:872492755027370054> from your adventure.]
$setUserVar[beli;$sum[$getUserVar[beli];$random[1;3000]]]
$setUserVar[exp;$sum[$getUserVar[exp];1]]
$footer[Money Multiplier 4x]
$if[$getUserVar[level]>=1]
$title[Adventure!]
$color[ff6000]
$authorIcon[$userAvatar[$botID]]
$author[$username[$botID]#$discriminator[$botID]]
$description[You got $numberSeparator[$random[1;3500]]<:beri:872492755027370054> from your adventure.]
$setUserVar[beli;$sum[$getUserVar[beli];$random[1;3500]]]
$setUserVar[exp;$sum[$getUserVar[exp];1]]
$footer[Money Multiplier 5x]
$endif
$endif
$endif
$endif
$endif
$endif
```
### -wallet
```
$nomention
$color[ff6000]
$authorIcon[$userAvatar[$botID]]
$author[$username[$botID]#$discriminator[$botID]]
$thumbnail[https://cdn.discordapp.com/emojis/872492755027370054.png]
$title[Wallet]
$addField[Beli;$numberSeparator[$getUserVar[beli]]<:beri:872492755027370054>]
```
### -bet
```
$nomention
$suppressErrors[❌ Error occured]
$if[$randomText[a;b]==a]
$color[ff6000]
$onlyIf[$message[1]!=;❌ Put an amount]
$onlyIf[$getUserVar[beli]>=$message[1];❌ You don't had ```$message[1]``` beli.]
$onlyIf[$isNumber[$message]==true;❌ ```$message[1]``` is not an number]
$authorIcon[$userAvatar[$botID]]
$author[$username[$botID]#$discriminator[$botID]]
$title[Bet!]
$description[You bet ```$message[1]``` and won ```$numberSeparator[$multi[$message[1];2]]```]
$setUserVar[beli;$sum[$multi[$message[1];2];$getUserVar[beli]]]
$else
$onlyIf[$message[1]!=;❌ Put an amount]
$onlyIf[$getUserVar[beli]>=$message[1];❌ You don't had ```$message[1]``` beli.]
$onlyIf[$isNumber[$message]==true;❌ ```$message[1]``` is not an number]
$color[ff6000]
$authorIcon[$userAvatar[$botID]]
$author[$username[$botID]#$discriminator[$botID]]
$description[You lose ```$message[1]```]
$setUserVar[beli;$sub[$getUserVar[beli];$message[1]]]
$endif
```
### -levelup
```
$nomention
$if[$getUserVar[level]>=0]
$onlyIf[$getUserVar[exp]>=150;You can't level up for now: ```$getUserVar[exp]/150```]
$setUserVar[level;$sum[$getUserVar[level];1]]
$color[ff6000]
$authorIcon[$userAvatar[$botID]]
$author[$username[$botID]#$discriminator[$botID]]
$title[Level up!]
$description[Your level turned to 1!]
$if[$getUserVar[level]>=1]
$onlyIf[$getUserVar[exp]>=300;You can't level up for now: ```$getUserVar[exp]/300```]
$color[ff6000]
$authorIcon[$userAvatar[$botID]]
$author[$username[$botID]#$discriminator[$botID]]
$setUserVar[level;$sum[$getUserVar[level];1]]
$title[Level up!]
$description[Your level turned to 2!]
$if[$getUserVar[level]>=2]
$onlyIf[$getUserVar[exp]>=450;You can't level up for now: ```$getUserVar[exp]/450```]
$color[ff6000]
$authorIcon[$userAvatar[$botID]]
$author[$username[$botID]#$discriminator[$botID]]
$setUserVar[level;$sum[$getUserVar[level];1]]
$title[Level up!]
$description[Your level turned to 2!]

$if[$getUserVar[level]>=3]
$onlyIf[$getUserVar[exp]>=500;You can't level up for now: ```$getUserVar[exp]/500```]
$color[ff6000]
$authorIcon[$userAvatar[$botID]]
$author[$username[$botID]#$discriminator[$botID]]
$setUserVar[level;$sum[$getUserVar[level];1]]
$title[Level up!]
$description[Your level turned to 3!]
$if[$getUserVar[level]>=3]
$onlyIf[$getUserVar[exp]>=650;You can't level up for now: ```$getUserVar[exp]/650```]
$color[ff6000]
$authorIcon[$userAvatar[$botID]]
$author[$username[$botID]#$discriminator[$botID]]
$setUserVar[level;$sum[$getUserVar[level];1]]
$title[Level up!]
$description[Your level turned to 4!]
$if[$getUserVar[level]>=4]
$onlyIf[$getUserVar[exp]>=800;You can't level up for now: ```$getUserVar[exp]/800```]
$color[ff6000]
$authorIcon[$userAvatar[$botID]]
$author[$username[$botID]#$discriminator[$botID]]
$setUserVar[level;$sum[$getUserVar[level];1]]
$title[Level up!]
$description[Your level turned to 5!]
$endif
$endif
$endif
$endif
$endif
$endif
```
### -rank
```
$nomention
$color[ff6000]
$authorIcon[$userAvatar[$botID]]
$author[$username[$botID]#$discriminator[$botID]]
$title[Rank card]
$addField[Level:;$getUserVar[level]]
$addField[EXP:;$getUserVar[exp]]
$thumbnail[$authorAvatar]
$addTimestamp
```
### -search
```
$nomention
$title[Search]
$setUserVar[hh;yes]
$description[type: ```grass/couch/ship``` to pick an location!]
$color[ff6000]
$authorIcon[$userAvatar[$botID]]
$author[$username[$botID]#$discriminator[$botID]]
```
## make a command and set the prefix to:
#### grass, couch and ship
##### also, put the code on the three commands
```
$nomention
$replyIn[5s]
$resetUserVar[hh]
```
## couch/ship/grass
#### couch
```
$nomention
$enabled[$getUserVar[hh];]
$title[Couch...]
$description[You searched in a couch and find **$random[0;600]**]
$color[ff6000]
$setUserVar[beli;$sum[$getUserVar[beli];$random[0;600]]]
$authorIcon[$userAvatar[$botID]]
$author[$username[$botID]#$discriminator[$botID]]
```
#### ship
```
$nomention
$enabled[$getUserVar[hh];]
$title[Ship...]
$description[You searched in a ship and find **$random[0;600]**]
$color[ff6000]
$setUserVar[beli;$sum[$getUserVar[beli];$random[0;600]]]
$authorIcon[$userAvatar[$botID]]
$author[$username[$botID]#$discriminator[$botID]]
```
#### grass
```
$nomention
$enabled[$getUserVar[hh];]
$title[Grass...]
$description[You searched in a grass and find **$random[0;600]**]
$color[ff6000]
$setUserVar[beli;$sum[$getUserVar[beli];$random[0;600]]]
$authorIcon[$userAvatar[$botID]]
$author[$username[$botID]#$discriminator[$botID]]
```
> License
