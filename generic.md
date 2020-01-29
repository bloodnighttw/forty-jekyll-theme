---
layout: post
title:  Blog
description: 紀錄生活大小事
image: assets/images/pic07.jpg
nav-menu: true
---

## 今天真的會被搞死
```2020-01-29  週三 下午3:00```

今天我原本要寫Jar Loader，我想說為了debug 方便，去用個slf4j 來用 結果 不知道為啥 slf4j一直丟出 Expection(好像是pakage 衝突到吧)，這樣下來了我快4、50分鐘，後來我想說先別用，先去搞Jar Loader 吧.....

結果我在寫我在寫Loader 時又有問題了，經過幾番波折後，我發現原因了，因為我path 的前面忘了加 "jar:file:"，又搞我好久喔。

寫完這些後，我決定為明天要寫的準備一下(這部份還沒push 上來)，結果，又噴了一小段時間......

明天我來寫Server 的主體吧！ 順便先去了解JVM多線程的機制。

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

