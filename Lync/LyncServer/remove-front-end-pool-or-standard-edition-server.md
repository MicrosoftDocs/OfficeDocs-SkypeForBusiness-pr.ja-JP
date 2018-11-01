---
title: フロントエンド プールまたは Standard Edition サーバーの削除
TOCTitle: フロントエンド プールまたは Standard Edition サーバーの削除
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49887030
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# フロントエンド プールまたは Standard Edition サーバーの削除

 

_**トピックの最終更新日:** 2012-10-04_

ここでは、フロント エンド プールまたは Standard Edition フロント エンド サーバーを削除するプロセスについて説明します。フロント エンド プールを削除する場合は、プール削除プロセスの一環として、そのプールに所属するそれぞれの フロント エンド サーバーを削除します。Standard Edition フロント エンド サーバーを削除する場合は、トポロジ ビルダーから SQL ストアの定義を削除する必要があります。

## フロントエンド サーバー プールを削除するには

1.  トポロジ ビルダーを開きます。

2.  Lync Server 2010 ノードに移動します。

3.  \[**Enterprise Edition フロントエンド プール**\]、フロント エンド プールの順に展開し、削除する フロント エンド プールを右クリックして、\[**削除**\] をクリックします。

4.  トポロジを公開し、レプリケーションの状態を確認し、必要に応じて Lync Server 展開ウィザードを実行します。

## Standard Edition フロントエンド サーバーを削除するには

1.  トポロジ ビルダーを開きます。

2.  Lync Server 2010 ノードに移動します。

3.  \[**Standard Edition フロントエンド サーバー**\] を展開し、削除する フロント エンド サーバーを右クリックして、\[**削除**\] をクリックします。

4.  \[**SQL ストア**\] を展開し、Standard Edition フロント エンド サーバーに関連付けられた SQL Server データベースを右クリックして、\[**削除**\] をクリックします。
    

    > [!IMPORTANT]
    > 併置された SQL Server データベースの定義を Standard Edition フロント エンド サーバーから削除する必要があります。



5.  トポロジを公開し、レプリケーションの状態を確認し、必要に応じて Lync Server 展開ウィザードを実行します。

