---
title: Cloud Connector での複数サイトの展開
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
description: Cloud Connector エディションに複数の PSTN サイトを展開する方法について説明します。
ms.openlocfilehash: 3c777c54690b1eb31671f71cff915f1bb4854a0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358923"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>Cloud Connector での複数サイトの展開

> [!Important] 
> Cloud Connector エディションは、2021年7月31日、Skype for Business Online と共に廃止されます。 組織が Teams にアップグレードされたら、 [直接ルーティング](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)を使用してオンプレミスのテレフォニーネットワークを teams に接続する方法について説明します。

Cloud Connector エディションに複数の PSTN サイトを展開する方法について説明します。
  
このセクションでは、複数の公衆交換電話網 (PSTN) サイトを展開する方法について説明します。 サイトは、1つのサイトの展開と同じ手順を使用して、一度に1つずつ展開されます。 このトピックでは、複数のサイト展開におけるサイト間の考慮事項と相違点について説明します。 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>複数の公衆交換電話網 (PSTN) サイト

以下は、異なる PSTN サイトに Skype for Business Cloud Connector エディションを展開するための構成例を示しています。 展開を開始する前に、構成設定が正しいことを確認してください。
  
PSTN サイト1
  
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

PSTN サイト2
  
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

追加する PSTN サイトごとに、「 [Deploy a single site In Cloud Connector](deploy-a-single-site-in-cloud-connector.md)」の手順を実行します。
  
> [!IMPORTANT]
> 高可用性 (HA) を準備するための共有フォルダーは、PSTN サイトごとです。 共有フォルダーは、PSTN サイト間で異なる **必要があり** ます。 複数のサイトに同じ共有フォルダーを使用しないでください。 > 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>マルチサイト展開と比較した高可用性 (HA) を備えた単一サイト
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

次の表に、HA サポートを備えた単一サイトと複数サイト展開の相違点を示します。
  
|**カテゴリ**|**項目**|**HA を備えた単一サイト**|**複数サイト**|
|:-----|:-----|:-----|:-----|
|構成  <br/> |アプライアンスのホスト名 <br/> |アプライアンス間での**違い** <br/> |PSTN サイト間で**異なる** <br/> |
|セットアップ  <br/> |共有フォルダー  <br/> |複数のアプライアンス間で **同じ** 共有フォルダーが必要 <br/> |**複数のアプライアンス**間で共有フォルダーが必要 <br/> |
|構成  <br/> |VirtualMachineDomain  <br/> |複数のアプライアンス間で **同じ** ドメインが必要 <br/> |PSTN サイト間で **同じ** ドメインが必要 <br/> |
|構成  <br/> |SIPDomains  <br/> |ドメイン名と順序は、アプライアンス間で **同じ** である必要があります。 <br/> |ドメイン名と順序は、PSTN サイト全体で **同じ** である必要があります。 <br/> |
|構成  <br/> |サイト名  <br/> |**同じ** 複数のアプライアンスにまたがるサイト名 <br/> |**異なる** PSTN サイト全体のサイト名 <br/> |
|構成  <br/> |サーバー名  <br/> |アプライアンス間での**違い** <br/> |PSTN サイト間で**異なる** <br/> |
|構成  <br/> |内部プールの Fqdn  <br/> |アプライアンス間で**同じ** <br/> |PSTN サイト間で**同じ** <br/> |
|構成  <br/> |内部 Ip  <br/> |アプライアンス間での**違い** <br/> |PSTN サイト間で**異なる** <br/> |
|構成  <br/> |外部 FQDN  <br/> |アプライアンス間で**同じ** <br/> |PSTN サイト間で**異なる** <br/> |
|構成  <br/> |外部 Ip  <br/> |アプライアンス間での**違い** <br/> |PSTN サイト間で**異なる** <br/> |
|構成  <br/> |PSTN GW 設定  <br/> |アプライアンス間で**同じ** <br/> |PSTN サイト間で**異なる** <br/> |
|構成  <br/> |DNS レコード  <br/> |**同じ**外部アクセス fqdn と**異なる**IP アドレスを持つレコードを追加する <br/> |**異なる**外部アクセス fqdn と**異なる**IP アドレスを持つレコードを追加する <br/> |
|セットアップ  <br/> |ハイブリッドテナント  <br/> |HybridPSTNSite の設定  <br/> フォールバックのための PeerDestination の設定  <br/> |HybridPSTNSite の設定  <br/> フォールバックのための PeerDestination の設定  <br/> |
|セットアップ  <br/> |ゲートウェイ  <br/> |このサイトの MS GW **M:N** マッピング <br/> |各 PSTN サイトの PSTN ゲートウェイは、同じサイトの仲介サーバーにのみ接続する必要があります。  <br/> |
|セットアップ  <br/> |ユーザー  <br/> |UserPSTNSettings の設定  <br/> |UserPSTNSettings の設定  <br/> |
   

