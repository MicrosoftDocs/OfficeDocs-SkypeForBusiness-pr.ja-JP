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
description: '概要: オンプレミスの展開と組織間の相互運用性を構成する方法について説明Teams。'
ms.openlocfilehash: 2c6fda43b939a616071009be2b8d28e636036101
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305971"
---
# <a name="configure-skype-for-business-hybrid"></a>Skype for Business ハイブリッドの構成

Skype for Business ハイブリッドを構成するには、次のことを実行する必要があります。

- [オンプレミスのエッジ サービスを構成して、サーバーとフェデレーション](#configure-your-on-premises-edge-service-to-federate-with-teams)Teams。
- [共有 SIP アドレス空間を信頼して有効にTeamsオンプレミス環境を構成します](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams)。
- [組織で共有 SIP アドレス空間をTeamsします](#enable-shared-sip-address-space-in-your-organization)。

オンプレミス環境Exchange場合は、オンプレミス環境とオンライン環境の間Exchange OAuth を構成Skype for Business場合があります。 詳細については、「Manage [server-to-server authentication](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) in Skype for Business Server」および「Plan to integrate Skype for Business and Exchange」 を[参照してください](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)。 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-teams"></a>オンプレミスのエッジ サービスを構成して、サーバーとフェデレーションTeams

フェデレーションを使用すると、オンプレミス展開のユーザーは、組織内Teamsオンライン Skype for Businessと通信できます。 フェデレーションを構成するには、管理シェルで次のコマンドレットSkype for Business Server実行します。
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

'-EnablePartnerDiscovery' の値が $True に設定されている場合、Skype for Business Server は DNS レコードを使用して、AllowedDomains リストに記載されていないパートナー ドメインを試して検出します。 値を [許可] に設定$False、Skype for Business Server AllowedDomains リストにあるドメインとのみフェデレーションします。 DNS のサービス ルーティングを使用する場合、このパラメーターは必須です。

> [!NOTE]
> オンプレミス Skype for Business 展開のユーザーと Microsoft 365 組織のユーザーとのフェデレーションを有効にする方法の詳細については、「Skype for Business Server での Microsoft 365 顧客のフェデレーション サポートの構成」[を参照してください](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md)。


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams"></a>オンプレミス環境を構成して、共有 SIP アドレス空間を有効にTeams

また、共有 SIP アドレス空間を信頼して有効にTeamsオンプレミス環境を構成する必要があります。 この構成は、Teamsオンプレミス環境と同じ一連の SIP ドメインのユーザー アカウントをホストする可能性があるという意味で、オンプレミスとオンラインでホストされているユーザー間でメッセージをルーティングできます。 以下で説明するように、ProxyFqdn=sipfed.online.lync.com を使用してホスティング プロバイダーを構成します。

まず、ProxyFqdn=sipfed.online.lync.com のホスティング プロバイダーが既にあるか確認します。 存在する場合は、管理シェルの次のコマンドを使用してSkype for Business Serverします。

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

次に、次のように New-CsHostingProviderコマンドレットを使用して、新しいホスティング プロバイダーを作成します。 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a>組織内の共有 SIP アドレス空間を有効にする
  
オンプレミス展開で行った変更に加えて、Teams 組織で対応する変更を行い、オンプレミス展開で共有 SIP アドレス空間を有効にする必要があります。  

組織内の共有 SIP アドレス空間を有効にするには、リモート PowerShell セッションを Teamsし、次のコマンドレットを実行します。
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> SharedSipAddressSpace 属性は、オンラインに移行するまで "True" に維持する必要があります。ユーザーはオンプレミスのままではありません。 
  
リモート PowerShell セッションを Teams (Skype for Business Online) で確立するには、まず PowerShell モジュールをインストールTeams[必要があります](/microsoftteams/teams-powershell-install)。 PowerShell Teamsモジュールは、廃止Skypeされた Busines Online Connector モジュールのモジュールを置き換えるものです。
  
モジュールをインストールした後、次のコマンドレットを使用してリモート セッションを確立できます。
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

Teams を使用してリモート PowerShell セッションを確立する方法、および Teams PowerShell モジュールを使用する方法の詳細については、「Windows PowerShell 用にコンピューターをセットアップする」[を参照してください](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。
  


## <a name="see-also"></a>関連項目

[New-CsHostingProvider](/powershell/module/skype/new-cshostingprovider?view=skype-ps)
