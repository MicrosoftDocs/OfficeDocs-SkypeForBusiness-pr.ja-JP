---
title: 'Lync Server 2013: メッセージの削除または廃止メッセージの削除'
TOCTitle: メッセージの削除または廃止メッセージの削除
ms:assetid: 3f0c612d-6dfd-41a4-a5fe-5ff3448eb0ce
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ215874(v=OCS.15)
ms:contentKeyID: 48271863
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのメッセージの削除または廃止メッセージの削除

 

_**トピックの最終更新日:** 2014-02-05_

常設チャット管理者が、常設チャット ルームからメッセージを削除したり、オプションで、メッセージを他のメッセージと置き換えたりできます。また、管理者は、日常のメンテナンスの一環として古いメッセージを削除し、データベースの拡大を最小限に抑えることもできます。たとえば、次の Windows PowerShell コマンドは、ユーザー kenmyer@litwareinc.com が ITChatRoom チャット ルームに投稿したすべてのメッセージを削除します。

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

また、次の例では、その削除されたすべてのメッセージが「削除されました」という通知で置き換えられます。

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

詳細については、[Remove-CsPersistentChatMessage](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsPersistentChatMessage) コマンドレットのヘルプ トピックを参照してください。

