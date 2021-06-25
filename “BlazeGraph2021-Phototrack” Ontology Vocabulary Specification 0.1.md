
"BlazeGraph2021-Phototrack" Ontology Vocabulary Specification 0.1
===
### Namespace Document 20 May 2021 - Initial Draft

### This version:
https://hackmd.io/@epsGZ2IDS96W-qwkLMe3xg/danielmse

### Latest version:
https://hackmd.io/@epsGZ2IDS96W-qwkLMe3xg/danielmse

### Previous version:
###### None

### Author:
[Daniel Hu](mailto:amilyhu0901@gmail.com), a student from National Yang Ming Chiao Tung University 

### Contributors:
Members of NYCU Workshop: [A Computational Journey Towards Humanities and Creativity: Starting from Graphs](http://e.cctcc.art/c1632).

Abstract
===

這是一個關於我自己的 **高中生活照片典藏集合** 。主要希望整理由過去自己手機、相機、網路截圖等等來源上的照片，這些照片可能都帶有一些故事或是對我自己而言較為主觀意識的回憶。我會非常想要將這些照片整理成更為細緻、有條理的線上資料庫，以作為不斷增長的、屬於自己非常重要的人生紀錄站。也希望能藉由這份典藏集合，即時將自己發生過的點點滴滴和他人分享。

Table of Contents
===

- [Phototrack at a glance](#Phototrack-at-a-glance)
  - [A-Z of Phototrack terms](#A-Z-of-Phototrack-terms)
- [Introduction: Phototrack Basics](#Introduction-Phototrack-Basics)
  - [Background](#Background)
  - [The Basic Idea](#The-Basic-Idea)
  - [What’s Phototrack for?](#What’s-Phototrack-for)
  - [Phototrack cross_reference: Listing Classes and Properties](#Phototrack-cross_reference-Listing-Classes-and-Properties)
- [Classes and Properties (full detail)](#Classes-and-Properties-full-detail)
  - [Classses](#Classses)
  - [Properties](#Properties)
- [External Vocabulary References](#External-Vocabulary-References)
  - [Schema.org Vocabulary]( #Schema.org-Vocabulary)
  - [Phototrack Vocabulary](#Phototrack-Vocabulary)
- [Acknowledgments](#Acknowledgments)
- [Recent Changes (未來改版時用)](#Recent-Changes-未來改版時用)

Phototrack at a glance
===

Phototrack類似於字典或者術語表，不同的是，它能讓電腦處理更多內容的細節和其結構。此將促進資料的互通性、資訊搜尋和檢索、自動推理和自然語言處理技術。Phototrack 類似建立於這樣的意義上，以照片作為資料的載體，照片上的細部資料提供電腦去辨識並加以分類整理不同性質的照片種類。


目前想整理的分類方式：
- **拍照日期和時間(Timeline)** – 目前主要想要列出製作日期(created) ／修改日期(modified)作為排序資訊。 由拍攝照片時所得到的Exif資訊內容取得。也包含相機設定：會利用照片上有的訊息作為排序整理的依據，目前有：
   ```
    - ifd0_datetime 
	- ifd0_orientation
	- jpeg_imageHeight	
	- jpeg_imageWidth
	- gps_TimeStamp
	- gps_DateStamp	
	- subIFD_datetime_original
	- file_name
	- file_siz
   ```
   其目前主要會以 " ++ifd0 datetime++ " 和 " ++file name++ " 為Timeline資料建構上取的關鍵資訊內容。
   
- **Timeline's model fit** - 以照片內容建立時軸內容。內容希望符合“Official TimelineJS3 Template”之主要格式。
   ``` 
   - datetime (year,month,day,time)
   - headline
   - text
   - Media
   - Media Credit
   - Media Caption
   ```
- **標誌性活動(Activity)** –藉由某些特殊活動(Personnal classification)作為某些照片的共同連結，其中可連結的部分應該為出現在多張照片的屬性（八大探索領域:Indicator of Exploration）以及人物、事件、物件（再細部區分探索領域:Details about the  Indicator）。



  ```
   - Personnal classification
   - Indicator of Exploration
   - Details about the  Indicator
   ```
    
| Timeline | Timeline's model fit |Activity|
| ------ | ----------- |----|
|ifd0_datetime| datetime (year,month,day,time)|Personnal classification 
|file_name| headline   |  Indicator of Exploration |
||  Media/Media_Credit/Media_Caption  |  Details about the  Indicator  |



### A-Z of Phototrack terms

- **Personnal classification:** |[`小聯課`](#Classes-PT-`小聯課`)|[`中研院`](#Classes-PT-`中研院`)｜[`企劃書`](#Classes-PT-`企劃書`)｜[`社課`](#Classes-PT-`社課`)｜[`思源`](#Classes-PT-`思源`)｜[`秋遊`](#Classes-PT-`秋遊`)｜[`科普列車`](#Classes-PT-`科普列車`)｜[`桌遊`](#Classes-PT-`桌遊`)｜[`高一預幹講版`](#Classes-PT-`高一預幹講版`)｜[`畢業後歡唱`](#Classes-PT-`畢業後歡唱`)｜[`畢業舞會＆通宵夜唱`](#Classes-PT-`畢業舞會＆通宵夜唱`)｜[`寒訓`](#Classes-PT-`寒訓`)｜[`暑訓`](#Classes-PT-`暑訓`)｜[`雄女幹見`](#Classes-PT-`雄女幹見`)｜[`試教`](#Classes-PT-`試教`)｜

- **Indicator of Exploration:** |[`休閒娛樂`](#Excepted-type-PT-`休閒娛樂`)|[`人際關係`](#Excepted-type-PT-人際關係)|[ `知識類` ](#Excepted-type-PT-`知識類`)|[ `感性類` ](#Excepted-type-PT-`感性類`)|[ `文學造詣` ](#Excepted-type-PT-`文學造詣`)|[`實作體驗` ](#Excepted-type-PT-`實作體驗`)|[ `創造力` ](#Excepted-type-PT-`創造力`)|[`毅力展現` ](#Excepted-type-PT-`毅力展現`)|

- **Details about the  Indicator :** |[`四藝（琴棋書畫）`](#Property-PT:-四藝（琴棋書畫）)|[`電影影集`](#Property-PT:-電影影集）)|[`遊戲`](#Property-PT:-遊戲)|[`動漫`](#Property-PT:-動漫)|[`出國遊玩`](#Property-PT:-出國遊玩)|[`社團活動`](#Property-PT:-社團活動)|[`畢業後遊玩`](#Property-PT:-畢業後遊玩)|[`人的性別`](#Property-PT:-人的性別)|[`同班同學（分別來自不同年級）`](#Property-PT:-同班同學（分別來自不同年級）)|[`社團同學（分別有自己高中與不同高中）`](#Property-PT:-社團同學（分別有自己高中與不同高中）)|[`很要好的朋友`](#Property-PT:-很要好的朋友)|[`老師（分別是自己高中與其他學校）`](#Property-PT:-老師（分別是自己高中與其他學校）)|[`不同年紀的同學（學長姐、學弟妹）`](#Property-PT:-不同年紀的同學（學長姐、學弟妹）)|[`雙人合照`](#Property-PT:-雙人合照)|[`團體大合照`](#Property-PT:-團體大合照)|[`社團我教過的學生`](#Property-PT:-社團我教過的學生)|[`物品的種類（動植物）`](#Property-PT:-物品的種類（動植物）)|[`校內知識（課堂學業、社團等）`](#Property-PT:-校內知識（課堂學業、社團等）)|[`校外知識（中研院、營隊、出國）`](#Property-PT:-校外知識（中研院、營隊、出國）)|[`專業論文研究內容`](#Property-PT:-專業論文研究內容)|[`科普知識`](#Property-PT:-科普知識)|[`簡報內容`](#Property-PT:-簡報內容)|[`未來求學相關`](#Property-PT:-未來求學相關)|[`風景`](#Property-PT:-風景)|[`網紅明星照`](#Property-PT:-網紅明星照)|[`心理研究相關`](#Property-PT:-心理研究相關)|[`感性內容（抽象情感展現）`](#Property-PT:-感性內容（抽象情感展現）)|[`名言佳句`](#Property-PT:-名言佳句)|[`科學實驗`](#Property-PT:-科學實驗)|[`程式設計`](#Property-PT:-程式設計)|[`廚藝`](#Property-PT:-廚藝)|[`影片剪輯`](#Property-PT:-影片剪輯)|[`設計與美術`](#Property-PT:-設計與美術)|[`團隊合作經驗`](#Property-PT:-團隊合作經驗)|[`運動相關`](#Property-PT:-運動相關)|






Introduction: Phototrack Basics
===

### Background

原意為 **追蹤照片** 。是希望能夠藉由建構資料庫的方式來更為方便的追蹤已經被分類好的照片。常常我們會很容易收藏東西，可是東西累積的多了就很容易消失在眾多收集的資訊之海當中，會用trackㄧ詞也是希望能夠更為精準的讓使用的人能馬上找出照片的位置與資訊內容。當然追蹤的項目不會只是單純的照片本身，能透過[照片有的細部資訊](https://www.flickr.com)像是Exif的資訊，來衍伸出額外與其他照片會有的連結，可能是活動、共同的人事物、地點等等，目的是希望能盡可能的追蹤完整的故事內容。

### The Basic Idea

剛開始的原因是來自我原本就有整理生活照片的習慣。我都是會把想收藏好的照片存到自己的google drive和隨身硬碟裡頭。隨著每年這樣的過去，照片量越來越大量，整理的狀況會越來越麻煩，也越來越難很快速的就找到以前整理過的照片，不同的分類開了不同的資料夾，也就導致了這樣的困擾。於是乎就想到如果可以結合ontology的概念，將照片的資訊加以彙整編列，說不定就能解決目前整理會遇上的缺點。

### What’s Phototrack for?

目前Phototrack整理的內容最主要僅提供我自己個人的生活紀錄，分類也較為主觀，所以蠻像是設計給自己看的資料庫。當然也會希望這樣的整理也能用於和他人分享使用，這部分目前還在思考每個人對生活屬性定義的不同，該如何串接雙向的資料加以分享或是有固定查閱模式。很重要的一點是關於[知識抽取](https://codertw.com/程式語言/520758/)。從不同來源、結構的資料中進行資訊提取，形成知識存入知識圖譜中。知識抽取處理的物件按照結構化程度可以分類出結構化資訊。這樣的結構化文件具有良好的佈局結構，可以很容易地對其執行知識抽取。主要的工作是通過編寫包裝器，從半結構化資料中提取實體屬性，適用在百科類站點、垂直網站中進行包裝器歸納，從網頁表格中提取屬性資訊。


### Phototrack cross_reference: Listing Classes and Properties

classes : [Personnal classification](#Excepted-type-PT-Personnal-classification)

properties : [Details about the Indicator](#Excepted-type-PT-Details-about-the-Indicator)



Classes and Properties (full detail)
===

### ==Classes==

### ++Classes PT: `小聯課`++
| Class name | Expected Type |Description|
| ------ | ----------- |----|
|[headline](#Excepted-type-PT:-headline)|[`小聯課`](#Classes-PT-`小聯課`) xsd:string |此活動是南ㄧ中科研社與南女科研社共同舉辦之活動|
|[datetime (year,month,day,time)](#Excepted-type-PT:-datetime)|xsd:string |由照片檔之Exif欄位取得資訊 |
|[Media](#Excepted-type-PT:-Media)| xsd:string  |Github照片連結 
|[Media_Credit](#Excepted-type-PT:-Media_Credit)|[Indicator of Exploration](#Excepted-type-PT-Indicator-of-Exploration) xsd:string| [`人際關係`](#Excepted-type-PT-人際關係) [ `知識類` ](#Excepted-type-PT-`知識類`)|
|[Media_Caption](#Excepted-type-PT:-Media_Caption)|[Details about the Indicator](#Excepted-type-PT-Details-about-the-Indicator) | [`社團同學（分別有自己高中與不同高中）`](#Property-PT:-社團同學（分別有自己高中與不同高中）) [`不同年紀的同學（學長姐、學弟妹）`](#Property-PT:-不同年紀的同學（學長姐、學弟妹）) [`校內知識（課堂學業、社團等）`](#Property-PT:-校內知識（課堂學業、社團等）) [`校外知識（中研院、營隊、出國）`](#Property-PT:-校外知識（中研院、營隊、出國）) |

 

### ++Classes PT: `中研院`++
| Class name | Expected Type |Description|
| ------ | ----------- |----|
|[headline](#Excepted-type-PT:-headline)|[`中研院`](#Classes-PT-`中研院`) xsd:string |以研究為重心的中央研究院，致力從事人文社會、數理與生命科學的頂尖研究，亦同樣具社會責任的科普知識推廣，讓大眾知道中研院在做什麼。因此，22年來，透過每年115月舉辦的「院區開放參觀活動」(Open House)，激發無數年輕學子的探索熱情，參觀人次屢創新高，近年更成為國內單日參觀人次最多的科普盛會。|
|[datetime (year,month,day,time)](#Excepted-type-PT:-datetime)|xsd:string |由照片檔之Exif欄位取得資訊 |
|[Media](#Excepted-type-PT:-Media)| xsd:string  |Github照片連結 
|[Media_Credit](#Excepted-type-PT:-Media_Credit)|[Indicator of Exploration](#Excepted-type-PT-Indicator-of-Exploration) xsd:string| [`人際關係`](#Excepted-type-PT-人際關係) [ `感性類` ](#Excepted-type-PT-`感性類`) [ `知識類` ](#Excepted-type-PT-`知識類`)|
|[Media_Caption](#Excepted-type-PT:-Media_Caption)|[Details about the Indicator](#Excepted-type-PT-Details-about-the-Indicator) | [`社團同學（分別有自己高中與不同高中）`](#Property-PT:-社團同學（分別有自己高中與不同高中）)  [`不同年紀的同學（學長姐、學弟妹）`](#Property-PT:-不同年紀的同學（學長姐、學弟妹）) [`感性內容（抽象情感展現）`](#Property-PT:-感性內容（抽象情感展現）) [`風景`](#Property-PT:-風景)[`校內知識（課堂學業、社團等）`](#Property-PT:-校內知識（課堂學業、社團等）) [`校外知識（中研院、營隊、出國）`](#Property-PT:-校外知識（中研院、營隊、出國）) |

### ++Classes PT: `企劃書`++
| Class name | Expected Type |Description|
| ------ | ----------- |----|
|[headline](#Excepted-type-PT:-headline)|[`企劃書`](#Classes-PT-`企劃書`) xsd:string |為歷代南ㄧ中幹部選舉的其中一項內容，學弟需組隊籌備一場會有過夜的大型活動，並撰寫完整企劃書|
|[datetime (year,month,day,time)](#Excepted-type-PT:-datetime)|xsd:string |由照片檔之Exif欄位取得資訊 |
|[Media](#Excepted-type-PT:-Media)| xsd:string  |Github照片連結 
|[Media_Credit](#Excepted-type-PT:-Media_Credit)|[Indicator of Exploration](#Excepted-type-PT-Indicator-of-Exploration) xsd:string| [ `知識類` ](#Excepted-type-PT-`知識類`)|
|[Media_Caption](#Excepted-type-PT:-Media_Caption)|[Details about the Indicator](#Excepted-type-PT-Details-about-the-Indicator) | [`簡報內容`](#Property-PT:-簡報內容) |

### ++Classes PT: `社課`++
| Class name | Expected Type |Description|
| ------ | ----------- |----|
|[headline](#Excepted-type-PT:-headline)|[`社課`](#Classes-PT-`社課`) xsd:string |科學研究社，簡稱科研社，是台南一中人文性社團，以科學研究為主旨。其歷史悠久，也是台南一中規模最龐大的社團。以本校科學教育大樓為主要活動範圍。（https://tnfsh.fandom.com/wiki/科學研究社）|
|[datetime (year,month,day,time)](#Excepted-type-PT:-datetime)|xsd:string |由照片檔之Exif欄位取得資訊 |
|[Media](#Excepted-type-PT:-Media)| xsd:string  |Github照片連結 
|[Media_Credit](#Excepted-type-PT:-Media_Credit)|[Indicator of Exploration](#Excepted-type-PT-Indicator-of-Exploration) xsd:string| [`人際關係`](#Excepted-type-PT-人際關係) [ `知識類` ](#Excepted-type-PT-`知識類`) [`實作體驗` ](#Excepted-type-PT-`實作體驗`)|
|[Media_Caption](#Excepted-type-PT:-Media_Caption)|[Details about the Indicator](#Excepted-type-PT-Details-about-the-Indicator) | [`社團同學（分別有自己高中與不同高中）`](#Property-PT:-社團同學（分別有自己高中與不同高中）) [`校內知識（課堂學業、社團等）`](#Property-PT:-校內知識（課堂學業、社團等）) [`科普知識`](#Property-PT:-科普知識) [`科學實驗`](#Property-PT:-科學實驗) |

### ++Classes PT: `思源`++
| Class name | Expected Type |Description|
| ------ | ----------- |----|
|[headline](#Excepted-type-PT:-headline)|[`思源`](#Classes-PT-`思源`) xsd:string |培養年輕學子喜愛基礎科學，激發創意思考能力，發展團隊合作精神，領略實際動手操作之樂趣。此課程設計的理念是鼓勵學生動手、動腦做自主性學習與反芻，將過去灌輸的「知識」與囫圇吞棗的「資料」消化並融入活動設計裡，以趣味性的方法來引發學習的興趣。|
|[datetime (year,month,day,time)](#Excepted-type-PT:-datetime)|xsd:string |由照片檔之Exif欄位取得資訊 |
|[Media](#Excepted-type-PT:-Media)| xsd:string  |Github照片連結 
|[Media_Credit](#Excepted-type-PT:-Media_Credit)|[Indicator of Exploration](#Excepted-type-PT-Indicator-of-Exploration) xsd:string| [`人際關係`](#Excepted-type-PT-人際關係) [ `感性類` ](#Excepted-type-PT-`感性類`) [ `創造力` ](#Excepted-type-PT-`創造力`)|
|[Media_Caption](#Excepted-type-PT:-Media_Caption)|[Details about the Indicator](#Excepted-type-PT-Details-about-the-Indicator) | [`社團同學（分別有自己高中與不同高中）`](#Property-PT:-社團同學（分別有自己高中與不同高中）) [`不同年紀的同學（學長姐、學弟妹）`](#Property-PT:-不同年紀的同學（學長姐、學弟妹）) [`風景`](#Property-PT:-風景) [`設計與美術`](#Property-PT:-設計與美術) |

### ++Classes PT: `秋遊`++
| Class name | Expected Type |Description|
| ------ | ----------- |----|
|[headline](#Excepted-type-PT:-headline)|[`秋遊`](#Classes-PT-`秋遊`) xsd:string |為台南一中科研社與其他全台友社共同舉辦的其中一項大型活動|
|[datetime (year,month,day,time)](#Excepted-type-PT:-datetime)|xsd:string |由照片檔之Exif欄位取得資訊 |
|[Media](#Excepted-type-PT:-Media)| xsd:string  |Github照片連結| 
|[Media_Credit](#Excepted-type-PT:-Media_Credit)|[Indicator of Exploration](#Excepted-type-PT-Indicator-of-Exploration) xsd:string|[`休閒娛樂`](#Excepted-type-PT-`休閒娛樂`)|
|[Media_Caption](#Excepted-type-PT:-Media_Caption)|[Details about the Indicator](#Excepted-type-PT-Details-about-the-Indicator) |[`社團活動`](#Property-PT:-社團活動) |

### ++Classes PT: `科普列車`++
| Class name | Expected Type |Description|
| ------ | ----------- |----|
|[headline](#Excepted-type-PT:-headline)|[`科普列車`](#Classes-PT-`科普列車`) xsd:string |「2018臺灣科普環島列車」今（4/30）日於臺北車站正式啟動，這輛四節車廂的火車，將於4月30日到5月4日間，用5天繞行台灣一周，共停靠23個車站，全臺各地的學童除了可以在火車上體驗各種科學實驗活動外，在火車進站前後，也可以在車站玩一個小時的科學活動。由科技部指導，成功大學、交通部台灣鐵路管理局及國家實驗研究院共同主辦的「2018臺灣科普環島列車」活動，為科技部和各縣市教育局處補助的「2018全民科學週（日）」科普活動揭開序幕。四節車廂的科學實驗活動分別由臺中女中、臺中一中、彰化女中、臺南一中、家齊高中、高雄中學、高雄女中等校學生與美光科技及台灣默克集團設計。每一停靠站則由各縣市「全民科學週（日）」科普活動計畫執行團隊在車站舉辦各種科學實驗和表演，接待約200至240位當地學童、家長及祖父母開心玩科學，上火車後繼續玩到下一站，然後再在下一站體驗不一樣的科學實驗。|
|[datetime (year,month,day,time)](#Excepted-type-PT:-datetime)|xsd:string |由照片檔之Exif欄位取得資訊 |
|[Media](#Excepted-type-PT:-Media)| xsd:string  |Github照片連結 
|[Media_Credit](#Excepted-type-PT:-Media_Credit)|[Indicator of Exploration](#Excepted-type-PT-Indicator-of-Exploration) xsd:string| [`人際關係`](#Excepted-type-PT-人際關係) [ `知識類` ](#Excepted-type-PT-`知識類`) [ `文學造詣` ](#Excepted-type-PT-`文學造詣`)  [`毅力展現` ](#Excepted-type-PT-`毅力展現`)[ `創造力` ](#Excepted-type-PT-`創造力`)|
|[Media_Caption](#Excepted-type-PT:-Media_Caption)|[Details about the Indicator](#Excepted-type-PT-Details-about-the-Indicator) | [`社團同學（分別有自己高中與不同高中）`](#Property-PT:-社團同學（分別有自己高中與不同高中）)  [`不同年紀的同學（學長姐、學弟妹）`](#Property-PT:-不同年紀的同學（學長姐、學弟妹）)[`老師（分別是自己高中與其他學校）`](#Property-PT:-老師（分別是自己高中與其他學校）)[`物品的種類（動植物）`](#Property-PT:-物品的種類（動植物）)[`設計與美術`](#Property-PT:-設計與美術)|

### ++Classes PT: `桌遊`++
| Class name | Expected Type |Description|
| ------ | ----------- |----|
|[headline](#Excepted-type-PT:-headline)|[`桌遊`](#Classes-PT-`桌遊`) xsd:string |為108屆的南一中科研社幹部一個小小的聚會|
|[datetime (year,month,day,time)](#Excepted-type-PT:-datetime)|xsd:string |由照片檔之Exif欄位取得資訊 |
|[Media](#Excepted-type-PT:-Media)| xsd:string  |Github照片連結 
|[Media_Credit](#Excepted-type-PT:-Media_Credit)|[Indicator of Exploration](#Excepted-type-PT-Indicator-of-Exploration) xsd:string|[`人際關係`](#Excepted-type-PT-人際關係) [`休閒娛樂`](#Excepted-type-PT-`休閒娛樂`)|
|[Media_Caption](#Excepted-type-PT:-Media_Caption)|[Details about the Indicator](#Excepted-type-PT-Details-about-the-Indicator) | [`社團同學（分別有自己高中與不同高中）`](#Property-PT:-社團同學（分別有自己高中與不同高中）) [`畢業後遊玩`](#Property-PT:-畢業後遊玩)|

### ++Classes PT: `高ㄧ預幹講版`++
| Class name | Expected Type |Description|
| ------ | ----------- |----|
|[headline](#Excepted-type-PT:-headline)|[`高ㄧ預幹講版`](#Classes-PT-`高ㄧ預幹講版`) xsd:string |為歷代南ㄧ中幹部選舉的其中一項內容，學弟需準備一項科學主題，以類似教課方式給學長們看|
|[datetime (year,month,day,time)](#Excepted-type-PT:-datetime)|xsd:string |由照片檔之Exif欄位取得資訊 |
|[Media](#Excepted-type-PT:-Media)| xsd:string  |Github照片連結 
|[Media_Credit](#Excepted-type-PT:-Media_Credit)|[Indicator of Exploration](#Excepted-type-PT-Indicator-of-Exploration) xsd:string|[ `知識類` ](#Excepted-type-PT-`知識類`)|
|[Media_Caption](#Excepted-type-PT:-Media_Caption)|[Details about the Indicator](#Excepted-type-PT-Details-about-the-Indicator) |  [`校內知識（課堂學業、社團等）`](#Property-PT:-校內知識（課堂學業、社團等）)[`科普知識`](#Property-PT:-科普知識)[`物品的種類（動植物）`](#Property-PT:-物品的種類（動植物）) |

### ++Classes PT: `畢業後歡唱`++
| Class name | Expected Type |Description|
| ------ | ----------- |----|
|[headline](#Excepted-type-PT:-headline)|[`畢業後歡唱`](#Classes-PT-`畢業後歡唱`) xsd:string |為108屆的南一中科研社幹部一個小小的聚會|
|[datetime (year,month,day,time)](#Excepted-type-PT:-datetime)|xsd:string |由照片檔之Exif欄位取得資訊 |
|[Media](#Excepted-type-PT:-Media)| xsd:string  |Github照片連結 
|[Media_Credit](#Excepted-type-PT:-Media_Credit)|[Indicator of Exploration](#Excepted-type-PT-Indicator-of-Exploration) xsd:string| [`人際關係`](#Excepted-type-PT-人際關係) [`休閒娛樂`](#Excepted-type-PT-`休閒娛樂`)|
|[Media_Caption](#Excepted-type-PT:-Media_Caption)|[Details about the Indicator](#Excepted-type-PT-Details-about-the-Indicator) | [`社團同學（分別有自己高中與不同高中）`](#Property-PT:-社團同學（分別有自己高中與不同高中）) [`畢業後遊玩`](#Property-PT:-畢業後遊玩) |

### ++Classes PT: `畢業舞會＆通宵夜唱`++
| Class name | Expected Type |Description|
| ------ | ----------- |----|
|[headline](#Excepted-type-PT:-headline)|[`畢業舞會＆通宵夜唱`](#Classes-PT-`畢業舞會＆通宵夜唱`) xsd:string |為南一中南女共同舉辦之畢業活動|
|[datetime (year,month,day,time)](#Excepted-type-PT:-datetime)|xsd:string |由照片檔之Exif欄位取得資訊 |
|[Media](#Excepted-type-PT:-Media)| xsd:string  |Github照片連結 
|[Media_Credit](#Excepted-type-PT:-Media_Credit)|[Indicator of Exploration](#Excepted-type-PT-Indicator-of-Exploration) xsd:string|[`人際關係`](#Excepted-type-PT-人際關係) [`休閒娛樂`](#Excepted-type-PT-`休閒娛樂`)|
|[Media_Caption](#Excepted-type-PT:-Media_Caption)|[Details about the Indicator](#Excepted-type-PT-Details-about-the-Indicator) | [`社團同學（分別有自己高中與不同高中）`](#Property-PT:-社團同學（分別有自己高中與不同高中）) [`雙人合照`](#Property-PT:-雙人合照) [`團體大合照`](#Property-PT:-團體大合照)[`畢業後遊玩`](#Property-PT:-畢業後遊玩)|

### ++Classes PT: `寒訓`++
| Class name | Expected Type |Description|
| ------ | ----------- |----|
|[headline](#Excepted-type-PT:-headline)|[`寒訓`](#Classes-PT-`寒訓`) xsd:string |為台南一中科研社與其他全台友社共同舉辦的其中一項大型活動|
|[datetime (year,month,day,time)](#Excepted-type-PT:-datetime)|xsd:string |由照片檔之Exif欄位取得資訊 |
|[Media](#Excepted-type-PT:-Media)| xsd:string  |Github照片連結 
|[Media_Credit](#Excepted-type-PT:-Media_Credit)|[Indicator of Exploration](#Excepted-type-PT-Indicator-of-Exploration) xsd:string|[`人際關係`](#Excepted-type-PT-人際關係) [ `感性類` ](#Excepted-type-PT-`感性類`)|
|[Media_Caption](#Excepted-type-PT:-Media_Caption)|[Details about the Indicator](#Excepted-type-PT-Details-about-the-Indicator) | [`社團同學（分別有自己高中與不同高中）`](#Property-PT:-社團同學（分別有自己高中與不同高中）) [`不同年紀的同學（學長姐、學弟妹）`](#Property-PT:-不同年紀的同學（學長姐、學弟妹）) [`感性內容（抽象情感展現）`](#Property-PT:-感性內容（抽象情感展現）)[`雙人合照`](#Property-PT:-雙人合照)|[`團體大合照`](#Property-PT:-團體大合照)|

### ++Classes PT: `暑訓`++
| Class name | Expected Type |Description|
| ------ | ----------- |----|
|[headline](#Excepted-type-PT:-headline)|[`暑訓`](#Classes-PT-`暑訓`) xsd:string |為台南一中科研社與其他全台友社共同舉辦的其中一項大型活動|
|[datetime (year,month,day,time)](#Excepted-type-PT:-datetime)|xsd:string |由照片檔之Exif欄位取得資訊 |
|[Media](#Excepted-type-PT:-Media)| xsd:string  |Github照片連結 
|[Media_Credit](#Excepted-type-PT:-Media_Credit)|[Indicator of Exploration](#Excepted-type-PT-Indicator-of-Exploration) xsd:string|[`人際關係`](#Excepted-type-PT-人際關係) [ `感性類` ](#Excepted-type-PT-`感性類`)|
|[Media_Caption](#Excepted-type-PT:-Media_Caption)|[Details about the Indicator](#Excepted-type-PT-Details-about-the-Indicator) |[`社團同學（分別有自己高中與不同高中）`](#Property-PT:-社團同學（分別有自己高中與不同高中）) [`不同年紀的同學（學長姐、學弟妹）`](#Property-PT:-不同年紀的同學（學長姐、學弟妹）) [`感性內容（抽象情感展現）`](#Property-PT:-感性內容（抽象情感展現）)[`雙人合照`](#Property-PT:-雙人合照)|[`團體大合照`](#Property-PT:-團體大合照)|

### ++Classes PT: `雄女幹見`++
| Class name | Expected Type |Description|
| ------ | ----------- |----|
|[headline](#Excepted-type-PT:-headline)|[`雄女幹見`](#Classes-PT-`雄女幹見`) xsd:string |此活動是南ㄧ中科研社與雄女生研社共同舉辦之活動|
|[datetime (year,month,day,time)](#Excepted-type-PT:-datetime)|xsd:string |由照片檔之Exif欄位取得資訊 |
|[Media](#Excepted-type-PT:-Media)| xsd:string  |Github照片連結 
|[Media_Credit](#Excepted-type-PT:-Media_Credit)|[Indicator of Exploration](#Excepted-type-PT-Indicator-of-Exploration) xsd:string|[`人際關係`](#Excepted-type-PT-人際關係)|
|[Media_Caption](#Excepted-type-PT:-Media_Caption)|[Details about the Indicator](#Excepted-type-PT-Details-about-the-Indicator) |[`社團同學（分別有自己高中與不同高中）`](#Property-PT:-社團同學（分別有自己高中與不同高中）) [`團體大合照`](#Property-PT:-團體大合照) |

### ++Classes PT: `試教`++
| Class name | Expected Type |Description|
| ------ | ----------- |----|
|[headline](#Excepted-type-PT:-headline)|[`試教`](#Classes-PT-`試教`) xsd:string |為歷代南ㄧ中幹部選舉的其中一項內容，學弟需準備一項科學主題，以類似論文發表的呈現在所有社團成員面前|
|[datetime (year,month,day,time)](#Excepted-type-PT:-datetime)|xsd:string |由照片檔之Exif欄位取得資訊 |
|[Media](#Excepted-type-PT:-Media)| xsd:string  |Github照片連結 
|[Media_Credit](#Excepted-type-PT:-Media_Credit)|[Indicator of Exploration](#Excepted-type-PT-Indicator-of-Exploration) xsd:string|[ `知識類` ](#Excepted-type-PT-`知識類`)|
|[Media_Caption](#Excepted-type-PT:-Media_Caption)|[Details about the Indicator](#Excepted-type-PT-Details-about-the-Indicator) | [`校內知識（課堂學業、社團等）`](#Property-PT:-校內知識（課堂學業、社團等）) [`科普知識`](#Property-PT:-科普知識) |


### ==Properties==

### ++Property PT: `四藝（琴棋書畫）`++
- __Status__:	[things](#Excepted-type-PT-status)
- __Domain__:	[`休閒娛樂`](#Excepted-type-PT-`休閒娛樂`)
- __Description__: 我在高中時期學過的、或是遇到的琴棋書畫，覺得印象深刻因此紀錄的照片內容

### ++Property PT: `電影影集`++
- __Status__:	[things](#Excepted-type-PT-status)
- __Domain__:	[`休閒娛樂`](#Excepted-type-PT-`休閒娛樂`)
- __Description__: 關於我看過吸引我的電影影集，因此紀錄的照片內容

### ++Property PT: `遊戲`++
- __Status__:	[things](#Excepted-type-PT-status)
- __Domain__:	[`休閒娛樂`](#Excepted-type-PT-`休閒娛樂`)
- __Description__: 關於我看過吸引我的遊戲，因此紀錄的照片內容

### ++Property PT: `動漫`++
- __Status__:	[things](#Excepted-type-PT-status)
- __Domain__:	[`休閒娛樂`](#Excepted-type-PT-`休閒娛樂`)
- __Description__: 關於我看過吸引我的動漫，因此紀錄的照片內容

### ++Property PT: `出國遊玩`++
- __Status__:	[matters](#Excepted-type-PT-status)
- __Domain__:	[`休閒娛樂`](#Excepted-type-PT-`休閒娛樂`)
- __Description__: 出國發現到有趣的事情，因此紀錄的照片內容

### ++Property PT: `社團活動`++
- __Status__:	[matters](#Excepted-type-PT-status)
- __Domain__:	[`休閒娛樂`](#Excepted-type-PT-`休閒娛樂`)
- __Description__: 紀錄與高中同學在社團生活的娛樂過程

### ++Property PT: `畢業後遊玩`++
- __Status__:	[matters](#Excepted-type-PT-status)
- __Domain__:	[`休閒娛樂`](#Excepted-type-PT-`休閒娛樂`)
- __Description__: 紀錄與高中同學的娛樂過程

### ++Property PT: `自拍照`++
- __Status__:	[people](#Excepted-type-PT-status)
- __Domain__:	[`人際關係`](#Excepted-type-PT-人際關係)
- __Description__: 我自己的照片

### ++Property PT: `同班同學（分別來自不同年級）`++
- __Status__:	[people](#Excepted-type-PT-status)
- __Domain__:	[`人際關係`](#Excepted-type-PT-人際關係)
- __Description__: 覺得特別有印象的或是契合的人，因此紀錄的照片內容

### ++Property PT: `社團同學（分別有自己高中與不同高中）`++
- __Status__:	[people](#Excepted-type-PT-status)
- __Domain__:	[`人際關係`](#Excepted-type-PT-人際關係)
- __Description__: 因為活動相識的同學，也覺得特別有印象的或是契合的人，因此紀錄的照片內容

### ++Property PT: `很要好的朋友`++
- __Status__:	[people](#Excepted-type-PT-status)
- __Domain__:	[`人際關係`](#Excepted-type-PT-人際關係)
- __Description__: 覺得特別有印象的或是契合的人，因此紀錄的照片內容

### ++Property PT: `老師（分別是自己高中與其他學校）`++
- __Status__:	[people](#Excepted-type-PT-status)
- __Domain__:	[`人際關係`](#Excepted-type-PT-人際關係)
- __Description__: 相當對我有影響的老師，因此紀錄的照片內容

### ++Property PT: `不同年紀的同學（學長姐、學弟妹）`++
- __Status__:	[people](#Excepted-type-PT-status)
- __Domain__:	[`人際關係`](#Excepted-type-PT-人際關係)
- __Description__: 覺得特別有印象的或是契合的人，因此紀錄的照片內容

### ++Property PT: `雙人合照`++
- __Status__:	[people](#Excepted-type-PT-status)
- __Domain__:	[`人際關係`](#Excepted-type-PT-人際關係)
- __Description__: 覺得特別有印象的或是契合的人，因此紀錄的照片內容

### ++Property PT: `團體大合照`++
- __Status__:	[people](#Excepted-type-PT-status)
- __Domain__:	[`人際關係`](#Excepted-type-PT-人際關係)
- __Description__: 通常配合某些特別活動存在的照片

### ++Property PT: `社團我教過的學生`++
- __Status__:	[people](#Excepted-type-PT-status)
- __Domain__:	[`人際關係`](#Excepted-type-PT-人際關係)
- __Description__: 印象特別深刻的人，因此紀錄的照片內容

### ++Property PT: `物品的種類（動植物）`++
- __Status__:	[things](#Excepted-type-PT-status)
- __Domain__:	[ `知識類` ](#Excepted-type-PT-`知識類`)
- __Description__: 覺得相當有趣的有趣事物，因此紀錄的照片內容

### ++Property PT: `校內知識（課堂學業、社團等）`++
- __Status__:	[things](#Excepted-type-PT-status)
- __Domain__:	[ `知識類` ](#Excepted-type-PT-`知識類`)
- __Description__: 覺得相當有趣的知識內容，因此紀錄的照片內容

### ++Property PT: `校外知識（中研院、營隊、出國）`++
- __Status__:	[things](#Excepted-type-PT-status)
- __Domain__:	[ `知識類` ](#Excepted-type-PT-`知識類`)
- __Description__: 覺得相當有趣的知識內容，因此紀錄的照片內容

### ++Property PT: `專業論文研究內容`++
- __Status__:	[things](#Excepted-type-PT-status)
- __Domain__:	[ `知識類` ](#Excepted-type-PT-`知識類`)
- __Description__: 覺得相當有深度的知識內容，因此紀錄的照片內容

### ++Property PT: `科普知識`++
- __Status__:	[things](#Excepted-type-PT-status)
- __Domain__:	[ `知識類` ](#Excepted-type-PT-`知識類`)
- __Description__: 覺得相當有趣的知識內容，因此紀錄的照片內容

### ++Property PT: `簡報內容`++
- __Status__:	[things](#Excepted-type-PT-status)
- __Domain__:	[ `知識類` ](#Excepted-type-PT-`知識類`)
- __Description__: 覺得很印象深刻的簡報呈現，因此紀錄的照片內容

### ++Property PT: `未來求學相關`++
- __Status__:	[things](#Excepted-type-PT-status)
- __Domain__:	[ `知識類` ](#Excepted-type-PT-`知識類`)
- __Description__: 覺得未來會在求學用得到的知識內容，因此紀錄的照片內容

### ++Property PT: `風景`++
- __Status__:	[things](#Excepted-type-PT-status)
- __Domain__:	[ `感性類` ](#Excepted-type-PT-`感性類`)
- __Description__: 感到特別有觸動到感覺的事物，因此紀錄的照片內容

### ++Property PT: `網紅明星照`++
- __Status__:	[things](#Excepted-type-PT-status)
- __Domain__:	[ `感性類` ](#Excepted-type-PT-`感性類`)
- __Description__: 覺得嚮往的網路名人，因此而紀錄的照片內容

### ++Property PT: `心理研究相關`++
- __Status__:	[matters](#Excepted-type-PT-status)
- __Domain__:	[ `感性類` ](#Excepted-type-PT-`感性類`)
- __Description__: 作為較為抽象的心理內容或事件，因此紀錄的照片內容

### ++Property PT: `感性內容（抽象情感展現）`++
- __Status__:	[things](#Excepted-type-PT-status)
- __Domain__:	[ `感性類` ](#Excepted-type-PT-`感性類`)
- __Description__: 感到特別有觸動到感覺的事物，因此紀錄的照片內容

### ++Property PT: `名言佳句`++
- __Status__:	[things](#Excepted-type-PT-status)
- __Domain__:	[ `文學造詣` ](#Excepted-type-PT-`文學造詣`)
- __Description__: 個人心理覺得很是觸動的文字感受，因此紀錄的照片內容

### ++Property PT: `科學實驗`++
- __Status__:	[matters](#Excepted-type-PT-status)
- __Domain__:	[`實作體驗` ](#Excepted-type-PT-`實作體驗`)
- __Description__: 作為在課堂、活動等體驗到的其中一項事物，以紀錄的照片內容

### ++Property PT: `程式設計`++
- __Status__: [things](#Excepted-type-PT-status)
- __Domain__:	[`實作體驗` ](#Excepted-type-PT-`實作體驗`)
- __Description__: 作為學習到的其中一項新事物，以紀錄的照片內容

### ++Property PT: `廚藝`++
- __Status__:	[matters](#Excepted-type-PT-status)
- __Domain__:	[`實作體驗` ](#Excepted-type-PT-`實作體驗`)
- __Description__: 作為學習到的其中一項新事物，以紀錄的照片內容

### ++Property PT: `影片剪輯`++
- __Status__:	[matters](#Excepted-type-PT-status)
- __Domain__:	[`實作體驗` ](#Excepted-type-PT-`實作體驗`)
- __Description__: 作為學習到的其中一項新事物，以紀錄的照片內容

### ++Property PT: `設計與美術`++
- __Status__:	[matters](#Excepted-type-PT-status)
- __Domain__:	[ `創造力` ](#Excepted-type-PT-`創造力`)
- __Description__: 紀錄自己創造出來的創意物品的照片內容

### ++Property PT: `團隊合作經驗`++
- __Status__:	[matters](#Excepted-type-PT-status)
- __Domain__:	[`毅力展現` ](#Excepted-type-PT-`毅力展現`)
- __Description__: 課程、活動等與他人合作的照片內容

### ++Property PT: `運動相關`++
- __Status__:	[matters](#Excepted-type-PT-status)
- __Domain__:	[`毅力展現` ](#Excepted-type-PT-`毅力展現`)
- __Description__: 關於高中時有關運動相關的照片內容


External Vocabulary References
===
### Schema.org Vocabulary
### Phototrack Vocabulary


### ++Excepted type PT: `休閒娛樂`++
    休閒娛樂 - 興趣的培養與身心放鬆的活動，比較沒有刻意的執行目的純粹遊玩
- __Properties include__:[`四藝（琴棋書畫）`](#Property-PT:-四藝（琴棋書畫）)|[`電影影集`](#Property-PT:-電影影集）)|[`遊戲`](#Property-PT:-遊戲)|[`動漫`](#Property-PT:-動漫)|[`出國遊玩`](#Property-PT:-出國遊玩)|[`社團活動`](#Property-PT:-社團活動)|[`畢業後遊玩`](#Property-PT:-畢業後遊玩)
- __Expected Type__: [Indicator of Exploration](#Excepted-type-PT-Indicator-of-Exploration) 
- __Description__: 休閒娛樂泛指大多我自己有興趣的課外休閒活動。從對應的Properties可以稍微了解我在高中有直接嘗試的相關事物，這個Properties也是目前的分類種類。

### ++Excepted type PT: `人際關係`++
    人際關係 - 從陌生到熟悉，情意脈絡的連結也是回憶最多最豐富的部分

- __Properties include__:[`自拍照`](#Property-PT:-自拍照)|[`同班同學（分別來自不同年級）`](#Property-PT:-同班同學（分別來自不同年級）)|[`社團同學（分別有自己高中與不同高中）`](#Property-PT:-社團同學（分別有自己高中與不同高中）)|[`很要好的朋友`](#Property-PT:-很要好的朋友)|[`老師（分別是自己高中與其他學校）`](#Property-PT:-老師（分別是自己高中與其他學校）)|[`不同年紀的同學（學長姐、學弟妹）`](#Property-PT:-不同年紀的同學（學長姐、學弟妹）)|[`雙人合照`](#Property-PT:-雙人合照)|[`團體大合照`](#Property-PT:-團體大合照)|[`社團我教過的學生`](#Property-PT:-社團我教過的學生)
- __Expected Type__: [Indicator of Exploration](#Excepted-type-PT-Indicator-of-Exploration) 
- __Description__: 人際關係泛指大多有出現在照片的人我都會有些印象。從對應的Properties可以稍微了解我在高中有從不同的角度認識到不同的人，也進而擁有很多不同故事。這個Properties也是目前的分類種類。


### ++Excepted type PT: `知識類`++
    知識類 - 拍攝的當下被內容吸引到，富有熱情的紀錄下來

- __Properties include__:[`物品的種類（動植物）`](#Property-PT:-物品的種類（動植物）)|[`校內知識（課堂學業、社團等）`](#Property-PT:-校內知識（課堂學業、社團等）)|[`校外知識（中研院、營隊、出國）`](#Property-PT:-校外知識（中研院、營隊、出國）)|[`專業論文研究內容`](#Property-PT:-專業論文研究內容)|[`科普知識`](#Property-PT:-科普知識)|[`簡報內容`](#Property-PT:-簡報內容)|[`未來求學相關`](#Property-PT:-未來求學相關)
- __Expected Type__: [Indicator of Exploration](#Excepted-type-PT-Indicator-of-Exploration) 
- __Description__: 知識類泛指大多我自己向不同地方吸收的有趣內容。從對應的Properties可以稍微了解我在高中也從四面八方的出處獲得不同的有趣資訊。這個Properties也是目前的分類種類。


### ++Excepted type PT: `感性類`++
    感性類 - 拍攝的當下被腦中無言得以抒發，極具衝動的拍攝紀錄 

- __Properties include__:[`風景`](#Property-PT:-風景)|[`網紅明星照`](#Property-PT:-網紅明星照)|[`心理研究相關`](#Property-PT:-心理研究相關)|[`感性內容（抽象情感展現）`](#Property-PT:-感性內容（抽象情感展現）)
- __Expected Type__: [Indicator of Exploration](#Excepted-type-PT-Indicator-of-Exploration) 
- __Description__: 感性類泛指大多我自己內心與照片可能有產生一些想法進而用照片的形式記錄下來。從對應的Properties可以稍微了解我在高中生活有捕捉到這種瞬間。這個Properties也是目前的分類種類。

### ++Excepted type PT: `文學造詣`++
    文學造詣 - 理工大腦就是沒有華美的文字，看書的同時隨手紀錄欣賞

- __Properties include__:[`名言佳句`](#Property-PT:-名言佳句)
- __Expected Type__: [Indicator of Exploration](#Excepted-type-PT-Indicator-of-Exploration) 
- __Description__: 文學造詣泛指大多是紀錄我自己欣賞的文字。從對應的Properties可以稍微了解我在高中有直接嘗試紀錄的相關部分文章，這個Properties也是目前的分類種類。

### ++Excepted type PT: `實作體驗`++
    實作體驗 - 親手體驗過更能了解紙本上的內容，每每看照片猶然興奮
- __Properties include__:[`科學實驗`](#Property-PT:-科學實驗)|[`程式設計`](#Property-PT:-程式設計)|[`廚藝`](#Property-PT:-廚藝)|[`影片剪輯`](#Property-PT:-影片剪輯)
- __Expected Type__: [Indicator of Exploration](#Excepted-type-PT-Indicator-of-Exploration) 
- __Description__: 實作體驗泛指大多我自己有親自嘗試過的一些有趣事情。從對應的Properties可以稍微了解我在高中有直接嘗試的相關事物，這個Properties也是目前的分類種類。

### ++Excepted type PT: `創造力`++
    創造力 - 從0到1的創造過程，充實感值得持續體會
- __Properties include__:[`設計與美術`](#Property-PT:-設計與美術)
- __Expected Type__: [Indicator of Exploration](#Excepted-type-PT-Indicator-of-Exploration) 
- __Description__: 創造力泛指我在高中突發其想做一些事情覺得有趣而紀錄的部分。從對應的Properties可以了解我目前對此部分定義的數量還不夠多且仔細，這個Properties也僅是目前的分類種類。

### ++Excepted type PT: `毅力展現`++
    毅力展現 - 累積到終點的勝利果實，翻看照片時也都歷歷在目。
- __Properties include__:[`團隊合作經驗`](#Property-PT:-團隊合作經驗)|[`運動相關`](#Property-PT:-運動相關)
- __Expected Type__: [Indicator of Exploration](#Excepted-type-PT-Indicator-of-Exploration) 
- __Description__: 毅力展現泛指大多我自己接觸過比較需要堅持的活動經驗。從對應的Properties可以稍微了解我在高中有直接嘗試的相關事物也還比較少，應該還可以再細分。這個Properties也是目前的分類種類。

### ++Excepted type PT: Personnal classification++
- **Personnal classification:** |[`小聯課`](#Classes-PT-`小聯課`)|[`中研院`](#Classes-PT-`中研院`)｜[`企劃書`](#Classes-PT-`企劃書`)｜[`社課`](#Classes-PT-`社課`)｜[`思源`](#Classes-PT-`思源`)｜[`秋遊`](#Classes-PT-`秋遊`)｜[`科普列車`](#Classes-PT-`科普列車`)｜[`桌遊`](#Classes-PT-`桌遊`)｜[`高一預幹講版`](#Classes-PT-`高一預幹講版`)｜[`畢業後歡唱`](#Classes-PT-`畢業後歡唱`)｜[`畢業舞會＆通宵夜唱`](#Classes-PT-`畢業舞會＆通宵夜唱`)｜[`寒訓`](#Classes-PT-`寒訓`)｜[`暑訓`](#Classes-PT-`暑訓`)｜[`雄女幹見`](#Classes-PT-`雄女幹見`)｜[`試教`](#Classes-PT-`試教`)｜

### ++Excepted type PT: Details about the Indicator++
- **Details about the  Indicator :** |[`四藝（琴棋書畫）`](#Property-PT:-四藝（琴棋書畫）)|[`電影影集`](#Property-PT:-電影影集）)|[`遊戲`](#Property-PT:-遊戲)|[`動漫`](#Property-PT:-動漫)|[`出國遊玩`](#Property-PT:-出國遊玩)|[`社團活動`](#Property-PT:-社團活動)|[`畢業後遊玩`](#Property-PT:-畢業後遊玩)|[`人的性別`](#Property-PT:-人的性別)|[`同班同學（分別來自不同年級）`](#Property-PT:-同班同學（分別來自不同年級）)|[`社團同學（分別有自己高中與不同高中）`](#Property-PT:-社團同學（分別有自己高中與不同高中）)|[`很要好的朋友`](#Property-PT:-很要好的朋友)|[`老師（分別是自己高中與其他學校）`](#Property-PT:-老師（分別是自己高中與其他學校）)|[`不同年紀的同學（學長姐、學弟妹）`](#Property-PT:-不同年紀的同學（學長姐、學弟妹）)|[`雙人合照`](#Property-PT:-雙人合照)|[`團體大合照`](#Property-PT:-團體大合照)|[`社團我教過的學生`](#Property-PT:-社團我教過的學生)|[`物品的種類（動植物）`](#Property-PT:-物品的種類（動植物）)|[`校內知識（課堂學業、社團等）`](#Property-PT:-校內知識（課堂學業、社團等）)|[`校外知識（中研院、營隊、出國）`](#Property-PT:-校外知識（中研院、營隊、出國）)|[`專業論文研究內容`](#Property-PT:-專業論文研究內容)|[`科普知識`](#Property-PT:-科普知識)|[`簡報內容`](#Property-PT:-簡報內容)|[`未來求學相關`](#Property-PT:-未來求學相關)|[`風景`](#Property-PT:-風景)|[`網紅明星照`](#Property-PT:-網紅明星照)|[`心理研究相關`](#Property-PT:-心理研究相關)|[`感性內容（抽象情感展現）`](#Property-PT:-感性內容（抽象情感展現）)|[`名言佳句`](#Property-PT:-名言佳句)|[`科學實驗`](#Property-PT:-科學實驗)|[`程式設計`](#Property-PT:-程式設計)|[`廚藝`](#Property-PT:-廚藝)|[`影片剪輯`](#Property-PT:-影片剪輯)|[`設計與美術`](#Property-PT:-設計與美術)|[`團隊合作經驗`](#Property-PT:-團隊合作經驗)|[`運動相關`](#Property-PT:-運動相關)|

### ++Excepted type PT: Indicator of Exploration++ 
- **Indicator of Exploration:** |[`休閒娛樂`](#Excepted-type-PT-`休閒娛樂`)|[`人際關係`](#Excepted-type-PT-人際關係)|[ `知識類` ](#Excepted-type-PT-`知識類`)|[ `感性類` ](#Excepted-type-PT-`感性類`)|[ `文學造詣` ](#Excepted-type-PT-`文學造詣`)|[`實作體驗` ](#Excepted-type-PT-`實作體驗`)|[ `創造力` ](#Excepted-type-PT-`創造力`)|[`毅力展現` ](#Excepted-type-PT-`毅力展現`)|

### ++Excepted type PT: status++
    people / things / matters

### ++Excepted type PT: headline++
- 為標記各活動的主題
### ++Excepted type PT:datetime++
- 取自各照片的Exif欄位的拍攝時間作為紀錄
### ++Excepted type PT: Media++
- 取自在Github上的照片連結作為連接在網路上的照片呈現方式
### ++Excepted type PT: Media_Credit++
- 為Indicator of Exploration分類，由各活動中照片說分類的照片內容（此分類較為主觀）
### ++Excepted type PT: Media_Caption++
- 為Details about the Indicator 分類，由各活動中照片說分類的照片內容（此分類較為主觀）



Acknowledgments
===

Recent Changes (未來改版時用)
===

