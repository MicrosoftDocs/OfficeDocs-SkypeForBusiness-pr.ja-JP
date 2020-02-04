---
title: 'Lync Server 2013: Lync Server からユーザーアカウントを削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a user account from Lync Server
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49733596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97ee26fd15eb9df9174fd33cf9a45a6fe49411af
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746827"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-user-account-from-lync-server-2013"></a>Lync Server 2013 からユーザーアカウントを削除する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-22_

Lync Server 2013 で、以前に追加したユーザーアカウントを削除するには、次の手順を使用します。

<div>


> [!NOTE]  
> ユーザーを削除すると、ユーザーアカウントに対して構成した設定が失われます。 代わりにユーザーアカウントを一時的に無効にする場合は、「 <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Lync Server 2013 のユーザーアカウントを無効にする、またはもう一度有効</A>にする」のトピックを参照してください。



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a>Lync Server 管理シェルを使用してユーザーアカウントを削除するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックします。

4.  [**ユーザーの検索**] ボックスで、無効または再度有効にするユーザーアカウントの表示名、名、姓、セキュリティアカウントマネージャー (SAM) アカウント名、SIP アドレス、または行の Uniform resource IDENTIFIER (URI) のすべてまたは最初の部分を入力して、[**検索**] をクリックします。

5.  テーブルで、削除するユーザーアカウントをクリックします。

6.  [**操作**] メニューの [ **Lync Server から削除**] を選択すると、ダイアログボックスが表示されます。

7.  ダイアログボックスで、[ **OK** ] を選択してユーザーを削除します。

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してユーザーアカウントを削除する

ユーザーアカウントを削除するには、ユーザーの無効化コマンドレットを使用します。 このコマンドレットは、Lync Server 2013 Management Shell またはリモートセッション Windows PowerShell から実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-remove-a-user-account"></a>ユーザーアカウントを削除するには

  - ユーザーアカウントを削除するには、ユーザーの無効化コマンドレットを使用します。 次に例を示します。
    
        Disable-CsUser -Identity "Ken Myer"
    
    このコマンドが実行されると、アカウントとその前の設定を再び有効にする方法はありません。 代わりに、ユーザーコマンドレットを使用して、Ken Myer の新しいアカウントを作成する必要があります。

</div>

詳細については、「[ユーザーの無効化](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser)」コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のユーザーアカウントを無効にするか、再び有効にする](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[Lync Server 2013 のユーザーを有効または無効にする](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

