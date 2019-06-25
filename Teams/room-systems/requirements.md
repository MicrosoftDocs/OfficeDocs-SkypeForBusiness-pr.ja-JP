---
title: Microsoft Teams の会議室の要件
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection: M365-voice
description: この記事では、Microsoft Teams のルームをサポートするための要件について説明します。
ms.openlocfilehash: d87d21c7b0111b4825f01b71a266e209edc2bccc
ms.sourcegitcommit: f7ec026accb0bb91ce62a9d5f24ac4b70a514c4e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2019
ms.locfileid: "35203994"
---
# <a name="microsoft-teams-rooms-requirements"></a>Microsoft Teams の会議室の要件

この記事では、Microsoft Teams のルームをサポートするための要件について説明します。 

「Microsoft teams ルームを[構成](console.md)する」の[](room-systems-v2.md)説明に従って、展開にはアカウントの作成が含まれます 

また、次の情報も参照する必要があります。

- [Skype for Business アドオンのライセンス](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [プランに基づくライセンスオプション: Microsoft Teams のルーム](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Microsoft Teams のルームは、Microsoft Teams、Skype for Business Server 2019、Skype for business Server 2015、または Skype for Business Online で使用することを目的としています。 <br><br>Lync Server 2013 などの以前のプラットフォームでは、Microsoft Teams のルームで動作することは想定されていません。

> [!NOTE]
> オンプレミスの Exchange server を使用している場合、Microsoft Teams ルームでは Exchange Server 2013 SP1 以降を使用する必要があります。

## <a name="hardware-requirements"></a>ハードウェア要件

Microsoft Teams のルームは、オーディオとビデオの周辺機器に応じて、アクセサリを使用してさまざまな部屋に拡大縮小できます。 この記事に記載されているハードウェアは、Skype と Teams の両方の会議モードをサポートしています。  オーディオおよびビデオの周辺機器は、ドッキングデバイスで USB または HDMI 接続を介して Microsoft Teams のルームに接続します。 また、以下も必要です。

- Windows 10 Enterprise 用の起動可能な Windows インストールメディアとして構成される 32 GB または大型の USB ディスク。 

- 次のタブレットまたはコンソールのいずれか。

**サポートされるタブレット**

|タブレット|プロセッサ|RAM|ディスク|
|:-----|:-----|:-----|:-----|
|Surface Pro 6          |Core i5  |16 GB または 8 GB |128GB 以上  |
|Surface Pro (第5世代)  |Core i5  |8 gb または 4 GB  |128GB 以上  |
|Surface Pro 4          |Core i5  |8 gb または 4 GB  |128GB 以上  |

- 会議室テーブルにタブレットをセキュリティで保護するための、次のドッキングステーションオプションのいずれか。 

  - [Logitech SmartDock](https://partnersolutions.skypeforbusiness.com/solutionscatalog/all/logitech-smart-dock)

  - [クリエイティブ](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system )

  - [Polycom MSR シリーズ](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)


**サポートされているコンソール**

|コンソール|プロセッサ|RAM|ディスク|ファームウェアのバージョン|
|:-----|:-----|:-----|:-----|:----|
|[Flex M150](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T)|Core i7|8GB |128GB|1.0.16.490|
|[会議室 G2 の HP エリート Slice](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5  |8GB  |128GB  | |
|[Microsoft Teams のルームでの HP エリート Slice G2 オーディオの準備](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8GB |128GB | |
|[Lenovo ThinkSmart Hub 500](https://www3.lenovo.com/us/en/hub500) |Core i5  |8GB  |128GB  |  |
|[Logitech ビデオ会議室のタッチコントローラーをタップする](https://www.logitech.com/en-us/product/tap) |Core i5  |8GB  |240GB  |  |
|[ごみ箱 MVC800](https://www.yealink.com/products_125.html)|Core i5|8GB|128GB|オーディオ-92.10.0.15</br>ビデオ-92.10.0.15|
|
> [!NOTE]
> コア M3 プロセッサはサポートされていません。

**USB オーディオおよびビデオの周辺機器についての認定済みファームウェア バージョン**

|Microsoft Teams 室の周辺機器|Microsoft Teams 会議室向けのファームウェアバージョンの認定|
|:-----|:-----|
|[Logitech 集結](https://www.logitech.com/en-us/product/rally-ultra-hd-conferencecam) <br/> |1.2.4 |
|[Logitech BRIO](https://www.logitech.com/en-us/product/brio) <br/> |v240|
|[Logitech MeetUp](http://www.logitech.com/en-us/product/meetup-conferencecam) <br/> |オーディオ-1.0.172  <br/> ビデオ-1.0.156  <br/> |
|[Logitech ConferenceCam Connect](http://www.logitech.com/en-us/product/conferencecam-connect) <br/> |1.1.248.0  <br/> 1.1.684  <br/> |
|[Logitech グループ](http://www.logitech.com/en-us/product/conferencecam-group) <br/> |8.5.778  <br/> |
|[Logitech 930e](http://www.logitech.com/en-us/product/c930e-webcam) <br/> | 8.0.914 <br/> |
|[Logitech PTZ Pro](http://www.logitech.com/en-us/product/conferencecam-ptz-pro) <br/> | 1.1.219 <br/> |
|[Logitech PTZ Pro 2](http://www.logitech.com/en-us/product/conferencecam-ptz-pro2) <br/> |
|[Polycom EagleEye IV](http://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl) <br/> |1.0.0  <br/> |
|[Polycom CX5100](http://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl) <br/> | 1.2.0.70232 <br/> |
|[Polycom Eagle アイディレクター II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom 3 つ 8500/8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html) <br/> |5.7.2.3205|
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc) <br/> |2.0.12.0  <br/> |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml) <br/> |1.2.15  <br/> |
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209) <br/> |2.10.0  <br/> |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710) <br/> |1.8.0  <br/> |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810) <br/> |1.2.23  <br/> |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/) <br/> |100c  <br/> |

- **USB エクステンダー**:

  - タブレットドック上の USB ポートは、USB 3.0 に対応しています。 USB 2. x エクステンダーは使用できますが、これによって usb 2 に制限されます。これは、USB 3.0 周辺機器にはお勧めできません。

  - Extender は USB 2.0 以降の仕様を満たしている必要があります。

  - タブレットドックは、外部 USB ハブ拡張機能の少なくとも2つのステージをサポートしています。 2つ以上の USB ハブを連続して接続する必要がある場合は、その方法がサポートされていることを dock の製造元に確認する必要があります。

- 室内での有線 GbE 接続。 適切な長さのイーサネットケーブル。

- 最大2つの1080p ディスプレイを HDMI 接続で表示します。 適切な長さの HDMI ケーブル。

> [!NOTE]
> 屋内ディスプレイの前面として使用される消費者向け TV では、スタンバイ モードからアクティブなビデオ ソースに自動的に切り替わるように、HDMI の CEC (Consumer Electronics Control) 機能をサポート/有効にする必要があります。 この機能はすべての TV でサポートされるものではありません。 

> [!NOTE]
> Microsoft Teams のルームではキーボードは使用されません。 必要に応じて、管理者はスクリーンキーボードを使用する必要があります。 Microsoft Teams の会議室のデバイスをイメージングするときは、USB キーボードまたはマウスを使用する必要があります。 

次の表では、room size に基づいた周辺機器の推奨事項について説明します。

**Microsoft Teams 会議のオーディオ周辺機器**

|会議室の種類|ユーザー数|マイクから相手の声までの推奨最大距離|部屋の最大サイズによるデバイス|コメント|
|:-----|:-----|:-----|:-----|:-----|
|**すばやく** <br/> 10 ' x 9 '  <br/> |2-4  <br/> |1.5 m  <br/> |Logitech Connect  <br/> |Logitech Connect デバイスにはカメラが含まれているため、ローカルの会議出席者をキャプチャするために、部屋の前面 (表の中央ではありません) に配置する必要があります。  <br/> |
|**微** <br/> 16 ' x 16 '  <br/> |4-6  <br/> |2.0 m  <br/> |Jabra 510  <br/> Sennheiser SP20  <br/> |再生音量が大規模な部屋で制限されることがあります。  <br/> |
|**中** <br/> 18 ' x 20 '  <br/> |6-12  <br/> |2.4 m  <br/> |Jabra 710  <br/> Jabra 810  <br/> Logitech MeetUp  <br/> Logitech グループ  <br/> Polycom 3 つ  <br/> Polycom CX5100  <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000MS  <br/> |Logitech MeetUp にはカメラが含まれているため、部屋の前に配置する必要があります (これは、ローカルの会議出席者をキャプチャするために、テーブルの中央に配置する必要があります)。  <br/> 一般的に、長い長方形または u 形の表を持つルームでは、サテライトマイクを追加すると便利です。  <br/> SP 220 ミリ秒は、デイジーチェーン構成で使用する必要があります。  <br/> |
|**さまざま** <br/> 15 ' x 32 '  <br/> |12-16  <br/> |3m  <br/> この距離は、対象のオーディオデバイスに接続されている各サテライトマイクでカバーされる領域にも適用されます。  <br/> |Logitech Group + 衛星マイク  <br/> Polycom 3 つ + 衛星マイク  <br/> Polycom CX5100 + 衛星マイク  <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000MS + 衛星マイク  <br/> |この行に示されているすべてのオーディオデバイスは、衛星マイクのオプションをサポートしています。  <br/> CX5100 には、デバイスを表の中央に配置できるように、組み込みの360度カメラが含まれています。  <br/> SP 220 ミリ秒は、デイジーチェーン構成で使用する必要があります。  <br/> |

**Microsoft Teams 会議室のビデオ周辺機器**

|会議室の種類|ユーザー数|最適な部屋のサイズによるデバイス|コメント|
|:-----|:-----|:-----|:-----|
|**すばやく** <br/> 10 ' x 9 '  <br/> |2-4  <br/> |Logitech Connect  <br/> Logitech MeetUp  <br/> Polycom CX5100  <br/> ||
|**微** <br/> 16 ' x 16 '  <br/> |4-6  <br/> |Logitech C930e  <br/> Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100  <br/> |Logitech PTZ Pro は Logitech グループにバンドルされることがよくあります。  <br/> |
|**中** <br/> 18 ' x 20 '  <br/> |6-12  <br/> |Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100  <br/> ||
|**さまざま** <br/> 15 ' x 32 '  <br/> |12-16  <br/> |Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100  <br/> ||

 > [!NOTE]
 > ルームの表示解像度の前には、1920x1080p 以下の値を設定する必要があります。

## <a name="required-software-downloads"></a>必要なソフトウェアのダウンロード

独自の Microsoft Teams のルームイメージを作成するには、「 [Microsoft Teams ルームコンソールを構成](console.md)する」の指示に従います。 これらの手順では、インストールプロセスに必要なすべてのソフトウェアをダウンロードする方法について説明します。 

> [!NOTE]
> IT 担当者は、ボリュームライセンス契約を通じて Windows 10 Enterprise ISO ファイルにアクセスする必要があります。

さらに、Microsoft Teams のルームアカウントのプロビジョニングに使用できる[SkypeRoomProvisioningScript](https://go.microsoft.com/fwlink/?linkid=870105)のコピーが必要になる場合もあります。

## <a name="see-also"></a>関連項目
[すべてのバンドルを参照する](https://products.office.com/en-us/microsoft-teams/across-devices/devices)

[Microsoft Teams のルームを計画する](skype-room-systems-v2-0.md)

[Microsoft Teams ルームの展開](room-systems-v2.md)

[Microsoft Teams 室コンソールを構成する](console.md)

[Microsoft Teams Rooms を管理する](skype-room-systems-v2.md)

[Skype for Business アドオンのライセンス](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
