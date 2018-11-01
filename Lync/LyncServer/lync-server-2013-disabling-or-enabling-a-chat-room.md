---
title: 'Lync Server 2013: チャット ルームの無効化または有効化'
TOCTitle: チャット ルームの無効化または有効化
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ215883(v=OCS.15)
ms:contentKeyID: 48273818
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのチャット ルームの無効化または有効化

 

_**トピックの最終更新日:** 2014-02-05_

常設チャット ルームのトピックが不要になった場合は、ユーザーがそのチャット ルームを使用できないようにチャット ルームを無効にできます。チャット ルームを無効にすると、すべてのメンバーがチャット ルームから即座に切断されます。チャット ルームを無効にした後、ユーザーは、そのチャット ルームに再び参加することも、チャット ルームを検索することもできません。

常設チャット管理者は、無効にしたチャット ルームを後で再度有効にできます。チャット ルームを無効にすると、メンバーシップ リストとその他の設定が保持されます。チャット ルームを再度有効にするときに、設定を手動で再作成する必要はありません。

チャット ルームの履歴が保持されている場合は、チャット ルームを無効にしても、コンテンツは保存されています (チャット ルームの履歴保持は、カテゴリ内のすべてのルームに適用されるカテゴリのオプション設定です。既定では、履歴が保持されますが、カテゴリの \[**チャット履歴を有効にする**\] を false に設定することにより履歴の保持をオフにできます)。ただし、チャット ルームが無効になっている間は、コンテンツは検索に表示されません。チャット ルームを後で有効にすると、ユーザーは、チャット ルームが無効になる前にポストされたメッセージを検索できます。

Windows PowerShell コマンドライン インターフェイスによるチャット ルームの有効化および無効化の詳細については、「[Windows PowerShell コマンドレットを使用した常設チャット サーバーの構成](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)」の「ルーム管理」を参照してください。チャット ルームを無効にするには、次のようなコマンドを使用します。

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

チャット ルームを有効にするには、Disabled プロパティを False に設定します。

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

Lync Server コントロール パネル では、チャット ルームを有効または無効にできません。

チャット ルームの構成の詳細については、「展開」のドキュメントの「[Lync Server 2013 でルームを構成する](lync-server-2013-configure-rooms.md)」を参照してください。

