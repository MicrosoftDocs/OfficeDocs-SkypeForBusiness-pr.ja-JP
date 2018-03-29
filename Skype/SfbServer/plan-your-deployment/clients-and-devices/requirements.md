---
title: Skype Room Systems バージョン 2 の要件
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
description: This article summarizes the requirements for supporting a Skype Room Systems v2.
ms.openlocfilehash: ca922efa719b956da5516958ce6f684b013ddc62
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-systems-v2-requirements"></a>Skype Room Systems バージョン 2 の要件
 
This article summarizes the requirements for supporting a Skype Room Systems v2. 
  
Your deployment will involve account creation as described in [Deploy Skype Room Systems v2](../../deploy/deploy-clients/room-systems-v2.md) and setting up a meeting console as described in [Configure a Skype Room Systems v2 console](../../deploy/deploy-clients/console.md). You may also need to refer to [Skype for Business add-on licensing](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).
  
## <a name="hardware-requirements"></a>ハードウェア要件

Skype Room Systems v2 can scale to different room sizes through accessories depending on audio and video peripherals. Audio and video peripherals connect to Skype Room Systems v2 via a USB or HDMI connection on the docking device. また、以下も必要です。
  
- A  32GB or larger USB disk you will configure as bootable Windows installation media for Windows 10 Enterprise. 
    
- 次のいずれかのタブレット:
    
**Supported tablets**


|**Tablet**|**Processor**|**RAM**|**Disk**|
|:-----|:-----|:-----|:-----|
|Surface Pro 4 &sup1;  <br/> |Core i5  <br/> |4GB  <br/> |128GB  <br/> |
|Surface Pro 4 &sup1;  <br/> |Core i5  <br/> |8GB  <br/> |256GB  <br/> |
|Surface Pro &sup1; <br/> |Core i5  <br/> |4GB  <br/> |128GB  <br/> |
|Surface Pro &sup1; <br/> |Core i5  <br/> |8GB  <br/> |256GB  <br/> |
|Surface Pro &sup1; <br/> |Core i7  <br/> |8GB  <br/> |128GB  <br/> |
|Surface Pro &sup1; <br/> |Core i7  <br/> |16GB  <br/> |512GB  <br/> |
|Surface Pro &sup1; <br/> |Core i7  <br/> |16GB  <br/> |1TB  <br/> |
   
&sup1; — Core M3 processors are not supported on this model.
    
 
    
- 会議室のテーブルにタブレットを固定するためのオプションとして、次のドッキング ステーションのいずれか 1 つ。 
    
  - [Logitech SmartDock](https://www.logitech.com/en-us/product/smartdock)
    
  - [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
    
  - [Polycom MSR Series](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl)

  - [Lenovo Hub 500](https://www3.lenovo.com/us/en/hub500)  
<!-- HP dock is still pending  -->  
 
**Certified firmware versions for USB audio and video peripherals**
|**Skype Room Systems v2 peripherals**|**Firmware version certified for Skype Room Systems v2**|
|:-----|:-----|
|[Logitech BRIO](https://www.logitech.com/en-us/product/brio) <br/> ||
|[Logitech MeetUp](http://www.logitech.com/en-us/product/meetup-conferencecam) <br/> |Audio - 1.0.172  <br/> Video - 1.0.156  <br/> |
|[Logitech ConferenceCam Connect](http://www.logitech.com/en-us/product/conferencecam-connect) <br/> |1.1.248.0  <br/> 1.1.684  <br/> |
|[Logitech Group](http://www.logitech.com/en-us/product/conferencecam-group) <br/> |8.5.778  <br/> |
|[Logitech 930e](http://www.logitech.com/en-us/product/c930e-webcam) <br/> | 8.0.914 <br/> |
|[Logitech PTZ Pro](http://www.logitech.com/en-us/product/conferencecam-ptz-pro) <br/> | 1.1.219 <br/> |
|[Polycom RealPresence Trio](http://www.polycom.com/voice-conferencing-solutions/conference-phones/realpresence-trio.mdl) <br/> |5.4.4.7511  <br/> |
|[Polycom EagleEye IV](http://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl) <br/> |1.0.0  <br/> |
|[Polycom CX5100](http://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl) <br/> | 1.2.0.70232 <br/> |
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc) <br/> |2.0.12.0  <br/> |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml) <br/> |1.2.15  <br/> |
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209) <br/> |2.10.0  <br/> |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710) <br/> |1.8.0  <br/> |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810) <br/> |1.2.23  <br/> |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/) <br/> |100c  <br/> |
   
- **USB エクステンダー**:
    
  - タブレットのドック上の USB ポートは USB 3.0 対応です。 USB 2.x エクステンダーを使用することはできますが、その場合は転送先の速度が USB 2.x の速度に制限されるため、USB 3.0 の周辺機器に対しては推奨されません。
    
  - エクステンダーは USB 2.0 以降の仕様に適合している必要があります。
    
  - タブレットのドックは、外部 USB ハブ拡張のステージを少なくとも 2 つサポートします。 2 つを超える USB ハブを直列で接続する必要がある場合は、そのような接続がサポートされていることをドックのメーカーに確認する必要があります。
    
- 室内での優先 GbE 接続。 適切な長さのイーサネット ケーブル。
    
- HDMI 接続を搭載した最大 2 台の 1080p ディスプレイ。 適切な長さの HDMI ケーブル。
    
    > [!NOTE]
    > 屋内ディスプレイの前面として使用される消費者向け TV では、スタンバイ モードからアクティブなビデオ ソースに自動的に切り替わるように、HDMI の CEC (Consumer Electronics Control) 機能をサポート/有効にする必要があります。 この機能はすべての TV でサポートされるものではありません。 
  
> [!NOTE]
> Skype Room Systems v2 does not use a keyboard. 必要な場合は、管理者がオンスクリーン キーボードを使用します。 A USB keyboard or mouse will be required when imaging the Skype Room Systems v2 device. 
  
次の表に、部屋のサイズに基づいた、周辺機器に関する推奨事項を示します。
  
**Skype Room Systems v2 Certified Audio Peripherals**

|**Room Type**|**Number of People**|**Recommended maximum distance from microphone to person speaking**|**Device by maximum room size**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|**Focus** <br/> 10' x 9'  <br/> |2 ~ 4  <br/> |1.5m  <br/> |Logitech Connect  <br/> |Logitech Connect デバイスはカメラを搭載しているため、ローカルの会議の出席者をキャプチャするために (テーブルの中央ではなく) 部屋の前方に設置する必要があります。  <br/> |
|**Small** <br/> 16' x 16'  <br/> |4 ～ 6  <br/> |2.0m  <br/> |Jabra 510  <br/> Sennheiser SP20  <br/> |大規模な部屋の場合、再生の音量が制限される場合があります。  <br/> |
|**Medium** <br/> 18' x 20'  <br/> |6 ～ 12  <br/> |2.4m  <br/> |Jabra 710  <br/> Jabra 810  <br/> Logitech MeetUp  <br/> Logitech Group  <br/> Polycom Trio  <br/> Polycom CX5100  <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000MS  <br/> |Logitech MeetUp はカメラを搭載しているため、ローカルの会議の出席者をキャプチャするために (テーブルの中央ではなく) 部屋の前方に設置する必要があります。  <br/> 一般的に、長方形または U 字型のテーブルが置かれている部屋では、追加のサテライト マイクを使用するメリットがある可能性があります。  <br/> SP 220 MS はデイジー チェーン構成で使用される必要があります。  <br/> |
|**Large** <br/> 15' x 20'  <br/> |12 ～ 16  <br/> |3m  <br/> この距離は、当該のオーディオ デバイスに接続されている追加の各サテライト マイクによってカバーされる領域にも適用されます。  <br/> |Logitech Group + サテライト マイク  <br/> Polycom Trio + サテライト マイク  <br/> Polycom CX5100 + サテライト マイク  <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000MS + サテライト マイク  <br/> |この行に示されているすべてのオーディオ デバイスはサテライト マイクのオプションをサポートします。  <br/> CX5100 はビルトインの 360 度カメラを搭載しているため、テーブルの中央に配置できます。  <br/> SP 220 MS はデイジー チェーン構成で使用される必要があります。  <br/> |
   
**Skype Room Systems v2 Certified Video Peripherals**

|**Room Type**|**Number of People**|**Device by Optimal room size**|**Comments**|
|:-----|:-----|:-----|:-----|
|**Focus** <br/> 10' x 9'  <br/> |2 ~ 4  <br/> |Logitech Connect  <br/> Logitech MeetUp  <br/> Polycom CX5100  <br/> ||
|**Small** <br/> 16' x 16'  <br/> |4 ～ 6  <br/> |Logitech C930e  <br/> Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100  <br/> |Logitech PTZ Pro often bundled with Logitech Group  <br/> |
|**Medium** <br/> 18' x 20'  <br/> |6 ～ 12  <br/> |Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100  <br/> ||
|**Large** <br/> 15' x 20'  <br/> |12 ～ 16  <br/> |Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100  <br/> ||
   
## <a name="required-software-downloads"></a>必要なソフトウェアのダウンロード

You will need the following downloads to build your own Skype Room Systems v2 image:
  
- The [Skype Room Systems v2 installation package](https://go.microsoft.com/fwlink/?linkid=851168).
    
- Windows 10 Enterprise Creators Update (英語版、ビルド 1703) の 64 ビット バージョンのコピーの入手。 
    
    > [!NOTE]
    > The 64-bit version of Windows 10 Enterprise Anniversary edition (English language, version 1607) is no longer supported as of Skype Room Systems v2 release 3.0.12.0 (update 3). 
  
- The supported [Surface Pro 4 drivers](https://go.microsoft.com/fwlink/?linkid=856887) or [Surface Pro drivers](https://go.microsoft.com/fwlink/?linkid=856888).
    
These downloads need to be combined into a bootable Windows installation media disk in a specific way, described further in [Configure a Skype Room Systems v2 console](../../deploy/deploy-clients/console.md). 
  
In addition, you will probably want a copy of the [Powershell script](https://go.microsoft.com/fwlink/?linkid=870105) used to provision Skype Room Systems v2 accounts.
  
## <a name="see-also"></a>関連項目

#### 

[Plan for Skype Room Systems v2](skype-room-systems-v2-0.md)
  
[Deploy Skype Room Systems v2](../../deploy/deploy-clients/room-systems-v2.md)
  
[Configure a Skype Room Systems v2 console](../../deploy/deploy-clients/console.md)
  
[Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)
#### 

[Skype for Business add-on licensing](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)

