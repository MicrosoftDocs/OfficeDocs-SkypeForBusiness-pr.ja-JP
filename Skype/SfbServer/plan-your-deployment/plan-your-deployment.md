---
title: Skype for Business Server 2015 の展開の計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/21/2018
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
ms.assetid: fefd4fff-57cc-4019-b3eb-3535ad3729a8
description: '概要: Skype for Business Server 2015 の機能、サーバー、およびトポロジを構成するための概念、論理、および物理設計を開発する方法について説明するリンクを参照してください。'
ms.openlocfilehash: 071d47433f9b7cb7d8e1cfdafdb9db1e55f238ce
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220947"
---
# <a name="plan-for-your-skype-for-business-server-2015-deployment"></a>Skype for Business Server 2015 の展開の計画
 
**概要:** Skype for Business Server 2015 の機能、サーバー、およびトポロジを構成するための概念設計、論理設計、物理設計の開発方法については、次のリンクを参照してください。
  
Skype for Business Server には、エンタープライズレベルのコラボレーション要件をサポートできるインスタントメッセージング (IM)、プレゼンス、会議、ビデオ、テレフォニーのソリューションが用意されています。 ここでは、Skype for Business Server の展開を成功させるための計画方法に関する情報へのリンクを提供します。 
  
これらの記事は、新しい情報が入り次第、またユーザーのフィードバックに基づいて随時更新されます。 このページは頻繁に更新されるため、よく確認してください。
## <a name="visual-resources-about-how-to-plan-for-skype-for-business-server"></a>Skype for Business Server の計画方法に関するビジュアルリソース

Skype for Business Server の展開を計画する方法については、以下のリソースを参照してください。
  
||**コンテンツ**|**説明**|
|:--- |:--- |:--- |
|![技術ダイアグラムのアイコン](../media/87de0d09-77fd-46f2-b9f6-99a7998fd332.png)|[Skype for Business Server 2015 の技術ダイアグラム](../technical-diagrams.md) <br/> |大判の図によって各アーキテクチャを一目で確認できます。  <br/> |
|![ビデオのアイコン](../media/143e0d86-1c68-482a-9bf9-93e7966acca0.png)|[Skype for Business: 簡単な紹介](https://www.youtube.com/watch?v=PRJqMuwW5yc&amp;feature=youtu.be) <br/> [Skype for Business: 新しいユーザーのためのステップバイステップガイド](https://www.youtube.com/watch?v=7_c4zVJ739M&amp;feature=youtu.be) <br/> |Skype for Business のビデオプレゼンテーションとトレーニングを検出します。  <br/> |
   
##  <a name="articles-about-planning-for-skype-for-business-server"></a>Skype for Business Server の計画に関する記事

Skype for Business Server の計画方法に関する以下の記事は、オンラインで読むことができます。 
  
|**ソリューションを計画する**|**サーバーアーキテクチャ、クライアント、デバイスを計画する**|
|:-----|:-----|
|![ソリューションコンテンツのアイコン](../media/3959ce46-bd94-40be-8a58-6108bc3583a8.png)           <br/> 次の記事を読んで、組織に適したソリューションを決定してください。  <br/> |![サーバーアーキテクチャコンテンツのアイコン](../media/1d7d8156-1ca9-4124-a17f-6bce5aa91966.png)           <br/> サーバーアーキテクチャおよびクライアントとデバイスのサポートを計画するには、次の記事を参照してください。  <br/> |
|**[Skype For Business Server 2015 でのインスタントメッセージングおよびプレゼンスの計画](instant-messaging-and-presence.md)** インスタントメッセージング (IM) とプレゼンスの要件を教えてください。 インスタントメッセージング (IM) とプレゼンスはすべての Skype for Business Server の展開に含まれていますが、技術的な要件、外部ユーザーとの通信、およびアーカイブに関する決定を行う必要があります。 <br/> |**[Skype for Business Server 2015 の環境要件](requirements-for-your-environment/environmental-requirements.md)** <br/> **[Skype for Business Server 2015 のサーバー要件](requirements-for-your-environment/server-requirements.md)** <br/> **[Skype for Business 2015 のネットワーク要件を計画する](network-requirements/network-requirements.md)** <br/> Skype for Business Server の前提条件を確認するには、最初にこれらのトピックを参照してください。  <br/> |
|**[Skype For Business Server 2015 でのエンタープライズ voip ソリューションの計画](enterprise-voice-solution/enterprise-voice-solution.md)** 音声の要件を教えてください。 Skype for Business Server の展開に組織の電話システムを統合する方法を定義します。エンタープライズ Voip は、最も包括的な音声サービスで、Outlook と Exchange との統合を含む豊富な機能セットを提供しています。 [勤務先から通話] を使用すると、Skype for Business ソリューションを既存の PBX 電話システムと統合することができます。 <br/> |**[Skype For Business Server 2015 のトポロジの基本](topology-basics/topology-basics.md)** 他のものを準備する前に、Skype for Business Server の展開に適したトポロジを計画していることをご確認ください。 最初に、Skype for Business Server のオンプレミス展開をする予定か、またはハイブリッド展開で Skype for Business Server Online 展開と統合するかどうかを決定する必要があります。 トポロジとサーバーの併置シナリオを計画するには、このセクションのトピックを参照してください。 <br/> |
|**[Skype For Business server 2015 でのビデオ相互運用サーバーの計画](video-interop-server.md)** 組織のビデオ要件を教えてください。 Skype for Business Server のビデオ相互運用サーバーを Cisco のテレビ会議システム (VTCs) と直接統合できるようになりました。 ビデオの機能と技術要件を確認します。 <br/> |**[Skype For Business Server 2015 へのアップグレードを計画する](upgrade.md)** 以前のバージョンの Lync Server からアップグレードしていますか? アップグレードを計画する方法についての情報を参照してください。 <br/> |
|**[Skype For business と Exchange の統合を計画する](integrate-with-exchange/integrate-with-exchange.md)** 組織では、Exchange Server と Skype for Business の両方のサーバーを展開していますか。 その場合は、両方の製品の機能を統合する方法について固有を参照してください。 たとえば、プレゼンス情報やデータのアーカイブなどがあります。 <br/> |**[クライアントとデバイスの計画](clients-and-devices/clients-and-devices.md)** Skype for Business Server では、組織のユーザーに展開できるクライアントインターフェイスのコレクションがサポートされています。 慎重に計画することで、従業員は必要な情報を得ることができます。また、どこにいても、Skype for Business を利用できるようになります。 <br/> |
|**[Skype For Business server 2015 での常設チャットサーバーの計画](persistent-chat-server/persistent-chat-server.md)** 組織では、組織内の複数のユーザーが時間の経過とともに持続する会話に参加できるようにするチャットルームを実装する必要がありますか。 その場合は、常設チャットサーバーを計画および展開する方法についてお読みください。 <br/> |**[Skype For Business Server 2015 での高可用性および障害復旧の計画](high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)** 高可用性とは、1つまたは複数のサーバーがダウンした場合でも、Skype for Business Server サービスが利用できるようにすることを意味します。 障害復旧とは、自然または人為的な障害が発生した場合にサービスを継続し、可能な限り多くのデータを保持することを意味します。 高可用性と障害復旧を計画するには、このセクションのトピックを参照してください。 <br/> |
|**[Skype For Business Server 2015 での会議の計画](conferencing/conferencing.md)** 組織の会議の要件を教えてください。 Web 会議、音声ビデオ会議、およびダイヤルイン会議の機能と要件について説明します。 <br/> |**[Skype For Business Server 2015 でのセキュリティの計画](security/security.md)** Skype for Business Server での認証の理解および計画に役立つ、ユーザー認証、サーバー間認証、アプリケーション認証についてのリソースが見つかります。 <br/> |
|**[Skype For Business Server と skype for Business Online 間のハイブリッド接続を計画](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)** する オンプレミスの Skype for Business Server と Skype for Business Online の両方に所属しているユーザーがいますか。 その場合は、1つのドメインでオンプレミスとオンラインの両方のユーザーを同期するハイブリッド展開をセットアップする方法についてお読みください。 <br/> ||
|**[Skype For Business server 2015 でのエッジサーバーの展開を計画する](edge-server-deployments/edge-server-deployments.md)** 組織は内部ネットワークの外部にいるユーザーと通信していますか? その場合は、組織のファイアウォールを介した通信をサポートするためにエッジサーバーを展開する方法について確認してください。 <br/> ||
   
## <a name="additional-resources-about-planning-for-skype-for-business-server"></a>Skype for Business Server の計画に関するその他のリソース

Skype for Business Server の計画方法に関する以下のリソースが、他の特定分野の専門家から提供されています。 
  
||**コンテンツ**|**説明**|
|:--- |:--- |:--- |
|![ドキュメントのアイコン](../media/4eff581b-890b-46cb-8224-a4122137d27e.png)|[Skype for Business Server (IT 担当者向け)](https://go.microsoft.com/fwlink/p/?LinkId=527960) <br/> |ビデオ、コミュニティサイト、ドキュメント、ダウンロードなどにアクセスするには、リソースセンターにアクセスしてください。  <br/> |
|![開発者向けコンテンツのアイコン](../media/3626138a-2778-407e-911f-a0dcbdc36684.png)|[Skype 開発者プラットフォーム](https://go.microsoft.com/fwlink/?LinkId=619775) <br/> |コードサンプル、トレーニング、Sdk など、Skype for Business Server の開発者向けリソースを見つけることができます。  <br/> |
|![ニュース、ブログなどのアイコン](../media/ac692cb8-7db8-4810-b53f-1bc88b1e4cac.png)|[変更の管理と導入](https://go.microsoft.com/fwlink/p/?LinkId=532796) <br/> [Office ブログ](https://go.microsoft.com/fwlink/p/?LinkId=528899) <br/> [Skype チームブログ](https://go.microsoft.com/fwlink/p/?LinkId=532818) <br/> |Skype for Business Server を作成してドキュメント化する teams からの最新ニュースを把握します。  <br/> |
