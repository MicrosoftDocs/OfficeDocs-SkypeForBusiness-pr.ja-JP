---
title: エンタープライズ VoIPのSkype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: エンタープライズ VoIP、地域Skype for Business Serverサイト間のネットワーク リンク、音声使用量トラフィックの見積もりなど、さまざまな方法で基本を計画します。
ms.openlocfilehash: 60b762d2e9ef49d912dc00407d7b12d44ec334c0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60762145"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a>エンタープライズ VoIPのSkype for Business Server
 
エンタープライズ VoIP、地域Skype for Business Serverサイト間のネットワーク リンク、音声使用量トラフィックの見積もりなど、さまざまな方法で基本を計画します。
  
アプリケーションの展開プロセスエンタープライズ VoIP、既存のトポロジ、インフラストラクチャ、およびサポートエンタープライズ VoIP機能によって異なります。 必要な手順は選択する機能によって異なりますが、計画に関して高レベルで考慮が必要なその他の事項があります。
  
通常は、展開するサイトの種類と数および地理的な場所、各サイトの通話ボリューム、サイト間を接続するネットワーク リンクの種類、各サイトの音声機能に冗長性とフェールオーバーを持たせるかどうか、および既存の PBX 機器を使用するかどうかを考慮してください。 高可用性など、一部の考慮事項は、全体として計画する際に検討Skype for Business Serverがあります。 これらの考慮事項については、このセクションのトピックで必要に応じて説明します。
  
## <a name="sites-and-regions"></a>サイトと地域

最初に、トポロジ内で展開するサイトと、エンタープライズ VoIPが属するネットワーク領域を特定します。 特に、それぞれのサイトにどのようにして公衆交換電話網 (PSTN) 接続を提供するかを考慮します。 管理上の理由から、これらのサイトが属する地域が決定的要素となります。 ゲートウェイをローカルに展開する場所、存続可能ブランチ アプライアンス (SA) が展開される場所、および SIP トランク (ローカルまたは中央サイト) をインターネット テレフォニー サービス プロバイダー (ITSP) に構成できる場所を決定します。
  
## <a name="network-links-between-sites"></a>サイト間のネットワーク リンク

また、中央サイトとそのブランチ サイト間のネットワーク リンクで予想される帯域幅の使用状況も考慮する必要があります。 サイト間に回復力のある WAN リンクを展開する場合、または展開する予定がある場合は、各ブランチ サイトにゲートウェイを展開して、それらのサイトのユーザーにローカル直接ダイヤル (DID) の終了を提供することをお勧めします。 回復可能な WAN リンクは存在するが、WAN リンクの帯域幅に制限がありそうな場合、そのリンクに通話受付管理を構成します。 回復力のある WAN リンクを持たなく、ブランチ サイトでホストするユーザー数が 1000 人未満で、ローカルのトレーニングを受けた Skype for Business Server 管理者が利用できない場合は、ブランチ サイトに存続可能ブランチ アプライアンスを展開することをお勧めします。 ブランチ サイトで 1000 ~ 5000 人のユーザーをホストし、回復力のある WAN 接続が不足し、使用可能な Skype for Business Server 管理者をトレーニングしている場合は、ブランチ サイトに小さなゲートウェイを持つ存続可能ブランチ サーバーを展開することをお勧めします。 メディア バイパスをサポートするゲートウェイ ピアが存在する場合は、制限のあるリンクでメディア バイパスを有効にすることも考慮してください。
  
## <a name="estimating-voice-usage-and-traffic"></a>音声の使用状況とトラフィックの見積もり

Microsoft Lync Server 2013 計画ツールは、次の指標を使用して、各サイトのユーザー トラフィックと、そのトラフィックをサポートするために必要なポートの数を推定します。
  
> **軽度のトラフィック** (1 人あたり 1 時間に 1 PSTN 通話) の場合、1 ポートに対して 15 ユーザーを割り当てます。
> 
> **中度のトラフィック** (1 人あたり 1 時間に 2 PSTN 通話) の場合、1 ポートに対して 10 ユーザーを割り当てます。
> 
> **重度のトラフィック** (1 人あたり 1 時間に 3 以上の PSTN 通話) の場合、1 ポートに対して 5 ユーザーを割り当てます。
    
ポートの数によって、必要な仲介サーバーとゲートウェイの数が決定されます。 ほとんどの組織が 2 ポートから最大 960 ポートの範囲を展開すると考える公衆交換電話網 (PSTN) ゲートウェイ。 (さらに大きなゲートウェイがありますが、これらは主にテレフォニー サービス プロバイダーによって使用されます)。
  
たとえば、10,000 名のユーザーを擁する、中度のトラフィックの組織の場合、1000 ポートが必要となります。 必要となるゲートウェイ数は、ゲートウェイの総合した処理能力によって決まる、必要とされるポート数の合計と同じになります。
  
## <a name="components-features-and-options-of-enterprise-voice"></a>アプリケーションのコンポーネント、機能、およびエンタープライズ VoIP

展開の計画の詳細については、以下のセクションエンタープライズ VoIPしてください。
  
- [エンタープライズ VoIPのSkype for Business Server](components-required-for-enterprise-voice.md)
    
- [PSTN 接続の計画を立Skype for Business Server](pstn-connectivity-0.md)
    
- [ネットワーク内の高度なエンタープライズ VoIP機能のネットワークSkype for Business Server](network-settings-for-advanced-features.md)
    
- [通話受付管理の計画を立Skype for Business Server](call-admission-control.md)
    
- [緊急サービスの計画を立Skype for Business Server](emergency-services.md)
    
- [ネットワークでメディア バイパスを計画Skype for Business](media-bypass.md)
    
- [電話回線を使用してプライベート電話回線を計画Skype for Business](private-telephone-lines.md)
    
- [[Location-Basedルーティングの計画Skype for Business](location-based-routing.md)
    
- [通話管理機能の計画を立Skype for Business](call-management-features.md)
    
- [システムの復元エンタープライズ VoIP計画Skype for Business Server](enterprise-voice-resiliency.md)
    

