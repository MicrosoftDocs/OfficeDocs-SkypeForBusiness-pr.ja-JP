---
title: 'Lync Server 2013: Lync Server のユーザーアカウントを無効にするか、再び有効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7944af89ffae7545ba3a2593c7617fc944a7916e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a>Lync Server 2013 のユーザーアカウントを無効にするか、再び有効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-04-04_

次の手順を使用して、ユーザーアカウント用に構成した Lync Server の設定を失わずに、Lync Server 2013 で以前に有効になっていたユーザーアカウントを無効にすることができます。 Lync Server のユーザーアカウント設定が失われないため、ユーザーアカウントを再構成することなく、以前に有効になっていたユーザーアカウントを再び有効にすることができます。

<div>


> [!WARNING]  
> Active Directory のユーザーアカウントを無効にしても、ユーザーが Lync Server にサインインしたり、使用できなくなること<STRONG>はありません</STRONG>。 これは、Lync では認証プロセスを合理化する証明書認証が使用されるため、これらのクライアント証明書は180日間有効です。 Lync Server へのアクセス許可が有効になっていた Active Directory アカウントを無効にするには、[<STRONG>無効</STRONG>にする] を使用するか、この記事で説明されているように<STRONG>Lync server コントロールパネル</STRONG>を使用する必要があります。 ユーザーが Lync で無効になっており、中央管理ストアが環境内でレプリケートされた後、ユーザーはサインインできなくなります。 また、サインインしたユーザーは切断されます。



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a>Lync Server で以前に有効になっていたユーザーアカウントを無効にするか、再び有効にするには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックします。

4.  [**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティアカウントマネージャー (SAM) アカウント名、SIP アドレス、またはもう一度有効にするユーザーアカウントの Ip Uniform リソース識別子 (URI) のすべてまたは最初の部分を入力します。[**検索**] をクリックします。

5.  表で、無効にする、またはもう一度有効にするユーザーアカウントをクリックします。

6.  [**アクション**] メニューで、次のいずれかの操作を行います。
    
      - Lync Server 2013 のユーザーアカウントを一時的に無効にするには、[ **Lync server に対して一時的に無効**にする] をクリックします。
    
      - Lync Server 2013 のユーザーアカウントを有効にするには、[ **Lync server の場合は再度有効**にする] をクリックします。

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Windows PowerShell を使用してユーザーアカウントを無効にするか、再び有効にする

ユーザーアカウントは一時的に無効にすることができます。また、**設定-CsUser**コマンドレットを使用して、後で再び有効にすることができます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>

## <a name="to-disable-a-user-account"></a>ユーザーアカウントを無効にするには

  - ユーザーアカウントを一時的に無効にするには、Enabled プロパティの値を False ($False) に設定します。 次に例を示します。
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a>ユーザーアカウントを再度有効にするには

  - 無効のユーザーアカウントを再び有効にするには、Enabled プロパティの値を True ($True) に設定します。 次に例を示します。
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

詳細については、「 [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser)コマンドレット」のヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のユーザーアカウントを追加して有効にする](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[Lync Server 2013 のユーザーを有効または無効にする](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

