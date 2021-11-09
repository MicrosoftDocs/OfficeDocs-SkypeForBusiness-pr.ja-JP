---
title: ビデオ相互運用サーバーの計画をSkype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- ms.lync.plan.VideoInterop
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: '概要: サード パーティ製の電話会議デバイスにSkype for Business Serverを計画する場合は、このトピックを確認してください。'
ms.openlocfilehash: b928e432b464e6bf1a5ccb8748ebf75ef8cc596b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862064"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a>ビデオ相互運用サーバーの計画をSkype for Business Server
 
**概要:** サード パーティ製の電話会議Skype for Business Server統合する計画を立てながら、このトピックを確認してください。
  
Skype for Business Server、特定のサードパーティ VTC (ビデオ電話会議システム) ソリューションと統合できます。 このビデオ会議の相互運用性を有効にする新しいサーバーの役割は、ビデオ相互運用サーバー (VIS) です。これは現在、オンプレミスインストールでのみ使用可能なスタンドアロン サーバーの役割として実装されています。 VIS は、サード パーティ製の電話会議システムと、第三者の電話会議システムとの間の仲介Skype for Business Serverします。 このリリースでは、VIS は、Cisco/Tandberg ビデオ システムとの相互運用性に重点を置いされています。 この記事を参照して、この機能をインストール環境で使用Skype for Business Serverしてください。
  
## <a name="device-interoperability"></a>デバイスの相互運用性

相互運用は、Cisco Unified Communications Manager (CallManager または CUCM) バージョン 10.5 および CUCM と VIS の間でセットアップされた TCP SIP トランクに登録される Cisco VTC でテストおよびサポートされます。
  
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
>  Cisco ソフトウェア リリース TC7.0.0 以上は、これらのシステムで、予期したSkype for Business Server機能するために必要です。
  
## <a name="sip-trunks"></a>SIP トランク

ビデオ相互運用サーバーは SIP トランク モードで機能し、VTC は既存のシスコ インフラストラクチャ (たとえば、Cisco Call Manager (CUCM) に登録し続けます。 ビデオ SIP トランクは CUCM と VIS の間で定義され、2 つのシステム間で通話をルーティングできます。 VTC から VIS への SIP トランク上の呼び出しだけがサポートされます。 したがって、VTC は Skype for Business 会議にダイヤルインできます (自動応答の呼び出しに関連付けられた電話番号をダイヤルします)、電話会議にドラッグ アンド ドロップすることはできません。
  
![SfB の VIS の図。](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a>機能

このサーバーの役割は、次の機能を提供します。
  
- サードパーティのビデオ システムで使用される H.264 形式と、その展開Skype for Business Server変換します。
    
- VTC から特定の解像度で 1 つのビデオ ストリームを、さまざまな解像度の複数の simulcast ストリームに変換し、Skype for Business Serverします。 これらのストリームは、AVMCU に送信してから、異なる解像度を要求Skype for Business Server他のビデオ システムに送信できます。 この変換は、サードパーティのビデオ システムがビデオ通話に関連する場合にもSkype for Business使用されます。 特定の VIS サーバーでトランスコード制限に達すると、さまざまな解像度に対する次の要求は、最も低い解像度のストリームのみを受信します。 
    
- CUCM ゲートウェイとビデオ相互運用サーバー間のビデオ SIP トランクSkype for Business Serverサポート。VTC は引き続き Cisco ゲートウェイに登録し、ゲートウェイを通Skype for Business展開への呼び出しを開始します。 通話は、ゲートウェイからビデオ SIP トランクをSkype for Businessビデオ相互運用サーバーにルーティングされます。
    
- サポートされているビデオ システムを備えた会議室のユーザーが、開いている会議または閉じている会議に参加するために、そのシステムからダイヤルするサポート。 この呼び出しはビデオ SIP トランクを通過します。
    
- サポートされているビデオ システムを使用して会議室内のユーザーがクライアントに電話をSkype for Businessします。 通話は SIP トランクを通過します。
    
- Skype for Business Server 側またはサポートされている VTC システムからの通話中通話制御をサポートし、ミュート/ミュート解除オーディオ、一時停止/再開ビデオ、ビデオのロック、保留/保留通話などのポイント間通話とマルチポイント通話の両方をサポートします。
    
## <a name="known-limitations"></a>既知の制限

このサーバーの役割には、次の制限があります。
  
- ビデオ SIP トランクをSkype for Business展開から VTC への新しい呼び出しはサポートされていません。 . つまり、ビデオ SIP トランクを使用してサポートされているのは、VTC から Skype for Business展開への新しい呼び出しのみです。 サポートされているビデオ システムのプレゼンスは、ビデオ SIP トランクから VIS に対して使用できません。 
    
- ビデオ SIP トランク モードでは、スタンドアロン VIS プールだけがサポートされます。
    
-  ビデオ SIP トランクを使用した VTC と VIS の間の通信では、TLS + SRTP または TCP + RTP がサポートされます。
    
- アプリケーション共有はサポートされていません。 会議室の Skype for Business ユーザーは、Skype for Business 会議に参加し (たとえば、ラップトップ経由)、VTC に関連付けされていない会議室の無料モニターの 1 つでアプリ共有画面を表示する必要があります。
    
- VTC が VIS を介してフェデレーション会議に参加する機能はサポートされていません。
    
- VTC が VIS を介してオンライン会議に参加する機能はサポートされていません。
    
- VTC から VIS 経由の PSTN への呼び出しはサポートされていません。
    
- PSTN から VIS 経由の VTC への呼び出しはサポートされていません。
    
## <a name="resiliency-mechanisms"></a>復元メカニズム
<a name="resiliency"> </a>

VIS は、ビデオ SIP トランクで引き継がれた CUCM からの着信呼び出しをサポートします。 アップストリームまたはダウンストリームのどちらかで接続が失われる可能性があります。そのため、堅牢な復元のためには、次の両方の可能性を検討してください。
  
1. **VIS プールのフェールオーバー** ビデオ ゲートウェイがポイントするメイン VIS プールがダウンしている場合、ビデオ ゲートウェイが 2 つ以上の VIS プールにトランクを定義している場合は、回復が可能です。 ビデオ ゲートウェイがプライマリ VIS プールを呼び出しできないと判断した場合は、単にセカンダリ VIS プールに呼び出しをルーティングします。
    
     ![VIS プールのフェールオーバーの図。](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    特定の VIS プールは、複数のゲートウェイへのトランクを持つ場合がありますが、通常、特定のゲートウェイには複数の VIS プールへのトランクを含めないので、このフェールオーバーをサポートするには、ビデオ ゲートウェイの同じ IP アドレスに解決する DNS で 2 つの FDQN を定義する必要があります。 トポロジ ドキュメント内の各 FQDN を個別のビデオ ゲートウェイとして表し、各ビデオ ゲートウェイに別の VIS プールへのトランクが設定され、回復が可能になります。 (TLS を使用する場合は、複数の名前がビデオ ゲートウェイ証明書の SAN にある必要があります)。
    
    > [!NOTE]
    > VIS では、トポロジ ドキュメントで構成されたゲートウェイからの着信呼び出しのみを許可します。 
  
2. **フロントエンド フェールオーバー** VIS プールが CUCM から呼び出しを受信するが、プライマリネクストホップ レジストラーまたはフロント エンド プールに到達できない場合、通話はバックアップ フロントエンド プールにルーティングされます。
    
     ![フロントエンド フェールオーバーの図。](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    VIS は、プライマリ フロント エンド プールとそのバックアップ フロント エンド プールの状態を追跡します (この設定は、トポロジ ドキュメントのレジストラー サービスのバックアップ設定にあります)。 1 分に 1 回、オプション ポーリングを両方のプールに送信し、連続する 5 つのエラーがある場合、VIS は特定のフロントエンド プールがダウンしていると見なします。 プライマリ フロント エンド プールがダウンとしてマークされ、使用可能な構成されたバックアップがある場合、VIS はゲートウェイからバックアップ フロント エンド プールに新しい呼び出しを送信します。 プライマリ フロント エンド プールが戻ると、VIS は新しい呼び出しにプライマリ フロント エンド プールの使用を再開します。
    
    VIS は、ビデオ SIP トランクからの呼び出しに対して 10 秒のタイマーも実装します。 ビデオ SIP トランクからの呼び出しにプライマリ ネクストホップ フロント エンド プールが使用され、プライマリネクストホップ フロント エンド プールが、このタイマー値内で送信された招待に対して一部の SIP メッセージ (100 Trying を含む) で応答しなかった場合は、構成されている場合は、その呼び出しのバックアップネクストホップ プロキシを試す必要があります。 
    
    > [!NOTE]
    > バックアップの次ホップが最初に試された場合、プライマリは次に試用されない。 
  
    管理者は、Windows PowerShell フェールオーバー コマンドを使用して、プライマリ フロント エンド プールでメンテナンスを実行する必要がある場合など、VIS にバックアップ フロント エンド プールの使用を強制することもできます。
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a>音声トランクとビデオ トランクを同じゲートウェイ ピアに同時に存在する
<a name="resiliency"> </a>

Skype for Business Server音声とビデオの SIP トランクで同じゲートウェイ ピアを使用できます。 したがって、同じ CUCM 展開では、仲介サーバーへの音声 SIP トランクとビデオ SIP トランクを VIS に設定できます。
  
- PSTN ゲートウェイは、音声 SIP トランクのトポロジ ドキュメントで特定の FQDN を使用して定義する必要があります。
    
- PSTN ゲートウェイのピアは仲介サーバーになります。
    
- 必要に応じて、PSTN ゲートウェイから複数の仲介サーバー プールにまたがって複数の音声トランクを定義できます。
    
- ビデオ ゲートウェイは、PSTN ゲートウェイと同じ FQDN を持つビデオ SIP トランクのトポロジ ドキュメントで定義する必要があります。
    
- ビデオ ゲートウェイへのピアは VIS です。
    
- 1 つのビデオ トランクをビデオ ゲートウェイから特定の VIS プールに定義できます。
    
- CUCM は、音声トランクとビデオ トランクの間で通話を正しくルーティングするように構成する必要があります。 たとえば、VTC からダイヤルするときに特別なダイヤル プレフィックスを使用できます。CUCM は、このダイヤル プレフィックスを VIS の呼び出しに関連付け、適切な変換ルールによって SIP Invite to VIS からこのプレフィックスが削除されます。
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a>Lync の以前のリリースとのSkype for Businessリリースでの VIS の共存在
<a name="resiliency"> </a>

VIS は、展開の一部としてのみSkype for Businessできます。 既存の展開の一部である Lync 2013 会議およびクライアントと相互運用できます。このような場合、VIS プールは、VIS プールのネクスト ホップであるレジストラー/FE プールを含む Skype for Business 展開の一部である必要があります。
  
VIS では、RTV と H.264 の間のトランスコードはサポートされていません。 会議では、Lync 2013 より前のクライアントと VTC 参加者の間にビデオの相互運用性はありません。
  
会議で Lync 2013 より前のクライアントを使用すると、モバイル クライアントが RTV を使用して送信され、モバイル クライアントが優勢なスピーカーになると、VTC はビデオを受信しません。
  
Lync 2013 が Skype for Business 展開の一部である VIS で正しく動作するには、Lync 2013 が適切な CU を適用して、Lync 2013 クライアント、CAA、および AVMCU を VIS で動作するようにする必要があります。
  
Lync 2013 およびデスクトップ クライアントSkype for Business VIS の相互運用性がテストされ、サポートされています。
  
デスクトップ以外との VIS の相互運用性 (Android、Ipad、Iphone、Windows Phone、LMX など)Skype for Business VIS リリース時に適用可能な Apps Store から利用可能なクライアントがテストされ、サポートされています。
  
## <a name="recovery-from-packet-loss-via-fec"></a>FEC によるパケット損失からの回復
<a name="resiliency"> </a>

FEC をオンにすると、パケット損失からの回復を支援できます。 オンにすると、VIS から VTC 方向に 50% 多くのビデオ帯域幅が使用されます。
  
## <a name="vis-sizing-and-transcoding-costs"></a>VIS のサイズ変更とトランスコードのコスト
<a name="resiliency"> </a>

単一のビデオ ストリームを Cisco VTC から複数の simulcast ストリームにトランスコードすると、CPU 容量が使用されます。 Lync 2013 推奨 FE プラットフォームと同等の 1 つの VIS で、約 16 台の VTC がビデオ をトランスコードできます (各 VTC の 720p ビデオ ストリームが 720p、360p、180p の 3 つの別々のシプルキャスト ストリームにトランスコードされる場合)。 トランスコードをオフにすると、VIS CPU に保存されます。 ただし、VTC から VIS によって要求されたビデオ イメージは、ビデオ 側のすべてのレシーバーを満たす最も低い共通解像度Skype for Businessされます。 トランスコードがオフの場合でも、クライアントが VTC が送信できない低解像度Skype for Business要求すると、トランスコードがアクティブ化される場合があります。
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a>ビデオ ゲートウェイから VIS への通話配布
<a name="resiliency"> </a>

配布は、CUCM 配布メカニズムのいずれかを介して行います。
  
- DNS を動的に使用する。
    
- CUCM 側では、個々のトランクを定義できます。各トランクは VIS プール内の別のサーバーで終了します。 CUCM は、異なるトランク間で通話をルーティングします。
    
## <a name="no-hybrid-interoperability"></a>ハイブリッド相互運用性なし
<a name="resiliency"> </a>

オンプレミス VIS を介してオンライン会議に参加する VTC のサポートは、Skype for Business。
  
## <a name="no-federation-support"></a>フェデレーションサポートなし
<a name="resiliency"> </a>

VIS を介してフェデレーション会議に参加する VTC のサポートは、Skype for Business。
  
## <a name="see-also"></a>関連項目
<a name="resiliency"> </a>

[ビデオ相互運用サーバーを展開Skype for Business Server](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
