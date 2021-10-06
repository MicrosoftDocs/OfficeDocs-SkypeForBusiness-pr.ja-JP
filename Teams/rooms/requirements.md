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
ms.localizationpriority: medium
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection:
- M365-collaboration
description: Microsoft Teams Rooms をサポートするための要件 (適切なデバイス、マイク、スピーカー、カメラ、ディスプレイの選択) について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aff7514e8c79597566206fb06898876e23723084
ms.sourcegitcommit: 74d3ab35c344d70b2399bc46a6ced3ab2762a470
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60138263"
---
# <a name="microsoft-teams-rooms-requirements"></a>Microsoft Teams Rooms の要件

Microsoft Teams会議室の規模は、部屋のサイズが異なります。 Teams会議室では、部屋のサイズと用途に基づいて、さまざまな認定オーディオおよびビデオ周辺機器が使用されます。 適切なコア デバイスと本体を選択し、マイク、スピーカー、カメラ、およびスペースに適したディスプレイと組み合わせると、Microsoft Teams 会議室を小さなハドル 空間から大きな会議スペースや会議室まで、任意のサイズの空間に展開できます。  Microsoft Teams Rooms を構成するために使用できる認定オーディオ/ビデオ周辺機器一式は、[デバイス ショーケース](https://products.office.com/microsoft-teams/across-devices)に用意されています。

この記事では、Microsoft Teams Rooms をサポートするためのデバイスの展開と構成に関する要件をまとめます。

展開作業では、[デプロイの概要](rooms-deploy.md)で説明している手順に従ってアカウントを作成する必要があります。また、[Microsoft Teams Rooms コンソールを構成する](console.md)で説明している手順に従って会議用コンソールを設定する必要もあります。

以下を参照してください。

- [Skype for Business アドオンのライセンス](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [プランに基づいたライセンス オプション: Microsoft Teams Rooms](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Microsoft Teams Rooms では、Microsoft Teams、Skype for Business Server 2019、Skype for Business Server 2015、または Skype for Business Online にサインインし、これらのサービスでホストされている会議に参加できます。
>
> Lync Server 2013 のような以前のプラットフォームは、Microsoft Teams Rooms ではサポートしていません。 Microsoft Teams会議室は、21Vianet Microsoft 365 DoD 環境Office 365、または 21Vianet が運営する環境ではサポートされていません。
>
> オンプレミスの Exchange サーバーをご使用の場合、Microsoft Teams Rooms では Exchange Server 2013 SP1 以降を使用する必要があります。

## <a name="hardware-requirements"></a>ハードウェアの要件
ハードウェアを展開するには、Microsoft Teams Room システムを選択し、認定オーディオ/ビデオ周辺機器およびこれらのデバイスを統合するためのケーブル接続ソリューションを組み合わせる必要があります。  ここでは、これらのオプションについて説明します。

**サポートされている Microsoft Teams Room システム**

現在サポートされているすべての Microsoft Teams Room デバイスとバンドルは、[ミーティング システムの製品ショーケース](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=20&page=1&filterIds=)に用意されています。

  |コンソール|プロセッサ|RAM|ディスク|
  |:-----|:-----|:-----|:-----|
  |[Intel NUC を使用したクレスロン Flex UC-M130-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|Core i5|8 GB |128 GB |
  |[Intel NUC を使用したクレスロン Flex UC - B130-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|Core i5|8 GB |128 GB |
  |[Intel NUC を使用したクレットロン Flex UC-B140-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|Core i5|8 GB |128 GB |
  [Intel NUC を使用したクセロン Flex UC-C140-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C140-T)|Core i7|8 GB |128 GB|
  |[Intel NUC を使用したクレスロン Flex UC-M150-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T)  + [CCS-UCA-MIC](https://www.crestron.com/Products/Audio/Microphones/Wired-Microphones/CCS-UCA-MIC-KIT)|Core i7|8 GB |128 GB |
  |[Intel NUC を使用したクレスロン Flex UC-MX150-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX150-T)|Core i5|8 GB |128 GB |
   [Intel NUC を使用したクレスロン Flex UC-B160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|Core i7|8 GB |128 GB|
  |[Intel NUC を使用したクセロン Flex UC-C160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|Core i7|8 GB|128 GB|
  |[Uc Presentation Transmitter (UC-PR) と ASUS PC を使用した、クレスロン Flex UC-MMX30-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MMX30-T)|Core i5|8 GB |128 GB |
  |[Uc Presentation Transmitter (UC-PR) と ASUS PC を使用した、クレスロン Flex UC-BX30-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-BX30-T)|Core i5|8 GB |128 GB |
  |[Uc Presentation Transmitter (UC-PR) と ASUS PC を使用した、クレスロン Flex UC-CX100-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-CX100-T)|Core i5|8 GB |128 GB |
  |[AsUS PC を使用したクレスロン Flex UC-B30-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B30-T)|Core i5|8 GB |128 GB |
   |[AsUS PC を使用したクセロン Flex UC-C100-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T)|Core i5|8 GB |128 GB |
   |[AsUS PC を使用したクレスロン Flex UC-M50-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M50-T)|Core i5|8 GB |128 GB |
   |[AsUS PC を使用したクレスロン Flex UC-M70-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M70-T)|Core i5|8 GB |128 GB |
   |[AsUS PC を使用したクレスロン Flex UC-MX50-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX50-T)|Core i5|8 GB |128 GB |
   |[AsUS PC を使用したクレスロン Flex UC-MX70-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX70-T)|Core i5|8 GB |128 GB |
  |[クレスロン・マーキュリー ミニ UC-MM30-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MM30-T)|Core i5|8 GB |128 GB |
  |[Dell OptiPlex 7080 と Logitech TAP](https://www.dell.com/work/shop/cty/pdp/spd/optiplex-7080-xe-teams) | Core i7 |16 GB |128 GB|
  |[HP Elite Slice for Meeting Rooms G2](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5 |8 GB |128 GB |
  |[HP Elite Slice G2 Audio Ready + Microsoft Teams Rooms](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8 GB |128 GB |
  |[Logicool TAP を備えた HP スライス パートナー対応]( https://www.logitech.com/video-collaboration/partners/hp.html)|Core i5|8 GB|128 GB| 
  | Lenovo ThinkSmart Hub 500 |Core i5 |8 GB |128 GB |
  |[Lenovo ThinkSmart Hub](https://news.lenovo.com/pressroom/press-releases/new-thinksmart-hub-collaboration-solution-from-lenovo-helps-organizations-embrace-hybrid-working-model/) |Core i5 |8 GB |128 GB|
  |Lenovo ThinkSmart Core Kit |Core i5|8 GB|128 GB|
  |[Logicool Tap と Intel NUC](https://www.logitech.com/product/microsoft-rooms)|Core i5|8 GB |128 GB |
  |Logitech Tap と Intel Tiger Canyon NUC PC |Core i5|8 GB|128 GB|
  |[Logitech Tap と Lenovo ThinkSmart Tiny](https://www.logitech.com/video-collaboration/partners/lenovo.html)|Core i5|8 GB |128 GB|
  |[Poly G10-T と Lenovo ThinkSmart Tiny](https://www.poly.com/us/en/products/video-conferencing/g/g10) |Core i5| 8 GB | 128 GB|
  |[Yealink MVC300 と Intel NUC](https://www.yealink.com/products_154.html)|Core i5|8 GB |128 GB |
  |[Yealink MVC500 と Intel NUC](https://www.yealink.com/products_126.html)|Core i5|8 GB |128 GB |
  |[Yealink MVC800 と Intel NUC](https://www.yealink.com/products_125.html)|Core i5|8 GB|128 GB|
  |[Yealink MVC900 と Intel NUC](https://www.yealink.com/product/microsoft-teams-room-system-mvc900)|Core i5|8 GB|128 GB|
  |[Yealink MVC 300 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc300II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC400](https://www.yealink.com/product/microsoft-teams-room-system-mvc400)        |Core i5|8 GB | 128 GB|
  |[Yealink MVC 500 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc500II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC 800 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc800II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC 900 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc900II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC840](https://www.yealink.com/product/microsoft-teams-room-system-mvc840) |Core i5|8 GB | 128 GB|
  |[Yealink MVC940](https://www.yealink.com/product/microsoft-teams-room-system-mvc940) |Core i5|8 GB | 128 GB|
  |Yealink MVC660|Core i5|8 GB | 128 GB|
  |Yealink MVC640|Core i5|8 GB | 128 GB|
  |Yealink MVC320|Core i5|8 GB | 128 GB|
  
  
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
|[Aver VC520 PRO2 会議システム](https://www.averusa.com/products/conference-camera/vc520pro2) | 00.0.7200.79 |
|[Aver VB342+ カメラ サウンド バー](https://www.averusa.com/products/conference-camera/vb342plus) | サウンドバー: 0.0.0000.97|
|[Aver CAM 540](https://www.averusa.com/products/conference-camera/cam540) |0.0.6002.83 |
|[Aver CAM 520 Pro](https://www.averusa.com/products/conference-camera/cam520pro) |0.0.1000.73 |
|[Aver CAM 520 Pro 2](https://www.averusa.com/products/conference-camera/cam520pro2) |0.0.7200.3 |
|[Aver CAM 130](https://www.averusa.com/products/conference-camera/cam130) |0.0.7400.03 |
|[Aver VB130 カメラ サウンド バー](https://www.averusa.com/products/conference-camera/vb130) |0.0.7300.71 |
|[Bose Video Bar VB1](https://pro.bose.com/en_us/products/conferencing/videobars/bose-videobar-vb1.html?mc=25_PS_VB_BO_00_BI_&&msclkid=fc99b79880f714727a63e86ea0e5642a&utm_source=bing&utm_medium=cpc&utm_campaign=US%20-%20Brand_Videobar%20VB1_Exact&utm_term=bose%20videobar%20vb1&utm_content=Bose%20Videobar%20VB1&gclid=fc99b79880f714727a63e86ea0e5642a&gclsrc=3p.ds) |19.2|
|[Biamp Devio SCR-20CX Web-Based会議ハブと Ceiling Microphone](https://www.biamp.com/products/product-families/devio/huddle-room-solutions) |2.2.0.9|
|[Biamp Devio SCR-20TX Web-Based会議ハブとテーブルトップ マイク](https://www.biamp.com/products/product-families/devio/huddle-room-solutions) |2.2.0.9 |
|[Crestron Huddly IQ](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  | 
|[Huddly キャンバス](https://www.huddly.com/blog/say-hello-to-huddly-canvas-our-latest-ai-technology-for-content-capture-and-enhancement/) | 1.3.25 |  &#x2714; |
|[Huddly IQ](https://www.huddly.com/conference-cameras/iq/) |1.3.22|
|[Huddly IQ Lite](https://www.huddly.com/conference-cameras/iq/) |1.3.29|
|[Huddly IQ カメラ](https://www.huddly.com/conference-cameras/iq/) |1.3.27|
|[Jabra Panacast3 Camera](https://www.jabra.com/business/video-conferencing/jabra-panacast)|1.3.9.12|
|[Jabra Panacast 50 ビデオ バー](https://www.jabra.com/business/video-conferencing/jabra-panacast-50)|1.9.3|
|[Lenovo ThinkSmart Cam Camera](https://www.lenovo.com/us/en/accessories-and-monitors/webcams-and-video/webcams/SMARTOF-BO-ThinkSmart-Cam/p/4Y71C41660)|1.0.111.4|
|[Lenovo ThinkSmart Bar](https://www.lenovo.com/us/en/virtual-reality-and-smart-devices/smart-collaboration/thinksmart/ThinkSmart-Bar/p/11SP1TSSDBR)|0.9.3|
|Lenovo ThinkSmart Bar Expand XL|5.9.5|
|[Logitech Brio](https://www.logitech.com/product/brio)   |V2.2.50| &#x2714; |
|[Logitech 930e](https://www.logitech.com/product/c930e-webcam)   | 8.0.914   | &#x2714; |
|[Logitech Rally](https://www.logitech.com/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Logitech Rally Bar](https://www.logitech.com/products/video-conferencing/room-solutions/rallybar.960-001308.html)   |10.3.82|
|[Logitech Rally Bar Mini](https://www.logitech.com/en-us/products/video-conferencing/room-solutions/rallybarmini.960-001336.html) |10.5.880|
|[Logitech MeetUp](https://www.logitech.com/product/meetup-conferencecam)   |オーディオ — 1.0.172 <br/> ビデオ — 1.0.156  |
|[Logitech ConferenceCam Connect](https://www.logitech.com/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Logitech Group](https://www.logitech.com/product/conferencecam-group)   |8.5.778   |
|[Logitech PTZ Pro](https://www.logitech.com/product/conferencecam-ptz-pro)   | 1.1.219   |
|[Logitech PTZ Pro 2](https://www.logitech.com/product/conferencecam-ptz-pro2)   |
|[Logitech Scribe](https://www.logitech.com/en-us/products/video-conferencing/room-solutions/scribe.960-001332.html) | 1.1.1 | &#x2714; |
|[Nureva HDL300](https://www.nureva.com/audio-conferencing/hdl300) |2.3.6|
|[Poly EagleEye Cube カメラ](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.html)  |1.2.0 |
|[Polycom EagleEye IV](https://www.poly.com/us/en/products/video-conferencing/eagleeye/eagleeye-iv)   |1.0.0   |
|[Polycom CX5100](https://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl)   | 1.2.0.70232   |
|[Polycom EagleEye Director II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom Studio サウンドバー](https://www.polycom.com/hd-video-conferencing/room-video-systems/polycom-studio.html)|1.1.2.000570|
|[Poly Sync 40](https://www.poly.com/us/en/products/phones/sync/sync-40)|0.0.94.1461|
|[Poly Sync 60](https://www.poly.com/us/en/products/phones/sync/sync-60)|0.0.150.1671|
|[Polycom Trio 8500 / 8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[Poly Trio C60](https://www.poly.com/us/en/products/phones/trio/trio-c60)  |5.9.5.3066|
|[Poly Studio P15 ビデオ バー](https://www.poly.com/us/en/products/video-conferencing/studio-p/studio-p15)|1.2.0.000287 |
|[EPOS SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[EPOS SP20](https://www.eposaudio.com/en/us/enterprise/products/sp-20-ml-142ee5ca-speakerphone-1000226)   |1.2.15   |
|[EPOS SP30](https://www.eposaudio.com/en/us/enterprise/products/sp-30-78c0cecc-bluetooth-speakerphone-1000223)   |2.1.52  |
|[EPOS SP30T](https://www.eposaudio.com/en/us/enterprise/products/sp-30t-b949fe9a-bluetooth-speakerphone-1000225)  |3.2.63  |
|[EPOS Expand 80T + 2 Extension Mics](https://www.eposaudio.com/en/us/enterprise/products/expand-80t-bluetooth-speakerphone-1000203) |Speakerphone — 4.6.55 <br/> Extension Mic — 0.2.314|
|[EPOS Expand Capture 5](https://www.eposaudio.com/en/us/enterprise/products/expand-capture-5-speakerphone-1000895)  |1.0.1|
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK&trade;-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[ヤマハ YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100c   |
|[ヤマハ YVC-1000MS](https://uc.yamaha.com/products/conference-phones/usb-bluetooth/) |1.0.0 |
|[Yealink CP900](https://www.yealink.com/products_150.html) |100.20.0.29 |
|[Yealink UVC30](https://www.yealink.com/product/microsoft-teams-room-system-uvc30)| 105.420.0.11 |  &#x2714; |
|[Yealink UVC40 All-in-one ビデオ バー](https://www.yealink.com/product/usb-videobar-uvc40) |128.410.0.10|  
|[Shure Intellimix P300 オーディオ プロセッサ](https://www.shure.com/products/mixers/p300)+</br></br> [Shure MXA 310 テーブル アレイ マイク](https://www.shure.com/products/microphones/mxa310) | 4.1 |
|[Shure Intellimix P300 オーディオ プロセッサ](https://www.shure.com/products/mixers/p300) + </br></br> [Shure MXA 910 + Intellimix シーリング アレイ マイク](https://www.shure.com/products/microphones/mxa910) | 4.1|
|[Shure Intellimix P300 オーディオ プロセッサ](https://www.shure.com/products/mixers/p300)+</br></br> [Shure MXA 310 Table Array Mic ](https://www.shure.com/products/microphones/mxa310) +</br></br> [MXN5W-C Ceiling speaker](https://www.shure.com/en-US/products/loudspeakers/mxn5)| P300 DSP: 4.1.11 </br> MXA310 Table Array マイク: 4.1.41 </br> MXN5W-C スピーカー: 1.0.4 |
|[Shure Intellimix P300 オーディオ プロセッサ](https://www.shure.com/products/mixers/p300) + </br></br> [Shure MXA 910 with Intellimix Ceiling Array Mic](https://www.shure.com/products/microphones/mxa910) +</br></br> [MXN5W-C Ceiling speaker](https://www.shure.com/en-US/products/loudspeakers/mxn5)| P300 DSP: 4.1.11 </br> MXA910 Ceiling Array マイク: 4.1.41 </br> MXN5W-C スピーカー: 1.0.4 |
|[Shure MXA 710 2ft Table Linear Array Microphone](https://www.shure.com/products/microphones/mxa710) + </br></br> [Shure Intellimix P300 オーディオ プロセッサ](https://www.shure.com/products/mixers/p300) +</br></br> [MXN5-C Ceiling Speaker](https://www.shure.com/en-US/products/loudspeakers/mxn5)| MXA710 2ft Table Linear Array Mic: 1.2.0 </br> P300 DSP: 4.4.8 </br> MXN5-C スピーカー: 1.1.1 |
|[Shure MXA 710 4ft Wall Linear Array Microphone](https://www.shure.com/products/microphones/mxa710) + </br></br> [Shure Intellimix P300 オーディオ プロセッサ](https://www.shure.com/products/mixers/p300) +</br></br> [MXN5-C Ceiling Speaker](https://www.shure.com/en-US/products/loudspeakers/mxn5)| MXA710 4ft Wall Linear Array Mic: 1.2.0 </br> P300 DSP: 4.4.8 </br> MXN5-C スピーカー: 1.1.1 |
|[Shure MXA 910 と Intellimix Ceiling Array Microphone](https://www.shure.com/products/microphones/mxa910) + </br> [Shure Intellimix Room Software](https://www.shure.com/products/software/intellimix_room) +</br> [クセロン UC-C100-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T)| Shure Intellimix Room Software: 3.0.4.14 </br> Shure MXA 910 with Intellimix Ceiling Array Microphone: 4.4.11 </br> Shure MXN5-C スピーカー: 1.2.1 </br> クセロン UC-C100-T: WINDOWS IOT 19h2/20h2 OS バージョン (4.8.31.0 の場合) </br> BIOS: ASUS Tek Computer INC 9934 8/27/2020 </br> CPU: i5-9500TCPU </br> 物理メモリ: 8 GB RAM |
|[Biamp Tesira Fore AVB VT4 Fixed audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ &Dagger;</br></br> [ゼンハイザー TeamConnect Ceiling 2 マイク](https://sennheiser.com/tcc2)+ &Dagger;</br></br> [Tesira EX-UBT](https://www.biamp.com/products/tesira/tesira-expanders) &Dagger; |  Biamp DSP: 3.12.0.15  </br></br> TCC2: 1.3.3 </br></br> EX-UBT: 3.12.0.15 |
|[Biamp Tesira FORTÉ AVB VT4 オーディオ DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br></br>[Biamp Parlé TCM-XA シーリング マイク](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br></br> [Biamp Desono C-IC6 天井埋め込み型スピーカー](https://www.biamp.com/products/tesira-speakers)| Audio FW バージョン: 3.15|
|[Biamp TesiraFORTE AVB VT4](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br></br>[Parle TTM-X(テーブル マイク)](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br></br>[Ex-UBT]() |Audio FW バージョン: 3.15|
|[Bose ControlSpace EX-440C DSP + </br>Bose P2600A AmpLink アンプ +</br> ゼンハイザー TCC2 シーリング マイク + </br> Bose EdgeMax EM180 天井埋め込み型スピーカー](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  |  |
|[Bose ControlSpace EX-440C DSP + </br>Bose P2600A AmpLink アンプ + ゼンハイザー TCC2 シーリング マイク + </br> Bose DesignMax DM2C-P 天井埋め込み型スピーカー](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  |  |
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Bose P2600A AmpLink プロパイア +</br> [Sennheiser TCC2 Ceiling Microphone](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [DesignMax DM2C -LP Ceiling Speaker](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/designmax/designmax_dm2c_lp.html#v=designmax_dm2c_lp_black) | Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  | 
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Bose P2600A AmpLink プロパイア+</br> [Sennheiser TCC2 Ceiling Microphone](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [EdgeMax EM180 Ceiling Speaker](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/edgemax/edgemax_em180.html#v=edgemax_em180_white) | Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  |
|QSC Q-SYS Core ([110f](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-110f/), [8 Flex](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-8-flex/), [Nano](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-nano/), or [NV-32-H](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/nv-32-h-core-capable/)) + </br> [Sennheiser TCC2 Ceiling Microphone](https://en-us.sennheiser.com/tcc2) + </br> QSC リペ-ト[(SPA シリーズまたは](https://www.qsc.com/solutions-products/power-amplifiers/installed/non-network/low-power-applications/spa-series/) [CX-Q シリーズ](https://www.qsc.com/solutions-products/power-amplifiers/installed/network/cx-q-series/)) + </br> [QSC AcousticDesign シリーズ スピーカー](https://www.qsc.com/solutions-products/loudspeakers/installed/passive/solutions/acousticdesigntm-series-solutions/) + </br> QSC IP カメラ ([PTZ-IP 20x60](https://www.qsc.com/solutions-products/q-sys-ecosystem/video/ptz-ip-conference-cameras/), [PTZ-IP 12x72](https://www.qsc.com/solutions-products/q-sys-ecosystem/video/ptz-ip-conference-cameras/)) 省略可能 + </br> [QSC Q-SYS I/O USB ブリッジ (省略可能](https://www.qsc.com/solutions-products/q-sys-ecosystem/audio-io-peripherals/io-usb-bridge/) ) | QSC Q-SYS Core、PTZ-IP カメラ、I/O USB ブリッジ: QSC Q-SYS Designer 9.0.1-2104.022 </br> Sennheiser TCC2 Ceiling Microphone: TCC2 - 1.5.1, Dante 1.2.0 </br> QSC の増幅: N/A </br> QSC AcousticDesign シリーズ ラウドスピーカー: N/A | 


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

|会議室の種類|ユーザー数|推奨されるマイクとスピーカーの最大間隔|
|:-----|:-----|:-----|
|**フォーカス** <br/> 10' x 9'   |2 ～ 4  |1.5 m  |
|**小規模** <br/> 16' x 16'  |4 ～ 6  |2.0 m  |
|**中規模** <br/> 18' x 20'  |6 ～ 12  |2.4 m  |
|**大規模** <br/> 15' x 32'  |12 ～ 16  |3 m <br/> この間隔は、接続されている各サテライト マイクの対象エリアにも適用されます。  |

**Microsoft Teams Rooms の認定ビデオ周辺機器**

|会議室の種類|ユーザー数|
|:-----|:-----|
|**フォーカス** <br/> 10' x 9'  |2 ～ 4  |
|**小規模** <br/> 16' x 16'  |4 ～ 6  |
|**中規模** <br/> 18' x 20'  |6 ～ 12  |
|**大規模** <br/> 15' x 32'  |12 ～ 16  |

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
