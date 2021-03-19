---
title: Microsoft Teams Rooms ライセンス
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: Microsoft Teams Rooms の通話と会議機能の種類に応じて使用できるライセンスについて説明します。
ms.openlocfilehash: 6f339136d6084046004506c30b6827aaed62971a
ms.sourcegitcommit: 71b9b5ec80014bd25758493bc06d633c4eac735c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2021
ms.locfileid: "50867126"
---
# <a name="teams-meeting-room-licensing-update"></a>Teams ミーティング ルームのライセンスの更新

## <a name="licensing-solutions-for-shared-communication-devices"></a>共有コミュニケーション デバイスのライセンス ソリューション

Microsoft には、会議室デバイスのライセンス会議と通話をデバイス単位で行う専用 SKU が 2 つあります (Microsoft Teams 会議室、Microsoft Surface Hub、Microsoft Teams のコラボレーション バーなど)。

||Microsoft Teams Rooms Standard |Microsoft Teams Rooms Premium |
|:--- |:---: |:---: |
|Skype for Business |&#x2714;| &#x2714;|
|Microsoft Teams|  &#x2714;|  &#x2714;|
|電話システム|  &#x2714;|  &#x2714;|
|電話会議|&#x2714; &sup1;|&#x2714; &sup1;|
|Microsoft Intune|&#x2714;|&#x2714;|  
|世界的な可用性 | &#x2714; &sup2;| &#x2714; &sup2;|
|チャネルの可用性 | EA、EAS、CSP、 <br/>Web ダイレクト | EA、EAS、CSP、 <br/>Web ダイレクト |
|管理対象サービス | | &#x2714; &sup3;|
| | | |

&sup1; 可用性と含まれる分数は、地域によって異なる場合があります。 サービスの可用性を確認するには、「[国および地域ごとの電話会議および通話プランの利用可能性](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans)」を参照してください。 追加のサービス (国内プランの無料の国際通話時間など) に対しては従量課金が発生する場合があります。ユーザーは、これらの機能を無効にして、追加の課金が発生しないようにできます。  

&sup2; ソブリン クラウドでは使用不可  

&sup3;詳細と空き時間情報については [、Microsoft Teams の会議室管理サービスを参照してください](microsoft-teams-rooms-premium.md)。

> [!NOTE]
> 電話会議が含まれる Skype for Business プラン 2、または Office 365 電話システムと通話プランで、E1、E3、E4、E5 SKU を現在お使いの場合、これらは引き続き機能します。 ただし、現在のライセンスの有効期限が切れた後は、上の表に示した、よりシンプルなライセンス モデルへの移行をご検討いただく必要があります。

> [!IMPORTANT]
> Skype for Business プラン 2 を使用している場合、[Skype for Business のみ] のモードでのみ Microsoft Teams Rooms をご利用いただけます。つまり、すべての会議が Skype for Business の会議になります。 Microsoft Teams のミーティングの会議室を使用できるようにするため、ミーティング ルーム ライセンスのご購入をお勧めします。 

次の表に、Microsoft Teams Rooms で使用できる機能と、その機能を利用するために購入する必要のあるライセンスをまとめて示します。
  
> [!NOTE]
> セットアップされる会議室はユーザー オブジェクトで、これらのライセンスが割り当てられている必要があります。

|  | Microsoft Teams または Skype for Business Online を所有。 <br/> 購入が必要なもの:   |Skype for Business Server 2015/2019 (オンプレミスまたはハイブリッド) を所有。 <br/> 購入が必要なもの:|
|:-----|:-----|:-----|
|スケジュールされた会議への参加  | Microsoft Teams Rooms Standard または Premium  |Skype for Business Server Standard CAL  |
|アドホック会議の開始 | Microsoft Teams Rooms Standard または Premium  |Skype for Business Server Standard CAL  <br/> Skype for Business Server Enterprise CAL|
|アドホック会議を開始し、会議から電話番号にダイヤル アウト |  Microsoft Teams Rooms Standard または Premium |Skype for Business Standard CAL  <br/> Skype for Business Server Enterprise CAL|
|会議室に電話番号を付け、その部屋から電話を受ける、または電話番号を使って音声会議に参加する  | 直接ルーティングの場合: Microsoft Teams Rooms Standard または Premium<br/>ダイレクト ルーティングなし: 国内通話プランまたは国際通話プラン<br/>Microsoft 365 Business Voice  |Skype for Business Server Standard CAL  <br/> Skype for Business Server Plus CAL  |
|Microsoft Intune を使用した会議室デバイスの管理 |Microsoft Teams Rooms Standard または Premium  |[オンプレミス MDM](https://docs.microsoft.com/configmgr/mdm/plan-design/plan-on-premises-mdm) を含む Microsoft Intune サブスクリプション |
|Microsoft Teams の会議室管理サービス | Microsoft Teams Rooms Premium ||
| |||

> [!NOTE]
> 既存のライセンスが会議室システムに割り当てられている場合、これらは中断されることなく機能します。 既存のライセンスの有効期限が切れた時点で、新しいミーティング ルーム SKU を使用するように移行する必要があります。  

 **正しいバージョンの Windows 10 を使用する**。Windows 10 イメージをデバイスに展開する場合は、「[Microsoft Teams Rooms コンソールを構成する](https://docs.microsoft.com/microsoftteams/room-systems/console)」を参照してください。 [ボリューム ライセンス サービス センター](https://www.microsoft.com/Licensing/servicecenter/)からコピーを入手できます。
