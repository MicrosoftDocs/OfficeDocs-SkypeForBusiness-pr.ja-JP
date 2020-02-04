---
title: 'Lync Server 2013: Lync Online からオンプレミスの Lync へのユーザーの移行を開始する前の最初の手順'
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
ms.openlocfilehash: 59ca20a994934a199504a4fb6a7dd5eec206c960
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742497"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="first-steps-before-you-start-migrating-users-from-lync-online-to-lync-on-premises-in-lync-server-2013"></a>Lync Online から内部設置型 lync へのユーザーの移行を開始する前の最初の手順2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-05-08_

Lync Online ユーザーをオンプレミス環境に移行する前に、次のすべての条件が満たされていることを確認します。

  - Lync Server のオンプレミス環境を完全に展開して検証する必要があります。 詳細については、「 [Lync Server 2013 の展開](lync-server-2013-deploying-lync-server.md)」を参照してください。

  - Lync Online テナントがリモート PowerShell アクセス用に構成されている必要があります。
    
    これを行うには、まず、Windows PowerShell 用の Lync Online モジュールをインストールします。 [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911)これは次の場所で入手できます。
    
    モジュールをインストールした後、Lync Server 管理シェルで次のコマンドレットを入力して、リモートセッションを確立できます。
    
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
    
    Lync Online とのリモート PowerShell セッションを確立する方法の詳細については、「 [Windows PowerShell を使用した Lync online への接続](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」を参照してください。
  
    Lync Online PowerShell モジュールの使用方法の詳細については、「 [Windows PowerShell を使用して Lync online を管理する](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」を参照してください。

  - Lync Online は共有 SIP アドレススペース用に構成されている必要があります。 これを行うには、まず、Lync Online とのリモート Powershell セッションを開始します。 続いて、次のコマンドレットを実行します。
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

これらの手順を完了したら、lync [Online ユーザーをオンプレミスの Lync Server 2013 で移行](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md)できます。

</div>

<span> </span>

</div>

</div>

</div>

