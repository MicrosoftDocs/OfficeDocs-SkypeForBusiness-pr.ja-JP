---
title: Skype for Business Server でのエンタープライズ Voip の計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: Skype for Business Server でのエンタープライズ Voip の計画の基本 (サイト、地域、サイト間のネットワークリンクなど) と、音声の使用状況のトラフィックの見積もり。
ms.openlocfilehash: 7ef2a37a1ab39dd9c2e40544e06cfb995e846f7a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802897"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a>Skype for Business Server でのエンタープライズ Voip の計画
 
Skype for Business Server でのエンタープライズ Voip の計画の基本 (サイト、地域、サイト間のネットワークリンクなど) と、音声の使用状況のトラフィックの見積もり。
  
エンタープライズボイスの展開プロセスは、既存のトポロジ、インフラストラクチャ、およびサポートするエンタープライズ Voip 機能によって異なります。 必要な手順は選択する機能によって異なりますが、計画に関して高レベルで考慮が必要なその他の事項があります。
  
通常は、展開するサイトの種類と数および地理的な場所、各サイトの通話ボリューム、サイト間を接続するネットワーク リンクの種類、各サイトの音声機能に冗長性とフェールオーバーを持たせるかどうか、および既存の PBX 機器を使用するかどうかを考慮してください。 Skype for Business Server を全体として計画する際に考慮する必要がある、高可用性などの特定の考慮事項があります。 これらの考慮事項については、このセクションのトピックで必要に応じて説明します。
  
## <a name="sites-and-regions"></a>サイトと地域

まず、エンタープライズボイスとそのサイトが属するネットワーク領域を展開するトポロジ内のサイトを特定します。 特に、それぞれのサイトにどのようにして公衆交換電話網 (PSTN) 接続を提供するかを考慮します。 管理上の理由から、これらのサイトが属する地域が決定的要素となります。 ゲートウェイがローカルで展開される場所を決定します。ここでは、Survivable Branch アプライアンス (SBAs) を展開し、SIP trunks (ローカルまたはセントラルサイト) をインターネットテレフォニーサービスプロバイダー (ITSP) に構成することができます。
  
## <a name="network-links-between-sites"></a>サイト間のネットワーク リンク

また、セントラルサイトとそのブランチサイト間のネットワークリンクで想定される帯域幅の使用状況についても考慮する必要があります。 サイト間の WAN リンクがある場合、または展開を計画している場合は、各ブランチサイトにゲートウェイを展開して、それらのサイトのユーザーに対してローカル直接の内部ダイヤル (DID) の終了を提供することをお勧めします。 回復可能な WAN リンクは存在するが、WAN リンクの帯域幅に制限がありそうな場合、そのリンクに通話受付管理を構成します。 回復可能な WAN リンクを持っておらず、ブランチサイトで1000ユーザー未満のホストを使用していて、ローカルでトレーニングした Skype for Business Server 管理者がいない場合は、ブランチサイトで Survivable Branch Appliance を展開することをお勧めします。 ブランチサイトで1000と5000のユーザーをホストしていて、回復可能な WAN 接続がなく、Skype for Business Server のトレーニングを利用できるようになっている場合は、Survivable ブランチサーバーを小規模ゲートウェイと共にブランチサイトに展開することをお勧めします。 メディア バイパスをサポートするゲートウェイ ピアが存在する場合は、制限のあるリンクでメディア バイパスを有効にすることも検討してください。
  
## <a name="estimating-voice-usage-and-traffic"></a>音声の利用状況とトラフィックの予測

Microsoft Lync Server 2013 の計画ツールでは、次のメトリックを使用して、各サイトのユーザートラフィックを見積もり、そのトラフィックをサポートするために必要なポート数を見積もります。
  
> **軽度のトラフィック** (1 人あたり 1 時間に 1 PSTN 通話) の場合、1 ポートに対して 15 ユーザーを割り当てます。
> 
> **中度のトラフィック** (1 人あたり 1 時間に 2 PSTN 通話) の場合、1 ポートに対して 10 ユーザーを割り当てます。
> 
> **重度のトラフィック** (1 人あたり 1 時間に 3 以上の PSTN 通話) の場合、1 ポートに対して 5 ユーザーを割り当てます。
    
ポートの数によって、必要な仲介サーバーとゲートウェイの数が決まります。 ほとんどの組織が、2つのポートから最大960ポートへの展開を検討している公衆交換電話網 (PSTN) ゲートウェイ。 (大規模なゲートウェイもありますが、主にテレフォニーサービスプロバイダーによって使用されます)。
  
たとえば、10,000 名のユーザーを擁する中度のトラフィックの組織の場合、1000 ポートが必要となります。必要となるゲートウェイ数は、ゲートウェイの総合した処理能力によって決まる、必要とされるポート数の合計と同じになります。
  
## <a name="components-features-and-options-of-enterprise-voice"></a>エンタープライズ Voip のコンポーネント、機能、およびオプション

エンタープライズ Voip 展開の計画の詳細については、次のセクションを参照してください。
  
- [Skype for Business Server でのエンタープライズ Voip に必要なコンポーネント](components-required-for-enterprise-voice.md)
    
- [Skype for Business Server での PSTN 接続を計画する](pstn-connectivity-0.md)
    
- [Skype for Business Server の高度なエンタープライズ Voip 機能のネットワーク設定](network-settings-for-advanced-features.md)
    
- [Skype for Business Server での通話受付制御の計画](call-admission-control.md)
    
- [Skype for Business Server の緊急サービスの計画](emergency-services.md)
    
- [Skype for Business でのメディアのバイパスの計画](media-bypass.md)
    
- [Skype for Business でのプライベート電話回線の計画](private-telephone-lines.md)
    
- [Skype for Business で位置情報に基づくルーティングを計画する](location-based-routing.md)
    
- [Skype for Business の通話管理機能の計画](call-management-features.md)
    
- [Plan for Enterprise Voice resiliency in Skype for Business Server](enterprise-voice-resiliency.md)
    

