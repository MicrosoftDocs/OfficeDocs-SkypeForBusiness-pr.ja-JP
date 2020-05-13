---
title: 'Lync Server 2013: Lync Online とのフェデレーションの構成'
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
ms.openlocfilehash: 2ce178e57b850ee4003f2596ee075d68ea14e00a
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a>Lync Online で Lync Server 2013 のフェデレーションを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-08-15_

このセクションの手順に従って、オンプレミス展開と Skype for Business Online の間の相互運用性を構成します。

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a>Skype for Business Online とのフェデレーション用にオンプレミスエッジサービスを構成する

フェデレーションにより、オンプレミス展開のユーザーは、組織内の Microsoft 365 または Office 365 ユーザーと通信できます。 フェデレーションを構成するには、次のコマンドレットを実行します。

   ```powershell
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```powershell
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a>共有 SIP アドレススペース用に Skype for Business Online テナントを構成する

セッション開始プロトコル (SIP) アドレスは、電話番号や電子メールアドレスと同様に、ネットワーク上の各ユーザーの一意の識別子です。 オンプレミスから Skype for Business Online に Lync ユーザーを移動する前に、Microsoft 365 または Office 365 組織を構成して、共有セッション開始プロトコル (SIP) アドレススペースを社内展開と共有する必要があります。 この設定が構成されていない場合は、次のエラーメッセージが表示されることがあります。

Move-CsUser: HostedMigration fault: Error = (510), Description = (このユーザーのテナントは、共有 sip アドレススペースに対して有効になっていません。)

共有 SIP アドレススペースを構成するには、Skype for Business Online でリモート PowerShell セッションを確立し、次のコマンドレットを実行します。
```powershell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```
Skype for Business Online とのリモート PowerShell セッションを確立するには、まず、Windows PowerShell 用の Skype for Business Online モジュールをインストールする必要があります。これには、次の情報を入手でき [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911) ます。

モジュールをインストールした後、次のコマンドレットを使用してリモートセッションを確立できます。

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

Skype for business Online とのリモート PowerShell セッションを確立する方法の詳細については、「 [Windows PowerShell を使用した skype For Business online への接続](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」を参照してください。

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
