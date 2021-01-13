---
title: Skype for Business Server でのインスタント メッセージングとプレゼンスの計画
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
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: '概要: Skype for Business Server でインスタント メッセージングとプレゼンスを計画する方法について説明します。'
ms.openlocfilehash: a29d68cc66e0ac4a70fc759283646fc3ce49cdf5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816277"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Skype for Business Server でのインスタント メッセージングとプレゼンスの計画
 
**概要:** Skype for Business Server でインスタント メッセージングとプレゼンスを計画する方法について説明します。
  
Skype for Business Server でインスタント メッセージングとプレゼンスを計画します。 オフライン インスタント メッセージング (IM) の有効化や無効化などの特定の展開オプションについては [、「Skype for Business Server](../deploy/im-and-presence/im-and-presence.md)でのインスタント メッセージングとプレゼンスの展開」を参照してください。
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Skype for Business Server でのインスタント メッセージングとプレゼンスの計画

フロントエンド サーバーは、インスタント メッセージング (IM) やプレゼンスなどの Skype for Business Server のコア機能を提供し、すべての Skype for Business Server 展開に含まれています。 利用できるエディションは 2 種類あり、主に大規模な組織向けに設計された Skype for Business Server Enterprise Edition と、ハードウェアへの投資が少ない、完全な高可用性オプションを必要としない小規模な組織向けに設計された Skype for Business Server Standard Edition があります。 どちらのエディションも、IM、プレゼンス、会議、および会議を含むすべての Skype for Business Server ワークロードをエンタープライズ VoIP。
  
インスタント メッセージング (IM) を使用すると、ユーザーは各自のコンピューターでテキスト ベースのメッセージを使用して、リアルタイムで相互通信を行うことができます。 2 パーティとマルチパーティの両方の IM セッションがサポートされています。 2 パーティの IM 会話の参加者は、3 番目の参加者をいつでも会話に追加できます。 この際には、会議機能をサポートするように会話ウィンドウが変更されます。
  
プレゼンスは、ネットワーク上の他のユーザーの状態に関する情報をユーザーに提供します。 ユーザーのプレゼンス状態は、他のユーザーがユーザーと連絡を取る必要があるかどうか、およびインスタント メッセージング、電話、または電子メールを使用するかどうかを決定するのに役立つ情報を提供します。 プレゼンスにより、可能な場合は即時に通信しやすくなりますが、ユーザーが会議中であるかどうかや、外出のために応答できない状況なのかに関する情報も提供されます。 このプレゼンス状態は、Skype for Business および Microsoft Outlook のメッセージングおよびコラボレーション クライアント、Microsoft SharePoint テクノロジ、および Microsoft Office などの他のプレゼンス対応アプリケーションでプレゼンス アイコンとして表示されます。 プレゼンス アイコンは、ユーザーの現在の可用性と通信の意思を表します。 
  
### <a name="technical-requirements"></a>技術的要件

インスタント メッセージング (IM) とプレゼンスは、常に Enterprise Edition フロントエンド プールと Standard Edition サーバーで実行されます。 サポートされるハードウェア、オペレーティング システム、およびデータベース ソフトウェアの詳細については、「Certified  [Gateways」、Skype](../../SfbPartnerCertification/certification/infra-gateways.md)  [for Business 2015](requirements-for-your-environment/requirements-for-your-environment.md)環境の要件、 [および Skype for Business Server 2019](../../SfBServer2019/plan/system-requirements.md)のインフラストラクチャ要件を参照してください。
  
### <a name="enabling-communication-with-external-users"></a>外部ユーザーとの通信を有効にする

ユーザーが外部ユーザーと通信できるようすることで、Skype for Business Server への投資のメリットを大幅に向上できます。 外部ユーザーには次のユーザーが含まれます。
  
- リモート ユーザー: 組織のユーザーがファイアウォールの外側で作業し、ノート PC や他の Skype for Business Server デバイスを使用している場合。
    
- フェデレーション ユーザー: Skype for Business Server も実行している、一緒に作業している会社のユーザー。 こちら側のユーザーがこれらのユーザーに容易にコンタクトできるようにするには、これらの企業とフェデレーション関係を作成する必要があります。 
    
- Skype ユーザー: Skype for Business ユーザーは、IM、音声、ビデオを使用して、Skype の数億人のユーザーにアクセスできます。
    
> [!NOTE]
> AOL、Yahoo、Google Talk はサポートされなくなりました。 
  
> [!NOTE]
> これらのシナリオの一部またはすべてを有効にするには、Skype for Business Server 展開と外部ユーザー間のセキュリティで保護された通信を有効にするのに役立つエッジ サーバーを展開する必要があります。 組織のリモート ユーザーとフェデレーション組織のユーザーは、IM を使用して互いにプレゼンスを確認し、通信することができます。 
  
> [!NOTE]
> XMPP (Extensible Messaging and Presence Protocol) は、Unified Capabilities Collaboration Platform (UCCP) Joint Interoperability Test Command (JITC) 認定シナリオでのみサポートされます。 
  
### <a name="archiving-im-content"></a>IM コンテンツのアーカイブ

Skype for Business Server は、組織がコンプライアンス規制に従う必要がある場合に使用できる機能を提供します。 アーカイブを使用すると、組織内のすべてのユーザーまたは指定した特定のユーザーの IM メッセージの内容をアーカイブできます。 詳細については [、「Skype for Business Server でのアーカイブの計画」を参照してください](archiving/archiving.md)。 
  
Microsoft Exchange Server 2013 も展開している場合は、Exchange データのアーカイブと Skype for Business Server データのアーカイブを統合し、1 つのツールを使用して両方の種類のアーカイブ データを検索できます。 詳細については [、「Skype for Business Server を構成して](../deploy/integrate-with-exchange-server/use-exchange-archiving.md)アーカイブを使用Exchange Server参照してください。
  
### <a name="topologies-and-components"></a>トポロジとコンポーネント

インスタント メッセージング (IM) とプレゼンスに必要なコンポーネントは次のとおりです。
  
- 組織のフロントエンド サーバー (プールと呼ばれる) または Standard Edition サーバー。 IM およびプレゼンス機能は、これらのサーバーで常に有効になります。 フロントエンド プールのトポロジと管理の詳細については、「フロントエンド プールの高可用性と管理」 [を参照してください](high-availability-and-disaster-recovery/high-availability.md)。
    
- ロード バランサー (Enterprise Edition フロントエンド プールがある場合)。
    
### <a name="supported-collocation"></a>サポートされるコロケーション

複数の役割がインストールされた単一のサーバーまたはサーバーのグループが含まれています。 コロケーションの詳細については [、「Topology Basics for Skype for Business Server」を参照してください](topology-basics/topology-basics.md)。 
  

