---
title: 'Lync Server 2013: ユーザーおよびユーザー グループのドメインをルーム カテゴリへ追加する'
TOCTitle: ユーザーおよびユーザー グループのドメインをルーム カテゴリへ追加する
ms:assetid: ee03f2cf-1c84-41c4-b524-d0729be33b8c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ215884(v=OCS.15)
ms:contentKeyID: 48273940
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でユーザーおよびユーザー グループのドメインをルーム カテゴリへ追加する

 

_**トピックの最終更新日:** 2014-02-07_

チャット ルームに大人数のユーザーのグループを追加するには、「展開」のドキュメントの「[Lync Server 2013 でのカテゴリの構成](lync-server-2013-configure-categories.md)」および「[カテゴリを管理する](manage-categories.md)」を参照してください。たとえば、次のコマンドでは、Active Directory の NorthAmericaUsers OU のすべてのユーザーを NorthAmerica チャット ルームに追加します。

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=litwareinc,DC=com"}

次のコマンドでは、Finance 配布グループのすべてのメンバーを同じチャット ルームに追加します。

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=litwareinc,DC=com"}

