# Anime commands
## License:
> Feel free to use it (c) Zenqi
### -watchlist
```
$nomention
$onlyIf[$checkContains[$message;add]==false;]
$onlyIf[$checkContains[$message;set]==false;]
$onlyIf[$checkContains[$message;ep]==false;]
$onlyIf[$checkContains[$message;reset]==false;]
$title[Watchlists!]
$addField[1.;$getUserVar[1]
$getUserVar[d1]
$getUserVar[s1]]
$addField[2.;$getUserVar[2]
$getUserVar[d2]
$getUserVar[s2]]
$addField[3.;$getUserVar[3]
$getUserVar[d3]
$getUserVar[s3]]
$author[$username[$botID]#$discriminator[$botID]]
$authorIcon[$userAvatar[$botID]]
$color[ff6000]
$addTimestamp
```
### -watchlist add
```
$nomention
$onlyIf[$message[1]!=;Usage: ```?watchlist add 1|2|3 <Anime Title>```]
$onlyIf[$message[2]!=;Usage: ```?watchlist add 1|2|3 <Anime Title>```]
$suppressErrors[Usage: ```?watchlist add 1|2|3 <Anime Title>```]
$if[$checkContains[$message;1]==true]
$color[ff6000]
$httpGet[https://api.jikan.moe/v3/search/anime?q=$replaceText[$message[2]; ;+;-1]]
$title[Added!]
$description[Added to your bucketlist!]
$setUserVar[1;$httpResult[results;0;title]
$resetUserVar[s1]
$resetUserVar[d1]]
$else
$if[$checkContains[$message;2]==true]
$color[ff6000]
$httpGet[https://api.jikan.moe/v3/search/anime?q=$replaceText[$message[2]; ;+;-1]]
$title[Added!]
$resetUserVar[s2]
$resetUserVar[d2]
$description[Added to your bucketlist!]
$setUserVar[2;$httpResult[results;0;title]]
$else
$if[$checkContains[$message;3]==true]
$color[ff6000]
$httpGet[https://api.jikan.moe/v3/search/anime?q=$replaceText[$message[2]; ;+;-1]]
$title[Added!]
$resetUserVar[s3]
$resetUserVar[d3]
$description[Added to your bucketlist!]
$setUserVar[3;$httpResult[results;0;title]]
$endif
$endif
$endif
```
### -watchlist set
```
$nomention
$onlyIf[$checkContains[$message;watching;watched;idle;planning]==true;Usage: ```?watchlist set 1|2|3 watching|watched|idle|planning```]
$onlyIf[$message!=;Usage: ```?watchlist set 1|2|3 watching|watched|idle|planning```]
$onlyIf[$getUserVar[$message[1]]!=none;❌ Theres no anime at **#$message[1]**]
$varExistError[$message[1];Usage: ```?watchlist set 1|2|3 watching|watched|idle|planning```]
$if[$checkContains[$message;1]==true]
$title[Set!]
$color[ff6000]
$description[Status $message[2] set!]
$setUserVar[s1;**Status:** ```$message[2]```]
$else
$if[$checkContains[$message;2]==true]
$onlyIf[$checkContains[$message;watching;watched;idle;planning]==true;Usage: ```?watchlist set watching|watched|idle|planning```]
$onlyIf[$message!=;Usage: ```?watchlist set watching|watched|idle|planning```]
$title[Set!]
$color[ff6000]
$description[Status $message[2] set!]
$setUserVar[s2;**Status:** ```$message[2]```]
$else
$if[$checkContains[$message;3]==true]
$onlyIf[$checkContains[$message;watching;watched;idle;planning]==true;Usage: ```?watchlist set watching|watched|idle|planning```]
$onlyIf[$message!=;Usage: ```?watchlist set watching|watched|idle|planning```]
$title[Set!]
$setUserVar[s3;**Status:** ```$message[2]```]
$color[ff6000]
$description[Status $message[2] set!]
$endif
$endif
$endif
```
### -watchlist ep
```
$nomention
$onlyIf[$checkContains[$message[1];1;2;3]==true;Usage: ```?watchlist ep 1|2|3 (episodes)```]
$onlyIf[$message[2]!=;```?watchlist ep 1|2|3 (episodes)```]
$onlyIf[$isNumber[$message[2]]==true;❌ ```$message[2]``` is not an ___number___]
$onlyIf[$getUserVar[$message[1]]!=none;❌ There's no anime at **#$message[1]**]
$varExistError[$message[1];```?watchlist ep 1|2|3 (episodes)```]
$if[$checkContains[$message[1];1]==true]
$setUserVar[d1;**Episodes:** $message[2]]
$title[Set!]
$color[ff6000]
$description[$getUserVar[1] current episode is **$message[2]**]
$else
$if[$checkContains[$message[1];2]==true]
$setUserVar[d2;**Episodes:** $message[2]]
$title[Set!]
$color[ff6000]
$description[$getUserVar[2] current episode is **$message[2]**]
$else
$if[$checkContains[$message[1];3]==true]
$setUserVar[d3;**Episodes:** $message[2]]
$title[Set!]
$color[ff6000]
$description[$getUserVar[3] current episode is **$message[2]**]
$endif
$endif
$endif
```
### -watchlist reset
```
$nomention
$setUserVar[en;yes]
$title[Reset!] 
$description[Are you sure to reset your watchlist?
yes/no]
$color[ff6000]

```
