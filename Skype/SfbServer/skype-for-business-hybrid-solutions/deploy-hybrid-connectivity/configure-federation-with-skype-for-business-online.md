---
title: Skype for Business Online とのフェデレーションを構成する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/12/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
description: '概要: は、オンライン ビジネスの設置型展開と Skype との間の相互運用性を構成する方法について説明します。'
ms.openlocfilehash: 1a08fdb9ad9522e50bc412adcc9214fff3bbb924
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-federation-with-skype-for-business-online"></a>Skype for Business Online とのフェデレーションを構成する
 
**の概要:**オンライン ビジネスの設置型展開と Skype との間の相互運用性を構成する方法について説明します。
  
ビジネス オンラインの設置型展開と Skype との間の相互運用性を構成するには、このセクションの手順を実行します。
  
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
  
ビジネス オンラインの Skype でのリモート PowerShell セッションを確立するためにまずここに到達することができる Windows PowerShell のオンライン ビジネスのコネクタ モジュールの Skype をインストールするのには: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911)。
  
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

ビジネス オンラインの Skype でのリモート PowerShell セッションを確立する方法の詳細については、 [Lync オンラインで使用する Windows PowerShell への接続](http://technet.microsoft.com/library/6167dad9-9628-4fdb-bed1-bdb3f7108e64.aspx)を参照してください。
  
Skype を使用して、オンライン ビジネスのコネクタの PowerShell モジュールの詳細については、 [Lync Online の管理に Windows PowerShell を使用する](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx)を参照してください。
  
## <a name="see-also"></a>関連項目

#### 

[新しい-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

