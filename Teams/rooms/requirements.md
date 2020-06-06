---
title: Microsoft Teams ミーティングの要件
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection:
- M365-collaboration
description: Microsoft Teams ミーティングをサポートするための要件 (適切なデバイス、マイク、スピーカー、カメラ、ディスプレイの選択) について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fbfad5deba6288736beea0ef69660426975bb6fa
ms.sourcegitcommit: 184f4f61a3e739a1cfa533c6d95d405d887ea25d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "44591307"
---
# <a name="microsoft-teams-rooms-requirements"></a>Microsoft Teams ミーティングの要件

Microsoft Teams ミーティングでは、会議室のサイズと用途に応じたさまざまな認定オーディオ/ビデオ周辺機器を使用して、会議室のサイズを調整します。 コアとなる適切なデバイスとコンソールを選択し、スペースに適したマイク、スピーカー、カメラ、ディスプレイを組み合わせることで、ごく小さな打ち合わせスペースから大規模な会議場や役員室まで、あらゆるサイズのスペースで Microsoft Teams ミーティングを活用できます。  Microsoft Teams ミーティングを構成するために使用できる認定オーディオ/ビデオ周辺機器一式は、[デバイス ショーケース](https://products.office.com/microsoft-teams/across-devices)に用意されています。

この記事では、Microsoft Teams ミーティングをサポートするためのデバイスの展開と構成に関する要件をまとめます。

展開作業では、[デプロイの概要](rooms-deploy.md)で説明している手順に従ってアカウントを作成する必要があります。また、[Microsoft Teams ミーティング コンソールを構成する](console.md)で説明している手順に従って会議用コンソールを設定する必要もあります。

次のリソースも参照してください。

- [Skype for Business アドオンのライセンス](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [プランに基づいたライセンス オプション: Microsoft Teams ミーティング](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Microsoft Teams ミーティングでは、Microsoft Teams、Skype for Business Server 2019、Skype for Business Server 2015、または Skype for Business Online にサインインし、これらのサービスでホストされている会議に参加できます。
>
> Lync Server 2013 のような以前のプラットフォームは、Microsoft Teams ミーティングではサポートしていません。 Microsoft Teams ミーティングは、21Vianet が運用している Office 365 や GCC-High 環境、DoD 環境ではサポートされません。
>
> オンプレミスの Exchange サーバーをご使用の場合、Microsoft Teams ミーティングでは Exchange Server 2013 SP1 以降を使用する必要があります。

## <a name="hardware-requirements"></a>ハードウェアの要件
ハードウェアを展開するには、Microsoft Teams ミーティング システムを選択し、認定オーディオ/ビデオ周辺機器およびこれらのデバイスを統合するためのケーブル接続ソリューションを組み合わせる必要があります。  ここでは、これらのオプションについて説明します。

**サポートされている Microsoft Teams ミーティング システム**

現在サポートされているすべての Microsoft Teams ミーティング デバイスとバンドルは、[ミーティング システムの製品ショーケース](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=20&page=1&filterIds=)に用意されています。

  |コンソール|プロセッサ|RAM|ディスク|
  |:-----|:-----|:-----|:-----|
  |[Crestron Flex UC-M130-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|Core i5|8 GB |128 GB |
  |[Crestron Flex UC- B130-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|Core i5|8 GB |128 GB |
  |[Crestron Flex UC-B140-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|Core i5|8 GB |128 GB |
  |[Crestron Flex UC-M150-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T) + [CCS-UCA-MIC](https://www.crestron.com/en-US/Products/Audio/Microphones/Wired-Microphones/CCS-UCA-MIC-KIT)|Core i7|8 GB |128 GB |
  [Crestron Flex UC-B160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|Core i7|8 GB |128 GB|
  |[Crestron Flex UC-C160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|Core i7|8 GB|128 GB|
  |[HP Elite Slice for Meeting Rooms G2](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5 |8 GB |128 GB |
  |[HP Elite Slice G2 Audio Ready + Microsoft Teams ミーティング](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8 GB |128 GB |
  |[Lenovo ThinkSmart Hub 500](https://www3.lenovo.com/us/en/hub500) |Core i5 |8 GB |128 GB |
  |[ロジクール Tap](https://www.logitech.com/product/microsoft-rooms)|Core i5|8 GB |128 GB |
  |[Logitech をタップして Lenovo 思考センター M920 Tiny](https://www.logitech.com/en-us/video-collaboration/partners/lenovo.html)|Core i5|8 GB |128 GB|
  |[Yealink MVC800](https://www.yealink.com/products_125.html)|Core i5|8 GB|128 GB|
  |[Yealink MVC500](https://www.yealink.com/products_126.html)|Core i5|8 GB |128 GB |
  |[Yealink MVC300](https://www.yealink.com/products_154.html)|Core i5|8 GB |128 GB |
  |[Yealink MVC900](https://www.yealink.com/product/microsoft-teams-room-system-mvc900)|Core i5|8 GB|128 GB|
  ||||||

> [!NOTE]
> - Core M3 プロセッサはサポートされません。
> - Windows 10 Enterprise 用の起動可能な Windows インストール メディアとして構成されている 32 GB 以上の USB ドライブが必要です。

**ドッキング式システム用のサポート対象の Surface Pro タブレット**

  |Tablet|プロセッサ|RAM|ディスク|
  |:-----|:-----|:-----|:-----|
  |Surface Pro 6| Core i5 |16 GB または 8 GB |128 GB 以上 |
  |Surface Pro </br>(第 5 世代) |Core i5 |8 GB または 4 GB |128 GB 以上 |
  |Surface Pro 4 |Core i5 |8 GB または 4 GB |128 GB 以上 |

- Surface Pro デバイスには、次のドッキングステーションオプションのいずれかが必要です。

  - [ロジクール SmartDock](https://www.logitech.com/product/smartdock)
  - [Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
  - [Polycom MSR シリーズ](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

### <a name="certified-firmware-versions-for-usb-audio-and-video-peripherals"></a>USB オーディオ/ビデオ周辺機器の認定ファームウェア バージョン

これらのデバイスは、[ミーティング システム アクセサリの製品ショーケース](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73&page=1&filterIds=)および [https://office.com/teamsdevices](https://office.com/teamsdevices) に用意されています。

|Microsoft Teams ミーティングの周辺機器|認定ファームウェア バージョン | コンテンツ カメラとして使用できるカメラ|
|:--- |:--- | :--- |
|[Crestron Huddly IQ](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  |  |
|[Huddly IQ](https://www.huddly.com/conference-cameras/iq/) |1.3.22|
|[Jabra Panacast カメラ](https://www.jabra.com/business/video-conferencing/jabra-panacast)|3.8.22|
|[ロジクール Brio](https://www.logitech.com/product/brio)   |V2.2.50| &#x2714; |
|[ロジクール 930e](https://www.logitech.com/product/c930e-webcam)   | 8.0.914   | &#x2714; |
|[ロジクール Rally](https://www.logitech.com/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[ロジクール MeetUp](https://www.logitech.com/product/meetup-conferencecam)   |オーディオ — 1.0.172 <br/> ビデオ — 1.0.156  |
|[ロジクール ConferenceCam Connect](https://www.logitech.com/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[ロジクール Group](https://www.logitech.com/product/conferencecam-group)   |8.5.778   |
|[ロジクール PTZ Pro](https://www.logitech.com/product/conferencecam-ptz-pro)   | 1.1.219   |
|[ロジクール PTZ Pro 2](https://www.logitech.com/product/conferencecam-ptz-pro2)   |
|[Poly EagleEye Cube カメラ](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.html)  |1.2.0 |
|[Polycom EagleEye IV](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl)   |1.0.0   |
|[Polycom CX5100](https://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl)   | 1.2.0.70232   |
|[Polycom EagleEye Director II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom Studio サウンドバー](https://www.polycom.com/hd-video-conferencing/room-video-systems/polycom-studio.html)|1.1.2.000570|
|[Polycom Trio 8500 / 8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[ゼンハイザー SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[ゼンハイザー SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml)   |1.2.15   |
|[ゼンハイザー SP30](https://en-us.sennheiser.com/sp-30)   |2.1.52  |
|[ゼンハイザー SP30T](https://en-us.sennheiser.com/sp-30)  |3.2.63  |
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK&trade;-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[ヤマハ YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100c   |
|[Yealink CP900](https://www.yealink.com/products_150.html) |100.20.0.29 |
|[Shure Intellimix P300 オーディオ プロセッサ](https://www.shure.com/en-US/products/mixers/p300)+</br></br> [Shure MXA 310 テーブル アレイ マイク](https://www.shure.com/en-US/products/microphones/mxa310) | 4.1 |
|[Shure Intellimix P300 オーディオ プロセッサ](https://www.shure.com/en-US/products/mixers/p300) + </br></br> [Shure MXA 910 + Intellimix シーリング アレイ マイク](https://www.shure.com/en-US/products/microphones/mxa910) | 4.1|
|[Biamp Tesira Fore AVB VT4 Fixed audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ &Dagger;</br></br> [ゼンハイザー TeamConnect Ceiling 2 マイク](https://en-us.sennheiser.com/tcc2)+ &Dagger;</br></br> [Tesira EX-UBT](https://www.biamp.com/products/tesira/tesira-expanders) &Dagger; |  Biamp DSP: 3.12.0.15  </br></br> TCC2: 1.3.3 </br></br> EX-UBT: 3.12.0.15 |
|[Bose ControlSpace EX-440C DSP + </br>Bose P2600A AmpLink アンプ +</br> ゼンハイザー TCC2 シーリング マイク + </br> Bose EdgeMax EM180 天井埋め込み型スピーカー](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  |  |
||||||

&Dagger; お客様は、Dante インターフェース、または Biamp/ゼンハイザーがこのバンドル用に推奨しているネットワーク スイッチのいずれかを選択できます。

#### <a name="usb-extenders"></a>USB エクステンダー

- タブレット ドック上の USB ポートは USB 3.0 対応です。 USB 2.x エクステンダーを使用することはできますが、その場合遠端での速度は USB 2.x の速度に制限されます。 USB 3.0 周辺機器にはエクステンダーの使用は推奨されていません。
- エクステンダーは USB 2.0 以降の仕様を満たしている必要があります。
  - タブレット ドックは、少なくとも 2 つの外部 USB ハブによる拡張をサポートします。 2 つを超える USB ハブを直列に接続する場合は、ドックの製造元に直列接続がサポートされるかどうかを確認してください。
  - 会議室内の有線 GbE 接続。 適切な長さのイーサネット ケーブル。
  - HDMI で接続された最大 2 台の 1080-p ディスプレイ。 適切な長さの HDMI ケーブル。

> [!NOTE]
> 屋内ディスプレイの前面として使用される消費者向け TV では、スタンバイ モードからアクティブなビデオ ソースに自動的に切り替わるように、HDMI の CEC (Consumer Electronics Control) 機能をサポート/有効にする必要があります。 この機能はすべての TV でサポートされるものではありません。
>
> Microsoft Teams ミーティングはキーボードを使用しません。 必要な場合は、管理者がオンスクリーン キーボードを使用する必要があります。 Microsoft Teams ミーティング デバイスのイメージングには、USB キーボードまたはマウスが必要です。

次の表で、会議室のサイズに基づいて推奨される周辺機器をご確認ください。

**Microsoft Teams ミーティングの認定オーディオ周辺機器**

|会議室の種類|ユーザー数|推奨されるマイクとスピーカーの最大間隔|会議室の最大サイズ別デバイス|注釈|
|:-----|:-----|:-----|:-----|:-----|
|**フォーカス** <br/> 10' x 9'   |2 ～ 4  |1.5 m  |ロジクール Connect  |ロジクール Connect デバイスにはカメラが組み込まれているため、ローカルの会議出席者を撮影するには、(テーブルの中央ではなく) 会議室の正面に配置する必要があります。 |
|**小規模** <br/> 16' x 16'  |4 ～ 6  |2.0 m  |Jabra 510 <br/> ゼンハイザー SP20  |これよりも大きい会議室では、再生音量が制限される場合があります。  |
|**中規模** <br/> 18' x 20'  |6 ～ 12  |2.4 m  |Jabra 710 <br/> Jabra 810 <br/> ロジクール MeetUp <br/> ロジクール Group <br/> Polycom Trio <br/> Polycom CX5100 <br/> ゼンハイザー SP 220 MS <br/> ヤマハ YVC-1000MS  |ロジクール Connect デバイスにはカメラが組み込まれているため、(ローカルの会議出席者を撮影するにはテーブルの中央ではなく) 会議室の正面に配置する必要があります。 <br/> 一般的に、長い長方形のテーブルまたは U 字型のテーブルが使用されている会議室では、サテライト マイクを使用すると役立ちます。 <br/> デイジーチェーン構成では SP 220 MS を使用する必要があります。  |
|**大規模** <br/> 15' x 32'  |12 ～ 16  |3 m <br/> この間隔は、接続されている各サテライト マイクの対象エリアにも適用されます。  |ロジクール Group + サテライト マイク <br/> Polycom Trio+ サテライト マイク <br/> Polycom CX5100 + サテライト マイク <br/> ゼンハイザー SP 220 MS <br/> ヤマハ YVC-1000MS + サテライト マイク  |この行に記載されているすべてのオーディオ デバイスは、サテライト マイク オプションをサポートしています。 <br/> CX5100 には全方位カメラが内蔵されているため、このデバイスはテーブルの中央に配置できます。 <br/> デイジーチェーン構成では SP 220 MS を使用する必要があります。  |

**Microsoft Teams ミーティングの認定ビデオ周辺機器**

|会議室の種類|ユーザー数|最適な会議室のサイズ別デバイス|注釈|
|:-----|:-----|:-----|:-----|
|**フォーカス** <br/> 10' x 9'  |2 ～ 4  |ロジクール Connect <br/> ロジクール MeetUp <br/> Polycom CX5100  ||
|**小規模** <br/> 16' x 16'  |4 ～ 6  |ロジクール C930e <br/> ロジクール MeetUp <br/> ロジクール BRIO <br/> ロジクール PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  |多くの場合、ロジクール PTZ Pro はロジクール Group にバンドルされています。  |
|**中規模** <br/> 18' x 20'  |6 ～ 12  |ロジクール MeetUp <br/> ロジクール BRIO <br/> ロジクール PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  ||
|**大規模** <br/> 15' x 32'  |12 ～ 16  |ロジクール PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  ||

 > [!NOTE]
 > 会議室正面のディスプレイの解像度は 1920x1080p 以下に設定してください。

## <a name="required-software-downloads"></a>必要なソフトウェア ダウンロード

Microsoft Teams ミーティングのイメージをビルドするには、「[Microsoft Teams ミーティング コンソールを構成する](console.md)」で説明している手順に従ってください。 これらの手順では、インストールに必要なすべてのソフトウェアをダウンロードする方法を説明しています。

> [!NOTE]
> IT 担当者は、ボリューム ライセンス契約を介して Windows 10 Enterprise ISO ファイルにアクセスする必要があります。

必要に応じ、[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105) をダウンロードして、Microsoft Teams ミーティング アカウントのプロビジョニングに使用できます。

## <a name="see-also"></a>関連項目

[全バンドルを参照する](https://products.office.com/microsoft-teams/across-devices/devices)

[Microsoft Teams ミーティングを計画する](rooms-plan.md)

[デプロイの概要](rooms-deploy.md)

[Microsoft Teams ミーティング コンソールを構成する](console.md)

[Microsoft Teams ミーティングの管理](rooms-manage.md)

[Skype for Business アドオンのライセンス](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
