---
title: "サービスの電話番号を取得します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, jastark, oscarr, makolomi
ms.date: 01/22/2018
ms.topic: article
ms.assetid: e434aeb2-af99-40e7-981e-a474f0383734
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: "ユーザーの電話番号を取得する、Office 365 から、ほかを検索し、有料またはフリー ダイヤル電話番号 (会議ブリッジ) の電話会議、自動応答では、通話のキュー (サービス番号とも呼ばれます) などのサービスを取得できます。サービスの電話番号では、ユーザーまたはサブスクライバーの電話番号をよりも高い同時呼び出し容量があります。"
ms.openlocfilehash: 16b152fd738b76f0abcfe7e93f2e6a43a2ac55bb
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="getting-service-phone-numbers"></a>サービスの電話番号を取得します。

ユーザーの電話番号を取得する、Office 365 から、ほかを検索し、有料またはフリー ダイヤル電話番号 (会議ブリッジ) の電話会議、自動応答では、通話のキュー (サービス番号とも呼ばれます) などのサービスを取得できます。サービスの電話番号では、ユーザーまたはサブスクライバーの電話番号をよりも高い同時呼び出し容量があります。たとえば、ユーザーの電話番号のいくつかの電話を同時に処理のみできますが、サービス番号は 100 通話を処理する同時にできます。
  
> [!NOTE]
> Office 365 の通信加算したものは、フリー ダイヤルの番号を取得するために、最初に設定する必要があります。[組織の通信クレジットを設定する](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md)を参照してください。 
  
2 つの方法を使えるように skype for Business とチームの Microsoft サービス番号を取得するがあります。
  
- Office 365 から新しい番号を取得します。
    
- ポートまたは Office 365 のサービス プロバイダーまたは航空会社の電話から、既存の番号に転送します。
    
    > [!NOTE]
    > サービス番号を転送するときは、同時呼び出しの容量が大きくと見なされます、正しく構成されていることを確認して[Microsoft のサポート](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)に連絡することを強くお勧めします。
  
## <a name="get-new-service-numbers"></a>新しいサービスの番号を取得します。

1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**します。
    
3. 左のナビゲーションでは、**音声**に移動 > **電話番号** > **新しい番号を追加**し、[**サービスの新しい番号**] をクリックします。
    
    > [!IMPORTANT] 
    > Skype for Business 管理センターの左のナビゲーションで [**音声**] オプションが表示するには、少なくとも 1 つの**エンタープライズ E5 ライセンス**、**電話システムで**アドオン ライセンスは 1 つ、または 1 つの**音声会議**アドオン ライセンスを購入する必要があります。
    
4. [**新しいサービス番号を追加する**] ページで、次のように選択します。
    
  - **{国/地域}**
    
  - **州/地域**
    
  - **{City}**
    
5. [**数量**] には、組織に必要し、予約を作成するのには**追加**] をクリックする、電話番号の数を入力します。自分の電話番号を選択する 10 分しか時間があります。10 分を超える場合は、電話番号は、電話番号のプールに返されます。
    
    > [!NOTE]
    > 電話番号は、横に表示される、ライセンス数に基づいて数を表示する**合計サービス番号ことができますを入手する**します。詳細については、次を参照してください[数の電話番号を取得することができますか?](../what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get.md) 。
  
6. **数値を表示する**電話番号の完全な一覧を表示する] をクリックすることができます。一覧で特定の携帯電話番号を選択しない場合に便利です。
    
7. 必要な電話番号を選択し、[**番号の取得**] をクリックします。
    
### <a name="assign-service-numbers"></a>サービス番号を割り当てる

サービス番号を作成したら、[割り当てることができます電話会議ブリッジにします。これを行うには、[変更の有料またはフリー ダイヤルの無料番号で電話会議ブリッジ](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md)を参照してください。
  
### <a name="port-or-transfer-existing-service-numbers"></a>既存のサービス番号のポートまたは転送

航空会社、現在のサービス プロバイダーからサービス番号に転送する場合は、Microsoft にポートの順序を手動で送信する必要があります。サービス番号 (フリー ダイヤルと有料) の種類が転送される、文字の承認 (山) を使用して別のポート注文を送信する必要があります。文字の承認 (山)、正しい型のサービスの番号を選択する必要があります。Microsoft サポートに問い合わせる場合は、サービス番号 (*しユーザーまたはサブスクライバー番号ではなく*) を転送する、または同時呼び出し容量できない場合があります通話ボリュームを処理することを指定することを確認してください。電話番号に転送または電話番号とその他の操作を行う場合は、[組織の管理の電話番号](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)を参照してください。

> [!NOTE]
> これよりも、その他の電話番号を取得する必要がある場合は、[ビジネス製品 - 管理者向けヘルプのサポートに連絡](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)してください。 
  
## <a name="related-topics"></a>関連トピック
[ここではされた電話システムで Office 365 での表示](here-s-what-you-get-with-phone-system.md)

[電話会議とプランの呼び出しの国と地域の空き時間情報](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
