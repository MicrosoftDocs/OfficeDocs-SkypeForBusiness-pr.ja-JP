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
ms.openlocfilehash: ccf140b62cdbad11605c99fe1cb0cc66aa1ee4dd
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780106"
---
# <a name="configure-skype-for-business-hybrid"></a>Skype for Business ハイブリッドの構成

Skype for Business ハイブリッドを構成するには、次のことを実行する必要があります。

- [Office 365 または別の組織とフェデレーションするようにオンプレミスのエッジサービスを構成](#configure-your-on-premises-edge-service-to-federate-with-office-365-or-another-organization)します。
- Office [365 を信頼するようにオンプレミス環境を構成し、office 365 で共有 SIP アドレススペースを有効](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365)にします。
- [Office 365 組織の共有 SIP アドレススペースを有効に](#enable-shared-sip-address-space-in-your-office-365-organization)します。

オンプレミスの Exchange を使用している場合は、Exchange のオンプレミスと Skype for business Online 環境の間で OAuth を構成することが必要になることに注意してください。 詳細については、「 [skype for Business server でサーバー間認証を管理](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications)する」および「 [skype For business と Exchange の統合を計画する](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support)」を参照してください。 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365-or-another-organization"></a>Office 365 または別の組織とフェデレーションするようにオンプレミスのエッジサービスを構成する

フェデレーションにより、オンプレミス展開のユーザーは、組織内の Microsoft 365 または Office 365 ユーザーと通信できます。 フェデレーションを構成するには、Skype for Business Server 管理シェルで次のコマンドレットを実行します。
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

'-EnablePartnerDiscovery ' の値が $True に設定されている場合、Skype for Business Server は DNS レコードを使用して、AllowedDomains リストに一覧表示されていないパートナードメインを検索して検出します。 この値が $False に設定されている場合、Skype for Business Server は AllowedDomains リストにあるドメインとのみフェデレーションを行います。 DNS のサービス ルーティングを使用する場合、このパラメーターは必須です。

> [!NOTE]
> オンプレミスの Skype for business 展開と Skype for Business Online 組織のユーザーとの間のフェデレーションを有効にする方法の詳細については、「skype for business [Server で skype For Business online ユーザーのフェデレーションサポートを構成](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support)する」を参照してください。


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a>Office 365 で共有 SIP アドレススペースを有効にするようにオンプレミス環境を構成する

また、Office 365 を信頼し Office 365 に対して共有 SIP アドレス スペースを有効にするように、オンプレミス環境を構成する必要があります。 つまり、Office 365 は、オンプレミス環境と同じセットの SIP ドメインに対してユーザーアカウントをホストする可能性があり、社内および online でホストされているユーザー間でメッセージをルーティングすることができます。  これを行うには、以下に示すように、ProxyFqdn = sipfed を使用してホスティングプロバイダーを構成します。

最初に、ProxyFqdn = sipfed を使用するホスティングプロバイダーが既に存在するかどうかを確認します。 存在する場合は、次のコマンドを使用して削除します。

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

次に、新しいホスティングプロバイダーを作成し、次のようにして、新しい-CsHostingProvider コマンドレットを使用します。 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-organization"></a>Office 365 組織の共有 SIP アドレススペースを有効にする
  
オンプレミス展開で行われた変更に加えて、Office 365 組織で対応する変更を行って、オンプレミス展開で共有 SIP アドレススペースを有効にする必要があります。  

Office 365 組織の共有 SIP アドレススペースを有効にするには、Skype for Business Online でリモート PowerShell セッションを確立し、次のコマンドレットを実行します。
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> SharedSipAddressSpace 属性は、オンラインへの移行が final になるまで「True」のままにしておき、ユーザーがオンプレミスのままにならないようにする必要があります。 
  
Teams または Skype for Business Online とのリモート PowerShell セッションを確立するには、まず Windows PowerShell 用 Skype for Business Online connector モジュールをインストールする必要があります。これは[こちら](https://go.microsoft.com/fwlink/p/?LinkId=391911)から入手できます。
  
モジュールをインストールした後、次のコマンドレットを使用してリモートセッションを確立できます。
  
```PowerShell
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

Skype for business Online でリモート PowerShell セッションを確立する方法と、Skype for Business Online Connector モジュールを使用する方法の詳細については、「 [Windows PowerShell 用にコンピューター](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)をセットアップする」を参照してください。
  


## <a name="see-also"></a>関連項目

[新規-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
