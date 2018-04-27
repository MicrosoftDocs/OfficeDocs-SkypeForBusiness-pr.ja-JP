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
description: この資料では、Skype ルーム システム v2 をサポートするための要件について説明します。
ms.openlocfilehash: 6b0265c8fc6269b7451a7757b8266078433ec9d5
ms.sourcegitcommit: 5cc51e2d3898fccd1969accedb5e185a332e83bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2018
---
# <a name="skype-room-systems-v2-requirements"></a>Skype Room Systems バージョン 2 の要件
 
この資料では、Skype ルーム システム v2 をサポートするための要件について説明します。 
  
[Skype ルーム システムの配置のバージョン 2](../../deploy/deploy-clients/room-systems-v2.md)で説明したようにアカウントを作成し、 [Skype ルーム システム v2 のコンソールの構成](../../deploy/deploy-clients/console.md)で説明したように、ミーティング コンソールの設定、展開が含まれます。 [Skype ビジネス アドオン ライセンス](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)を参照する必要もあります。
  
## <a name="hardware-requirements"></a>ハードウェア要件

Skype ルーム システム v2 は、別の部屋のサイズによっては、オーディオとビデオの周辺機器、アクセサリを使用する拡張可能です。 オーディオおよびビデオの周辺機器は、ドッキング デバイスに USB や HDMI 接続経由で Skype ルーム システム v2 に接続します。 また、以下も必要です。
  
- 32 GB またはより大きい USB ディスク 10 企業の Windows のブート可能な Windows インストール メディアとして構成します。 
    
- 次のいずれかのタブレット:
    
**サポートされているタブレット**


|**タブレット**|**プロセッサ**|**RAM**|**ディスク**|
|:-----|:-----|:-----|:-----|
|Surface Pro 4 & sup1;  <br/> |Core i5  <br/> |4 GB  <br/> |128 GB  <br/> |
|Surface Pro 4 & sup1;  <br/> |Core i5  <br/> |8 GB  <br/> |256 GB  <br/> |
|Surface Pro & sup1; <br/> |Core i5  <br/> |4 GB  <br/> |128 GB  <br/> |
|Surface Pro & sup1; <br/> |Core i5  <br/> |8 GB  <br/> |256 GB  <br/> |
|Surface Pro & sup1; <br/> |Core i7  <br/> |8 GB  <br/> |128 GB  <br/> |
|Surface Pro & sup1; <br/> |Core i7  <br/> |16 GB  <br/> |512 GB  <br/> |
|Surface Pro & sup1; <br/> |Core i7  <br/> |16 GB  <br/> |1 TB  <br/> |
   
& sup1;-M3 コアは、このモデルではサポートされていません。
    
 
    
- 会議室のテーブルにタブレットを固定するためのオプションとして、次のドッキング ステーションのいずれか 1 つ。 
    
  - [Logitech (ロジクール) SmartDock](https://www.logitech.com/en-us/product/smartdock)
    
  - [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
    
  - [ポリコム MSR シリーズ](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

  - [Lenovo ハブ 500](https://www3.lenovo.com/us/en/hub500)  
<!-- HP dock is still pending  -->  
 
**オーディオおよびビデオの USB の周辺機器のファームウェアのバージョンの認定**
|**Skype ルーム システム v2 の周辺機器**|**ファームウェアのバージョンの Skype ルーム システム v2 の認定**|
|:-----|:-----|
|[BRIO の logitech (ロジクール)](https://www.logitech.com/en-us/product/brio) <br/> ||
|[MeetUp の logitech (ロジクール)](http://www.logitech.com/en-us/product/meetup-conferencecam) <br/> |オーディオ - 1.0.172  <br/> ビデオ - 1.0.156  <br/> |
|[Logitech (ロジクール) の ConferenceCam を接続します。](http://www.logitech.com/en-us/product/conferencecam-connect) <br/> |1.1.248.0  <br/> 1.1.684  <br/> |
|[Logitech (ロジクール) のグループ](http://www.logitech.com/en-us/product/conferencecam-group) <br/> |8.5.778  <br/> |
|[930e の logitech (ロジクール)](http://www.logitech.com/en-us/product/c930e-webcam) <br/> | 8.0.914 <br/> |
|[Logitech (ロジクール) PTZ Pro](http://www.logitech.com/en-us/product/conferencecam-ptz-pro) <br/> | 1.1.219 <br/> |
|[RealPresence の 3 つのポリコム](http://www.polycom.com/voice-conferencing-solutions/conference-phones/realpresence-trio.mdl) <br/> |5.4.4.7511  <br/> |
|[ポリコム EagleEye IV](http://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl) <br/> |1.0.0  <br/> |
|[ポリコム CX5100](http://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl) <br/> | 1.2.0.70232 <br/> |
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc) <br/> |2.0.12.0  <br/> |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml) <br/> |1.2.15  <br/> |
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209) <br/> |2.10.0  <br/> |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710) <br/> |1.8.0  <br/> |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810) <br/> |1.2.23  <br/> |
|[Yamaha YVC 1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/) <br/> |100 c  <br/> |
   
- **USB エクステンダー**:
    
  - タブレットのドック上の USB ポートは USB 3.0 対応です。 USB 2.x エクステンダーを使用することはできますが、その場合は転送先の速度が USB 2.x の速度に制限されるため、USB 3.0 の周辺機器に対しては推奨されません。
    
  - エクステンダーは USB 2.0 以降の仕様に適合している必要があります。
    
  - タブレットのドックは、外部 USB ハブ拡張のステージを少なくとも 2 つサポートします。 2 つを超える USB ハブを直列で接続する必要がある場合は、そのような接続がサポートされていることをドックのメーカーに確認する必要があります。
    
- 室内での優先 GbE 接続。 適切な長さのイーサネット ケーブル。
    
- HDMI 接続を搭載した最大 2 台の 1080p ディスプレイ。 適切な長さの HDMI ケーブル。
    
    > [!NOTE]
    > 屋内ディスプレイの前面として使用される消費者向け TV では、スタンバイ モードからアクティブなビデオ ソースに自動的に切り替わるように、HDMI の CEC (Consumer Electronics Control) 機能をサポート/有効にする必要があります。 この機能はすべての TV でサポートされるものではありません。 
  
> [!NOTE]
> Skype ルーム システム v2 では、キーボードは使用しません。 必要な場合は、管理者がオンスクリーン キーボードを使用します。 Skype ルーム システム v2 デバイスをイメージングするとき、USB キーボードまたはマウスが必要があります。 
  
次の表に、部屋のサイズに基づいた、周辺機器に関する推奨事項を示します。
  
**オーディオ周辺機器を認定する Skype ルーム システム v2**

|**ルームのタイプ**|**人の数**|**話す人にマイクからの推奨される最大距離**|**最大の部屋のサイズによって、デバイス**|**コメント**|
|:-----|:-----|:-----|:-----|:-----|
|**フォーカス** <br/> 10' x 9'  <br/> |2 ~ 4  <br/> |1.5 m  <br/> |Logitech Connect  <br/> |Logitech Connect デバイスはカメラを搭載しているため、ローカルの会議の出席者をキャプチャするために (テーブルの中央ではなく) 部屋の前方に設置する必要があります。  <br/> |
|**小さな** <br/> 16' x 16'  <br/> |4 ～ 6  <br/> |2.0 m  <br/> |Jabra 510  <br/> Sennheiser SP20  <br/> |大規模な部屋の場合、再生の音量が制限される場合があります。  <br/> |
|**[中]** <br/> 18' x 20'  <br/> |6 ～ 12  <br/> |2.4 m  <br/> |Jabra 710  <br/> Jabra 810  <br/> Logitech MeetUp  <br/> Logitech Group  <br/> Polycom Trio  <br/> Polycom CX5100  <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000MS  <br/> |Logitech MeetUp はカメラを搭載しているため、ローカルの会議の出席者をキャプチャするために (テーブルの中央ではなく) 部屋の前方に設置する必要があります。  <br/> 一般的に、長方形または U 字型のテーブルが置かれている部屋では、追加のサテライト マイクを使用するメリットがある可能性があります。  <br/> SP 220 MS はデイジー チェーン構成で使用される必要があります。  <br/> |
|**大規模です** <br/> 15' x 20'  <br/> |12 ～ 16  <br/> |3 m  <br/> この距離は、当該のオーディオ デバイスに接続されている追加の各サテライト マイクによってカバーされる領域にも適用されます。  <br/> |Logitech Group + サテライト マイク  <br/> Polycom Trio + サテライト マイク  <br/> Polycom CX5100 + サテライト マイク  <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000MS + サテライト マイク  <br/> |この行に示されているすべてのオーディオ デバイスはサテライト マイクのオプションをサポートします。  <br/> CX5100 はビルトインの 360 度カメラを搭載しているため、テーブルの中央に配置できます。  <br/> SP 220 MS はデイジー チェーン構成で使用される必要があります。  <br/> |
   
**Skype ルーム システム v2 ビデオ周辺機器の認定**

|**ルームのタイプ**|**人の数**|**最適な部屋のサイズによって、デバイス**|**コメント**|
|:-----|:-----|:-----|:-----|
|**フォーカス** <br/> 10' x 9'  <br/> |2 ~ 4  <br/> |Logitech Connect  <br/> Logitech MeetUp  <br/> Polycom CX5100  <br/> ||
|**小さな** <br/> 16' x 16'  <br/> |4 ～ 6  <br/> |Logitech C930e  <br/> Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100  <br/> |Logitech (ロジクール) PTZ Pro の logitech (ロジクール) のグループにバンドルされることがよくあります。  <br/> |
|**[中]** <br/> 18' x 20'  <br/> |6 ～ 12  <br/> |Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100  <br/> ||
|**大規模です** <br/> 15' x 20'  <br/> |12 ～ 16  <br/> |Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100  <br/> ||
   
## <a name="required-software-downloads"></a>必要なソフトウェアのダウンロード

Skype ルーム システム v2 の独自のイメージを作成する次のダウンロードを必要となります。
  
- [Skype ルーム システム v2 のインストール パッケージ](https://go.microsoft.com/fwlink/?linkid=851168)です。
    
- Windows 10 Enterprise Creators Update (英語版、ビルド 1703) の 64 ビット バージョンのコピーの入手。 
    
    > [!NOTE]
    > Skype ルーム システム v2 リリース 3.0.12.0 (アップデート 3) は、Windows 10 企業の記念日の版 (英語、1607 のバージョン) の 64 ビット バージョンがサポートされていません。 
  
- [Surface Pro 4 ドライバー](https://go.microsoft.com/fwlink/?linkid=856887)のサポートされているか、 [Surface Pro のドライバー](https://go.microsoft.com/fwlink/?linkid=856888)です。
    
これらのダウンロードは、特定の方法で起動可能な Windows インストール メディアのディスクに結合する必要があります[Skype ルーム システム v2 のコンソールの構成](../../deploy/deploy-clients/console.md)で詳細に説明します。 
  
さらに、Skype ルーム システム v2 のアカウントを準備するための[Powershell スクリプト](https://go.microsoft.com/fwlink/?linkid=870105)のコピーを必要があります。
  
## <a name="see-also"></a>関連項目

#### 

[Skype ルームの計画システム v2](skype-room-systems-v2-0.md)
  
[Skype の部屋を配置するシステム v2](../../deploy/deploy-clients/room-systems-v2.md)
  
[Skype ルーム システム v2 のコンソールを構成します。](../../deploy/deploy-clients/console.md)
  
[Skype ルームの管理システム v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)
#### 

[Skype ビジネス アドオン ライセンス](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)

