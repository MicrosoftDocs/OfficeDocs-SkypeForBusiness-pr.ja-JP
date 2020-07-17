---
title: Exchange ユニファイドメッセージング連絡先オブジェクトの移動
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3b3091a342b46b5c1aad1d456aa9159d951a4ba
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a>Exchange ユニファイドメッセージング連絡先オブジェクトの移動

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-19_

自動応答 (AA) およびサブスクライバーアクセス (SA) の連絡先オブジェクトを新しい Lync Server 2013 展開に移行するには、まず、従来の Office Communications Server 2007 R2 展開から新しい Lync Server 2013 展開にオブジェクトを移動するには、まず、 **Get-csexumcontact**および**Move-csexumcontact**コマンドレットを使用します。 Exchange サーバーでは、次のように、 **Exchucutil** Windows PowerShell スクリプトを実行して、新しく展開された Lync プールに対して次の操作を行います。

  - ユニファイド メッセージング IP ゲートウェイに追加します。

  - ユニファイド メッセージング ハント グループに追加します。

<div>


> [!NOTE]  
> <STRONG>Get-CsExUmContact</STRONG> および <STRONG>Move-CsExUmContact</STRONG> コマンドレットを使用するには、RTCUniversalUserAdmins グループのメンバーであり、連絡先オブジェクトを格納する組織単位 (OU) に対する OU アクセス許可を持っている必要があります。OU アクセス許可は <STRONG>Grant-OUPermission</STRONG> コマンドレットを使用して付与できます。



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a>Lync Server 管理シェルを使用して連絡先オブジェクトを移動するには

1.  Lync Server 管理シェルを開きます。

2.  コマンドラインで、Exchange UM に登録されている各プール (pool1.contoso.net は、Office Communications Server 2007 R2 展開からのプールで、pool2.contoso.net は Lync Server 2013 展開からのプールである) に対して、次のように入力します。
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    連絡先オブジェクトが移動されたことを確認するには、**Get-CsExumContact** コマンドレットを実行し、**RegistrarPool** が新しいプールを参照していることを確認します。

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a>Windows PowerShell の ExchUCUtil スクリプトを実行するには

1.  Exchange 組織管理者特権のあるユーザーとして Exchange UM Server にログオンします。

2.  ExchUCUtil Windows PowerShell スクリプトに移動します。
    
    Exchange 2007 では、ExchUCUtil.ps1 は次の場所にあります。 **% Program Files% \\ Microsoft \\ Exchange Server \\ Scripts \\ExchUCUtil.ps1**
    
    Exchange 2010 では、ExchUCUtil.ps1 は次の場所にあります。 **% Program Files% \\ Microsoft \\ Exchange Server \\ V14 \\ Scripts \\ExchUCUtil.ps1**

3.  Exchange が単一のフォレストに展開されている場合は、次のように入力します。
    
        exchucutil.ps1
    
    Exchange が複数のフォレストに展開されている場合は、次のように入力します。
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    フォレスト FQDN には、Lync Server 2013 が展開されているフォレストを指定します。
    
    <div>
    

    > [!IMPORTANT]  
    > exchucutil.ps1 を実行した<EM></EM>後で、<STRONG>Lync サーバー フロントエンド</STRONG> サービス (rtcsrv.exe) を再起動してください。 それ以外の場合、Lync Server 2013 は、トポロジ内のユニファイドメッセージングを検出しません。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

