---
title: 'Lync Server 2013: Lync Server 2013 のフロント エンド プールへの存続可能ブランチ アプライアンスの接続'
TOCTitle: Lync Server 2013 のフロント エンド プールへの存続可能ブランチ アプライアンスの接続
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49886920
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のフロント エンド プールへの存続可能ブランチ アプライアンスの接続

 

_**トピックの最終更新日:** 2012-10-05_

すべての 存続可能ブランチ アプライアンス (SBA) が、この SBA のバックアップ レジストラーとして機能する フロント エンド プールに関連付けられています。フロント エンド プールが Lync Server 2013 にアップグレードされるとき、フロント エンド プールのアップグレード中は、SBA と フロント エンド プールの関連付けを解除する必要があります。フロント エンド プールがアップグレードされたら、SBA と フロント エンド プールを再度関連付けることができます。これには、トポロジ ビルダーのトポロジから SBA を削除し、再度 SBA をトポロジ ビルダーに追加する作業が含まれます。SBA のユーザーは、SBA をトポロジから削除する前に他の フロント エンド プールに移動しておく必要があります。SBA をトポロジに戻したら、これらのユーザーは SBA に戻すことができます。

これらの手順の概要を次に示します。

1.  SBA のブランチ ユーザーを他の フロント エンド プールに移動します。

2.  トポロジから SBA を削除し、この SBA と、バックアップ レジストラーとして機能している既存の フロント エンド プールとの関連付けを解除します。

3.  フロント エンド プールを Microsoft Lync Server 2013 にアップグレードします。

4.  SBA をトポロジに追加します。

5.  バックアップ レジストラーとして新しい フロント エンド プールを SBA に関連付けます。

6.  ブランチ ユーザーを SBA に移動します。

## このセクション中

  - [トポロジへの Lync Server 2013 存続可能ブランチ アプライアンスのブランチ サイトの追加](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [トポロジへの Lync Server 2010 存続可能ブランチ アプライアンスのブランチ サイトの追加](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

