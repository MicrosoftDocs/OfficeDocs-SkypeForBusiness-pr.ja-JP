---
title: サービス電話番号の取得
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, jastark, oscarr, makolomi
ms.topic: article
ms.assetid: e434aeb2-af99-40e7-981e-a474f0383734
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: Office 365 から、ユーザーの電話番号を取得するだけでなく、検索、電話会議 (会議ブリッジ用) 、自動応答、および通話キュー (サービス番号とも呼ばれます) などのサービスの無料または有料電話番号を取得できます。 サービス電話番号では、同時に処理できる通話の容量が、ユーザーまたはサブスクライバーの電話番号よりも大きくなります。
ms.openlocfilehash: f45bccd76e560dacc94211d6339858e82541821e
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2018
ms.locfileid: "23779160"
---
# <a name="getting-service-phone-numbers"></a>サービス電話番号の取得

Office 365 から、ユーザーの電話番号を取得するだけでなく、検索、電話会議 (会議ブリッジ用) 、自動応答、および通話キュー (サービス番号とも呼ばれます) などのサービスの無料または有料電話番号を取得できます。 サービス電話番号では、同時に処理できる通話の容量が、ユーザーまたはサブスクライバーの電話番号よりも大きくなります。 たとえば、サービス電話番号では同時に 100 件の通話を処理できますが、ユーザーの電話番号では同時に数件の通話しか処理できません。
  
> [!NOTE]
> Office 365 コミュニケーション クレジットは、フリー ダイヤル番号を取得できるように、最初にセットアップする必要があります。 「[組織のためにコミュニケーション クレジットをセットアップする](/microsoftteams/set-up-communications-credits-for-your-organization)」を参照してください。 
  
サービス番号を取得して Skype for Business と Microsoft Teams で使用できるようにするには、次の 2 つの方法があります。
  
- Office 365 から新しい番号を取得します。
    
- 現在のサービス プロバイダーまたは電話会社から Office 365 に既存の番号を移行または転送します。
    
    > [!NOTE]
    > サービス番号を転送する場合は、同時通話容量を考慮して正しく構成するために、[Microsoft サポート](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)に連絡することを強くお勧めします。
  
## <a name="get-new-service-numbers"></a>新しいサービス番号を取得する

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **[Office 365 管理センター]** > **[Skype for Business]** に進みます。
    
3. 左側のナビゲーションで、**[音声]**  >  **[電話番号]**  >  **[新しい番号を追加]** と進み、**[新しいユーザーの番号]** をクリックします。
    
    > [!IMPORTANT] 
    > Skype for Business 管理センターの左のナビゲーションに  **[音声]** オプションが表示されるようにするには、最初に **Enterprise E5 ライセンス**、**電話システム** アドオン ライセンス、または **電話会議** アドオン ライセンスを少なくとも 1 件購入する必要があります。
    
4. [ **新しいサービス番号の追加**] ページで、次を選択します。
    
  - **国/地域**
    
  - **都道府県/地域**
    
  - **市区町村**
    
5. [ **数量**] の下に、組織に必要な電話番号の数を入力し、[ **追加**] をクリックして、予約を作成します。 電話番号を選ぶのに与えられた時間は 10 分間です。選ぶのに 10 分以上かかると、電話番号は電話番号のプールに戻ります。
    
    > [!NOTE]
    > [ **取得できる合計ユーザー数**] の横に表示されるライセンス数に基づいた電話番号の数を確認できます。 詳細は、「[取得できる電話番号の数について](/microsoftteams/how-many-phone-numbers-can-you-get)」を参照してください
  
6. [ **番号を表示**] をクリックすると、電話番号の完全なリストを表示できます。 リストにある電話番号を選びたくない場合には、この方法が便利です。
    
7. 目的の電話番号を選んでから、[ **番号を取得**] を選びます。
    
### <a name="assign-service-numbers"></a>サービス番号を割り当てる

取得したサービス電話番号は、電話会議ブリッジに割り当てることができます。 これを行う場合は、「[電話会議ブリッジの有料または無料の電話番号を変更する](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)」をご覧ください。
  
### <a name="port-or-transfer-existing-service-numbers"></a>既存のサービス番号を移行または転送する

現在のサービスプロバイダーまたは通信業者からサービスの番号を転送する場合は、マイクロソフトに番号移行注文を手動で提出する必要があります。 承認状（LOA)を使用して、移行したいサービス番号（有料・無料）の種類ごとに各々番号移行注文を提出する必要があります。 承認状（LOA)では、適切な種類のサービス番号を選択する必要があります。 マイクロソフト サポートに問い合わせる場合は、サービス番号 (*ユーザーまたはサブスクライバーの番号ではなく*) を転送すること、または通話量に対応するための同時通話許容量が十分ではないことを指定してください。 電話番号を転送したり、自分の電話番号で他の操作をする場合は、「[組織の電話番号の管理](/microsoftteams/manage-phone-numbers-for-your-organization)」を参照してください。

> [!NOTE]
> さらに追加で電話番号が必要な場合は、「[一般法人向け Office 365 のサポートへのお問い合わせ - 管理者向けヘルプ](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)」をご覧ください。 
  
## <a name="related-topics"></a>関連トピック
[Office 365 での電話システムで利用できる機能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[国および地域ごとの電話会議および通話プランの利用可能性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 