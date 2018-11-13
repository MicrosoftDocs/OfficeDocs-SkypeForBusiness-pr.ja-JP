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
ms.openlocfilehash: fb04ecd53c93ae7bd64fca760b752d2d69324c3d
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295356"
---
# <a name="configure-skype-for-business-hybrid"></a>Skype をビジネスのハイブリッドを構成します。

ビジネスのハイブリッド用には、Skype を構成するにする必要があります。

- [フェデレーションを構成します。](#configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online)
- [共有セッション開始プロトコル (SIP) のアドレス スペースを構成します。](#configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space)
- [必要な場合は、サーバーからサーバーへの認証を構成します。](#configure-server-to-server-authentication-if-required)
  
## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a>ビジネス オンラインの Skype で、設置型のエッジ サービスのフェデレーションを構成します。

フェデレーションにより、組織で Office 365 のユーザーと通信する設置型展開でユーザーです。 フェデレーションを構成するには、ビジネス サーバー管理シェルの Skype で次のコマンドレットを実行します。
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

```
New-CSHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
```

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a>共有 SIP アドレス スペースのオンライン ビジネスのテナントは、Skype を構成します。

セッション開始プロトコル (SIP) アドレスは、電話番号や電子メール アドレスに似た、ネットワーク上の各ユーザーの一意の識別子です。 オンライン ビジネスのユーザーを設置から Skype に移動しようとすると、前に、社内設置型展開と共有のセッション開始プロトコル (SIP) アドレス空間を共有するのには、Office 365 のテナントを構成する必要があります。 これが構成されていないと、次のエラー メッセージが表示されることがあります。
  
移動-CsUser: HostedMigration フォールト: Error=(510)、説明 = (このユーザーのテナントが対応でない共有 sip アドレス スペースです)。
  
共有 SIP アドレス スペースを構成するには、ビジネス オンラインでは、Skype でのリモート PowerShell セッションを確立し、次のコマンドレットを実行し。
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> SharedSipAddressSpace 属性は、オンラインへの移行が終わり、オンプレミス状態のユーザーがいなくなるまで「True」のままにする必要があります。 
  
ビジネス オンラインの Skype でのリモート PowerShell セッションを確立するためにまず取得することができる Windows PowerShell のオンライン ビジネスのコネクタ モジュールの Skype をインストールするのには[ここ](https://go.microsoft.com/fwlink/p/?LinkId=391911)です。
  
そのモジュールをインストールしたら、次のコマンドレットによってリモート セッションを確立します。
  
```
Import-Module SkypeOnlineConnector
```

```
$cred = Get-Credential
```

```
$CSSession = New-CsOnlineSession -Credential $cred
```

```
Import-PSSession $CSSession -AllowClobber
```

ビジネス online では、Skype でのリモート PowerShell セッションを確立する方法と、Skype のビジネス オンライン コネクタ モジュールの使用方法に関する詳細については、 [Windows PowerShell には、コンピューターの設定](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)を参照してください。
  
## <a name="configure-server-to-server-authentication-if-required"></a>必要な場合は、サーバーからサーバーへの認証を構成します。

、ハイブリッド環境を構成しているの種類によっては、サーバーからサーバーへの認証を構成する必要があります。  詳細については、 [Skype のビジネス サーバーの管理サーバーからサーバーへの認証](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications)を参照してください。


## <a name="see-also"></a>関連項目

[新しい-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

