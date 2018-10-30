---
title: 通話受付管理のリセット
TOCTitle: 通話受付管理のリセット
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49886967
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 通話受付管理のリセット

 

_**トピックの最終更新日:** 2012-10-11_

Lync Server 2010フロント エンド プールで通話受付管理 (CAC) をホストしている場合、Lync Server 2010フロント エンド プールを削除するには、CAC のホスティングを Lync Server 2013 プールに移行しておく必要があります。

## CAC をリセットするには

1.  トポロジ ビルダーを開きます。

2.  サイト ノードを右クリックし、\[**プロパティの編集**\] をクリックします。

3.  \[**通話受付管理の設定**\] で、\[**通話受付管理の有効化**\] が選択されていることを確認します。

4.  \[**通話受付管理 (CAC) を実行するフロントエンド プール**\] で、CAC をホストする Lync Server 2013 プールを選択し、\[**OK**\] をクリックします。

5.  トポロジを公開します。

