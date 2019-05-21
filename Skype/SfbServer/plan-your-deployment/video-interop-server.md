---
title: Skype for Business Server のビデオ相互運用機能サーバーを計画する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.VideoInterop
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: '概要: Skype for Business Server とサードパーティのテレビ会議デバイスとの統合を計画しているときに、このトピックを確認してください。'
ms.openlocfilehash: 24220a0013e12d65759baed33b8966b5c83a78f3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296771"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a>Skype for Business Server のビデオ相互運用機能サーバーを計画する
 
**概要:** このトピックでは、Skype for Business Server とサードパーティのテレビ会議デバイスとの統合を計画しています。
  
Skype for Business Server で、特定のサードパーティの VTC (ビデオ会議システム) ソリューションと統合できるようになりました。 このビデオ会議の相互運用性を実現する新しいサーバーの役割は、ビデオ相互運用機能サーバー (VIS) です。現在、オンプレミスのインストールでのみ利用可能なスタンドアロンサーバーの役割として実装されています。 VIS は、サードパーティの電話会議システムと Skype for Business Server の展開の間の媒介として機能します。 このリリースでは、VIS は Cisco/Tandberg ビデオ システムとの相互運用性に焦点を合わせています。 Skype for Business Server のインストールでこの機能を使用するかどうかを確認するには、この記事を参照してください。
  
## <a name="device-interoperability"></a>デバイスの相互運用性

相互運用は、cisco のユニファイドコミュニケーションマネージャー (CallManager、または CUCM) バージョン10.5 と、CUCM と VIS の間に設定された TCP SIP trunks を使った、Cisco VTCs でのテストとサポートを行います。
  
現在サポートされている VTC:
  
- Cisco C40
    
- Cisco C60
    
- Cisco C90
    
- Cisco MX200
    
- Cisco MX300
    
- Cisco DX80
    
- Cisco EX60
    
- Cisco EX90
    
- Cisco SX20
    
> [!NOTE]
>  Skype for Business Server との統合には、Cisco software release TC 7.0.0 以上が必要です。
  
## <a name="sip-trunks"></a>SIP トランク

SIP トランクモードでは、VTCs は既存の Cisco インフラストラクチャに登録されているので、「Cisco Call Manager (CUCM)」などのビデオ相互運用機能サーバーが機能します。 ビデオ SIP トランクは、CUCM と VIS 間に定義されるので、2 つのシステム間で通話をルーティングできます。 VTC から VIS への SIP トランク上の通話のみがサポートされます。 したがって、VTCs は、Skype for Business 会議にダイヤルインすることができます (通話自動応答に関連付けられた電話番号にダイヤルするため)。会議にドラッグアンドドロップすることはできません。
  
![SfB の VIS の図](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a>機能

このサーバーの役割の機能:
  
- サードパーティのビデオシステムと Skype for Business Server の展開で使用される .H 形式間の変換。
    
- 特定の解像度の1つのビデオストリームを VTC から複数の simulcast ストリームに変換することで、Skype for Business Server の展開で使用するさまざまな解像度を使用できます。 これらのストリームは、AVMCU に送信した後、Skype for Business Server のエンドポイント、および別の解像度を要求したその他のビデオシステムに送ることができます。 この変換は、サードパーティのビデオシステムが Skype for Business A/V 会議通話に関与している場合にも使用されます。 特定の VIS サーバーでトランスコードの制限に達すると、次のようなさまざまな解像度の要求では、最も低い解像度のストリームしか受信できなくなります。 
    
- CUCM gateway と Skype for Business Server ビデオ相互運用サーバーとの間のビデオ SIP トランクのサポートVTCs は引き続き Cisco ゲートウェイに登録され、ゲートウェイ経由で Skype for Business 展開への通話が開始されます。 通話は、ビデオ SIP トランクを介してゲートウェイから Skype for Business ビデオ相互運用サーバーにルーティングされます。
    
- サポートされているビデオ システムがある会議室のユーザーは、そのシステムからダイヤルして、公開または非公開の会議に参加できます。 この通話は、ビデオ SIP トランクを通過します。
    
- サポートされているビデオシステムで Skype for Business クライアントを呼び出す、会議室内のユーザーをサポートします。 この通話は、SIP トランクを通過します。
    
- Skype for Business Server 側またはサポートされている VTC システムで、音声のミュート/ミュート解除、ビデオの一時停止、再開、ビデオのロック、通話の保留/保留の切り替えを含む、中間通話コントロールをサポートします。
    
## <a name="known-limitations"></a>既知の制限

このサーバーの役割には、次の制限があります。
  
- Skype for Business の展開から VTCs への新規通話は、ビデオ SIP トランクを介してはサポートされていません。 . これは、ビデオ SIP トランクを介して、VTCs から Skype for Business の展開への新しい通話のみがサポートされることを意味します。 サポートされているビデオシステムのプレゼンスは、VIS へのビデオ SIP トランク経由では利用できません。 
    
- ビデオ SIP トランク モードでは、スタンドアロン VIS プールのみがサポートされます。
    
-  ビデオ SIP トランク上の VTC と VIS 間の通信では、TLS + SRTP または TCP + RTP がサポートされます。
    
- アプリケーション共有はサポートされていません。 会議室の Skype for Business ユーザーは、Skype for Business 会議 (たとえば、ノート pc 経由) に参加し、VTC に関連付けられていない会議室のいずれかの無料モニターでアプリ共有画面を表示する必要があります。
    
- VTC から、VIS を介してフェデレーション会議に参加することはできません。
    
- VTC から、VIS を介してオンライン会議に参加することはできません。
    
- VTC から、VIS を介して PSTN に発信することはできません。
    
- PSTN から、VIS を介して VTC に発信することはできません。
    
## <a name="resiliency-mechanisms"></a>復元のメカニズム
<a name="resiliency"> </a>

VIS は、ビデオ SIP トランク上で実行された CUCM からの着信をサポートしています。 アップストリームまたはダウンストリームの接続が切断される可能性があるので、確実な復元のために、次の両方の可能性を考慮してください。
  
1. **VIS プールのフェールオーバー**ビデオゲートウェイが指しているメインの VIS プールがダウンしている場合は、2つ (以上) の VIS プールへの trunks がビデオゲートウェイで定義されていると、回復が可能になります。 ビデオゲートウェイによってプライマリ VIS プールへの通話を発信できないと判断された場合は、単に着信をセカンダリ VIS プールにルーティングします。
    
     ![VIS プール フェールオーバーの図](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    特定の VIS プールには複数のゲートウェイを指定できますが、通常、特定のゲートウェイには複数の VIS プールを設定することはできません。そのため、このフェールオーバーをサポートするには、2 FDQNs を DNS で定義し、ビデオゲートウェイと同じ IP アドレスに解決する必要があります。 各各ビデオゲートウェイが別の VIS プールにトランクを持っていて、回復が可能になったトポロジドキュメントで、各 FQDN を個別のビデオゲートウェイとして表します。 (TLS が使用されている場合は、複数の名前がビデオゲートウェイ証明書の SAN に存在する必要があります)。
    
    > [!NOTE]
    > VIS は、トポロジ ドキュメントに構成されているゲートウェイからの着信のみを受けることができます。 
  
2. **フロントエンドフェールオーバー**VIS プールが CUCM から通話を受信したが、プライマリ next-hop レジストラーまたはフロントエンドプールにアクセスできない場合、通話はバックアップフロントエンドプールにルーティングされます。
    
     ![フロント エンド フェールオーバーの図](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    VIS は、プライマリフロントエンドプールとバックアップフロントエンドプールの状態を追跡します (設定は、トポロジドキュメントのレジストラーサービスのバックアップ設定にあります)。 オプションのポーリングは両方のプールに1分間隔で送信され、5回連続して失敗すると、VIS は特定のフロントエンドプールがダウンしていることを前提とします。 プライマリフロントエンドプールがダウンとマークされていて、使用可能な構成済みのバックアップがある場合、VIS は新しい通話をゲートウェイからバックアップフロントエンドプールに送信します。 プライマリフロントエンドプールが再び表示されると、VIS は、新しい通話に対して、プライマリフロントエンドプールの使用を再開します。
    
    VIS は、ビデオ SIP トランクからの通話に 10 秒間のタイマーも実装します。 プライマリ next-hop フロントエンドプールがビデオ SIP トランクからの通話に使用されていて、プライマリ next-hop フロントエンドプールが、一部の SIP メッセージ (100 試行を含む) に対して、このタイマー値で送信された招待状に応答しなかった場合は、その通話の次ホッププロキシをバックアップします。構成されている場合は、この設定を試してみてください。 
    
    > [!NOTE]
    > 最初にバックアップ次ホップが試行された場合、次にプライマリは試行されません。 
  
    管理者は、Windows PowerShell フェールオーバー コマンドを使用して、たとえば、プライマリ フロント エンド プールを保守する必要がある場合などに、VIS がバックアップ フロント エンド プールを使用するように強制することもできます。
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a>同じゲートウェイ ピアに対する音声およびビデオ トランクの共存
<a name="resiliency"> </a>

Skype for Business Server では、音声とビデオの SIP trunks で同じゲートウェイピアを使用できます。 そのため、同じ CUCM の展開で、仲介サーバーに対する音声 SIP トランクと、VIS に対するビデオ SIP トランクを使用することができます。
  
- 音声 SIP トランクのトポロジ ドキュメントで、特定の FQDN を指定した PSTN ゲートウェイを定義する必要があります。
    
- PSTN ゲートウェイに対するピアは、仲介サーバーになります。
    
- 必要に応じて、1 つの PSTN ゲートウェイから複数の仲介サーバー プールまで、複数の音声トランクを定義できます。
    
- PSTN ゲートウェイの場合、FQDN が同じビデオ SIP トランクのトポロジ ドキュメントで、ビデオ ゲートウェイを定義する必要があります。
    
- ビデオ ゲートウェイに対するピアは VIS になります。
    
- ビデオ ゲートウェイから特定の VIS プールに対して、1 つのビデオ トランクを定義できます。
    
- CUCM は、音声トランクとビデオトランクの間で通話を正しくルーティングするように構成されている必要があります。 たとえば、VTC からダイヤルするときに特別なダイヤルプレフィックスを使うことができます。CUCM はこのダイヤルプレフィックスを VIS への通話に関連付けることができます。また、適切な翻訳ルールにより、このプレフィックスは SIP 招待状から VIS に除去されます。
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a>Skype for Business リリースの VIS と以前のリリースの Lync との共存
<a name="resiliency"> </a>

VIS は、Skype for Business 展開の一部としてのみ展開できます。 Lync 2013 会議と、既存の展開に含まれているクライアントと相互運用することができます。このような場合、VIS pool は、VIS プールの次ホップであるレジストラー/FE プールを含む Skype for Business 展開の一部である必要があります。
  
VIS は、RTV と H.264 間のトランスコーディングをサポートしていません。 会議に参加する Lync 2013 より前のクライアントと VTC 間にビデオの相互運用性はありません。
  
会議に Lync 2013 より前のクライアントが参加する場合、モバイル クライアントが主発言者になると、モバイル クライアントは RTV を使用して送信するので、結果として VTC はビデオを受信しません。
  
Lync 2013 が、Skype for Business の展開に含まれる VIS と正しく連携するには、Lync 2013 は、VIS と連携できるように Lync 2013 クライアント、CAA、および AVMCU をアップグレードできる適切な CU を適用する必要があります。
  
VIS と、Lync 2013 および Skype for Business デスクトップ クライアント間の相互運用性はテスト済みで、サポートされています。
  
デスクトップ以外の VIS (Android、Ipad、Iphone、Windows Phone、LMX など) との相互運用性VIS release の時点で該当するアプリストアから利用できる Skype for Business クライアントは、テストが完了し、サポートされています。
  
## <a name="recovery-from-packet-loss-via-fec"></a>FEC を介したパケット損失からの復元
<a name="resiliency"> </a>

FEC を有効にすると、パケット損失からの復元を補助することができます。 有効にすると、50% 以上のビデオ帯域幅が VIS から VTC の方向に使用されます。
  
## <a name="vis-sizing-and-transcoding-costs"></a>VIS のサイズ設定とトランスコーディングのコスト
<a name="resiliency"> </a>

Cisco VTC からの 1 つのビデオ ストリームを複数のサイマルキャスト ストリームに変換する処理には、CPU 能力を使います。 約16の VTCs はビデオコードトランスコードを持つことができます (各 VTC からの720p のビデオストリームは、2013で使用されている simulcast の1つの VIS で、2つの別々のストリームにトランスコードされていることを前提としています)。 トランスコーディングを無効にすると、VIS の CPU が節約されます。 ただし、VIS が要求して VTC から送信されるビデオ画像は、Skype for Business 側のすべての受信者を満たす最小限の共通解像度になります。 トランスコーディングを無効にしたとしても、VTC が送信できない低解像度を Skype for Business クライアントが要求した場合、トランスコーディングが有効になることがあります。
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a>ビデオ ゲートウェイから VIS への通話配信
<a name="resiliency"> </a>

配信は、CUCM 配信メカニズムのいずれかを使用して実行されます。
  
- DNS を使用した動的配信。
    
- CUCM side では、各トランクを VIS プールの異なるサーバー上で終了する個々の trunks を定義できます。 CUCM は、異なる trunks 間で通話をルーティングします。
    
## <a name="no-hybrid-interoperability"></a>ハイブリッドの相互運用性はサポート対象外
<a name="resiliency"> </a>

オンプレミス型 VIS を介してオンライン会議に参加する VTC は、Skype for Business のサポート対象外です。
  
## <a name="no-federation-support"></a>フェデレーションはサポート対象外
<a name="resiliency"> </a>

VIS を介してフェデレーション会議に参加する VTC は、Skype for Business のサポート対象外です。
  
## <a name="see-also"></a>関連項目
<a name="resiliency"> </a>

[Skype for Business Server でビデオ相互運用機能サーバーを展開する](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
