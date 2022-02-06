---
title: インスタント メッセージングとプレゼンスの計画を立Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: '概要: インスタント メッセージングとプレゼンスを計画する方法について説明します。Skype for Business Server。'
---

# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>インスタント メッセージングとプレゼンスの計画を立Skype for Business Server
 
**概要:** インスタント メッセージングとプレゼンスを計画する方法については、Skype for Business Server。
  
インスタント メッセージングとプレゼンスを計画Skype for Business Server。 オフライン インスタント メッセージング (IM) の有効化や無効化などの特定の展開オプションについては、「Deploy instant Messaging and presence in Skype for Business Server」[を参照してください](../deploy/im-and-presence/im-and-presence.md)。
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>インスタント メッセージングとプレゼンスの計画を立Skype for Business Server

フロントエンド サーバーは、インスタント Skype for Business Server (IM) やプレゼンスなどの主要な機能を提供し、すべての展開にSkype for Business Serverされます。 利用できるエディションは 2 種類Skype for Business Server Enterprise Edition、主に大規模な組織向けと大規模な組織向けSkype for Business Server Standard Editionこれは、主に、ハードウェアへの投資を小さくし、完全な高可用性オプションを必要としない小規模な組織向けです。 どちらのエディションも、IM、プレゼンスSkype for Business Server会議、および会議など、すべてのワークロードをサポートエンタープライズ VoIP。
  
インスタント メッセージング (IM) を使用すると、ユーザーは各自のコンピューターでテキスト ベースのメッセージを使用して、リアルタイムで相互通信を行うことができます。 2 パーティとマルチパーティの両方の IM セッションがサポートされています。 2 パーティの IM 会話の参加者は、3 番目の参加者をいつでも会話に追加できます。 この際には、会議機能をサポートするように会話ウィンドウが変更されます。
  
プレゼンスは、ネットワーク上の他のユーザーの状態に関する情報をユーザーに提供します。 ユーザーのプレゼンス状態は、他のユーザーがユーザーに問い合わせるべきかどうか、およびインスタント メッセージング、電話、または電子メールを使用するかどうかを決定するのに役立つ情報を提供します。 プレゼンスにより、可能な場合は即時に通信しやすくなりますが、ユーザーが会議中であるかどうかや、外出のために応答できない状況なのかに関する情報も提供されます。 このプレゼンス状態は、Skype for Business および他のプレゼンス対応アプリケーション (Microsoft Outlook メッセージングおよびコラボレーション クライアント、Microsoft SharePoint テクノロジ、および Microsoft Office など) のプレゼンス アイコンとして表示されます。 プレゼンス アイコンは、ユーザーの現在の可用性と通信の意思を表します。 
  
### <a name="technical-requirements"></a>技術的要件

インスタント メッセージング (IM) とプレゼンスは、常にフロントエンド プールEnterprise EditionサーバーでStandard Editionされます。 サポートされるハードウェア、オペレーティング システム、およびデータベース ソフトウェアの詳細については、「認定[](../../SfbPartnerCertification/certification/infra-gateways.md)ゲートウェイ、[Skype for Business 2015](requirements-for-your-environment/requirements-for-your-environment.md) 環境の要件、および Skype for Business Server [2019 のインフラストラクチャ要件」を参照](../../SfBServer2019/plan/system-requirements.md)してください。
  
### <a name="enabling-communication-with-external-users"></a>外部ユーザーとの通信を有効にする

ユーザーが外部ユーザーと通信することで、Skype for Business Serverへの投資のメリットを大幅に増やします。 外部ユーザーには次のユーザーが含まれます。
  
- リモート ユーザー: 組織のユーザーがファイアウォールの外で作業し、ラップトップや他のデバイスを使用Skype for Business Serverです。
    
- フェデレーション ユーザー: ユーザーが作業している会社のユーザーで、ユーザーがSkype for Business Server。 こちら側のユーザーがこれらのユーザーに容易にコンタクトできるようにするには、これらの企業とフェデレーション関係を作成する必要があります。 
    
- Skypeユーザー: Skype for Businessユーザーは、IM、音声、ビデオを使用して、Skype数億人のユーザーにアクセスできます。
    
> [!NOTE]
> AOL、Yahoo、Google Talk はサポートされなくなりました。 
  
> [!NOTE]
> これらのシナリオの一部またはすべてを有効にするには、エッジ サーバーを展開して、エッジ サーバーの展開と外部ユーザーとの間のSkype for Business Serverを有効にする必要があります。 組織のリモート ユーザーとフェデレーション組織のユーザーは、IM を使用して相互のプレゼンスを確認し、通信できます。 
  
> [!NOTE]
> 拡張可能メッセージングとプレゼンス プロトコル (XMPP) は、統合機能コラボレーション プラットフォーム (UCCP) 共同相互運用性テスト コマンド (JITC) 認定シナリオでのみサポートされます。 
  
### <a name="archiving-im-content"></a>IM コンテンツのアーカイブ

Skype for Business Serverコンプライアンス規制に従う必要がある場合に使用できる機能を提供します。 アーカイブを使用すると、組織内のすべてのユーザーまたは指定した特定のユーザーに対して IM メッセージのコンテンツをアーカイブできます。 詳細については、「Plan [for archiving in Skype for Business Server」 を参照してください](archiving/archiving.md)。 
  
Microsoft Exchange Server 2013 も展開している場合は、Exchange データのアーカイブと Skype for Business Server データのアーカイブを統合し、1 つのツールを使用して両方の種類のアーカイブ データを検索できます。 詳細については、「アーカイブを使用[Skype for Business Server構成Exchange Server参照してください](../deploy/integrate-with-exchange-server/use-exchange-archiving.md)。
  
### <a name="topologies-and-components"></a>トポロジとコンポーネント

インスタント メッセージング (IM) とプレゼンスに必要なコンポーネントは次のとおりです。
  
- 組織のフロントエンド サーバー (プールと呼ばれる) またはサーバー Standard Editionします。 IM とプレゼンス機能は、これらのサーバーで常に有効になります。 フロントエンド プールのトポロジと管理の詳細については、「フロントエンド プールの高可用性と管理 [」を参照してください](high-availability-and-disaster-recovery/high-availability.md)。
    
- ロード バランサー (フロントエンド プールにEnterprise Edition場合)。
    
### <a name="supported-collocation"></a>サポートされているコロケーション

Collocation は、複数の役割がインストールされた単一のサーバーまたはサーバーのグループを持つとして定義されます。 コロケーションの詳細については、「[トポロジの基本」を参照Skype for Business Server](topology-basics/topology-basics.md)。 
  

