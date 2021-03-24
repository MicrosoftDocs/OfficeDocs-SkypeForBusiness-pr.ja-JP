---
title: クラウド コネクタでの複数サイトの展開
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: クラウド コネクタ エディションでの複数の PSTN サイトの展開について説明します。
ms.openlocfilehash: 059b9a39a082e876b1dd9cd772a235c384a29107
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098403"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>クラウド コネクタでの複数サイトの展開

> [!Important] 
> Cloud Connector Edition は、Skype for Business Online と共に 2021 年 7 月 31 日に廃止されます。 組織が Teams にアップグレードしたら、直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。

クラウド コネクタ エディションでの複数の PSTN サイトの展開について説明します。
  
このセクションでは、複数の公衆交換電話網 (PSTN) サイトを展開する方法について説明します。 サイトは、1 つのサイトの展開と同じ手順を使用して一度に 1 つ展開されます。 このトピックでは、複数のサイト展開におけるサイトの考慮事項と相違点について説明します。 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>複数の公衆交換電話網 (PSTN) サイト

次に、Skype for Business Cloud Connector Edition をさまざまな PSTN サイトに展開する構成例を示します。 展開を開始する前に、構成設定が正しいか確認してください。
  
PSTN サイト 1
  
```console
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
  
```console
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

追加する PSTN サイトごとに、「Cloud Connector で単一サイトを展開する」の [手順に従います](deploy-a-single-site-in-cloud-connector.md)。
  
> [!IMPORTANT]
> 高可用性 (HA) を準備するための共有フォルダーは、PSTN サイトごとに行います。 共有フォルダーは **PSTN サイト** 間で異なる必要があります。 複数の sites.> に同じ共有フォルダーを使用> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>複数サイト展開と比較した高可用性 (HA) を備えた単一サイト
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

次の表に、HA をサポートする単一サイトと複数のサイト展開の違いを示します。
  
|**カテゴリ**|**項目**|**HA を使用した単一サイト**|**マルチサイト**|
|:-----|:-----|:-----|:-----|
|構成  <br/> |アプライアンスのホスト名 <br/> |**アプライアンス間** で異なる <br/> |**PSTN サイト** 間で異なる <br/> |
|セットアップ  <br/> |共有フォルダー  <br/> |アプライアンス間 **で同じ** 共有フォルダーが必要 <br/> |アプライアンス間 **で別の** 共有フォルダーが必要 <br/> |
|構成  <br/> |VirtualMachineDomain  <br/> |アプライアンス間 **で同じ** ドメインが必要 <br/> |PSTN サイト間 **で同** じドメインが必要 <br/> |
|構成  <br/> |SIPDomains  <br/> |ドメイン名と順序は、アプライアンス間 **で同じ** である必要があります <br/> |ドメイン名と順序は PSTN サイト **間で** 同じである必要があります <br/> |
|構成  <br/> |サイト名  <br/> |**同じ** アプライアンス間のサイト名 <br/> |**異なる** PSTN サイト間のサイト名 <br/> |
|構成  <br/> |サーバー名  <br/> |**アプライアンス間** で異なる <br/> |**PSTN サイト** 間で異なる <br/> |
|構成  <br/> |内部プールの FQDN  <br/> |**アプライアンス間** で同じ <br/> |**PSTN サイト** 間で同じ <br/> |
|構成  <br/> |内部の IPs  <br/> |**アプライアンス間** で異なる <br/> |**PSTN サイト** 間で異なる <br/> |
|構成  <br/> |外部 FQDN  <br/> |**アプライアンス間** で同じ <br/> |**PSTN サイト** 間で異なる <br/> |
|構成  <br/> |外部 AP  <br/> |**アプライアンス間** で異なる <br/> |**PSTN サイト** 間で異なる <br/> |
|構成  <br/> |PSTN GW の設定  <br/> |**アプライアンス間** で同じ <br/> |**PSTN サイト** 間で異なる <br/> |
|構成  <br/> |DNS レコード  <br/> |同じ外部アクセス FQDN **と** 異なる IP アドレスを持つ **レコードを** 追加する <br/> |異なる外部 **アクセス** FQDN と異なる IP アドレスを持つ **レコードを** 追加する <br/> |
|セットアップ  <br/> |ハイブリッド テナント  <br/> |HybridPSTNSite の設定  <br/> フォールバック用に PeerDestination を設定する  <br/> |HybridPSTNSite の設定  <br/> フォールバック用に PeerDestination を設定する  <br/> |
|セットアップ  <br/> |ゲートウェイ  <br/> |このサイトの MS GW **M:N** マッピング <br/> |各 PSTN サイトの PSTN ゲートウェイは、同じサイトの仲介サーバーにのみ接続する必要があります。  <br/> |
|セットアップ  <br/> |User  <br/> |UserPSTNSettings の設定  <br/> |UserPSTNSettings の設定  <br/> |
