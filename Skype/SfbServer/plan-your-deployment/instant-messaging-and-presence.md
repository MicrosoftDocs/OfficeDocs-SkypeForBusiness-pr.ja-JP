---
title: Business Server のインスタント メッセージングと Skype のプレゼンスの計画します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: '概要: ビジネスのサーバーにインスタント メッセージングとプレゼンスの Skype を計画する方法を説明します。'
ms.openlocfilehash: e68a7b427545105db9ed543e2f1ad77411ba88b7
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21002234"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Business Server のインスタント メッセージングと Skype のプレゼンスの計画します。
 
**の概要:** ビジネスのサーバーにインスタント メッセージングとプレゼンスの Skype を計画する方法について説明します。
  
ビジネスのサーバーにインスタント メッセージングとプレゼンスの Skype を計画します。 有効にするか、オフライン インスタント メッセージング (IM)、無効にするなど、特定の展開オプションの詳細については、[インスタント メッセージングを展開しビジネス サーバーの Skype のプレゼンス](../deploy/im-and-presence/im-and-presence.md)を参照してください。
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Business Server のインスタント メッセージングと Skype のプレゼンスの計画します。

フロント エンド サーバーを提供インスタント メッセージング (IM) とプレゼンスなどのビジネスのサーバーの機能のための Skype のコア ビジネス サーバー配置のすべての Skype に含まれています。 使用可能な 2 つのエディションがあります: 大規模な組織に主に設計されていますが、ビジネス サーバー Enterprise Edition の Skype と Skype ビジネス Server Standard Edition は、主に小規模な組織であるより小さいかどうかのハードウェアへの投資の完全な高可用性オプションを必要としません。 両方のエディションでは、IM、プレゼンス、会議、およびエンタープライズ VoIP を含むビジネス サーバー ワークロードのすべての Skype をサポートします。
  
インスタント メッセージング (IM) を使用すると、ユーザーは各自のコンピューターでテキスト ベースのメッセージを使用して、リアルタイムで相互通信を行うことができます。 2 パーティとマルチパーティの両方の IM セッションがサポートされています。 2 パーティの IM 会話の参加者は、3 番目の参加者をいつでも会話に追加できます。 この際には、会議機能をサポートするように会話ウィンドウが変更されます。
  
プレゼンスは、ネットワーク上の他のユーザーの状態に関する情報をユーザーに提供します。 ユーザーのプレゼンス状態は、他のユーザーかどうかする必要がありますしようとするユーザーに連絡し、インスタント メッセージング、電話、または電子メールを使用するかどうかを決定に役立つ情報を提供します。 プレゼンスにより、可能な場合にはすぐにやりとりできますが、他にも、ユーザーが会議中であるかどうかや、外出のために応答できない状況なのかに関する情報も提供されます。 プレゼンス状態は、Skype for Business およびその他のプレゼンス対応のアプリケーション (Microsoft Outlook のメッセージングおよびコラボレーション クライアント、Microsoft SharePoint テクノロジ、Microsoft Office など) で、プレゼンス アイコンとして表示されます。 プレゼンス アイコンは、ユーザーの現在の可用性と通信意思を表します。 
  
### <a name="technical-requirements"></a>技術要件

インスタント メッセージング (IM) とプレゼンスは、常に Enterprise Edition フロントエンド プールと Standard Edition サーバーで実行されます。 サポートされているハードウェア、オペレーティング システム、およびデータベース ソフトウェアについては、[認定ゲートウェイ](../../SfbPartnerCertification/certification/infra-gateways.md)、 [2015 のビジネス環境について、Skype の要件](requirements-for-your-environment/requirements-for-your-environment.md)、およびビジネス サーバー 2019 の Skype のための[インフラストラクチャの要件を参照してください。](../../SfBServer2019/plan/system-requirements.md).
  
### <a name="enabling-communication-with-external-users"></a>外部ユーザーとの通信を有効にする

Skype for Business Server への投資による収益性は、ユーザーが外部ユーザーと通信できるようにすることで大幅に高められます。外部ユーザーには次のユーザーが含まれます。
  
- リモート ユーザー: 組織のユーザー、あなたはファイアウォールの外側で作業し、ビジネス サーバー デバイスをラップトップ コンピューターやその他の Skype を使用しています。
    
- フェデレーション ユーザー: ユーザーも Skype をビジネスのサーバーの実行を使用する企業からです。 自社ユーザーがこうしたユーザーに容易にコンタクトできるようにするには、これらの企業とフェデレーション関係を作成する必要があります。 
    
- Skype ユーザー:   Skype for Business ユーザーは、Skype で IM、音声、ビデオを使用して数億人のユーザーと連絡を取ることができます。
    
> [!NOTE]
> AOL、Yahoo、Google Talk はサポートされなくなりました。 
  
> [!NOTE]
> これらのシナリオのいくつか、またはすべてを有効にするには、Skype for Business Server の展開と外部ユーザーの間でセキュリティで保護された通信を有効にできるようにエッジ サーバーを展開する必要があります。 組織のリモート ユーザーとフェデレーション組織のユーザーは、互いの存在を確認し、IM を使用して通信できるようなります。 
  
> [!NOTE]
> XMPP (eXtensible Messaging and Presence Protocol) は、Unified Capabilities Collaboration Platform (UCCP) Joint Interoperability Test Command (JITC) 証明書シナリオでのみサポートされます。 
  
### <a name="archiving-im-content"></a>IM コンテンツをアーカイブする

Skype for Business Server には、組織で法令上の規制に従う必要がある場合に使用できる機能があります。 アーカイブを使用すると、組織内のすべてのユーザーまたは指定する特定のユーザーの IM メッセージの内容をアーカイブすることができます。 詳細については、 [Skype のビジネス サーバーでアーカイブするための計画](archiving/archiving.md)を参照してください。 
  
Microsoft Exchange Server 2013 も展開している場合は、Exchange データのアーカイブと Skype for Business Server データのアーカイブを統合して、1 つのツールを使用して両種類のアーカイブ データを検索することができます。 詳細については、[ビジネス サーバーで Exchange Server のアーカイブを使用する Skype の設定](../deploy/integrate-with-exchange-server/use-exchange-archiving.md)を参照してください。
  
### <a name="topologies-and-components"></a>トポロジとコンポーネント

インスタント メッセージング (IM) とプレゼンスに必要なコンポーネントは、次に示すものだけです。
  
- (プールと呼ばれます)、組織のフロント エンド サーバーまたは Standard Edition サーバーです。 これらのサーバーで、IM およびプレゼンス機能は常にオンになっています。 フロント エンド プール トポロジと管理の詳細については、[フロント エンド プールの高可用性と管理](high-availability-and-disaster-recovery/high-availability.md)を参照してください。
    
- ロード バランサー (Enterprise Edition フロントエンド プールがある場合)
    
### <a name="supported-collocation"></a>サポートされる併置

併置の定義は、複数の役割がインストールされた単一のサーバーまたはサーバー グループが存在することです。 コロケーションの詳細については、 [Skype のビジネス サーバーのトポロジの基礎](topology-basics/topology-basics.md)を参照してください。 
  

