---
layout: post
title:  Blog
description: 紀錄生活大小事
image: assets/images/pic07.jpg
nav-menu: true
show_tile: true
---

## 有點久沒更新了
```2020-02-19  週六 下午8:13``
這兩個禮拜 稍微讀了點書 不然一直寫程式也不行 XDDD

首先我把wrapper 寫完了，結果我變成不知道要寫啥，渾渾噩噩的過了快一個禮拜。

結果我突然想到，我來寫個online judge 看看。dja

結果，我就瘋狂查google 到現在。

我用django 寫動態網頁，再沒有學過python 的狀況下直接實戰，老實說，python 不會很難，有得觀念跟Java 很像，讓我比較不習慣的是它 弱型別 的特色，變成是 有時候會搞不太清楚他是啥型態，而html 我也算一點熟 ，比較有問題的是css 和javascript ，後來我發現bootstrap 可以用 ，變成是我css 不用學了，然後 開工！

其實我知道java 也有跟django 很像的框架，好像叫spring mvc ，但我稍微看過了一下 ，有一點小複雜 ， 而且我本來就想碰python ，因為這兩個因素，讓我決定學習寫python + django !

然後 即使python django 簡單易懂，但我還是卡關了，models 好複雜喔，到底要怎樣處理 list 和 dict 阿阿阿阿阿阿阿阿阿阿阿阿阿阿阿阿阿阿...........


- - - 

## 準備來寫Wrapper 摟
```2020-02-08  週六 下午7:36```

最近心血來潮，想到去查一下以沒有 丟程式進去 會自動回傳結果的API ，結果還真的有，所以我就花了幾天研究一下這東西。

這東西叫做 [Judge0](https://github.com/judge0/api) , [官網](https://judge0.com)也有提供[不用自己開的api server](https://api.judge0.com) 可以使用。

一開始五還在想說到底怎樣使用這API 的說 結果我到最後花了一整天研究，原來要靠http request 來使用 API。

於是我在昨天就寫了個用java實現編譯某段字串的程式(拿python來測，因為最簡短 XDDD)，花了一小段時間，成功了！！！

所以我在想，如果把它架在我的電腦上，自己存取自己架的Api Server ，不是更好嗎？  的確官方有提供檔案，可以裝在docker上，但我絕對沒想到我會在上面搞那樣的久。

按照它github repo 上的說明，在安裝時要更改設定檔，沒有錯我是改了，但卻發現api server 還是不能存取，找來找去找不到原因(也許是我某項重要的東西沒有改到)。所以我重裝第2遍(然後我又花了幾十分鐘等待8G 的檔案下載完)......

在安裝第2遍時，我更謹慎了，這一次，我把所有config 檔內的所有設定都看一次，只改了幾項東西和幾個一定要改的東西，這一次比較好一點，api server 的主頁進去了，但好笑的事情發生了，當我試著發送 http request到 /languages 時，它一直給我回傳401，到底是為啥.......

我又花了1、2小時 尋找原因與解決方法，但我找不出方法，只好先去睡覺了......

而今天，我裝了第3 和 第4次，讓我慢慢說....

第3次，我裝在別的電腦上的虛擬機，結果裝虛擬機就折騰我1、2 小時，安裝到docker 時就白痴的一股腦裝下去，安裝時改的config 連動都沒動，我到吃飯才想起來....

然後第4次，我TM 終於成功了，結果是 我token 沒有設定，造成它無法正常存取，後來我查官方doc ，結果官方的doc 竟然有寫，而我竟然沒有看到......

然後，明天準備架第5次，順便來寫wrapper 摟。

- - - 

## 想要變更讀取Class 的方式
```2020-02-04  週四 下午8:34```

我在寫完後 一直如何簡化移植的手續，想著想著，我突然想到之前完全沒碰過的Annotation 所以花了幾天讀了相關資料，並做了練習。
有空開始開發吧！
 
[[練習範例連結](https://repl.it/@bbeenn1227/AnnotationPractice2)]

- - -

## 今天做了很多事情
```2020-01-30  週四 下午9:01```

今天我把 server 的框架完成了，並重寫了之前的一個專案，移植到我寫的這個框架......

而我原本昨天弄的maven repo 雖然可以deploy，結果我發現一個很好玩的事情deploy 是成功了，但我卻不能正常使用maven package ，可能我哪邊有問題吧......

然後我發現一件事，不知為啥我寫的新插件居然在沒有info.json 時可以執行，可能我要稍微處理一下（像是丟個Expection 之類的）

接下來我可能就是會對程式加入多線程，雖然我寫的框架還蠻小的，不過就當作練習吧

[[GitHub Repo](https://github.com/bloodnighttw/JDAwP)]

- - -

## 今天真的會被搞死
```2020-01-29  週三 下午3:00```

今天我原本要寫Jar Loader，我想說為了debug 方便，去用個slf4j 來用，結果不知道為啥 slf4j一直丟出 Expection(好像是pakage 衝突到吧)，這樣下來了我快4、50分鐘，後來我想說先別用，先去搞Jar Loader 吧.....

結果我在寫我在寫Loader 時又有問題了，經過幾番波折後，我發現原因了，因為我path 的前面忘了加 "jar:file:"，又搞我好久喔。

寫完這些後，我決定為明天要寫的準備一下(這部份還沒push 上來)，結果，又噴了一小段時間......

明天我來寫Server 的主體吧！ 順便先去了解JVM多線程的機制。

然後我現在才發現，我忘記push 了

[[GitHub Repo](https://github.com/bloodnighttw/JDAwP)]

- - -

## 一切正在開始，但今天還蠻順利的  
```2020-01-28  週二 下午4:31```

今天主要做了幾個事情

我把依賴管理平台從 Gradle 轉換成 Maven，畢竟Maven 用的比較習慣，而且暫時沒有會用到gradle script 的需求。

然後我寫了一個專門處理路徑的物件，裡面處理了包掛一些很重要的事情，像是取得工作路徑、取得所有能載入的Jar 檔案 的功能（當然該丟出的Expection 我沒有忽略掉），很棒。

原本打算今天只寫這些，結果因為寫完還有很多時間，所以我有去寫載入Jar 包info 檔的功能，結果一直丟出Expection ，原本我想說是Path 裡面某個已經open 的inputstream 沒有 close 掉，所以我又去修改Path 的程式，結果，竟然不是，JVM丟出Expection 的原因是我路徑格式不太對，然後在加上路徑打錯......

不過前前後後debug的時間不長，前前後後大約只花20 幾分鐘而已。

然後我明天來寫class loader 吧

[[GitHub Repo](https://github.com/bloodnighttw/JDAwP)][[這一次的Commit](https://github.com/bloodnighttw/JDAwP/commit/d7d93f1c47dc77db78bde7a70cc99a503303d3dc)]

