---
title: ビジネスのサーバーに、Skype でエンタープライズ VoIP を計画します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: エンタープライズ VoIP の Skype の基本の Business Server の計画、サイト、地域、サイト間のネットワーク リンクを含むおよび音声の使用量のトラフィックを見積もるします。
ms.openlocfilehash: 7a540721cd8b8e9dc24436bc54138cfd503d4de8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924389"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a>ビジネスのサーバーに、Skype でエンタープライズ VoIP を計画します。
 
エンタープライズ VoIP の Skype の基本の Business Server の計画、サイト、地域、サイト間のネットワーク リンクを含むおよび音声の使用量のトラフィックを見積もるします。
  
エンタープライズ VoIP の展開プロセスは、既存のトポロジ、インフラストラクチャ、およびエンタープライズ VoIP 機能をサポートするかによって異なります。 必要な手順は選択する機能によって異なりますが、計画に関して高レベルで考慮が必要なその他の事項があります。
  
通常は、展開するサイトの種類と数および地理的な場所、各サイトの通話ボリューム、サイト間を接続するネットワーク リンクの種類、各サイトの音声機能に冗長性とフェールオーバーを持たせるかどうか、および既存の PBX 機器を使用するかどうかを考慮してください。 ビジネス サーバー全体に Skype を計画するときに考慮する必要がありますが、高可用性などの特定の考慮事項があります。 これらの考慮事項については、このセクションのトピックで必要に応じて説明します。
  
## <a name="sites-and-regions"></a>サイトと地域

最初に、エンタープライズ VoIP とそれらのサイトに所属しているネットワーク領域を配置するトポロジでは、サイトを特定します。 特に、それぞれのサイトにどのようにして公衆交換電話網 (PSTN) 接続を提供するかを考慮します。 管理上の理由から、これらのサイトが属する地域が決定的要素となります。 ゲートウェイをローカルに配置されますが、リカバリ性に優れたブランチ アプライアンス (Sba) を配置する場所、および構成できる SIP トランク (ローカルまたはセントラル サイトで) インターネット テレフォニー サービス プロバイダー (ITSP) を決定します。
  
## <a name="network-links-between-sites"></a>サイト間のネットワーク リンク

セントラル サイトおよびそのブランチ サイト間のネットワーク リンクの必要な帯域幅の使用を検討する必要があります。 ある、またはサイト間での弾力性のある WAN リンクの展開を計画する場合は、それらのサイトでユーザーのローカル直接の内側のダイヤル (DID) の終了を提供するには、各ブランチ サイトでゲートウェイを展開することをお勧めします。 回復可能な WAN リンクは存在するが、WAN リンクの帯域幅に制限がありそうな場合、そのリンクに通話受付管理を構成します。 弾力性のある WAN リンクを使用する必要はありません、する場合は、ブランチ サイトに 1000 未満のユーザーをホストし、ビジネス サーバーの管理者が使用可能なブランチ サイトでのリカバリ性に優れたブランチ アプライアンスを展開することをお勧めします。 ローカルのトレーニングを受けた Skype はありません。 1000、5000、ブランチ サイトのユーザーとの間のホストが、弾力性のある WAN 接続がないし、のビジネスのサーバーの管理者が使用できる場合は、Skype がトレーニングを受けた場合は、小規模ブランチ サイトでゲートウェイでの存続可能ブランチ サーバーを展開することをお勧めします。 メディア バイパスをサポートするゲートウェイ ピアが存在する場合は、制限のあるリンクでメディア バイパスを有効にすることも検討してください。
  
## <a name="estimating-voice-usage-and-traffic"></a>音声の利用状況とトラフィックの予測

Microsoft Lync Server 2013、計画ツールは、ユーザーのトラフィックでは、各サイトおよびそのトラフィックをサポートするのにために必要なポートの数を推定するのには次のメトリックを使用します。
  
> **軽度のトラフィック** (1 人あたり 1 時間に 1 PSTN 通話) の場合、1 ポートに対して 15 ユーザーを割り当てます。
> 
> **中度のトラフィック** (1 人あたり 1 時間に 2 PSTN 通話) の場合、1 ポートに対して 10 ユーザーを割り当てます。
> 
> **重度のトラフィック** (1 人あたり 1 時間に 3 以上の PSTN 通話) の場合、1 ポートに対して 5 ユーザーを割り当てます。
    
ポートの数には、仲介サーバーとゲートウェイが必要になることの順番を決定します。 960 個のポートに 2 つのポートからのサイズの範囲を展開するほとんどの組織を検討している公衆交換電話網 (PSTN) ゲートウェイです。 (がさらに大きくゲートウェイがこれらの主にテレフォニー サービス プロバイダーによって使用されます)。
  
たとえば、10,000 名のユーザーを擁する中度のトラフィックの組織の場合、1000 ポートが必要となります。必要となるゲートウェイ数は、ゲートウェイの総合した処理能力によって決まる、必要とされるポート数の合計と同じになります。
  
## <a name="components-features-and-options-of-enterprise-voice"></a>コンポーネント、機能、およびエンタープライズ VoIP のオプション

エンタープライズ VoIP 展開の計画に関する詳細については次のセクションを参照してください。
  
- [Skype でエンタープライズ VoIP のサーバーのビジネスに必要なコンポーネント](components-required-for-enterprise-voice.md)
    
- [ビジネス サーバーに、Skype で PSTN への接続を計画します。](pstn-connectivity-0.md)
    
- [Skype で高度なエンタープライズ VoIP 機能のビジネス サーバー用のネットワーク設定](network-settings-for-advanced-features.md)
    
- [ビジネス サーバーに、Skype で通話受付制御を計画します。](call-admission-control.md)
    
- [ビジネス サーバーに、Skype で緊急サービスを計画します。](emergency-services.md)
    
- [ビジネス用の Skype でメディアをバイパスするための計画します。](media-bypass.md)
    
- [ビジネス用の Skype でプライベート電話回線の計画](private-telephone-lines.md)
    
- [Skype のビジネスの場所ベースのルーティングの計画](location-based-routing.md)
    
- [ビジネス用の Skype での通話管理機能の計画](call-management-features.md)
    
- [Plan for Enterprise Voice resiliency in Skype for Business Server](enterprise-voice-resiliency.md)
    

