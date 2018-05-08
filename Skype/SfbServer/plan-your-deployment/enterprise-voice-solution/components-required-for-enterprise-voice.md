---
title: Skype for Business Server 2015 のエンタープライズ VoIP に必要なコンポーネント
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Skype ビジネス サーバーでエンタープライズ VoIP のコンポーネントの概要です。
ms.openlocfilehash: 4f28b0dc42b9a64cae7883490a7e9f5e09dd8d80
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 のエンタープライズ VoIP に必要なコンポーネント
 
Skype ビジネス サーバーでエンタープライズ VoIP のコンポーネントの概要です。
  
エンタープライズ VoIP を展開するには、トポロジでは、次のコンポーネントが必要です。 
  
- 信号と、構成によっては、内部の Skype ビジネス サーバー、エンタープライズ VoIP インフラストラクチャと公衆交換電話網 (PSTN) ゲートウェイまたはセッション開始プロトコルの間でのメディアを変換する 1 つまたは複数の仲介サーバー(SIP) トランク。 仲介サーバーは、エンタープライズ VoIP 展開で最も重要なコンポーネントです。 詳細については、 [Skype のビジネス サーバー 2015 の仲介サーバーのコンポーネント](mediation-server.md)を参照してください。
    
    仲介サーバーをフロント エンド サーバーと同じ場所またはスタンドアロン サーバーとしてインストールされていることができます。
    
- SIP トランクまたは PSTN ゲートウェイを含めることができる、PSTN 接続コンポーネント。 詳細については、 [Skype のビジネス サーバー 2015 の PSTN 接続のコンポーネント](pstn-connectivity.md)を参照してください。
    
- エッジ サーバーは、組織のファイアウォールの外部にいるときに、ユーザーがエンタープライズ VoIP 機能の使用を有効にします。 
    
    アクセス エッジ サービスは、ビジネス ユーザーが、組織のファイアウォール外の Skype からの通話の SIP シグナリングを提供します。 音声ビデオ エッジ サービスを使用すると、メディアが NAT およびファイアウォールを通過できます。 企業ファイアウォールの外部で統合コミュニケーション (UC) クライアントを使用する発信者には、個別の通話と電話会議の両方に音声ビデオ エッジ サービスが必要です。
    
    音声ビデオ認証サービスは音声ビデオ エッジ サービスと同じコンピューターに配置され、音声ビデオ エッジ サービスのための認証サービスを実行します。外部のユーザーが音声ビデオ エッジ サービスに接続するには、発信を行う前に、音声ビデオ認証サービスから認証トークンを取得する必要があります。
    
- さらに、エンタープライズ VoIP のコンポーネントのいくつかは、フロント エンド サーバーで実行します。 これらのコンポーネントに関する詳細については、 [Skype のビジネス サーバー 2015 のフロント エンド サーバーの VoIP コンポーネント](front-end-server-voip.md)を参照してください。
    

