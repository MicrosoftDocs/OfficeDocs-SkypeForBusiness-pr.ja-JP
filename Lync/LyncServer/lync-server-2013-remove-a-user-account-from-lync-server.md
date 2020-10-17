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
ms.openlocfilehash: 782077cc532dc751076d3152467de865fe799a29
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536514"
---
# <a name="remove-a-user-account-from-lync-server-2013"></a>Lync Server 2013 からユーザーアカウントを削除する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-22_

次の手順を使用して、Lync Server 2013 で以前に追加したユーザーアカウントを削除できます。

<div>


> [!NOTE]  
> ユーザーを削除すると、そのユーザー アカウントに対して構成したすべての設定が失われます。 代わりにユーザーアカウントを一時的に無効にする場合は、「 <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Lync Server 2013 のユーザーアカウントの無効化または再有効化</A>」を参照してください。



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a>Lync Server 管理シェルを使用してユーザーアカウントを削除するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックします。

4.  [**ユーザーの検索**] ボックスに、無効または再度有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、あるいは回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。

5.  表で、削除するユーザー アカウントをクリックします。

6.  [**操作**] メニューの [**Lync Server から削除**] をクリックします。ダイアログ ボックスが表示されます。

7.  ダイアログ ボックスで、ユーザーを削除するかどうかを確認するメッセージが表示されます。[**OK**] をクリックします。

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してユーザーアカウントを削除する

Disable-CsUser コマンドレットを使用して、ユーザーアカウントを削除できます。 このコマンドレットは、Lync Server 2013 管理シェルまたはリモートセッション Windows PowerShell から実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-remove-a-user-account"></a>ユーザーアカウントを削除するには

  - ユーザー アカウントを削除するには、Disable-CsUser コマンドレットを使用します。次に例を示します。
    
        Disable-CsUser -Identity "Ken Myer"
    
    このコマンドを実行した後、削除したアカウントおよびその以前の設定を再度有効化することはできません。Enable-CsUser コマンドレットを使用して、Ken Myer の新規アカウントを作成する必要があります。

</div>

詳細については、「 [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) コマンドレット」のヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のユーザーアカウントを無効または再度有効にする](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[Lync Server 2013 のユーザーの有効化および無効化](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

