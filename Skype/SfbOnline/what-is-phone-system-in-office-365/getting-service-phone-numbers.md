---
title: サービスの電話番号の取得
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, jastark, oscarr, makolomi
ms.topic: article
ms.assetid: e434aeb2-af99-40e7-981e-a474f0383734
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Office 365 から、ユーザーの電話番号を取得するだけでなく検索し、有料またはオーディオの会議 (会議ブリッジ) の自動応答、および呼び出しキュー (サービス番号とも呼ばれます) などのサービスの無料電話番号を取得できます。 サービス用電話番号の同時通話容量は、ユーザーまたは登録者の電話番号より大きくなります。
ms.openlocfilehash: f5627333475d04b14805a1749ccf56b1337047d4
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884072"
---
# <a name="getting-service-phone-numbers"></a>サービスの電話番号の取得

Office 365 から、ユーザーの電話番号を取得するだけでなく検索し、有料またはオーディオの会議 (会議ブリッジ) の自動応答、および呼び出しキュー (サービス番号とも呼ばれます) などのサービスの無料電話番号を取得できます。 サービス用電話番号の同時通話容量は、ユーザーまたは登録者の電話番号より大きくなります。 などのサービス数 100 コールの同時に処理できます、ユーザーの電話番号で、いくつかの呼び出しを同時に処理のみことができますが。
  
> [!NOTE]
> Office 365 コミュニケーション クレジットは、フリー ダイヤル番号を取得できるように、最初にセットアップする必要があります。 [組織の通信のクレジットの設定](/microsoftteams/set-up-communications-credits-for-your-organization)を参照してください。 
  
使用できるようにする Skype でビジネスおよびマイクロソフトのチームには、サービス番号を取得する 2 とおりの方法があります。
  
- Office 365 から新しい番号を取得します。
    
- ポートまたはサービス プロバイダーまたは電話のキャリアから、既存の番号を Office 365 に転送します。
    
    > [!NOTE]
    > サービス番号を転送するときは、同時呼び出し元の容量が大きくと見なされ、正しく構成されていることを確認するのには[Microsoft のサポート](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)を問い合わせることを強くお勧めします。
  
## <a name="get-new-service-numbers"></a>新しいサービス番号を取得する

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. ** [Office 365 管理センター] ** > ** [Skype for Business]** に移動します。
    
3. 左側のナビゲーションでは、**音声**に移動 > **電話番号** > **新しい番号を追加**し、**新しいサービスの番号**をクリックします。
    
    > [!IMPORTANT] 
    > ビジネス管理センターの Skype では、左側のナビゲーションの**音声**オプションを表示するため、まず**E5 のエンタープライズ ライセンス**を少なくとも 1 つ、1 つの**電話システム**のアドオン ライセンスまたはアドオンのライセンスが 1 つの**電話会議**を購入する必要があります。
    
4. **新しいサービス番号の追加**] ページで、次の手順を選択します。
    
  - **国/地域**
    
  - **都道府県/地域**
    
  - **市区町村**
    
5. [ **数量**] の下に、組織に必要な電話番号の数を入力し、[ **追加**] をクリックして、予約を作成します。 自分の電話番号を選択するのには 10 分間があります。10 分以上を実行する場合、電話番号は電話番号のプールに返されます。
    
    > [!NOTE]
    > 横に表示されているライセンスの数に基づいた、電話番号の数を確認することができます**合計サービス番号をことができます取得**。 詳細についてを参照してください[電話番号の数を取得することができますか?](/microsoftteams/how-many-phone-numbers-can-you-get)
  
6. [ **番号を表示**] をクリックすると、電話番号の完全なリストを表示できます。 リストで特定の電話番号を選択したくない場合に便利です。
    
7. 目的の電話番号を選んでから、[ **番号の入手**] を選びます。
    
### <a name="assign-service-numbers"></a>サービス番号を割り当てる

サービス番号を作成したら、それらに割り当てて、オーディオ会議ブリッジにします。 これを行う場合は、「[電話会議ブリッジの有料または無料の電話番号を変更する](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)」をご覧ください。
  
### <a name="port-or-transfer-existing-service-numbers"></a>既存のサービス番号を移行または転送する

現在のサービスプロバイダーまたは通信業者からサービスの番号を転送する場合は、マイクロソフトに番号移行注文を手動で提出する必要があります。 承認状（LOA)を使用して、移行したいサービス番号（有料・無料）の種類ごとに各々番号移行注文を提出する必要があります。 承認状（LOA)では、適切な種類のサービス番号を選択する必要があります。 マイクロソフト サポートに問い合わせる場合は、サービス番号 (*ユーザーまたはサブスクライバーの番号ではなく*) を転送すること、または通話量に対応するための同時通話許容量が十分ではないことを指定してください。 電話番号を転送したり、自分の電話番号で他の操作をする場合は、 [組織の電話番号の管理](/microsoftteams/manage-phone-numbers-for-your-organization) を参照してください。

> [!NOTE]
> さらに追加で電話番号が必要な場合は、「[一般法人向け Office 365 のサポートへのお問い合わせ - 管理者向けヘルプ](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)」をご覧ください。 
  
## <a name="related-topics"></a>関連トピック
[Office 365 での電話システムで利用できる機能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[国および地域ごとの電話会議および通話プランの利用可能性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 