---
title: Skype for Business Server でインスタントメッセージとプレゼンスを計画する
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
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: '概要: Skype for Business Server でインスタントメッセージングとプレゼンスを計画する方法について説明します。'
ms.openlocfilehash: d62559afe0c7767ee7863f41b41f2d1b64127643
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815905"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Skype for Business Server でインスタントメッセージとプレゼンスを計画する
 
**概要:** Skype for Business Server でインスタントメッセージ (im) とプレゼンスを計画する方法について説明します。
  
Skype for Business Server でインスタントメッセージとプレゼンスを計画します。 オフラインインスタントメッセージング (IM) の有効化または無効化などの特定の展開オプションの詳細については、「 [Skype For Business Server でインスタントメッセージングとプレゼンスを展開](../deploy/im-and-presence/im-and-presence.md)する」を参照してください。
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Skype for Business Server でインスタントメッセージとプレゼンスを計画する

フロントエンドサーバーは、インスタントメッセージング (IM) やプレゼンスなどの Skype for business Server の主要な機能を提供し、すべての Skype for Business Server の展開に含まれています。 次の2つのエディションを使用できます。 Skype for Business Server Enterprise Edition は、主に大規模な組織向けに設計されており、Skype for Business Server Standard Edition 向けに設計されています。ハードウェアへの投資。高可用性の完全なオプションは必要ありません。 どちらのエディションも、IM、プレゼンス、会議、エンタープライズ Voip などのすべての Skype for Business Server のワークロードをサポートしています。
  
インスタント メッセージング (IM) を使用すると、ユーザーは各自のコンピューターでテキスト ベースのメッセージを使用して、リアルタイムで相互通信を行うことができます。 2 パーティとマルチパーティの両方の IM セッションがサポートされています。 2 パーティの IM 会話の参加者は、3 番目の参加者をいつでも会話に追加できます。 この際には、会議機能をサポートするように会話ウィンドウが変更されます。
  
プレゼンスは、ネットワーク上の他のユーザーの状態に関する情報をユーザーに提供します。 ユーザーのプレゼンス状態は、ユーザーに連絡を試みる必要があるかどうか、またインスタントメッセージング、電話、メールのどちらを使用するかを他のユーザーが判断するのに役立つ情報を提供します。 プレゼンスにより、可能な場合にはすぐにやりとりできますが、他にも、ユーザーが会議中であるかどうかや、外出のために応答できない状況なのかに関する情報も提供されます。 プレゼンス状態は、Skype for Business およびその他のプレゼンス対応のアプリケーション (Microsoft Outlook のメッセージングおよびコラボレーション クライアント、Microsoft SharePoint テクノロジ、Microsoft Office など) で、プレゼンス アイコンとして表示されます。 プレゼンスアイコンは、ユーザーの現在の可用性とコミュニケーションの意思を示します。 
  
### <a name="technical-requirements"></a>技術要件

インスタント メッセージング (IM) とプレゼンスは、常に Enterprise Edition フロントエンド プールと Standard Edition サーバーで実行されます。 サポートされているハードウェア、オペレーティングシステム、データベースソフトウェアの詳細については、[認定ゲートウェイ](../../SfbPartnerCertification/certification/infra-gateways.md)、 [skype for business 2015 環境の要件](requirements-for-your-environment/requirements-for-your-environment.md)、および[skype For business Server 2019 のインフラストラクチャ要件](../../SfBServer2019/plan/system-requirements.md)を参照してください。
  
### <a name="enabling-communication-with-external-users"></a>外部ユーザーとの通信を有効にする

ユーザーが外部ユーザーと通信できるようにすることで、Skype for Business Server での投資のメリットを大幅に向上させることができます。 外部ユーザーには次のユーザーが含まれます。
  
- リモートユーザー: ファイアウォール外で作業していて、自分のラップトップやその他の Skype for Business Server デバイスを使っている場合に、組織の独自のユーザー。
    
- フェデレーションユーザー: Skype for Business Server も実行している会社のユーザー。 自社ユーザーがこうしたユーザーに容易にコンタクトできるようにするには、これらの企業とフェデレーション関係を作成する必要があります。 
    
- Skype ユーザー:   Skype for Business ユーザーは、Skype で IM、音声、ビデオを使用して数億人のユーザーと連絡を取ることができます。
    
> [!NOTE]
> AOL、Yahoo、Google Talk はサポートされなくなりました。 
  
> [!NOTE]
> これらのシナリオのいずれか、またはすべてを有効にするには、microsoft Edge Server を展開して、Skype for Business Server の展開と外部ユーザー間の通信をセキュリティで保護できるようにする必要があります。 組織のリモートユーザーとフェデレーションされた組織のユーザーは、互いのプレゼンスを表示して、IM を使って通信することができます。 
  
> [!NOTE]
> XMPP (eXtensible Messaging and Presence Protocol) は、Unified Capabilities Collaboration Platform (UCCP) Joint Interoperability Test Command (JITC) 証明書シナリオでのみサポートされます。 
  
### <a name="archiving-im-content"></a>IM コンテンツをアーカイブする

Skype for Business Server には、組織が法令遵守法に準拠する必要がある場合に使用できる機能が用意されています。 アーカイブを使用すると、組織内のすべてのユーザーまたは指定する特定のユーザーの IM メッセージの内容をアーカイブすることができます。 詳細については、「 [Skype For Business Server でのアーカイブの計画](archiving/archiving.md)」を参照してください。 
  
Microsoft Exchange Server 2013 が展開されている場合は、Exchange データのアーカイブを Skype for Business Server データのアーカイブと統合することができます。また、単一のツールを使用して、両方の種類のアーカイブデータを検索することもできます。 詳細については、「 [Exchange server のアーカイブを使用するように Skype For Business server を構成する](../deploy/integrate-with-exchange-server/use-exchange-archiving.md)」を参照してください。
  
### <a name="topologies-and-components"></a>トポロジとコンポーネント

インスタント メッセージング (IM) とプレゼンスに必要なコンポーネントは、次に示すものだけです。
  
- 組織のフロントエンドサーバー (プールとも呼ばれます) または Standard Edition サーバー。 これらのサーバーで、IM およびプレゼンス機能は常にオンになっています。 フロントエンドプールのトポロジと管理の詳細については、「[フロントエンドプールの高可用性と管理](high-availability-and-disaster-recovery/high-availability.md)」を参照してください。
    
- ロード バランサー (Enterprise Edition フロントエンド プールがある場合)
    
### <a name="supported-collocation"></a>サポートされる併置

併置の定義は、複数の役割がインストールされた単一のサーバーまたはサーバー グループが存在することです。 Collocation の詳細については、「 [Skype For Business Server のトポロジの基礎](topology-basics/topology-basics.md)」を参照してください。 
  

