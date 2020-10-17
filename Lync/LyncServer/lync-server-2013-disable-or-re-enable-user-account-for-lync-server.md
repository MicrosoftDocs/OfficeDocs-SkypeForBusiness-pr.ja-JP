---
title: 'Lync Server 2013: Lync Server のユーザーアカウントの無効化または再有効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 646f4ae59ce5058af84c0e5ddd3197f7a9f47fe7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528994"
---
# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a>Lync Server 2013 のユーザーアカウントを無効または再度有効にする

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-04-04_

次の手順を使用して、ユーザーアカウントに対して構成した Lync Server 設定を失わずに、Lync Server 2013 で既に有効になっているユーザーアカウントを無効にすることができます。 Lync Server ユーザーアカウント設定が失われないため、ユーザーアカウントを再構成せずに、以前に有効になっていたユーザーアカウントを再度有効にすることができます。

<div>


> [!WARNING]  
> Active Directory のユーザーアカウントを無効にしても、ユーザーが Lync Server にサインインしたり、Lync Server を使用したりでき <STRONG>なくなることはありません</STRONG> 。 これは、Lync は認証プロセスを合理化する証明書認証を使用し、これらのクライアント証明書は180日間有効であるためです。 Lync Server へのアクセスが Lync Server に対して有効になっていた、無効にされた Active Directory アカウントを停止するには、 <STRONG>ユーザー</STRONG> コマンドレットを使用するか、この記事で説明しているように <STRONG>Lync server コントロールパネル</STRONG> を使用する必要があります。 ユーザーが Lync で無効にされ、中央管理ストアが環境内でレプリケートされ、ユーザーはサインインできなくなります。 また、サインインしているユーザーは切断されます。



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a>Lync Server で既に有効になっているユーザーアカウントを無効にするか、再び有効にするには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックします。

4.  [**ユーザーの検索**] ボックスに、無効または再度有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、あるいは回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。

5.  表で、無効または再度有効にするユーザー アカウントをクリックします。

6.  [**アクション**] メニューで、次のいずれかを実行します。
    
      - Lync server 2013 のユーザーアカウントを一時的に無効にするには、[ **Lync server に対して一時的に無効**にする] をクリックします。
    
      - Lync Server 2013 のユーザーアカウントを有効にするには、[ **Lync server の再有効化**] をクリックします。

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Windows PowerShell を使用してユーザーアカウントを無効にするか、再度有効にする

ユーザーアカウントを一時的に無効にして **から、ユーザーコマンドレット** を使用して再び有効にすることができます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-disable-a-user-account"></a>ユーザーアカウントを無効にするには

  - ユーザー アカウントを一時的に無効にするには、Enabled プロパティの値を False ($False) に設定します。 次に例を示します。
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a>ユーザーアカウントを再度有効にするには

  - 無効になっているユーザー アカウントを再度有効にするには、Enabled プロパティの値を True ($True) に設定します。 次に例を示します。
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

詳細については、「 [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のユーザーアカウントを追加して有効にする](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[Lync Server 2013 のユーザーの有効化および無効化](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

