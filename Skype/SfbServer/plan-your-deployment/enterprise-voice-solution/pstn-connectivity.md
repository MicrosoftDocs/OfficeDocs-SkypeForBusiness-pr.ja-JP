---
title: Skype ビジネス サーバーの PSTN 接続のコンポーネント
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
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: ビジネス サーバーの Skype でエンタープライズ VoIP の SIP トランキングと PSTN ゲートウェイについて説明します。
ms.openlocfilehash: 69b010d7f4e444214581ebc1b84babadbf14e68f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20998519"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a>Skype ビジネス サーバーの PSTN 接続のコンポーネント
 
ビジネス サーバーの Skype でエンタープライズ VoIP の SIP トランキングと PSTN ゲートウェイについて説明します。
  
エンタープライズ レベルの VoIP ソリューションでは、サービスの品質 (QoS) を低下させずに公衆交換電話網 (PSTN) との通話の発信および着信を処理する必要があります。 また、通話の発信時および着信時に、基礎となるテクノロジをユーザーが意識しなくても済むようにする必要があります。 ユーザーの観点から、エンタープライズ VoIP インフラストラクチャと PSTN との間の呼び出しする必要がありますように 1 つの SIP セッション。
  
PSTN 接続を行うには、(PBX (直接 SIP リンク) を使用して、または PBX を使用せずに) SIP トランクまたは PSTN ゲートウェイを展開します。
  
## <a name="sip-trunking"></a>SIP トランキング

PSTN ゲートウェイを使用する代わりに、エンタープライズ VoIP ソリューションを PSTN に SIP トランクを使用して接続できます。 SIP トランキングを使用すると、次のようなシナリオが実現します。
  
- 企業のファイアウォールの内側または外側にいるエンタープライズ ユーザーが、E.164 準拠の番号で指定される市内通話や長距離通話を発信できます。この通話は、対応するサービス プロバイダーのサービスとして PSTN 上で終端されます。
    
- PSTN サブスクライバーはだれでも、エンタープライズ ユーザーに関連付けられた Direct Inward Dialing (DID) 番号をダイヤルして、企業のファイアウォールの内側または外側にいるエンタープライズ ユーザーに連絡することができます。
    
この展開ソリューションを使用するには、SIP トランキング サービス プロバイダーが必要です。 
  
## <a name="pstn-gateways"></a>PSTN ゲートウェイ

PSTN ゲートウェイとは、信号に変換するサードパーティ製のデバイスとエンタープライズ VoIP インフラストラクチャと、PSTN または PBX の間でのメディアです。 PSTN ゲートウェイは、PSTN または PBX、エンタープライズ VoIP クライアント呼び出しを表示する仲介サーバーと連携します。 仲介サーバーは、エンタープライズ VoIP クライアントからゲートウェイへの通話、PSTN PSTN または PBX にルーティングするためにも説明します。 ビジネス サーバーの Skype 上で動作するデバイスを提供する Microsoft と協力しているパートナーの一覧は、[マイクロソフトのユニファイド コミュニケーション パートナーの web サイト](https://go.microsoft.com/fwlink/p/?linkId=202836)を参照してください。 
  
## <a name="private-branch-exchanges"></a>構内交換機

 構内交換機 (PBX) を使用する既存の音声インフラストラクチャがある場合は、エンタープライズ VoIP を PBX を使用できます。
  
サポートされているエンタープライズ VoIP を PBX 統合のシナリオは次のとおりです。
  
- メディアをサポートしている IP-PBX は、仲介サーバーをバイパスします。
    
- スタンドアロンの PSTN ゲートウェイが必要な IP-PBX。
    
- 時分割多重 (TDM) PBX とスタンドアロンの PSTN ゲートウェイ。
    
> [!NOTE]
> メディア バイパスは、すべての PSTN ゲートウェイ、IP-PBX、および SBC と相互運用できるとは限りません。 Microsoft は、認定パートナーと共に一連の PSTN ゲートウェイおよび SBC をテストし、Cisco IP-PBX についてもいくつかのテストを完了しています。 メディアのバイパスが製品でのみサポートされているし、バージョンに記載されている[ユニファイド コミュニケーション オープン相互運用性プログラムの Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406)です。 
  
詳細については、エンタープライズ VoIP ソリューションを提供するパートナーは、[マイクロソフトのユニファイド コミュニケーション パートナーの web サイト](https://go.microsoft.com/fwlink/p/?linkId=202836)を参照してください。
  
PSTN ゲートウェイを含め、エンタープライズ VoIP のハードウェア ソリューションを提供するパートナーの詳細については、[マイクロソフトのユニファイド コミュニケーション パートナーの web サイト](https://go.microsoft.com/fwlink/p/?linkId=202836)を参照してください。
  

