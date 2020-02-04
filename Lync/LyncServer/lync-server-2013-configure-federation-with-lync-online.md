---
title: 'Lync Server 2013: Lync Online とのフェデレーションを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation with Lync Online
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205126(v=OCS.15)
ms:contentKeyID: 48184946
ms.date: 08/15/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba9179f05918504df15a18b35b9c411f23919330
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a>Lync Server 2013 と Lync Online のフェデレーションを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-08-15_

このセクションの手順に従って、オンプレミス展開と Skype for Business Online の間の相互運用性を構成します。

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a>Skype for Business Online とのフェデレーション用にオンプレミスエッジサービスを構成する

フェデレーションによって、オンプレミスの展開のユーザーは、組織内の Office 365 ユーザーと通信することができます。 フェデレーションを構成するには、次のコマンドレットを実行します。

   ```powershell
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```powershell
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a>共有 SIP アドレス空間用に Skype for Business Online テナントを構成する

セッション開始プロトコル (SIP) アドレスは、電話番号や電子メール アドレスに似た、ネットワーク上の各ユーザーの一意の識別子です。 Lync ユーザーをオンプレミスから Skype for Business Online に移行する前に、オンプレミスの展開を使用して共有セッション開始プロトコル (SIP) アドレススペースを共有するように Office 365 テナントを構成する必要があります。 これが構成されていないと、次のエラー メッセージが表示されることがあります。

Move-CsUser : HostedMigration エラー: エラー=(510), 説明=(このユーザーのテナントは共有 SIP アドレス スペース用に有効化されていません。)

共有 SIP アドレス空間を構成するには、Skype for Business Online とのリモート PowerShell セッションを確立して、次のコマンドレットを実行します。
```powershell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```
Skype for Business Online とのリモート PowerShell セッションを確立するには、まず、Windows PowerShell 用 Skype for Business Online モジュールをインストールする必要があります。 [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911)これには、次のページを参照してください。

そのモジュールをインストールしたら、次のコマンドレットによってリモート セッションを確立します。

   ```powershell
    Import-Module LyncOnlineConnector
   ```

   ```powershell
    $cred = Get-Credential
   ``` 

   ```powershell
    $CSSession = New-CsOnlineSession -Credential $cred
   ```

   ```powershell
    Import-PSSession $CSSession -AllowClobber
   ```

Skype for Business Online とのリモート PowerShell セッションを確立する方法の詳細については、「 [Windows PowerShell を使用して skype For Business online に接続](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)する」を参照してください。

Skype for Business Online PowerShell モジュールの使用方法の詳細については、「 [Windows PowerShell を使用して skype For Business online を管理する](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」を参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[新規-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

