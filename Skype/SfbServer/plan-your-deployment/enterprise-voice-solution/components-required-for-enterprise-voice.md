---
title: Skype でエンタープライズ VoIP のサーバーのビジネスに必要なコンポーネント
ms.author: crowe
author: CarolynRowe
manager: serdars
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
ms.openlocfilehash: 800a12b2d83703f188fff04452cf865757d5cad9
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20970480"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>Skype でエンタープライズ VoIP のサーバーのビジネスに必要なコンポーネント
 
Skype ビジネス サーバーでエンタープライズ VoIP のコンポーネントの概要です。
  
エンタープライズ VoIP を展開するには、トポロジでは、次のコンポーネントが必要です。 
  
- 信号と、構成によっては、内部の Skype ビジネス サーバー、エンタープライズ VoIP インフラストラクチャと公衆交換電話網 (PSTN) ゲートウェイまたはセッション開始プロトコルの間でのメディアを変換する 1 つまたは複数の仲介サーバー(SIP) トランク。 仲介サーバーは、エンタープライズ VoIP 展開で最も重要なコンポーネントです。 詳細については、 [Skype のビジネス サーバーの仲介サーバーのコンポーネント](mediation-server.md)を参照してください。
    
    仲介サーバーをフロント エンド サーバーと同じ場所またはスタンドアロン サーバーとしてインストールされていることができます。
    
- SIP トランクまたは PSTN ゲートウェイを含めることができる、PSTN 接続コンポーネント。 詳細については、 [Skype のビジネス サーバーの PSTN 接続のコンポーネント](pstn-connectivity.md)を参照してください。
    
- エッジ サーバーは、組織のファイアウォールの外部にいるときに、ユーザーがエンタープライズ VoIP 機能の使用を有効にします。 
    
    アクセス エッジ サービスは、ビジネス ユーザーが、組織のファイアウォール外の Skype からの通話の SIP シグナリングを提供します。 音声ビデオ エッジ サービスを使用すると、メディアが NAT およびファイアウォールを通過できます。 企業ファイアウォールの外部で統合コミュニケーション (UC) クライアントを使用する発信者には、個別の通話と電話会議の両方に音声ビデオ エッジ サービスが必要です。
    
    音声ビデオ認証サービスは音声ビデオ エッジ サービスと同じコンピューターに配置され、音声ビデオ エッジ サービスのための認証サービスを実行します。外部のユーザーが音声ビデオ エッジ サービスに接続するには、発信を行う前に、音声ビデオ認証サービスから認証トークンを取得する必要があります。
    
- さらに、エンタープライズ VoIP のコンポーネントのいくつかは、フロント エンド サーバーで実行します。 これらのコンポーネントに関する詳細については、 [Skype のビジネス サーバーのフロント エンド サーバーの VoIP コンポーネント](front-end-server-voip.md)を参照してください。
    

