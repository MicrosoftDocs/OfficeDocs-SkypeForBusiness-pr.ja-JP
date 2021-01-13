---
title: Skype for Business Server でのビデオ相互運用サーバーの計画
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- ms.lync.plan.VideoInterop
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: '概要: Skype for Business Server をサードパーティの電話会議デバイスと統合する計画を立てながら、このトピックを確認してください。'
ms.openlocfilehash: c14d92042922f30ca5dd43acce12d11ef50a8683
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831947"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a>Skype for Business Server でのビデオ相互運用サーバーの計画
 
**概要:** Skype for Business Server をサードパーティの電話会議デバイスと統合する計画を立てながら、このトピックを確認してください。
  
Skype for Business Server では、特定のサード パーティ VTC (ビデオ会議システム) ソリューションと統合できます。 このビデオ会議の相互運用性を有効にする新しいサーバーの役割は、ビデオ相互運用サーバー (VIS) です。現在、オンプレミスインストールでのみ使用できるスタンドアロン サーバーの役割として実装されています。 VIS は、サードパーティの電話会議システムと Skype for Business Server 展開の仲介者として機能します。 このリリースでは、VIS は Cisco/Tandberg ビデオ システムとの相互運用性に重点を置いされています。 この記事を確認して、Skype for Business Server インストールでこの機能を使用するかどうかを決定します。
  
## <a name="device-interoperability"></a>デバイスの相互運用性

相互運用は、Cisco Unified Communications Manager (CallManager または CUCM) バージョン 10.5 および CUCM と VIS の間にセットアップされた TCP SIP トランクに登録された Cisco VTC でテストおよびサポートされます。
  
現在サポートされている VTC は次のとおりです。
  
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
>  Skype for Business Server との統合が期待通り動作するには、これらのシステムで Cisco ソフトウェア リリース TC7.0.0 以上が必要です。
  
## <a name="sip-trunks"></a>SIP トランク

ビデオ相互運用サーバーは SIP トランク モードで機能します。このモードでは、VTC は既存の Cisco インフラストラクチャ (Cisco Call Manager (CUCM) など) に引き続き登録されます。 ビデオ SIP トランクは CUCM と VIS の間で定義され、2 つのシステム間で通話をルーティングできます。 VTC から VIS への SIP トランクの呼び出しだけがサポートされます。 したがって、(Call Automated Attendant に関連付けられた電話番号をダイヤルして) SKYPE for Business 会議にダイヤルインできますが、電話会議にドラッグ アンド ドロップすることはできません。
  
![SfB の VIS の図](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a>機能

このサーバーの役割は、次の機能を提供します。
  
- サードパーティ製のビデオ システムで使用される H.264 形式と Skype for Business Server 展開間の変換。
    
- VTC からの特定の解像度での単一のビデオ ストリームを、Skype for Business Server 展開で使用するために異なる解像度の複数のシマルチキャスト ストリームに変換します。 これらのストリームは、AVMCU に送信してから、異なる解像度を要求した Skype for Business Server エンドポイントや他のビデオ システムに送信できます。 この変換は、サード パーティ製のビデオ システムが Skype for Business の A/V 電話会議に参加する場合にも使用されます。 特定の VIS サーバーでコード変換の制限に達すると、次に示すさまざまな解像度の要求は、最も低い解像度のストリームのみを受け取ります。 
    
- CUCM ゲートウェイと Skype for Business Server ビデオ相互運用サーバー間のビデオ SIP トランクのサポートVTC は引き続き Cisco ゲートウェイに登録し、ゲートウェイを介して Skype for Business 展開への通話を開始します。 通話は、ゲートウェイからビデオ SIP トランクを経由して Skype for Business ビデオ相互運用サーバーにルーティングされます。
    
- サポートされているビデオ システムを備えた会議室のユーザーが、そのシステムからダイヤルして、開いている会議または閉じている会議に参加できます。 この呼び出しは、ビデオ SIP トランクをスキャンします。
    
- Skype for Business クライアントを呼び出すビデオ システムがサポートされている会議室内のユーザーのサポート。 呼び出しは SIP トランクを通過します。
    
- 音声のミュート/ミュート解除、ビデオの一時停止/再開、ビデオのロック、通話の保留/保留解除などのポイント間通話とマルチポイント通話の両方について、Skype for Business Server 側またはサポートされている VTC システムからの通話中の制御のサポート。
    
## <a name="known-limitations"></a>既知の制限

このサーバーの役割には、次の制限があります。
  
- Skype for Business 展開からビデオ SIP トランク経由の VTC への新しい通話はサポートされていません。 . つまり、ビデオ SIP トランク経由でサポートされているのは、VTC から Skype for Business 展開への新しい呼び出しのみです。 サポートされているビデオ システムのプレゼンスは、ビデオ SIP トランクを使用して VIS に対して使用できません。 
    
- ビデオ SIP トランク モードでは、スタンドアロンの VIS プールだけがサポートされます。
    
-  ビデオ SIP トランクを使用した VTC と VIS の間の通信では、TLS + SRTP または TCP + RTP がサポートされます。
    
- アプリケーション共有はサポートされていません。 会議室の Skype for Business ユーザーは、Skype for Business 会議に参加し (ノート PC など)、VTC に関連付けされていない会議室のいずれかの無料モニターにアプリ共有画面を表示する必要があります。
    
- VTC が VIS を介してフェデレーション会議に参加する機能はサポートされていません。
    
- VTC が VIS を介してオンライン会議に参加する機能はサポートされていません。
    
- VTC から VIS 経由の PSTN への通話はサポートされていません。
    
- PSTN から VIS 経由の VTC への通話はサポートされていません。
    
## <a name="resiliency-mechanisms"></a>復元メカニズム
<a name="resiliency"> </a>

VIS は、ビデオ SIP トランクを引き継ぐ CUCM からの着信呼び出しをサポートします。 アップストリームまたはダウンストリームのどちらかの接続を失う可能性があります。したがって、堅牢な回復性を得る上で、次の両方の可能性を考慮してください。
  
1. **VIS プールフェールオーバー** ビデオ ゲートウェイがポイントするメイン VIS プールがダウンしている場合、ビデオ ゲートウェイが 2 つ以上の VIS プールにトランクを定義している場合、回復が可能です。 ビデオ ゲートウェイがプライマリ VIS プールに通話できないと判断した場合は、単に通話をセカンダリ VIS プールにルーティングします。
    
     ![VIS プールのフェールオーバーの図](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    特定の VIS プールは複数のゲートウェイへのトランクを持つ場合がありますが、通常、特定のゲートウェイは複数の VIS プールへのトランクを持てないので、このフェールオーバーをサポートするには、2 つの FDQN を DNS で定義する必要があります。これは、ビデオ ゲートウェイの同じ IP アドレスに解決されます。 各ビデオ ゲートウェイが異なる VIS プールへのトランクを持ち、回復が可能なトポロジ ドキュメントで、各 FQDN を個別のビデオ ゲートウェイとして表します。 (TLS を使用する場合は、複数の名前がビデオ ゲートウェイ証明書の SAN にある必要があります)。
    
    > [!NOTE]
    > VIS では、トポロジ ドキュメントで構成されたゲートウェイからの着信のみを許可します。 
  
2. **フロントエンドフェールオーバー** VIS プールが CUCM から通話を受信したが、プライマリの次ホップ レジストラーまたはフロントエンド プールに到達できない場合、通話はバックアップ フロントエンド プールにルーティングされます。
    
     ![フロントエンド フェールオーバーの図](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    VIS は、プライマリ フロントエンド プールとそのバックアップ フロントエンド プールの状態を追跡します (この設定は、トポロジ ドキュメントのレジストラー サービスのバックアップ設定にあります)。 オプション ポーリングは、1 分に 1 回、両方のプールに送信され、連続して 5 回エラーが発生した場合、VIS は特定のフロントエンド プールがダウンしたと見なします。 プライマリ フロントエンド プールがダウンとしてマークされ、利用可能な構成済みのバックアップがある場合、VIS はゲートウェイからバックアップ フロントエンド プールに新しい呼び出しを送信します。 プライマリ フロントエンド プールが戻ると、VIS はプライマリ フロントエンド プールを使用して新しい通話を再開します。
    
    VIS は、ビデオ SIP トランクからの呼び出しに 10 秒のタイマーも実装します。 プライマリ次ホップ フロント エンド プールがビデオ SIP トランクからの通話に使用され、プライマリ次ホップ フロント エンド プールが、このタイマー値内で送信された招待に対する一部の SIP メッセージ (100 を含む) で応答しなかった場合は、通話のバックアップの次ホップ プロキシが構成されている場合に試みる必要があります。 
    
    > [!NOTE]
    > バックアップの次ホップが最初に試みらた場合、プライマリは次に試みらなされます。 
  
    管理者は、プライマリ フロントエンド プールでメンテナンスを実行する必要がある場合など、Windows PowerShell フェールオーバー コマンドを使用して VIS にバックアップ フロントエンド プールを強制的に使用することもできます。
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a>同じゲートウェイ ピアへの音声トランクとビデオ トランクの同時使用
<a name="resiliency"> </a>

Skype for Business Server では、音声とビデオの SIP トランクで同じゲートウェイ ピアを使用できます。 したがって、同じ CUCM 展開で、仲介サーバーへの音声 SIP トランクと VIS へのビデオ SIP トランクを使用できます。
  
- PSTN ゲートウェイは、音声 SIP トランクのトポロジ ドキュメントで特定の FQDN で定義する必要があります。
    
- PSTN ゲートウェイへのピアが仲介サーバーになります。
    
- 必要に応じて、PSTN ゲートウェイから複数の仲介サーバー プールに及ぶ複数の音声トランクを定義できます。
    
- ビデオ ゲートウェイは、PSTN ゲートウェイと同じ FQDN を持つビデオ SIP トランクのトポロジ ドキュメントで定義する必要があります。
    
- ビデオ ゲートウェイへのピアは VIS です。
    
- 1 つのビデオ トランクをビデオ ゲートウェイから特定の VIS プールに定義できます。
    
- CUCM は、音声トランクとビデオ トランクを正しくルーティングするように構成する必要があります。 たとえば、VTC からダイヤルするときに特殊なダイヤル プレフィックスを使用できます。CUCM は、このダイヤル プレフィックスを VIS への呼び出しに関連付け、適切な変換ルールによってこのプレフィックスが VIS への SIP 招待から削除されます。
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a>Skype for Business リリースでの VIS と Lync の以前のリリースとの関連付け
<a name="resiliency"> </a>

VIS は、Skype for Business 展開の一部としてのみ展開できます。 既存の展開の一部である Lync 2013 会議およびクライアントと相互運用できます。このような場合、VIS プールは、VIS プールの次ホップであるレジストラー/FE プールを含む Skype for Business 展開の一部である必要があります。
  
VIS では、RTV と H.264 の間のコード変換はサポートされていません。 会議に参加する Lync 2013 より前のクライアントと VTC 参加者の間には、ビデオの相互運用性はありません。
  
会議に Lync 2013 より前のクライアントがある場合、モバイル クライアントは RTV を使用して送信し、その結果、モバイル クライアントが優先スピーカーになると、ビデオを受信しません。
  
Lync 2013 が Skype for Business 展開の一部である VIS と正しく動作するには、Lync 2013 が VIS と動作するように Lync 2013 クライアント、CAA、および AVMCU をアップグレードする適切な CU を適用する必要があります。
  
VIS と Lync 2013 および Skype for Business デスクトップ クライアントとの相互運用性はテスト済みで、サポートされています。
  
VIS とデスクトップ以外との相互運用性 (Android、Ipad、Iphone、Windows Phone、LMX など)VIS リリース時に該当するアプリ ストアから利用できる Skype for Business クライアントはテスト済みで、サポートされています。
  
## <a name="recovery-from-packet-loss-via-fec"></a>FEC によるパケット損失からの回復
<a name="resiliency"> </a>

FEC をオンにすると、パケット損失からの回復を支援できます。 オンにすると、VIS から VTC 方向に 50% 多くのビデオ帯域幅が使用されます。
  
## <a name="vis-sizing-and-transcoding-costs"></a>VIS のサイズ変更とコード変換のコスト
<a name="resiliency"> </a>

Cisco VTC から複数のサイマルチ キャスト ストリームへの単一のビデオ ストリームのコード変換では、CPU 容量が使用されます。 Lync 2013 の推奨 FE プラットフォームと同等の動作をしている単一の VIS で、約 16 台の VTC でビデオをコード変換できます (各 VTC からの 720p ビデオ ストリームが 720p、360p、180p の 3 つの別々のサイプルキャスト ストリームにコード変換されている場合)。 コード変換をオフにすると、VIS CPU が節約されます。 ただし、VTC から VIS によって要求されたビデオ 画像は、Skype for Business 側のすべての受信者を満たすために最も低い共通解像度になります。 コード変換をオフにした場合でも、Skype for Business クライアントが、VTC が送信できない低解像度を要求すると、コード変換がアクティブ化される可能性があります。
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a>ビデオ ゲートウェイから VIS への通話の配布
<a name="resiliency"> </a>

配信は、CUCM 配布メカニズムのいずれかを使用して行います。
  
- DNS を動的に使用します。
    
- CUCM 側では、VIS プール内の異なるサーバーで各トランクが終了する個々のトランクを定義できます。 CUCM は、異なるトランク間で通話をルーティングします。
    
## <a name="no-hybrid-interoperability"></a>ハイブリッド相互運用性なし
<a name="resiliency"> </a>

オンプレミス VIS を介してオンライン会議に参加する VTC のサポートは、Skype for Business の一部ではありません。
  
## <a name="no-federation-support"></a>フェデレーションのサポートなし
<a name="resiliency"> </a>

VIS を介してフェデレーション会議に参加する VTC のサポートは、Skype for Business の一部ではありません。
  
## <a name="see-also"></a>関連項目
<a name="resiliency"> </a>

[Skype for Business Server でのビデオ相互運用サーバーの展開](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
