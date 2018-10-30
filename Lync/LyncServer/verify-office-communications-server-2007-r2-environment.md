---
title: Office Communications Server 2007 R2 環境の確認
TOCTitle: Office Communications Server 2007 R2 環境の確認
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49887177
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Office Communications Server 2007 R2 環境の確認

 

_**トピックの最終更新日:** 2012-10-16_

Lync Server 2013 を展開して Office Communications Server 2007 R2 と共存状態にする前に、 Office Communications Server 2007 R2 サービスが構成され、起動されていることを確認する必要があります。

**Office Communications Server 2007 R2 管理ツールを使用してプールが開始されていることを確認する**

1.  Office Communications Server 2007 R2 管理ツールを開きます。

2.  \[**フォレスト**\] ノード、\[**Standard Edition サーバー**\] ノードまたは \[**エンタープライズ プール**\] ノード、プールまたはサーバー名の順に展開します。

3.  Standard Edition サーバーまたはエンタープライズ プールでサービスが実行していることを確認します。
    
    ![Office Communications Server 2007 R2 管理コンソール](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 管理コンソール")

**Office Communications Server 2007 R2 用に構成されたユーザーを確認する**

1.  Office Communications Server 2007 R2 管理ツールを開きます。

2.  \[**フォレスト**\] ノード、\[**Standard Edition サーバー**\] ノードまたは \[**エンタープライズ プール**\] ノード、プールまたはサーバー名の順に展開します。

3.  \[**ユーザー**\] をクリックします。

4.  Office Communications Server 2007 R2 ユーザーのリストを確認します。
    
    ![OCS 管理ツールのユーザーの一覧](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "OCS 管理ツールのユーザーの一覧")

**レガシ XMPP フェデレーション パートナーの構成を確認する**

1.  レガシ XMPP サーバーから、管理ツール\\サービス アプレットに移動します。

2.  Office Communications Server XMPP Gateway サービスが開始されていることを確認します。
    
    ![Office Communications Server XMPP ゲートウェイ サービス](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP ゲートウェイ サービス")

