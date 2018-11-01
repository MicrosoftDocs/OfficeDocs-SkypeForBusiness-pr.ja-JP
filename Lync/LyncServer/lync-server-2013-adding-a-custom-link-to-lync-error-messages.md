---
title: 'Lync Server 2013: Lync エラー メッセージへのユーザー設定リンクの追加'
TOCTitle: Lync エラー メッセージへのユーザー設定リンクの追加
ms:assetid: de756088-fcc3-4e47-bde8-4fa4cc852fd1
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398979(v=OCS.15)
ms:contentKeyID: 52056720
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Lync エラー メッセージへのユーザー設定リンクの追加

 

_**トピックの最終更新日:** 2013-02-20_

独自のトラブルシューティングやヘルプ デスク情報へのリンクを追加して、Lync 2013 エラー メッセージをカスタマイズします。これを行うには、**New-CSClientPolicy** コマンドレットまたは **Set-CSClientPolicy** Lync Server 管理シェル コマンドレットと CustomLinkInErrorMessages パラメーターを使用します。ユーザー設定リンクのテキストが \[管理者からのサポート トピックについては、ここをクリックしてください\] の場合には、カスタマイズできません。

たとえば、次のコマンドによって、ユーザー設定リンクが Lync 2013 エラー メッセージの脚注に表示され、リンク先が http://contoso.com/help/LyncHelpDesk.aspx:

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

この新しいポリシーをユーザーに割り当てるには、 **Grant-CSClientPolicy** を使用します。詳細については、「 Lync Server 管理シェル」のドキュメントの「 **New-CSClientPolicy**」と「 **Grant-CSClientPolicy**」を参照してください。

