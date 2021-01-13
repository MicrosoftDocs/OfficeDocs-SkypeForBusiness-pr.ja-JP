---
title: Skype for Business Server のエンタープライズ VoIPに必要なコンポーネント
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
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Skype for Business Server のエンタープライズ VoIPコンポーネントの概要。
ms.openlocfilehash: 1a7f13cc171af44ecbd0f48706ec12d882e50b33
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825827"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>Skype for Business Server のエンタープライズ VoIPに必要なコンポーネント
 
Skype for Business Server のエンタープライズ VoIPコンポーネントの概要。
  
トポロジをエンタープライズ VoIPするには、トポロジで次のコンポーネントが必要です。 
  
- 1 つ以上の仲介サーバー。内部の Skype for Business Server、エンタープライズ VoIP インフラストラクチャ、公衆交換電話網 (PSTN) ゲートウェイ、またはセッション開始プロトコル (SIP) トランク間で信号を変換し、一部の構成ではメディアを変換します。 仲介サーバーは、新しい展開で最も重要エンタープライズ VoIPコンポーネントです。 詳細については [、Skype for Business Server の仲介サーバー コンポーネントを参照してください](mediation-server.md)。
    
    仲介サーバーは、フロントエンド サーバーと一緒に展開するか、スタンドアロン サーバーとしてインストールできます。
    
- SIP トランクまたは PSTN ゲートウェイを含む PSTN 接続コンポーネント。 詳細については、Skype for Business Server の PSTN 接続 [コンポーネントを参照してください](pstn-connectivity.md)。
    
- エッジ サーバー エンタープライズ VoIP。 
    
    アクセス エッジ サービスは、組織のファイアウォールの外側にある Skype for Business ユーザーからの呼び出しに対して SIP 信号を提供します。 音声ビデオ エッジ サービスを使用すると、メディアが NAT およびファイアウォールを通過できます。 企業ファイアウォールの外部で統合コミュニケーション (UC) クライアントを使用する発信者には、個別の通話と電話会議の両方に音声ビデオ エッジ サービスが必要です。
    
    音声ビデオ認証サービスは音声ビデオ エッジ サービスと同じコンピューターに配置され、音声ビデオ エッジ サービスのための認証サービスを実行します。外部のユーザーが音声ビデオ エッジ サービスに接続するには、発信を行う前に、音声ビデオ認証サービスから認証トークンを取得する必要があります。
    
- さらに、一部エンタープライズ VoIPコンポーネントはフロントエンド サーバー上で実行されます。 これらのコンポーネントの詳細については [、「Skype for Business Server のフロントエンド サーバー VoIP コンポーネント」を参照してください。](front-end-server-voip.md)
    

