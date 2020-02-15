---
title: 'Lync Server 2013: Lync Online から Lync オンプレミスへのユーザーの移行を開始する前の最初の手順'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: First steps before you start migrating users from Lync Online to Lync on-premises
ms:assetid: 98245b04-ded4-4186-8da3-ba1c554b5c39
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689118(v=OCS.15)
ms:contentKeyID: 62258123
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bf61b4e2f3e3a14d5e2434ff80bd5d6f612f267
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="first-steps-before-you-start-migrating-users-from-lync-online-to-lync-on-premises-in-lync-server-2013"></a>Lync Online から lync Server 2013 の Lync オンプレミスへのユーザーの移行を開始する前の最初の手順

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-05-08_

Lync Online ユーザーのオンプレミス環境への移行を開始する前に、以下の条件がすべて満たされていることを確認してください。

  - Lync Server のオンプレミス環境を完全に展開し、検証する必要があります。 詳細については、「 [Lync Server 2013 の展開](lync-server-2013-deploying-lync-server.md)」を参照してください。

  - Lync Online テナントは、リモート PowerShell へのアクセス用に構成する必要があります。
    
    これを行うには、まず、Windows PowerShell 用 Lync Online モジュールをインストールします。これ[http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911)は、次の場所から入手できます。
    
    モジュールをインストールした後、Lync Server 管理シェルで次のコマンドレットを入力することによって、リモートセッションを確立できます。
    
       ```PowerShell
        Import-Module LyncOnlineConnector
       ```  
    
       ```PowerShell
        $cred = Get-Credential
       ``` 
    
       ```PowerShell
        $CSSession = New-CsOnlineSession -Credential $cred
       ```
    
       ```PowerShell
        Import-PSSession $CSSession -AllowClobber
       ```
    
    Lync Online とのリモート PowerShell セッションを確立する方法の詳細については、「 [Windows PowerShell を使用した Lync Online への接続](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」を参照してください。
  
    Lync Online PowerShell モジュールの使用方法の詳細については、「 [Using Windows powershell to Manage Lync online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」を参照してください。

  - 共有 SIP アドレススペースを使用するように Lync Online を構成する必要があります。 これを行うには、まず、Lync Online を使用してリモート Powershell セッションを開始します。 その後、次のコマンドレットを実行します。
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

これらの手順を完了したら、lync [Online ユーザーを Lync Server 2013 の lync オンプレミスに移行](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md)することができます。

</div>

<span> </span>

</div>

</div>

</div>

