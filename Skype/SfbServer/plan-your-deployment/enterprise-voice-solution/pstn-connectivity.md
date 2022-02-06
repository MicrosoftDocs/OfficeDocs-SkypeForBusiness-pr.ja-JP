---
title: PSTN 接続コンポーネント (Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
ms.custom: null
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: SIP トランキングと PSTN ゲートウェイの詳細については、エンタープライズ VoIPのSkype for Business Server。
---

# <a name="pstn-connectivity-components-in-skype-for-business-server"></a>PSTN 接続コンポーネント (Skype for Business Server
 
SIP トランキングと PSTN ゲートウェイの詳細については、エンタープライズ VoIPのSkype for Business Server。
  
エンタープライズ レベルの VoIP ソリューションでは、サービスの品質 (QoS) を低下させずに公衆交換電話網 (PSTN) との通話の発信および着信を処理する必要があります。また、通話の発信時および着信時に、基礎となるテクノロジをユーザーが意識しなくても済むようにする必要があります。ユーザーからは、エンタープライズ VoIP インフラストラクチャと PSTN 間の通話は、別の SIP セッションのように見えます。
  
PSTN 接続の場合は、SIP トランクまたは PSTN ゲートウェイ (PBX (ダイレクト SIP リンクとも呼ばれる) を展開するか、PBX を使用せずに展開できます。
  
## <a name="sip-trunking"></a>SIP トランキング

PSTN ゲートウェイを使用する代わりに、SIP トランキングを使用してエンタープライズ VoIP ソリューションを PSTN に接続することもできます。 SIP トランキングを使用すると、次のようなシナリオが実現します。
  
- 企業のファイアウォールの内側または外側にいるエンタープライズ ユーザーが、E.164 準拠の番号で指定される市内通話や長距離通話を発信できます。この通話は、対応するサービス プロバイダーのサービスとして PSTN 上で終端されます。
    
- PSTN サブスクライバーはだれでも、エンタープライズ ユーザーに関連付けられた Direct Inward Dialing (DID) 番号をダイヤルして、企業のファイアウォールの内側または外側にいるエンタープライズ ユーザーに連絡することができます。
    
この展開ソリューションを使用するには、SIP トランキング サービス プロバイダーが必要です。 
  
## <a name="pstn-gateways"></a>PSTN ゲートウェイ

PSTN ゲートウェイは、エンタープライズ VoIP インフラストラクチャと PSTN または PBX の間の信号とメディアを変換する、サードパーティのデバイスです。 PSTN ゲートウェイは、仲介サーバーと連携して、エンタープライズ VoIP クライアントへの PSTN または PBX の通話を処理します。 また、仲介サーバーは、PSTN または PBX にルーティングするために、エンタープライズ VoIP クライアントから PSTN ゲートウェイへの通話も処理します。 Microsoft と連携してデバイスを提供するパートナーの一覧については、「Microsoft [Unified Communications Partners web](https://go.microsoft.com/fwlink/p/?linkId=202836) サイト」を参照Skype for Business Serverを参照してください。 
  
## <a name="private-branch-exchanges"></a>構内交換機

 プライベート ブランチ 交換 (PBX) を使用する既存の音声インフラストラクチャがある場合は、PBX を使用して、既存の音声インフラストラクチャを使用エンタープライズ VoIP。
  
サポートされているエンタープライズ VoIP と PBX の統合シナリオは、次のとおりです。
  
- メディア バイパスをサポートしている IP-PBX と仲介サーバー。
    
- スタンドアロンの PSTN ゲートウェイが必要な IP-PBX。
    
- 時分割多重 (TDM) PBX とスタンドアロンの PSTN ゲートウェイ。
    
> [!NOTE]
> メディア バイパスは、すべての PSTN ゲートウェイ、IP-PBX、および SBC と相互運用できるとは限りません。 Microsoft は、認定パートナーと一緒に一連の PSTN ゲートウェイと SBC をテストし、Cisco IP-PBX でいくつかのテストを行いました。 メディア バイパスは、「 [Unified Communications Open Interoperability Program - Lync Server](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)」に記載されている製品とバージョンでのみサポートされます。 
  
ソリューションを提供するパートナーのエンタープライズ VoIPについては、「[Microsoft Unified Communications Partners web サイト」を参照してください](https://go.microsoft.com/fwlink/p/?linkId=202836)。
  
PSTN ゲートウェイを含むハードウェア エンタープライズ VoIP提供するパートナーの詳細については、「[Microsoft Unified Communications Partners web サイト」を参照してください](https://go.microsoft.com/fwlink/p/?linkId=202836)。
