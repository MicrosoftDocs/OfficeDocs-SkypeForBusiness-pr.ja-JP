---
title: Skype for Business Server エンタープライズ VoIPの計画
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: エンタープライズ VoIP、地域、サイト間のネットワーク リンクを含む Skype for Business Server の基本計画、および音声使用状況トラフィックの見積もりについて説明します。
ms.openlocfilehash: 8f10eed8dfcfa7a8878b673ab76fd4d1fd40cc29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825677"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a>Skype for Business Server エンタープライズ VoIPの計画
 
エンタープライズ VoIP、地域、サイト間のネットワーク リンクを含む Skype for Business Server の基本計画、および音声使用状況トラフィックの見積もりについて説明します。
  
展開プロセスはエンタープライズ VoIP、既存のトポロジ、インフラストラクチャ、およびサポートするエンタープライズ VoIP機能によって異なります。 必要な手順は選択する機能によって異なりますが、計画に関して高レベルで考慮が必要なその他の事項があります。
  
通常は、展開するサイトの種類と数および地理的な場所、各サイトの通話ボリューム、サイト間を接続するネットワーク リンクの種類、各サイトの音声機能に冗長性とフェールオーバーを持たせるかどうか、および既存の PBX 機器を使用するかどうかを考慮してください。 Skype for Business Server 全体を計画する際には、高可用性など、特定の考慮事項を考慮する必要があります。 これらの考慮事項については、このセクションのトピックで必要に応じて説明します。
  
## <a name="sites-and-regions"></a>サイトと地域

最初に、展開するトポロジ内のサイトとエンタープライズ VoIPサイトが属するネットワーク地域を特定します。 特に、それぞれのサイトにどのようにして公衆交換電話網 (PSTN) 接続を提供するかを考慮します。 管理上の理由から、これらのサイトが属する地域が決定的要素となります。 ゲートウェイをローカルに展開する場所、存続可能ブランチ アプライアンス (SA) を展開する場所、および SIP トランク (ローカルまたは中央サイト) をインターネット テレフォニー サービス プロバイダー (ITSP) に構成できる場所を決定します。
  
## <a name="network-links-between-sites"></a>サイト間のネットワーク リンク

また、中央サイトとブランチ サイトの間のネットワーク リンクで予想される帯域幅使用量も考慮する必要があります。 サイト間の復元 WAN リンクを展開または展開する計画がある場合は、各ブランチ サイトにゲートウェイを展開して、それらのサイトのユーザーにローカルのダイレクト インワード ダイヤル (DID) 終端を提供することをお勧めします。 回復可能な WAN リンクは存在するが、WAN リンクの帯域幅に制限がありそうな場合、そのリンクに通話受付管理を構成します。 回復可能な WAN リンクを使用していない場合、ブランチ サイトでホストするユーザー数が 1000 未満で、ローカルのトレーニングを受けた Skype for Business Server 管理者が利用できない場合は、ブランチ サイトに存続可能ブランチ アプライアンスを展開することをお勧めします。 ブランチ サイトで 1000 ~ 5,000 人のユーザーをホストし、回復力のある WAN 接続が不足し、トレーニングを受けた Skype for Business Server 管理者が利用できる場合は、ブランチ サイトに小さなゲートウェイを備える存続可能ブランチ サーバーを展開することをお勧めします。 メディア バイパスをサポートするゲートウェイ ピアが存在する場合は、制限のあるリンクでメディア バイパスを有効にすることも考慮してください。
  
## <a name="estimating-voice-usage-and-traffic"></a>音声の使用状況とトラフィックの見積もり

Microsoft Lync Server 2013 計画ツールは、次の指標を使用して、各サイトのユーザー トラフィックと、そのトラフィックをサポートするために必要なポート数を見積もっています。
  
> **軽度のトラフィック** (1 人あたり 1 時間に 1 PSTN 通話) の場合、1 ポートに対して 15 ユーザーを割り当てます。
> 
> **中度のトラフィック** (1 人あたり 1 時間に 2 PSTN 通話) の場合、1 ポートに対して 10 ユーザーを割り当てます。
> 
> **重度のトラフィック** (1 人あたり 1 時間に 3 以上の PSTN 通話) の場合、1 ポートに対して 5 ユーザーを割り当てます。
    
その後のポート数によって、必要な仲介サーバーとゲートウェイの数が決まれます。 ほとんどの組織が 2 ポートから最大 960 ポートの範囲の展開を検討している公衆交換電話網 (PSTN) ゲートウェイ。 (ゲートウェイはさらに大きくなりますが、主にテレフォニー サービス プロバイダーによって使用されます)。
  
たとえば、10,000 名のユーザーを擁する、中度のトラフィックの組織の場合、1000 ポートが必要となります。 必要となるゲートウェイ数は、ゲートウェイの総合した処理能力によって決まる、必要とされるポート数の合計と同じになります。
  
## <a name="components-features-and-options-of-enterprise-voice"></a>アプリケーションのコンポーネント、機能、およびエンタープライズ VoIP

展開の計画の詳細については、以下のセクションエンタープライズ VoIPしてください。
  
- [Skype for Business Server のエンタープライズ VoIPに必要なコンポーネント](components-required-for-enterprise-voice.md)
    
- [Skype for Business Server での PSTN 接続の計画](pstn-connectivity-0.md)
    
- [Skype for Business Server の高度エンタープライズ VoIP機能のネットワーク設定](network-settings-for-advanced-features.md)
    
- [Skype for Business Server で通話受付管理を計画する](call-admission-control.md)
    
- [Skype for Business Server で緊急サービスを計画する](emergency-services.md)
    
- [Skype for Business でのメディア バイパスの計画](media-bypass.md)
    
- [Skype for Business を使用してプライベート電話回線を計画する](private-telephone-lines.md)
    
- [Skype for Business Location-Basedルーティングの計画](location-based-routing.md)
    
- [Skype for Business の通話管理機能を計画する](call-management-features.md)
    
- [Skype for Business Server エンタープライズ VoIP回復性を計画する](enterprise-voice-resiliency.md)
    

