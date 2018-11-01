---
title: 'Lync Server 2013: PSTN 接続コンポーネント'
TOCTitle: PSTN 接続コンポーネント
ms:assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398504(v=OCS.15)
ms:contentKeyID: 48272411
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での PSTN 接続コンポーネント

 

_**トピックの最終更新日:** 2016-12-08_

エンタープライズ レベルの VoIP ソリューションでは、サービスの品質 (QoS) を低下させずに公衆交換電話網 (PSTN) との通話の発信および着信を処理する必要があります。また、通話の発信時および着信時に、基礎となるテクノロジをユーザーが意識しなくても済むようにする必要があります。ユーザーからは、エンタープライズ VoIP インフラストラクチャと PSTN 間の通話は、別の SIP セッションのように見えます。

PSTN 接続を行うには、SIP トランクまたは PSTN ゲートウェイを展開します (PBX (直接 SIP リンク) を使用して、または PBX を使用せずに)。

## SIP トランキング

PSTN ゲートウェイを使用する代わりに、SIP トランキングを使用してエンタープライズ VoIP ソリューションを PSTN に接続することもできます。SIP トランキングを使用すると、次のようなシナリオが実現します。

  - 企業のファイアウォールの内側または外側にいるエンタープライズ ユーザーが、E.164 準拠の番号で指定される市内通話や長距離通話を発信できます。この通話は、対応するサービス プロバイダーのサービスとして PSTN 上で終端されます。

  - PSTN サブスクライバーはだれでも、エンタープライズ ユーザーに関連付けられた Direct Inward Dialing (DID) 番号をダイヤルして、企業のファイアウォールの内側または外側にいるエンタープライズ ユーザーに連絡することができます。

この展開ソリューションを使用するには、SIP トランキング サービス プロバイダーが必要です。

## PSTN ゲートウェイ

PSTN ゲートウェイは、エンタープライズ VoIP インフラストラクチャと PSTN または PBX の間の信号とメディアを変換する、サードパーティのデバイスです。PSTN ゲートウェイは、仲介サーバーと連携して、エンタープライズ VoIP クライアントへの PSTN または PBX の通話を処理します。また、仲介サーバーは、PSTN または PBX にルーティングするために、エンタープライズ VoIP クライアントから PSTN ゲートウェイへの通話も処理します。マイクロソフトと連携して Lync Server と連動するデバイスを提供しているパートナーの一覧については、Microsoft 統合コミュニケーション パートナーの Web サイト ( [http://go.microsoft.com/fwlink/?linkid=202836\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=202836%26clcid=0x411)) を参照してください。

## 構内交換機

構内交換機 (PBX) を使用する既存の音声インフラストラクチャがある場合、PBX と Lync Server エンタープライズ VoIP を使用できます。

サポートされているエンタープライズ VoIP と PBX の統合シナリオは、次のとおりです。

  - メディア バイパスをサポートしている IP-PBX と仲介サーバー。

  - スタンドアロンの PSTN ゲートウェイが必要な IP-PBX。

  - 時分割多重 (TDM) PBX とスタンドアロンの PSTN ゲートウェイ。

> [!NOTE]
> メディア バイパスは、すべての PSTN ゲートウェイ、IP-PBX、および SBC と相互運用できるとは限りません。マイクロソフトでは、認定パートナーの PSTN ゲートウェイと SBC でテストを行い、Cisco IP-PBX でも一定のテストを行いました。メディア バイパスは、「Unified Communications Open Interoperability Program - Lync Server (英語)」( <a href="http://go.microsoft.com/fwlink/?linkid=214406%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=214406&amp;clcid=0x411</a>) に記載されている製品とバージョンのみでサポートされます。


エンタープライズ VoIP ソリューションを提供しているパートナーの詳細については、Microsoft 統合コミュニケーション パートナーの Web サイト ( [http://go.microsoft.com/fwlink/?linkid=202836\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=202836%26clcid=0x411)) を参照してください。

PSTN ゲートウェイを含む、エンタープライズ VoIP ハードウェア ソリューションを提供しているパートナーの詳細については、Microsoft 統合コミュニケーション パートナーの Web サイト ( [http://go.microsoft.com/fwlink/?linkid=202836\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=202836%26clcid=0x411)) を参照してください。

