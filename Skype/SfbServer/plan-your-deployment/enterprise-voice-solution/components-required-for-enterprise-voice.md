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
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: このページのエンタープライズ VoIPコンポーネントSkype for Business Server。
ms.openlocfilehash: 80fce2f32521f2d4d5e493efafebbc344cba0e26
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768525"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>エンタープライズ VoIPのSkype for Business Server
 
このページのエンタープライズ VoIPコンポーネントSkype for Business Server。
  
トポロジをエンタープライズ VoIPするには、トポロジで次のコンポーネントが必要です。 
  
- 1 つ以上の仲介サーバー。信号を変換し、一部の構成では、内部 Skype for Business Server、エンタープライズ VoIP インフラストラクチャと公衆交換電話網 (PSTN) ゲートウェイまたはセッション開始プロトコル (SIP) トランク間のメディア。 仲介サーバーは、展開の最も重要なエンタープライズ VoIPです。 詳細については、「仲介サーバー[コンポーネント」を参照Skype for Business Server。](mediation-server.md)
    
    仲介サーバーは、フロント エンド サーバーと一緒に展開するか、スタンドアロン サーバーとしてインストールできます。
    
- SIP トランクまたは PSTN ゲートウェイを含む PSTN 接続コンポーネント。 詳細については、「PSTN 接続コンポーネント」を[参照Skype for Business Server。](pstn-connectivity.md)
    
- エッジ サーバーは、組織のファイアウォールエンタープライズ VoIPユーザーが機能を使用できるサーバーです。 
    
    Access Edge サービスは、組織のファイアウォールの外部Skype for Businessユーザーからの通話に対する SIP シグナリングを提供します。 音声ビデオ エッジ サービスを使用すると、メディアが NAT およびファイアウォールを通過できます。 企業ファイアウォールの外部で統合コミュニケーション (UC) クライアントを使用する発信者には、個別の通話と電話会議の両方に音声ビデオ エッジ サービスが必要です。
    
    音声ビデオ認証サービスは音声ビデオ エッジ サービスと同じコンピューターに配置され、音声ビデオ エッジ サービスのための認証サービスを実行します。外部のユーザーが音声ビデオ エッジ サービスに接続するには、発信を行う前に、音声ビデオ認証サービスから認証トークンを取得する必要があります。
    
- さらに、一部エンタープライズ VoIPコンポーネントはフロント エンド サーバーで実行されます。 これらのコンポーネントの詳細については、「フロントエンド[サーバー VoIP コンポーネント」を参照Skype for Business Server](front-end-server-voip.md)
    

