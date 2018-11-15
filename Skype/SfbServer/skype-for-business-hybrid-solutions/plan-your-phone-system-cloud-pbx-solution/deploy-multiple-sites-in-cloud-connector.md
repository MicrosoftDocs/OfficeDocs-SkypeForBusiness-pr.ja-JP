---
title: Cloud Connector でマルチサイトを展開する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Cloud Connector エディションで複数の PSTN サイトを展開する方法について説明します。
ms.openlocfilehash: 388915d0ab22dc50378d84a82c01291cfd7c99eb
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532370"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>Cloud Connector でマルチサイトを展開する
 
Cloud Connector エディションで複数の PSTN サイトを展開する方法について説明します。
  
このセクションでは、複数の公衆交換電話網 (PSTN) サイトを展開する方法を説明します。サイトは、単一サイトの展開と同じ手順を使用して、一度に 1 つずつ展開します。このトピックでは、マルチサイト展開の考慮事項と、マルチサイト展開でのサイト間の違いについて説明します。 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>複数の公衆交換電話網 (PSTN) サイト

PSTN の別のサイトのビジネス クラウド コネクタ ・ エディションの Skype を配置する構成の例を次に示します。 展開を開始する前に、構成設定が正しいこと確認してください。
  
PSTN サイト 1
  
```
[Common]
SiteName=Site1
[EdgeServer]
InternalMachineName= cc-edge1
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.241

ExternalSIPPoolName=access1
ExternalSIPIPs=192.168.1.4

ExternalMRFQDNPoolName=mr1
ExternalMRIPs=192.168.1.4
ExternalMRPublicIPs=23.99.115.35
```

PSTN サイト 2
  
```
[Common]
SiteName=Site2
[EdgeServer]
InternalMachineName= cc-edge2
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.242

ExternalSIPPoolName=access2
ExternalSIPIPs=192.168.1.5

ExternalMRFQDNPoolName=mr2
ExternalMRIPs=192.168.1.5
ExternalMRPublicIPs=104.42.226.134
```

サイトごとに PSTN を追加する、[クラウドのコネクタで 1 つのサイトの展開](deploy-a-single-site-in-cloud-connector.md)の手順に従います。
  
> [!IMPORTANT]
> 高可用性 (HA) を準備するための共有フォルダーは、PSTN サイト別です。 共有フォルダーは、PSTN サイトごとに異なる**必要があります**。 複数サイトに同じ共有フォルダーを使用しないで > 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>マルチサイト展開と高可用性 (HA) 対応の単一サイトの比較
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

次の表に、HA 対応の単一サイトとマルチサイト展開の違いのリストを示します。
  
|**[カテゴリ]**|**項目**|**HA 対応の単一サイト**|**マルチサイト**|
|:-----|:-----|:-----|:-----|
|構成  <br/> |アプライアンスのホスト名 <br/> |複数のアプライアンス全体にわたって**異なる** <br/> |複数の PSTN サイト全体にわたって**異なる** <br/> |
|セットアップ  <br/> |共有フォルダー  <br/> |アプライアンスの間で**同一**の共有フォルダーが必要です。 <br/> |複数のアプライアンス全体にわたって**異なる**共有フォルダーが必要 <br/> |
|構成  <br/> |VirtualMachineDomain  <br/> |複数のアプライアンス全体にわたって**同じ**ドメインが必要 <br/> |複数の PSTN サイト全体にわたって**同じ**ドメインが必要 <br/> |
|構成  <br/> |SIPDomains  <br/> |ドメイン名と注文する必要があります、**同じ**アプライアンスの間で <br/> |ドメイン名と順序は、**同じ**サイト間である PSTN <br/> |
|構成  <br/> |サイト名  <br/> |複数のアプライアンス全体にわたって**同じ**サイト名 <br/> |複数の PSTN サイト全体にわたって**異なる**サイト名 <br/> |
|構成  <br/> |サーバー名  <br/> |複数のアプライアンス全体にわたって**異なる** <br/> |複数の PSTN サイト全体にわたって**異なる** <br/> |
|構成  <br/> |内部プールの FQDN  <br/> |複数のアプライアンス全体にわたって**同じ** <br/> |複数の PSTN サイト全体にわたって**同じ** <br/> |
|構成  <br/> |内部 IP  <br/> |複数のアプライアンス全体にわたって**異なる** <br/> |複数の PSTN サイト全体にわたって**異なる** <br/> |
|構成  <br/> |外部 FQDN  <br/> |複数のアプライアンス全体にわたって**同じ** <br/> |複数の PSTN サイト全体にわたって**異なる** <br/> |
|構成  <br/> |外部 IP  <br/> |複数のアプライアンス全体にわたって**異なる** <br/> |複数の PSTN サイト全体にわたって**異なる** <br/> |
|構成  <br/> |PSTN ゲートウェイの設定  <br/> |複数のアプライアンス全体にわたって**同じ** <br/> |複数の PSTN サイト全体にわたって**異なる** <br/> |
|構成  <br/> |DNS レコード  <br/> |レコードを**同じ**外部アクセスの Fqdn と**異なる**IP アドレスを追加します。 <br/> |**異なる**外部アクセス FQDN と**異なる** IP アドレスを持つレコードを追加 <br/> |
|セットアップ  <br/> |ハイブリッド テナント  <br/> |HybridPSTNSite の設定  <br/> フォールバック用 PeerDestination の設定  <br/> |HybridPSTNSite の設定  <br/> フォールバック用 PeerDestination の設定  <br/> |
|セットアップ  <br/> |ゲートウェイ  <br/> |このサイトでの MS GW **M:N** マッピング <br/> |各 PSTN サイトの PSTN ゲートウェイは、必ず同じサイトの仲介サーバーのみに接続します  <br/> |
|セットアップ  <br/> |ユーザー  <br/> |UserPSTNSettings の設定  <br/> |UserPSTNSettings の設定  <br/> |
   

