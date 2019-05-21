---
title: サービス電話番号を取得する
author: CarolynRowe
ms.author: crowe
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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Office 365 からユーザーの電話番号を取得することに加えて、電話会議 (会議ブリッジの場合)、自動応答、通話キュー (サービス番号とも呼ばれます) などのサービスの有料または無料の電話番号を検索して取得することができます。 サービス用電話番号の同時通話容量は、ユーザーまたは登録者の電話番号より大きくなります。
ms.openlocfilehash: ca00db8882837bc748dee89a100b2e7d9dd2d04f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297973"
---
# <a name="getting-service-phone-numbers"></a>サービス電話番号を取得する

Office 365 ユーザー用の電話番号の取得に加え、電話会議 (会議ブリッジ用)、自動応答、通話キュー (別名: サービス番号) などのサービス用に、有料または無料電話番号を検索し、取得できます。ユーザーまたはサブスクライバーの電話番号に比べて、サービス電話番号はより高い同時通話の処理能力を持ちます。たとえば、ユーザーの電話番号 1 つが同時に取り扱える通話数はごく少数なのに対して、1 つのサービス番号は何百もの通話を同時に取り扱えます。
  
> [!NOTE]
> Office 365 コミュニケーション クレジットは、フリー ダイヤル番号を取得できるように、最初にセットアップする必要があります。 「[組織のためにコミュニケーションクレジットを設定する](/microsoftteams/set-up-communications-credits-for-your-organization)」を参照してください。 
  
サービス番号を取得して、Skype for Business および Microsoft Teams で使用できるようにするには、次の2つの方法があります。
  
- Office 365 から新しい番号を取得します。
    
- サービスプロバイダーまたは電話会社から Office 365 に既存の番号を移行する。
    
    > [!NOTE]
    > サービス番号を転送する場合は、同時通話容量が優先され、正しく構成されていることを確認するために、 [Microsoft サポート](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)に連絡することを強くお勧めします。
  
## <a name="get-new-service-numbers"></a>新しいサービス番号を取得する

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business 管理センターを使用する**

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **管理センター** > **チームと skype** > **skype 従来の管理者**にお進みください。
    
3. In the left navigation go to **Voice** > **Phone numbers** > **Add** then click **New service numbers**.
    
    > [!IMPORTANT] 
    > Skype for Business 管理センターの左のナビゲーションに [**音声**] オプションが表示されるようにするには、最初に **Enterprise E5 ライセンス**、**電話システム**アドオン ライセンス、または**電話会議**アドオン ライセンスを少なくとも 1 件購入する必要があります。
    
4. [**新しいサービス番号の追加**] ページで、次を選択します。
    
   - **国/地域**
    
   - **都道府県/地域**
    
   - **市区町村**
    
5. [ **数量**] の下に、組織に必要な電話番号の数を入力し、[ **追加**] をクリックして、予約を作成します。 電話番号を選択するには、10分間かかります。10分以上かかる場合は、電話番号のプールに電話番号が返されます。
    
    > [!NOTE]
    > [**取得可能なサービスの合計**数] の横に表示されるライセンス数に基づいて、電話番号の数を確認できます。 詳細については、「[取得できる電話番号の数](/microsoftteams/how-many-phone-numbers-can-you-get)を確認する方法」を参照してください。
  
6. [ **番号を表示**] をクリックすると、電話番号の完全なリストを表示できます。 これは、リスト内の特定の電話番号を選択しない場合に便利です。
    
7. 目的の電話番号を選んでから、[ **番号の入手**] を選びます。
    
### <a name="assign-service-numbers"></a>サービス番号を割り当てる

サービス番号を取得すると、電話会議ブリッジに割り当てることができます。 これを行う場合は、「[電話会議ブリッジの有料または無料の電話番号を変更する](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)」をご覧ください。
  
### <a name="port-or-transfer-existing-service-numbers"></a>既存のサービス番号を移行または転送する

現在のサービス プロバイダーまたは通信事業者からサービス番号を移動する場合は、ポートの注文を手動で Microsoft に送信する必要があります。承認状 (LOA) を使用して、移動するサービス番号の種類 (有料電話番号または無料電話番号) ごとに別々のポート注文を送信する必要があります。承認状 (LOA) では、適切な種類のサービス番号が選択されている必要があります。Microsoft サポートに連絡する際は、移動する番号は*ユーザーまたはサブスクライバーの番号ではなく*、サービス番号であることを必ず指定してください。これを指定しない場合、実際の通話件数を処理するには同時通話処理能力が不十分なものになる可能性があります。電話番号の移動や電話番号に関するその他の手続きを行うには、「[組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)」を参照してください。

> [!NOTE]
> さらに追加で電話番号が必要な場合は、「[一般法人向け Office 365 のサポートへのお問い合わせ - 管理者向けヘルプ](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)」をご覧ください。 
  
## <a name="related-topics"></a>関連トピック
[Office 365 の電話システムでできること](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[国および地域ごとの電話会議および通話プランの利用可能性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 