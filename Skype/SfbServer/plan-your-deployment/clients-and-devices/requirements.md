---
title: マイクロソフト チームの会議室の要件
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection: M365-voice
description: この資料は、マイクロソフト チームの会議室をサポートするための要件をまとめたものです。
ms.openlocfilehash: aff26f2f69b134569b8792df79c2afa4e4a18318
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214506"
---
# <a name="microsoft-teams-rooms-requirements"></a>マイクロソフト チームの会議室の要件

この資料は、マイクロソフト チームの会議室をサポートするための要件をまとめたものです。 

[マイクロソフト チーム ルームの展開](../../deploy/deploy-clients/room-systems-v2.md)で説明したようにアカウントを作成し、[マイクロソフト チームの会議室のコンソールの構成](../../deploy/deploy-clients/console.md)で説明したように、ミーティング コンソールの設定、展開が含まれます。 

参照する場合もあります。

- [Skype for Business アドオンのライセンス](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [計画に基づいてオプションをライセンス: マイクロソフトのチーム会議室](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> マイクロソフト チームの会議室は、オンライン ビジネスのビジネス サーバー 2015、マイクロソフトのチーム、または Skype のビジネス サーバー 2019 の Skype、Skype での使用です。 <br><br>Lync Server 2013 のような以前のプラットフォームは、マイクロソフト チームの会議室を使用する必要もありません。

> [!NOTE]
> Prem の Exchange サーバーを使用すると、マイクロソフト チームの会議室には Exchange Server 2013 SP1 またはそれ以降の使用が必要です。

## <a name="hardware-requirements"></a>ハードウェア要件

マイクロソフト チームの会議室は、別の部屋のサイズによっては、オーディオとビデオの周辺機器、アクセサリを使用する拡張可能です。 この資料に記載されたハードウェアでは、Skype とチームの両方の会議モードをサポートします。  オーディオおよびビデオの周辺機器は、ドッキング デバイスに USB や HDMI 接続経由でマイクロソフト チームのルームに接続します。 また、以下も必要です。

- 32 GB またはより大きい USB ディスク 10 企業の Windows のブート可能な Windows インストール メディアとして構成します。 

- タブレットまたはコンソールは、次のいずれかです。

**サポートされるタブレット**

|タブレット|プロセッサ|RAM|ディスク|
|:-----|:-----|:-----|:-----|
|Surface Pro 6          |Core i5  |16 GB または 8 GB |128 GB またはそれ以上  |
|Surface Pro (第 5 世代)  |Core i5  |8 GB または 4 GB  |128 GB またはそれ以上  |
|Surface Pro 4          |Core i5  |8 GB または 4 GB  |128 GB またはそれ以上  |

> [!NOTE]
> M3 プロセッサはサポートされていません。

**サポートされているコンソール**

|コンソール|プロセッサ|RAM|ディスク|
|:-----|:-----|:-----|:-----|
|[Lenovo ThinkSmart ハブ 500](https://www3.lenovo.com/us/en/hub500) |Core i5  |8GB  |128GB  |  
|[会議室 G2 の HP のエリート スライス](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5  |8GB  |128GB  |  

- 会議にタブレットをセキュリティで保護する次のようなドッキング ステーション オプションのいずれかのルームのテーブルです。 

  - [Logitech (ロジクール) SmartDock](https://partnersolutions.skypeforbusiness.com/solutionscatalog/all/logitech-smart-dock)

  - [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system )

  - [ポリコム MSR シリーズ](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)



**USB オーディオおよびビデオの周辺機器についての認定済みファームウェア バージョン**

|マイクロソフト チームの会議室の周辺機器|ファームウェアのバージョンの Microsoft チームの会議室の認定|
|:-----|:-----|
|[BRIO の logitech (ロジクール)](https://www.logitech.com/en-us/product/brio) <br/> |v240|
|[MeetUp の logitech (ロジクール)](http://www.logitech.com/en-us/product/meetup-conferencecam) <br/> |オーディオ - 1.0.172  <br/> ビデオ - 1.0.156  <br/> |
|[Logitech (ロジクール) の ConferenceCam を接続します。](http://www.logitech.com/en-us/product/conferencecam-connect) <br/> |1.1.248.0  <br/> 1.1.684  <br/> |
|[Logitech (ロジクール) のグループ](http://www.logitech.com/en-us/product/conferencecam-group) <br/> |8.5.778  <br/> |
|[930e の logitech (ロジクール)](http://www.logitech.com/en-us/product/c930e-webcam) <br/> | 8.0.914 <br/> |
|[Logitech (ロジクール) PTZ Pro](http://www.logitech.com/en-us/product/conferencecam-ptz-pro) <br/> | 1.1.219 <br/> |
|[Logitech (ロジクール) PTZ Pro 2](http://www.logitech.com/en-us/product/conferencecam-ptz-pro2) <br/> |
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

  - タブレットのドッキング ステーションの USB ポートは、USB 3.0 の互換性です。 USB 2.x のエクステンダーを使用することができますが、これは制限する向こう側の末端に USB 2.x の速度を行うのでお勧めしません USB 3.0 の周辺機器の

  - エクステンダーには、USB 2.0 またはより新しい仕様を満たす必要があります。

  - タブレットのドッキング ステーションでは、外部の USB ハブの拡張機能の 2 つ以上の段階をサポートします。 接続する必要がある複数の系列の 2 つの USB ハブはかどうか、実行はサポートされてを確認するドッキング ステーションの製造元に確認する必要があります。

- ルームで GbE 接続ワイヤード (有線)。 適切な長さのケーブルです。

- HDMI 接続で最大 2 つの 1080 p 表示します。 適切な長さの HDMI ケーブルです。

    > [!NOTE]
    > 屋内ディスプレイの前面として使用される消費者向け TV では、スタンバイ モードからアクティブなビデオ ソースに自動的に切り替わるように、HDMI の CEC (Consumer Electronics Control) 機能をサポート/有効にする必要があります。 この機能はすべての TV でサポートされるものではありません。 

> [!NOTE]
> マイクロソフト チームの会議室では、キーボードは使用しません。 管理者が使用する必要がありますが必要な場合、スクリーン キーボードです。 マイクロソフト チーム室デバイスをイメージングするとき、USB キーボードまたはマウスが必要があります。 

次の表は、部屋のサイズに基づく周辺機器に関する推奨事項を提供します。

**オーディオ周辺機器を認定するマイクロソフトのチーム会議室**

|ルームのタイプ|人の数|話す人にマイクからの推奨される最大距離|最大の部屋のサイズによって、デバイス|コメント|
|:-----|:-----|:-----|:-----|:-----|
|**フォーカス** <br/> 10' × 9 '  <br/> |2-4  <br/> |1.5 m  <br/> |Logitech (ロジクール) を接続します。  <br/> |Logitech (ロジクール) の接続デバイスには、ローカル会議の出席者をキャプチャする部屋 (テーブルの中心ではない) の前面に配置する必要がありますので、カメラが含まれます。  <br/> |
|**小さな** <br/> 16' × 16 '  <br/> |4-6  <br/> |2.0 m  <br/> |Jabra 510  <br/> Sennheiser SP20  <br/> |再生ボリュームが大きい部屋の限られた可能性があります。  <br/> |
|**中** <br/> 18' x 20 '  <br/> |6-12  <br/> |2.4 m  <br/> |Jabra 710  <br/> Jabra 810  <br/> MeetUp の logitech (ロジクール)  <br/> Logitech (ロジクール) のグループ  <br/> ポリコムの 3 つ  <br/> ポリコム CX5100  <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000 ミリ秒  <br/> |Logitech (ロジクール) の MeetUp が含まれています、カメラには、部屋 (ローカル会議の出席者をキャプチャするのにはテーブルの中心ではない) の前面に配置する必要があります。  <br/> 一般に、長い長方形または u 形のテーブルでルームは、マイクの他のサテライトから利点可能性があります。  <br/> デイジー ・ チェーン構成で 220 MS SP を使用する必要があります。  <br/> |
|**大規模です** <br/> 15' x 32 '  <br/> |12-16  <br/> |3 m  <br/> この距離は、対象のオーディオ デバイスに接続されている各追加サテライト マイクがカバーする領域にも適用されます。  <br/> |Logitech (ロジクール) のグループ + サテライトのマイク  <br/> ポリコム トリオ + サテライト マイク  <br/> ポリコム CX5100 + サテライトのマイク  <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000 ミリ秒 + サテライトのマイク  <br/> |この行サポート サテライトのマイクのオプションに記載されているすべてのオーディオのデバイスです。  <br/> CX5100 には、デバイスは、テーブルの中央に配置できるように、組み込みの 360 度のカメラが含まれます。  <br/> デイジー ・ チェーン構成で 220 MS SP を使用する必要があります。  <br/> |

**ビデオ周辺機器を認定するマイクロソフトのチーム会議室**

|ルームのタイプ|人の数|最適な部屋のサイズによって、デバイス|コメント|
|:-----|:-----|:-----|:-----|
|**フォーカス** <br/> 10' × 9 '  <br/> |2-4  <br/> |Logitech (ロジクール) を接続します。  <br/> MeetUp の logitech (ロジクール)  <br/> ポリコム CX5100  <br/> ||
|**小さな** <br/> 16' × 16 '  <br/> |4-6  <br/> |Logitech (ロジクール) C930e  <br/> MeetUp の logitech (ロジクール)  <br/> BRIO の logitech (ロジクール)  <br/> Logitech (ロジクール) PTZ Pro  <br/> ポリコム MSR  <br/> ポリコム CX5100  <br/> |Logitech (ロジクール) PTZ Pro の logitech (ロジクール) のグループにバンドルされることがよくあります。  <br/> |
|**中** <br/> 18' x 20 '  <br/> |6-12  <br/> |MeetUp の logitech (ロジクール)  <br/> BRIO の logitech (ロジクール)  <br/> Logitech (ロジクール) PTZ Pro  <br/> ポリコム MSR  <br/> ポリコム CX5100  <br/> ||
|**大規模です** <br/> 15' x 32 '  <br/> |12-16  <br/> |Logitech (ロジクール) PTZ Pro  <br/> ポリコム MSR  <br/> ポリコム CX5100  <br/> ||

 > [!NOTE]
 > ルームのディスプレイの解像度の前面を 1920x1080p を超えるに設定してください。

## <a name="required-software-downloads"></a>必要なソフトウェアをダウンロードします。

マイクロソフト チームの会議室のイメージを作成するには、するには、[マイクロソフト チームの会議室のコンソールの構成](../../deploy/deploy-clients/console.md)の指示に従います。 指示に従って、インストール プロセスのすべての必要なソフトウェアをダウンロードします。 

> [!NOTE]
> IT プロフェッショナルには、ボリューム ライセンス契約を通じて Windows 10 企業の ISO ファイルへのアクセスを必要があります。

さらに、 [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)、マイクロソフト チームの会議室のアカウントのプロビジョニングに使用できるのコピーにする必要があります。

## <a name="see-also"></a>関連項目

[マイクロソフト チームの会議室のプラン](skype-room-systems-v2-0.md)

[マイクロソフト チームの会議室を配置します。](../../deploy/deploy-clients/room-systems-v2.md)

[マイクロソフト チームの会議室のコンソールを構成します。](../../deploy/deploy-clients/console.md)

[Microsoft Teams Rooms を管理する](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

[Skype for Business アドオンのライセンス](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
