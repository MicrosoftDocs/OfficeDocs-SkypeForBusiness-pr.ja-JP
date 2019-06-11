---
title: Exchange ユニファイドメッセージングの連絡先オブジェクトを移動する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 946bf7221ab9f4c5a7111839bca25dabaad31d82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848037"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a>Exchange ユニファイドメッセージングの連絡先オブジェクトを移動する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-19_

自動応答 (AA) および加入者アクセス (SA) 連絡先オブジェクトを新しい Lync Server 2013 の展開に移行するには、まず、**従来の Office Communications Server 2007 R2 の展開から新しい Lync server 2013 展開にオブジェクトを移動します。CsExUmContact**と**移動-csexumcontact**コマンドレット。 Exchange サーバーで、 **Exchucutil** Windows PowerShell スクリプトを実行して、新しく展開された Lync プールに対して次の操作を行います。

  - ユニファイドメッセージング IP ゲートウェイに追加します。

  - ユニファイドメッセージングハントグループに追加します。

<div>


> [!NOTE]  
> <STRONG>Get-csexumcontact</STRONG>および<STRONG>Move-csexumcontact</STRONG>コマンドレットを使用するには、RTCUniversalUserAdmins グループのメンバーであり、連絡先オブジェクトが保存されている OU に対して組織単位 (ou) のアクセス許可を持っている必要があります。 権限付与は、 <STRONG>Grant permission</STRONG>コマンドレットを使って行うことができます。



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a>Lync Server 管理シェルを使用して連絡先オブジェクトを移動するには

1.  Lync Server 管理シェルを開きます。

2.  Exchange UM に登録されている各プール (pool1.contoso.net は、Office Communications Server 2007 R2 の展開からのプールであり、pool2.contoso.net は Lync Server 2013 の展開からのプールである) には、次のように入力します。
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    連絡先オブジェクトが移動されたことを確認する**** には、 **RegistrarPool**コマンドレットを実行し、新しいプールをポイントしていることを確認します。

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a>ExchUCUtil Windows PowerShell スクリプトを実行するには

1.  Exchange の組織管理者権限を持つユーザーとして Exchange UM サーバーにログオンします。

2.  ExchUCUtil Windows PowerShell スクリプトに移動します。
    
    Exchange 2007 では、ExchUCUtil は次の場所にあります。 **%\\Program\\Files%\\Microsoft\\Exchange Server スクリプト exchucutil**
    
    Exchange 2010 では、ExchUCUtil は次の場所にあります: **%\\Program\\Files%\\Microsoft\\Exchange\\Server V14 スクリプト exchucutil**

3.  1つのフォレストに Exchange が展開されている場合は、次のように入力します。
    
        exchucutil.ps1
    
    または、複数のフォレストに Exchange が展開されている場合は、次のように入力します。
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    ここで、[フォレスト FQDN の指定は Lync Server 2013 が展開されているフォレストを指定します。
    
    <div>
    

    > [!IMPORTANT]  
    > Exchucutil を実行し<EM>た後</EM>、必ず<STRONG>Lync Server のフロントエンド</STRONG>サービス (rtcsrv) を再起動してください。 そうしないと、Lync Server 2013 は、トポロジでユニファイドメッセージングを検出しません。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

