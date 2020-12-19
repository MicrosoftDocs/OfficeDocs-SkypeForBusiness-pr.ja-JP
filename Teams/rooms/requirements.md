---
title: Microsoft Teams Rooms の要件
ms.author: dstrome
author: dstrome
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
description: Microsoft Teams Rooms をサポートするための要件 (適切なデバイス、マイク、スピーカー、カメラ、ディスプレイの選択) について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 125c53690e8793ed48a66ffb8f4b3842541997e6
ms.sourcegitcommit: 9c1f3a72fb166b49a4b68bcdb9a2868bf86ca680
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2020
ms.locfileid: "49718621"
---
# <a name="microsoft-teams-rooms-requirements"></a>Microsoft Teams Rooms の要件

Microsoft Teams Rooms では、会議室のサイズと用途に応じたさまざまな認定オーディオ/ビデオ周辺機器を使用して、会議室のサイズを調整します。 コアとなる適切なデバイスとコンソールを選択し、スペースに適したマイク、スピーカー、カメラ、ディスプレイを組み合わせることで、ごく小さな打ち合わせスペースから大規模な会議場や役員室まで、あらゆるサイズのスペースで Microsoft Teams Rooms を活用できます。  Microsoft Teams Rooms を構成するために使用できる認定オーディオ/ビデオ周辺機器一式は、[デバイス ショーケース](https://products.office.com/microsoft-teams/across-devices)に用意されています。

この記事では、Microsoft Teams Rooms をサポートするためのデバイスの展開と構成に関する要件をまとめます。

展開作業では、[デプロイの概要](rooms-deploy.md)で説明している手順に従ってアカウントを作成する必要があります。また、[Microsoft Teams Rooms コンソールを構成する](console.md)で説明している手順に従って会議用コンソールを設定する必要もあります。

次のリソースも参照してください。

- [Skype for Business アドオンのライセンス](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [プランに基づいたライセンス オプション: Microsoft Teams Rooms](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Microsoft Teams Rooms では、Microsoft Teams、Skype for Business Server 2019、Skype for Business Server 2015、または Skype for Business Online にサインインし、これらのサービスでホストされている会議に参加できます。
>
> Lync Server 2013 のような以前のプラットフォームは、Microsoft Teams Rooms ではサポートしていません。 Microsoft Teams Rooms は、21Vianet、GCC-High もしくは DoD 環境で運用している Microsoft 365 または Office 365 ではサポートされません。
>
> オンプレミスの Exchange サーバーをご使用の場合、Microsoft Teams Rooms では Exchange Server 2013 SP1 以降を使用する必要があります。

## <a name="hardware-requirements"></a>ハードウェアの要件
ハードウェアを展開するには、Microsoft Teams Room システムを選択し、認定オーディオ/ビデオ周辺機器およびこれらのデバイスを統合するためのケーブル接続ソリューションを組み合わせる必要があります。  ここでは、これらのオプションについて説明します。

**サポートされている Microsoft Teams Room システム**

現在サポートされているすべての Microsoft Teams Room デバイスとバンドルは、[ミーティング システムの製品ショーケース](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=20&page=1&filterIds=)に用意されています。

  |コンソール|プロセッサ|RAM|ディスク|
  |:-----|:-----|:-----|:-----|
  |[Intel NUC を使用した、クナロンFlex UC-M130-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|Core i5|8 GB |128 GB |
  |[Intel NUC を使用した、ブレットロンFlex UC- B130-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|Core i5|8 GB |128 GB |
  |[Intel NUC を使用した、ブレットロンFlex UC-B140-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|Core i5|8 GB |128 GB |
  [Intel NUC を使用した、セボロンFlex UC-C140-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C140-T)|Core i7|8 GB |128 GB|
  |[Intel NUC を使用した、クナロンFlex UC-M150-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T)  + [CCS-UCA-MIC](https://www.crestron.com/en-US/Products/Audio/Microphones/Wired-Microphones/CCS-UCA-MIC-KIT)|Core i7|8 GB |128 GB |
  |[Intel NUC を使用した、エボロンFlex UC-MX150-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX150-T)|Core i5|8 GB |128 GB |
   [Intel NUC を使用した、ブレットロンFlex UC-B160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|Core i7|8 GB |128 GB|
  |[Intel NUC を使用した、セボロンFlex UC-C160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|Core i7|8 GB|128 GB|
  |[Dell OptiPlex 7080 with Logitech TAP](https://www.dell.com/en-us/work/shop/cty/pdp/spd/optiplex-7080-xe-teams) | Core i5 & i7 |8 GB |128 GB|
  |[HP Elite Slice for Meeting Rooms G2](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5 |8 GB |128 GB |
  |[HP Elite Slice G2 Audio Ready + Microsoft Teams Rooms](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8 GB |128 GB |
  |[Logicool TAP を備えた HP スライス パートナー対応]( https://www.logitech.com/en-us/video-collaboration/partners/hp.html)|Core i5|8 GB|128 GB|
  |[Lenovo ThinkSmart Hub 500](https://www3.lenovo.com/us/en/hub500) |Core i5 |8 GB |128 GB |
  |[Lenovo ThinkSmart Hub](https://news.lenovo.com/pressroom/press-releases/new-thinksmart-hub-collaboration-solution-from-lenovo-helps-organizations-embrace-hybrid-working-model/) |Core i5 |8 GB |128 GB|
  |[Logicool Tap と Intel NUC](https://www.logitech.com/product/microsoft-rooms)|Core i5|8 GB |128 GB |
  |[Logitech Tap と Lenovo ThinkSmart Tiny](https://www.logitech.com/en-us/video-collaboration/partners/lenovo.html)|Core i5|8 GB |128 GB|
  |[Lenovo ThinkSmart Tiny を含む Poly G10-T](https://www.poly.com/us/en/products/video-conferencing/g/g10) |Core i5| 8 GB | 128 GB|
  |[Yealink MVC300 と Intel NUC](https://www.yealink.com/products_154.html)|Core i5|8 GB |128 GB |
  |[Yealink MVC500 と Intel NUC](https://www.yealink.com/products_126.html)|Core i5|8 GB |128 GB |
  |[Yealink MVC800 と Intel NUC](https://www.yealink.com/products_125.html)|Core i5|8 GB|128 GB|
  |[Yealink MVC900 と Intel NUC](https://www.yealink.com/product/microsoft-teams-room-system-mvc900)|Core i5|8 GB|128 GB|
  |[Yealink MVC 300 II ](https://www.yealink.com/product/microsoft-teams-room-system-mvc300II) |Core i5|8 GB | 128 GB|
  |[Yealink(YEAlink)](https://www.yealink.com/product/microsoft-teams-room-system-mvc400)        |Core i5|8 GB | 128 GB|
  |[Yealink MVC 500 II ](https://www.yealink.com/product/microsoft-teams-room-system-mvc500II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC 800 II ](https://www.yealink.com/product/microsoft-teams-room-system-mvc800II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC 900 II ](https://www.yealink.com/product/microsoft-teams-room-system-mvc900II) |Core i5|8 GB | 128 GB|
  

> [!NOTE]
> - Core M3 プロセッサはサポートされません。
> - Windows 10 Enterprise 用の起動可能な Windows インストール メディアとして構成されている 32 GB 以上の USB ドライブが必要です。

**ドッキング式システム用のサポート対象の Surface Pro タブレット**

  |Tablet|プロセッサ|RAM|ディスク|
  |:-----|:-----|:-----|:-----|
  |Surface Pro 6| Core i5 |16 GB または 8 GB |128 GB 以上 |
  |Surface Pro </br>(第 5 世代) |Core i5 |8 GB または 4 GB |128 GB 以上 |
  |Surface Pro 4 |Core i5 |8 GB または 4 GB |128 GB 以上 |

- Surface Pro デバイスでは、次のドッキング ステーション オプションのいずれか 1 つが必要です:

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)
  - [Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
  - [Polycom MSR シリーズ](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

### <a name="certified-firmware-versions-for-usb-audio-and-video-peripherals"></a>USB オーディオ/ビデオ周辺機器の認定ファームウェア バージョン

これらのデバイスは、[ミーティング システム アクセサリの製品ショーケース](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73&page=1&filterIds=)および [https://office.com/teamsdevices](https://office.com/teamsdevices) に用意されています。

|Microsoft Teams Rooms の周辺機器|認定ファームウェア バージョン | コンテンツ カメラとして使用できるカメラ|
|:--- |:--- | :--- |
|[Aver VC520 Pro Camera + Speakerphone](https://www.averusa.com/products/conference-camera/vc520pro) |1004.35|
|[Aver VB342+ カメラ サウンド バー](https://www.averusa.com/products/conference-camera/vb342plus) | サウンド バー: 0.0.0000.97|
|[Aver CAM 540](https://www.averusa.com/products/conference-camera/cam540) |0.0.6002.83 |
|[Aver CAM 520 Pro](https://www.averusa.com/products/conference-camera/cam520pro) |0.0.1000.73 |
|[Crestron Huddly IQ](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  | 
|[Huddly キャンバス](https://www.huddly.com/blog/say-hello-to-huddly-canvas-our-latest-ai-technology-for-content-capture-and-enhancement/) | 1.3.25 |  &#x2714; |
|[Huddly IQ](https://www.huddly.com/conference-cameras/iq/) |1.3.22|
|[Huddly IQ Lite](https://www.huddly.com/conference-cameras/iq/) |1.3.29|
|[Huddly IQ カメラ](https://www.huddly.com/conference-cameras/iq/) |1.3.27|
|[Jabra Panacast カメラ](https://www.jabra.com/business/video-conferencing/jabra-panacast)|3.8.22|
|[Logitech Brio](https://www.logitech.com/product/brio)   |V2.2.50| &#x2714; |
|[Logitech 930e](https://www.logitech.com/product/c930e-webcam)   | 8.0.914   | &#x2714; |
|[Logitech Rally](https://www.logitech.com/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Logitech MeetUp](https://www.logitech.com/product/meetup-conferencecam)   |オーディオ — 1.0.172 <br/> ビデオ — 1.0.156  |
|[Logitech ConferenceCam Connect](https://www.logitech.com/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Logitech Group](https://www.logitech.com/product/conferencecam-group)   |8.5.778   |
|[Logitech PTZ Pro](https://www.logitech.com/product/conferencecam-ptz-pro)   | 1.1.219   |
|[Logitech PTZ Pro 2](https://www.logitech.com/product/conferencecam-ptz-pro2)   |
|[Nureva HDL300](https://www.nureva.com/audio-conferencing/hdl300) |2.3.6|
|[Poly EagleEye Cube カメラ](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.html)  |1.2.0 |
|[Polycom EagleEye IV](https://www.poly.com/us/en/products/video-conferencing/eagleeye/eagleeye-iv)   |1.0.0   |
|[Polycom CX5100](https://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl)   | 1.2.0.70232   |
|[Polycom EagleEye Director II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom Studio サウンドバー](https://www.polycom.com/hd-video-conferencing/room-video-systems/polycom-studio.html)|1.1.2.000570|
|[Polycom Trio 8500 / 8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[EPOS SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[EPOS SP20](https://www.eposaudio.com/en/us/enterprise/products/sp-20-ml-142ee5ca-speakerphone-1000226)   |1.2.15   |
|[EPOS SP30](https://www.eposaudio.com/en/us/enterprise/products/sp-30-78c0cecc-bluetooth-speakerphone-1000223)   |2.1.52  |
|[EPOS SP30T](https://www.eposaudio.com/en/us/enterprise/products/sp-30t-b949fe9a-bluetooth-speakerphone-1000225)  |3.2.63  |
|[EPOS Expand 80T + 2 Extension Mics](https://www.eposaudio.com/en/us/enterprise/products/expand-80t-bluetooth-speakerphone-1000203) |スピーカーフォン — 4.6.55 <br/> 拡張機能マイク : 0.2.314|
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK&trade;-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[ヤマハ YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100c   |
|[Yealink CP900](https://www.yealink.com/products_150.html) |100.20.0.29 |
|[YealinkUVC30](https://www.yealink.com/product/microsoft-teams-room-system-uvc30)| 105.420.0.11 |  &#x2714; |
|[Shure Intellimix P300 オーディオ プロセッサ](https://www.shure.com/en-US/products/mixers/p300)+</br></br> [Shure MXA 310 テーブル アレイ マイク](https://www.shure.com/en-US/products/microphones/mxa310) | 4.1 |
|[Shure Intellimix P300 オーディオ プロセッサ](https://www.shure.com/en-US/products/mixers/p300) + </br></br> [Shure MXA 910 + Intellimix シーリング アレイ マイク](https://www.shure.com/en-US/products/microphones/mxa910) | 4.1|
|[Shure Intellimix P300 オーディオ プロセッサ](https://www.shure.com/en-US/products/mixers/p300)+</br></br> [Shure MXA 310 Table Array Mic ](https://www.shure.com/en-US/products/microphones/mxa310) +</br></br> [MXN5W-C Ceiling スピーカー](https://www.shure.com/en-US/products/loudspeakers/mxn5)| P300 DSP: 4.1.11 </br> MXA310 Table Array mic: 4.1.41 </br> MXN5W-C スピーカー: 1.0.4 |
|[Shure Intellimix P300 オーディオ プロセッサ](https://www.shure.com/en-US/products/mixers/p300) + </br></br> [Shure MXA 910 with Intellimix Ceiling Array Mic](https://www.shure.com/en-US/products/microphones/mxa910) +</br></br> [MXN5W-C Ceiling スピーカー](https://www.shure.com/en-US/products/loudspeakers/mxn5)| P300 DSP: 4.1.11 </br> MXA910 Ceiling Array mic: 4.1.41 </br> MXN5W-C スピーカー: 1.0.4 |
|[Biamp Tesira Fore AVB VT4 Fixed audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ &Dagger;</br></br> [ゼンハイザー TeamConnect Ceiling 2 マイク](https://en-us.sennheiser.com/tcc2)+ &Dagger;</br></br> [Tesira EX-UBT](https://www.biamp.com/products/tesira/tesira-expanders) &Dagger; |  Biamp DSP: 3.12.0.15  </br></br> TCC2: 1.3.3 </br></br> EX-UBT: 3.12.0.15 |
|[Biamp Tesira FORTÉ AVB VT4 オーディオ DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br></br>[Biamp Parlé TCM-XA シーリング マイク](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br></br> [Biamp Desono C-IC6 天井埋め込み型スピーカー](https://www.biamp.com/products/tesira-speakers)| Audio FW バージョン: 3.15|
|[Biamp TesiraFORTE AVB VT4](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br></br>[Parle TTM-X(テーブル マイク)](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br></br>[Ex-UBT]() |Audio FW バージョン: 3.15|
|[Bose ControlSpace EX-440C DSP + </br>Bose P2600A AmpLink アンプ +</br> ゼンハイザー TCC2 シーリング マイク + </br> Bose EdgeMax EM180 天井埋め込み型スピーカー](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  |  |
|[Bose ControlSpace EX-440C DSP + </br>Bose P2600A AmpLink アンプ + ゼンハイザー TCC2 シーリング マイク + </br> Bose DesignMax DM2C-P 天井埋め込み型スピーカー](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  |  |
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Bose P2600A AmpLink 200A-2016</br> [Sennheiser TCC2 Ceiling Microphone](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [DesignMax DM2C -LP Ceiling Speaker](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/designmax/designmax_dm2c_lp.html#v=designmax_dm2c_lp_black) | Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  | 
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Bose P2600A AmpLink 分け前+</br> [Sennheiser TCC2 Ceiling Microphone](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [EdgeMax EM180 Ceiling Speaker](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/edgemax/edgemax_em180.html#v=edgemax_em180_white) | Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  |
|[QSC Q-SYS Core 110f](https://www.qsc.com/systems/products/q-sys-ecosystem/products-peripherals-accessories/q-sys-cores/core-110f/) +</br> [Sennheiser TCC2 Ceiling Microphone]() +</br> [QSC EnergyStar Power Energy Spa2-60](https://www.qsc.com/systems/products/power-amplifiers/energystar-amplifiers/spa-series/spa2-60/) +</br> [Q-SYS NS Series Network Switch NS-1108P](https://www.qsc.com/systems/products/q-sys-ecosystem/products-peripherals-accessories/network-switches/q-sys-ns-series-network-switches/) + </br> [QSC Column Surface mount Speakers AD-S402T](https://www.qsc.com/systems/products/loudspeakers/column-surface-mount-loudspeakers/acousticdesigntm-series-column-surface-mount/ad-s402t/) |Q-sys Designer: 8.4.0 </br> <br> TCC2 : 1.5.1 Dante 1.2.0 </br>  <br> N/A </br>  <br>N1100v6.4.2.8 </br> N/A|
|[QSC Q-SYS Core 110f](https://www.qsc.com/systems/products/q-sys-ecosystem/products-peripherals-accessories/q-sys-cores/core-110f/) +</br> [Sennheiser TCC2 Ceiling Microphone]() +</br> [QSC EnergyStar Power Energy Spa2-60](https://www.qsc.com/systems/products/power-amplifiers/energystar-amplifiers/spa-series/spa2-60/) +</br> [Q-SYS NS Series Network Switch NS-1108P](https://www.qsc.com/systems/products/q-sys-ecosystem/products-peripherals-accessories/network-switches/q-sys-ns-series-network-switches/) + </br> [QSC Column Surface mount Speakers AD-C6T-LP](https://www.qsc.com/systems/products/loudspeakers/ceiling-mount-loudspeakers/acousticdesigntm-series-ceiling-mount/ad-c6t-lp/?L=) |Q-sys Designer: 8.4.0 </br> <br> TCC2 : 1.5.1 Dante 1.2.0 </br>  <br> N/A </br>  <br>N1100v6.4.2.8 </br> N/A|


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
> Microsoft Teams Rooms はキーボードを使用しません。 必要な場合は、管理者がオンスクリーン キーボードを使用する必要があります。 Microsoft Teams Rooms デバイスのイメージングには、USB キーボードまたはマウスが必要です。

次の表で、会議室のサイズに基づいて推奨される周辺機器をご確認ください。

**Microsoft Teams Rooms の認定オーディオ周辺機器**

|会議室の種類|ユーザー数|推奨されるマイクとスピーカーの最大間隔|会議室の最大サイズ別デバイス|注釈|
|:-----|:-----|:-----|:-----|:-----|
|**フォーカス** <br/> 10' x 9'   |2 ～ 4  |1.5 m  |Logitech Connect  |ロジクール Connect デバイスにはカメラが組み込まれているため、ローカルの会議出席者を撮影するには、(テーブルの中央ではなく) 会議室の正面に配置する必要があります。 |
|**小規模** <br/> 16' x 16'  |4 ～ 6  |2.0 m  |Jabra 510 <br/> ゼンハイザー SP20  |これよりも大きい会議室では、再生音量が制限される場合があります。  |
|**中規模** <br/> 18' x 20'  |6 ～ 12  |2.4 m  |Jabra 710 <br/> Jabra 810 <br/> Logitech MeetUp <br/> Logitech Group <br/> Polycom Trio <br/> Polycom CX5100 <br/> ゼンハイザー SP 220 MS <br/> ヤマハ YVC-1000MS  |Logitech Connect デバイスにはカメラが組み込まれているため、(ローカルの会議出席者を撮影するにはテーブルの中央ではなく) 会議室の正面に配置する必要があります。 <br/> 一般的に、長い長方形のテーブルまたは U 字型のテーブルが使用されている会議室では、サテライト マイクを使用すると役立ちます。 <br/> デイジーチェーン構成では SP 220 MS を使用する必要があります。  |
|**大規模** <br/> 15' x 32'  |12 ～ 16  |3 m <br/> この間隔は、接続されている各サテライト マイクの対象エリアにも適用されます。  |Logitech Group + サテライト マイク <br/> Polycom Trio+ サテライト マイク <br/> Polycom CX5100 + サテライト マイク <br/> ゼンハイザー SP 220 MS <br/> ヤマハ YVC-1000MS + サテライト マイク  |この行に記載されているすべてのオーディオ デバイスは、サテライト マイク オプションをサポートしています。 <br/> CX5100 には全方位カメラが内蔵されているため、このデバイスはテーブルの中央に配置できます。 <br/> デイジーチェーン構成では SP 220 MS を使用する必要があります。  |

**Microsoft Teams Rooms の認定ビデオ周辺機器**

|会議室の種類|ユーザー数|最適な会議室のサイズ別デバイス|注釈|
|:-----|:-----|:-----|:-----|
|**フォーカス** <br/> 10' x 9'  |2 ～ 4  |Logitech Connect <br/> Logitech MeetUp <br/> Polycom CX5100  ||
|**小規模** <br/> 16' x 16'  |4 ～ 6  |Logitech C930e <br/> Logitech MeetUp <br/> Logitech BRIO <br/> Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  |多くの場合、Logitech PTZ Pro Logitech Group にバンドルされています。  |
|**中規模** <br/> 18' x 20'  |6 ～ 12  |Logitech MeetUp <br/> Logitech BRIO <br/> Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  ||
|**大規模** <br/> 15' x 32'  |12 ～ 16  |Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  ||

 > [!NOTE]
 > 会議室正面のディスプレイの解像度は 1920x1080p 以下に設定してください。

## <a name="required-software-downloads"></a>必要なソフトウェア ダウンロード

Microsoft Teams Rooms のイメージをビルドするには、「[Microsoft Teams Rooms コンソールを構成する](console.md)」で説明している手順に従ってください。 これらの手順では、インストールに必要なすべてのソフトウェアをダウンロードする方法を説明しています。

> [!NOTE]
> IT 担当者は、ボリューム ライセンス契約を介して Windows 10 Enterprise ISO ファイルにアクセスする必要があります。

必要に応じ、[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105) をダウンロードして、Microsoft Teams Rooms アカウントのプロビジョニングに使用できます。

## <a name="see-also"></a>関連項目

[全バンドルを参照する](https://products.office.com/microsoft-teams/across-devices/devices)

[Microsoft Teams Rooms を計画する](rooms-plan.md)

[Microsoft Teams Rooms をデプロイする](rooms-deploy.md)

[Microsoft Teams Rooms コンソールを構成する](console.md)

[Microsoft Teams Rooms の管理](rooms-manage.md)

[Skype for Business アドオンのライセンス](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
