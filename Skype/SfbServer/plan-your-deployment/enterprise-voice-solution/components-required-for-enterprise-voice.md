---
title: Skype for Business Server でのエンタープライズ Voip に必要なコンポーネント
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Skype for Business Server のエンタープライズボイスコンポーネントの概要。
ms.openlocfilehash: a2e32e2301a404afd06038d438fbb62a13235d65
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803107"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>Skype for Business Server でのエンタープライズ Voip に必要なコンポーネント
 
Skype for Business Server のエンタープライズボイスコンポーネントの概要。
  
エンタープライズ Voip を展開するには、トポロジに次のコンポーネントが必要です。 
  
- 1つまたは複数の仲介サーバー (シグナリングと、一部の構成では、内部の Skype for Business Server、エンタープライズ Voip インフラストラクチャ、公衆交換電話網 (PSTN) ゲートウェイ、またはセッション開始プロトコル間のメディア)(SIP) トランク。 仲介サーバーは、エンタープライズ Voip 展開で最も重要なコンポーネントです。 詳細については、「 [Skype For Business server の仲介サーバーコンポーネント](mediation-server.md)」を参照してください。
    
    仲介サーバーは、フロントエンドサーバーと併置したり、スタンドアロンサーバーとしてインストールしたりすることができます。
    
- SIP トランクまたは PSTN ゲートウェイを含めることができる、PSTN 接続コンポーネント。 詳細については、「 [Skype For Business Server の PSTN 接続コンポーネント](pstn-connectivity.md)」を参照してください。
    
- エッジサーバー: 組織のファイアウォール外にいるユーザーによるエンタープライズ Voip 機能の使用を可能にします。 
    
    アクセスエッジサービスは、組織のファイアウォール外の Skype for Business ユーザーからの通話に対する SIP シグナルを提供します。 音声ビデオ エッジ サービスを使用すると、メディアが NAT およびファイアウォールを通過できます。 企業ファイアウォールの外部で統合コミュニケーション (UC) クライアントを使用する発信者には、個別の通話と電話会議の両方に音声ビデオ エッジ サービスが必要です。
    
    音声ビデオ認証サービスは音声ビデオ エッジ サービスと同じコンピューターに配置され、音声ビデオ エッジ サービスのための認証サービスを実行します。外部のユーザーが音声ビデオ エッジ サービスに接続するには、発信を行う前に、音声ビデオ認証サービスから認証トークンを取得する必要があります。
    
- さらに、一部のエンタープライズボイスコンポーネントはフロントエンドサーバーで実行されます。 これらのコンポーネントの詳細については、「 [Skype For Business Server のフロントエンドサーバー VoIP コンポーネント](front-end-server-voip.md)」を参照してください。
    

