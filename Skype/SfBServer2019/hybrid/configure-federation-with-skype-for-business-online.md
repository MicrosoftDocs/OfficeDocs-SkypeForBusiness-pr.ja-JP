---
title: Skype をビジネスのハイブリッドを構成します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: '概要: は、オンライン ビジネスの設置型展開と Skype との間の相互運用性を構成する方法について説明します。'
ms.openlocfilehash: db03636d412caa72a3b7a38d0c1d691c83d96a5b
ms.sourcegitcommit: a54864c3fcd1b8d240d0f7f2ccf68f8cba566e47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2018
ms.locfileid: "25849349"
---
# <a name="configure-skype-for-business-hybrid"></a>Skype をビジネスのハイブリッドを構成します。

ビジネスのハイブリッド用には、Skype を構成するにする必要があります。

- [Office 365 とフェデレーションを行う、オンプレミスの環境を構成します。](#configure-your-on-premises-edge-service-to-federate-with-Office-365)
- [オンプレミス環境に Office 365 を信頼するを構成し、Office 365 との共有 SIP アドレス スペースを有効にします。](#configure-your-on-premises-environment-to-share-your-SIP-address-space-with-Office-365)
- [Office 365 テナント内の共有 SIP アドレス スペースを有効にします。](#configure-server-to-server-authentication-if-required)

> [!NOTE]
> Exchange 設置がある場合は、する可能性がある場合は、オンライン ビジネス環境の Exchange の設置型と Skype の OAuth を構成するのには。 詳細については、 [Skype のビジネス サーバーの管理サーバーからサーバーへの認証](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications)と[ビジネスとの交換用 Skype を統合する計画](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support)を参照してください。 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365"></a>Office 365 とフェデレーションを行うには、設置端サービスを構成します。

フェデレーションにより、組織で Office 365 のユーザーと通信する設置型展開でユーザーです。 フェデレーションを構成するには、ビジネス サーバー管理シェルの Skype で次のコマンドレットを実行します。
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```



## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a>Office 365 の共有 SIP アドレス スペースを有効にするのには、オンプレミス環境を構成します。

Office 365 の信頼、オンプレミス環境を構成しと Office 365 の共有 SIP アドレス スペースを有効にする必要がありますもします。 つまり、Office 365 では、オンプレミス環境では、SIP ドメインの同じセットのユーザー アカウントをホストできる可能性のある施設内でホストされているユーザー間でルーティングとオンラインをメッセージとして使用することができます。  ProxyFqdn=sipfed.online.lync.com 以下に示すように、ホスティング プロバイダーを構成することによってこれを行います。

最初に、ProxyFqdn=sipfed.online.lync.com のホスティング プロバイダーが既にあるかどうかを確認してください。 1 つ存在する場合、次のコマンドを使用して削除します。

```
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

新しいホスティング プロバイダーを作成し、新規 CsHostingProvider コマンドレットを使用して、次のようにします。 

```
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-tenant"></a>Office 365 テナント内の共有 SIP アドレス スペースを有効にします。
  
、設置型展開で行った変更に加え、社内設置型展開と共有 SIP アドレス スペースを有効にする、Office 365 テナントに対応する変更を行う必要があります。  

Office 365 テナント内の共有 SIP アドレス スペースを有効にするには、ビジネス オンラインでは、Skype でのリモート PowerShell セッションを確立し、次のコマンドレットを実行します。
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> SharedSipAddressSpace 属性は、オンラインへの移行が終わり、オンプレミス状態のユーザーがいなくなるまで「True」のままにする必要があります。 
  
ビジネス オンラインのチームと Skype、リモート PowerShell セッションを確立するためにまず取得することができる Windows PowerShell のオンライン ビジネスのコネクタ モジュールの Skype をインストールするのには[ここ](https://go.microsoft.com/fwlink/p/?LinkId=391911)です。
  
そのモジュールをインストールしたら、次のコマンドレットによってリモート セッションを確立します。
  
```
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

ビジネス online では、Skype でのリモート PowerShell セッションを確立する方法と、Skype のビジネス オンライン コネクタ モジュールの使用方法に関する詳細については、 [Windows PowerShell には、コンピューターの設定](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)を参照してください。
  


## <a name="see-also"></a>関連項目

[新しい-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

