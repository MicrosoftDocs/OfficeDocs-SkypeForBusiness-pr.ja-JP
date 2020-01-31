---
title: Microsoft Teams ミーティング ライセンス
ms.author: v-lanac
author: lanachin
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
f1keywords: None
ms.custom:
- Licensing
- LIL_Placement
description: 'Microsoft Teams のルームで利用できる機能について説明します。 '
ms.openlocfilehash: 9358eafd4b4e4c9f556a6cca350afa2a5fa4b6fc
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628253"
---
# <a name="teams-meeting-room-licensing-update"></a>Teams 会議室のライセンス更新

## <a name="licensing-solutions-for-shared-communication-devices"></a>共有通信デバイスのライセンスソリューション

Microsoft には、会議のライセンスを取得し、会議室のデバイス (Microsoft Teams 室や Microsoft Surface Hub など) のデバイスごとに通話を発信する専用の SKU があります。

||会議室の SKU |  
|:--- |:---: |
|Skype for Business |&#x2714;|
|Microsoft Teams|  &#x2714;|
|電話システム|  &#x2714;|
|電話会議|&#x2714; &sup1;|
|Microsoft Intune|&#x2714;|  
|世界中どこでも利用可能 | &#x2714; &sup2;|
|チャネルの可用性 | EA、EAS、CSP、 <br/>Web ダイレクト |
| | | |

&sup1;利用可能時間と含まれる分数は、地域によって異なる場合があります。 サービスの利用状況を確認するには、[電話会議と通話プランの国と地域の空き時間](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans)情報を参照してください。 国内プランの無料通話、国際通話分数などの追加サービスには、消費料金が適用される場合があります。お客様は、これらの機能を無効にして追加の請求を避けることができます。  

&sup2;主権 cloud では使用できません。  


> [!NOTE]
> 現在、電話会議、または Office 365 電話システムと通話プランを使って、Skype for Business プラン2で E1、E3、E4、E5 Sku を使用している場合、これらは引き続き機能します。 ただし、現在のライセンスの有効期限が切れた後の表では、よりシンプルなライセンスモデルに移行することを検討する必要があります。

> [!IMPORTANT]
> Skype for Business Plan 2 を使用している場合は、Skype for Business のみのモードで Microsoft Teams ルームのみを使用できます。つまり、すべての会議が Skype for Business 会議になります。 Microsoft Teams 会議の会議室を有効にするには、会議室のライセンスを購入することをお勧めします。 

次の表は、Microsoft Teams のルームで利用できる機能と、それらを取得するためにどのライセンスを購入する必要があるかを示しています。
  
> [!NOTE]
> セットアップされている会議室はユーザー オブジェクトであり、該当するライセンスが割り当てられている必要があります。

|  | Microsoft Teams または Skype for Business Online を使用している場合 <br/> 購入する必要のあるもの:   |Skype for Business Server 2015/2019 (オンプレミスまたはハイブリッド) を使用しています。 <br/> 購入する必要のあるもの:|
|:-----|:-----|:-----|
|スケジュールされている会議に参加する  | 会議室の SKU  |Skype for Business Server Standard CAL  |
|臨時の会議を開始する | 会議室の SKU  |Skype for Business Server Standard CAL  <br/> Skype for Business Server Enterprise CAL|
|臨時の会議を開始して、会議から電話番号にダイヤルアウトする |  会議室の SKU |Skype for Business Standard CAL  <br/> Skype for Business Server Enterprise CAL|
|会議室に電話番号を付け、会議室からの通話の発信や受信を行うか、電話番号を使って電話会議に参加する  | 会議室の SKU  |Skype for Business Server Standard CAL  <br/> Skype for Business Server Plus CAL  |
|Microsoft Intune で room デバイスを管理する |会議室の SKU  |[オンプレミス MDM](https://docs.microsoft.com/configmgr/mdm/plan-design/plan-on-premises-mdm)付きの Microsoft Intune サブスクリプション |
| |||

> [!NOTE]
> Room システムに既存のライセンスが割り当てられている場合、これらのライセンスは中断されることなく引き続き機能します。 既存のライセンスの有効期限が切れた場合は、新しい会議室の SKU を使用するように移動する必要があります。  

 **適切なバージョンの windows 10 を使用**する: windows 10 イメージをデバイスに展開する場合は、「 [Microsoft Teams ルームコンソールを構成](https://docs.microsoft.com/microsoftteams/room-systems/console)する」を参照してください。 [ボリュームライセンスサービスセンター](https://www.microsoft.com/Licensing/servicecenter/)からコピーを取得できます。
