---
title: Skype for Business ハイブリッドの構成
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: '概要: オンプレミス展開と Skype for Business Online の間の相互運用性を構成する方法について説明します。'
ms.openlocfilehash: a97072c9c4b65b4cc13d29a733b8ddc840529363
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569219"
---
# <a name="configure-skype-for-business-hybrid"></a>Skype for Business ハイブリッドの構成

Skype for Business ハイブリッドを構成するには、次のことを実行する必要があります。

- [Microsoft 365 または Office 365](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365)とフェデレーションするために、オンプレミスエッジ サービスを構成します。
- [Microsoft 365 または Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365)を信頼し、共有 SIP アドレス空間を有効にOfficeオンプレミス環境を構成します。
- [Microsoft 365 または 365](#enable-shared-sip-address-space-in-your-organization)組織で共有 SIP Officeを有効にします。

Exchange がオンプレミスの場合は、Exchange オンプレミス環境と Skype for Business Online 環境の間で OAuth を構成できます。 詳細については  [、「Manage server-to-server authentication in Skype for Business Server」および「Plan to](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) [integrate Skype for Business and Exchange」を参照してください](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support)。 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365"></a>Microsoft 365 または Office 365 とのフェデレーションを行うオンプレミスエッジ サービスを構成する

フェデレーションを使用すると、オンプレミス展開のユーザーは、組織内の Microsoft 365 Office 365 ユーザーと通信できます。 フェデレーションを構成するには、Skype for Business Server 管理シェルで次のコマンドレットを実行します。
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

'-EnablePartnerDiscovery' の値が $True に設定されている場合、Skype for Business Server は DNS レコードを使用して、AllowedDomains リストに記載されていないパートナー ドメインを試して検出します。 値が [ドメイン] に$False場合、Skype for Business Server は AllowedDomains リストにあるドメインとのみフェデレーションします。 DNS のサービス ルーティングを使用する場合、このパラメーターは必須です。

> [!NOTE]
> オンプレミスの Skype for Business 展開のユーザーと Skype for Business Online 組織のユーザー間のフェデレーションを有効にする方法の詳細については、「Skype for Business Server での [Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support)顧客のフェデレーション サポートの構成」を参照してください。


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365"></a>Microsoft 365 または Microsoft 365 または 365 で共有 SIP アドレス空間を有効にOfficeする

また、Microsoft 365 または 365 を信頼し、共有 SIP アドレス空間を有効Officeオンプレミス環境を構成する必要があります。 つまり、Microsoft 365 または Office 365 は、オンプレミス環境と同じ一連の SIP ドメインのユーザー アカウントをホストする可能性があります。また、メッセージはオンプレミスとオンラインでホストされているユーザー間でルーティングできます。  これを行うには、以下で説明するように ProxyFqdn=sipfed.online.lync.com を使用してホスティング プロバイダーを構成します。

まず、ProxyFqdn=sipfed.online.lync.com のホスティング プロバイダーが既にあるか確認します。 存在する場合は、次のコマンドを使用して削除します。

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

次に、新しいホスティング プロバイダーを作成し、次のように New-CsHostingProviderコマンドレットを使用します。 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a>組織内の共有 SIP アドレス空間を有効にする
  
オンプレミス展開で行った変更に加えて、Microsoft 365 または Office 365 組織で対応する変更を行い、オンプレミス展開で共有 SIP アドレス空間を有効にする必要があります。  

組織内の共有 SIP アドレス空間を有効にするには、Skype for Business Online でリモート PowerShell セッションを確立し、次のコマンドレットを実行します。
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> SharedSipAddressSpace 属性は、オンラインに移行するまで "True" に維持する必要があります。ユーザーはオンプレミスのままではありません。 
  
Teams または Skype for Business Online とのリモート PowerShell セッションを確立するには、まず [Teams PowerShell モジュールをインストールする必要があります](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。
  
モジュールをインストールした後、次のコマンドレットを使用してリモート セッションを確立できます。
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

Skype for Business Online でリモート PowerShell セッションを確立する方法、および Skype for Business Online Connector モジュールを使用する方法の詳細については、「Set up your computer for Windows PowerShell」を参照 [してください](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。
  


## <a name="see-also"></a>関連項目

[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
