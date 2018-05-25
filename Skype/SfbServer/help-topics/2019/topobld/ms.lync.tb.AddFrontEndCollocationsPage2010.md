---
title: フロント エンド サーバー Collocations 2010 を追加します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: Enterprise Edition 展開では、どちらか A に集約できます V 会議サービス、仲介サーバー、またはフロント エンド プール、または両方を展開できますスタンドアロン サーバーとして各とします。 Standard Edition サーバーの展開、A V 会議サービスは、常に同じ場所に会議が有効になっている場合とします。
ms.openlocfilehash: f8a1abf168447af7f45ed8f222ef80f029aff2bc
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2018
---
# <a name="add-front-end-server-collocations-2010"></a>フロント エンド サーバー Collocations 2010 を追加します。
 
Enterprise Edition 展開では、どちらか A に集約できます V 会議サービス、仲介サーバー、またはフロント エンド プール、または両方を展開できますスタンドアロン サーバーとして各とします。 Standard Edition サーバーの展開、A V 会議サービスは、常に同じ場所に会議が有効になっている場合とします。
  
> [!NOTE]
> A/V 会議サービスは、**会議**は、**機能の選択**] ページで選択した場合必要です。 エンタープライズ エディションのフロント エンド プールを使用して、配置されている可能性があります A/V 会議サービスまたはスタンドアロンの A/V 会議のプールです。 会議がなかった場合は、選択すると、Collocate A/V 会議サービスを使用可能にすることはできません。
  
標準エディションのフロント エンド サーバーまたはエンタープライズ エディションのフロント エンド プールに仲介サーバーの役割に集約できます。 メディア バイ パスとドメイン ネーム システム (DNS) 負荷分散をサポートする修飾の公衆交換電話網 (PSTN) ゲートウェイに直接 SIP 接続を展開する場合、スタンドアロンの仲介サーバー プールは必要ではありません。 修飾のゲートウェイは、仲介サーバーのプールに DNS のロードバランシングに対応し、プール内のすべての仲介サーバーからのトラフィックを受信できるため、スタンドアロンの仲介サーバー プールは必要ではありません。 まとめてフロント エンド プールに仲介サーバー IP Pbx を展開しているか、接続、インターネット テレフォニー サービス プロバイダーのセッション ボーダー コント ローラー (SBC) に次の条件のいずれかを満たしている限り、またお勧めします。
  
- IP PBX、または SBC、プール内のすべての仲介サーバーからのトラフィックを受信するように構成し、プール内のすべての仲介サーバーに均等にトラフィックをルーティングできます。
    
- IP PBX、または SBC、プール内のすべての仲介サーバーからのトラフィックを受信するように構成し、プール内のすべての仲介サーバーに均等にトラフィックをルーティングできます。
    
Microsoft Lync Server 2013 フロント エンド プール、仲介サーバーを連結するが、負荷を処理できるかどうかを評価するために、計画ツールを使用することができます。 お客様の環境では、これら要件を満たすことはできません、する場合は、スタンドアロン仲介サーバー プールを展開する必要があります。
  
A の全般的なコロケーションに/V 会議サーバーまたは仲介サーバー組織が高可用性とスケーラビリティ要件の詳細、Enterprise Edition フロント エンド プールでこれらのサーバー ロールを配置している場合を推奨されていません展開、展開に関するドキュメントの[定義およびフロント エンド プールを構成する](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)を参照してください。 詳細については、A の V 会議の機能およびコンポーネントは、計画のドキュメントで[の会議を計画する](http://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx)を参照するくださいとします。 エンタープライズ VoIP 機能と、仲介サーバーを含め、コンポーネントの詳細についてを参照してください[ビジネス サーバー 2015 の Skype でエンタープライズ VoIP の計画](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)計画マニュアルを参照します。
  

