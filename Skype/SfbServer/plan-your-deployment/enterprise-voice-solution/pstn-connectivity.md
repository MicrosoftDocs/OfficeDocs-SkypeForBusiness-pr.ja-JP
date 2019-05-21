---
title: Skype for Business Server の PSTN 接続コンポーネント
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: Skype for Business Server でのエンタープライズ Voip の SIP トランクと PSTN ゲートウェイについて説明します。
ms.openlocfilehash: 6d11ea3204c9b924c9e700194ee04beb9a0df56c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276484"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a>Skype for Business Server の PSTN 接続コンポーネント
 
Skype for Business Server でのエンタープライズ Voip の SIP トランクと PSTN ゲートウェイについて説明します。
  
エンタープライズ レベルの VoIP ソリューションでは、サービスの品質 (QoS) を低下させずに公衆交換電話網 (PSTN) との通話の発信および着信を処理する必要があります。 また、通話の発信時および着信時に、基礎となるテクノロジをユーザーが意識しなくても済むようにする必要があります。 ユーザーから見れば、エンタープライズボイスインフラストラクチャと PSTN 間の通話は、別の SIP セッションと同じように見えます。
  
PSTN 接続を行うには、(PBX (直接 SIP リンク) を使用して、または PBX を使用せずに) SIP トランクまたは PSTN ゲートウェイを展開します。
  
## <a name="sip-trunking"></a>SIP トランキング

PSTN ゲートウェイを使用する代わりに、SIP トランキングを使用してエンタープライズ Voip ソリューションを PSTN に接続することもできます。 SIP トランキングを使用すると、次のようなシナリオが実現します。
  
- 企業のファイアウォールの内側または外側にいるエンタープライズ ユーザーが、E.164 準拠の番号で指定される市内通話や長距離通話を発信できます。この通話は、対応するサービス プロバイダーのサービスとして PSTN 上で終端されます。
    
- PSTN サブスクライバーはだれでも、エンタープライズ ユーザーに関連付けられた Direct Inward Dialing (DID) 番号をダイヤルして、企業のファイアウォールの内側または外側にいるエンタープライズ ユーザーに連絡することができます。
    
この展開ソリューションを使用するには、SIP トランキング サービス プロバイダーが必要です。 
  
## <a name="pstn-gateways"></a>PSTN ゲートウェイ

PSTN ゲートウェイは、エンタープライズボイスインフラストラクチャと PSTN または PBX 間のシグナリングおよびメディアを変換するサードパーティ製のデバイスです。 PSTN ゲートウェイは、仲介サーバーと連携して、エンタープライズボイスクライアントに PSTN または PBX 通話を提供します。 また、仲介サーバーは、PSTN または PBX にルーティングするために、エンタープライズボイスクライアントから PSTN ゲートウェイへの通話を提供します。 Microsoft と連携して Skype for Business Server で動作するデバイスを提供しているパートナーのリストについては、 [Microsoft ユニファイドコミュニケーションパートナーの web サイト](https://go.microsoft.com/fwlink/p/?linkId=202836)を参照してください。 
  
## <a name="private-branch-exchanges"></a>構内交換機

 構内交換会社 (PBX) を使用する既存の音声インフラストラクチャを使用している場合は、PBX をエンタープライズ Voip として使用できます。
  
サポートされているエンタープライズ Voip 統合シナリオは、次のとおりです。
  
- 仲介サーバーでメディアバイパスをサポートする IP PBX。
    
- スタンドアロンの PSTN ゲートウェイが必要な IP-PBX。
    
- 時分割多重 (TDM) PBX とスタンドアロンの PSTN ゲートウェイ。
    
> [!NOTE]
> メディア バイパスは、すべての PSTN ゲートウェイ、IP-PBX、および SBC と相互運用できるとは限りません。 マイクロソフトでは、認定パートナーの PSTN ゲートウェイと SBC でテストを行い、Cisco IP-PBX でも一定のテストを行いました。 メディアのバイパスは、統合された通信の[オープンな相互運用性プログラム-Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406)での製品とバージョンでのみサポートされます。 
  
エンタープライズ Voip ソリューションを提供しているパートナーの詳細については、 [Microsoft ユニファイドコミュニケーションパートナーの web サイト](https://go.microsoft.com/fwlink/p/?linkId=202836)を参照してください。
  
PSTN ゲートウェイなど、エンタープライズボイスハードウェアソリューションを提供しているパートナーの詳細については、 [Microsoft ユニファイドコミュニケーションパートナーの web サイト](https://go.microsoft.com/fwlink/p/?linkId=202836)を参照してください。
  

