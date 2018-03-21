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
- Strat_SB_PSTN
description: "Office 365 から、ユーザーの電話番号を取得するだけでなく検索し、有料またはオーディオの会議 (会議ブリッジ) の自動応答、および呼び出しキュー (サービス番号とも呼ばれます) などのサービスの無料電話番号を取得できます。 サービス用電話番号の同時通話容量は、ユーザーまたは登録者の電話番号より大きくなります。"
ms.openlocfilehash: 4736de90f1a58896f744b154c26066e49a89f1cd
ms.sourcegitcommit: 50446359cd7c359eb2536176545291c723392e47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2018
---
# <a name="getting-service-phone-numbers"></a>サービスの電話番号を取得します。

Office 365 から、ユーザーの電話番号を取得するだけでなく検索し、有料またはオーディオの会議 (会議ブリッジ) の自動応答、および呼び出しキュー (サービス番号とも呼ばれます) などのサービスの無料電話番号を取得できます。 サービス用電話番号の同時通話容量は、ユーザーまたは登録者の電話番号より大きくなります。 などのサービス数 100 コールの同時に処理できます、ユーザーの電話番号で、いくつかの呼び出しを同時に処理のみことができますが。
  
> [!NOTE]
> Office 365 の通信のクレジットは、フリー ダイヤル番号を取得するために最初に設定する必要があります。 [組織の通信のクレジットの設定](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md)を参照してください。 
  
使用できるようにする Skype でビジネスおよびマイクロソフトのチームには、サービス番号を取得する 2 とおりの方法があります。
  
- Office 365 から新しい番号を取得します。
    
- ポートまたはサービス プロバイダーまたは電話のキャリアから、既存の番号を Office 365 に転送します。
    
    > [!NOTE]
    > サービス番号を転送するときは、同時呼び出し元の容量が大きくと見なされ、正しく構成されていることを確認するのには[Microsoft のサポート](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)を問い合わせることを強くお勧めします。
  
## <a name="get-new-service-numbers"></a>新しいサービス番号を取得する

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 左側のナビゲーションでは、**音声**に移動 > **電話番号** > **新しい番号を追加**し、**新しいサービスの番号**をクリックします。
    
    > [!IMPORTANT] 
    > ビジネス管理センターの Skype では、左側のナビゲーションの**音声**オプションを表示するため、まず**E5 のエンタープライズ ライセンス**を少なくとも 1 つ、1 つの**電話システム**のアドオン ライセンスまたはアドオンのライセンスが 1 つの**電話会議**を購入する必要があります。
    
4. **新しいサービス番号の追加**] ページで、次の手順を選択します。
    
  - **国/地域**
    
  - **都道府県/地域**
    
  - **市区町村**
    
5. [ **数量**] の下に、組織に必要な電話番号の数を入力し、[ **追加**] をクリックして、予約を作成します。 自分の電話番号を選択するのには 10 分間があります。10 分以上を実行する場合、電話番号は電話番号のプールに返されます。
    
    > [!NOTE]
    > 横に表示されているライセンスの数に基づいた、電話番号の数を確認することができます**合計サービス番号をことができます取得**。 詳細についてを参照してください[電話番号の数を取得することができますか?](../what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get.md)
  
6. [ **番号を表示**] をクリックすると、電話番号の完全なリストを表示できます。 リストで特定の電話番号を選択したくない場合に便利です。
    
7. 目的の電話番号を選んでから、[ **番号の入手**] を選びます。
    
### <a name="assign-service-numbers"></a>サービス番号を割り当てる

サービス番号を作成したら、それらに割り当てて、オーディオ会議ブリッジにします。 これを行う場合は、「[電話会議ブリッジの有料または無料の電話番号を変更する](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md)」をご覧ください。
  
### <a name="port-or-transfer-existing-service-numbers"></a>既存のサービス番号を移行または転送する

現在のサービスプロバイダーまたは通信業者からサービスの番号を転送する場合は、マイクロソフトにポートの順序を手動で送信する必要があります。 種類ごとにサービスの番号 (フリー ダイヤルとダイヤル)、転送される、文字の承認 (ロード) を使用して別のポートの注文を送信する必要があります。 文字の承認 (ロード)、適切な種類のサービス番号を選択する必要があります。 マイクロソフト サポートに問い合わせる場合は、サービス番号 (*および数値以外のユーザーまたはサブスクライバー*) を転送すること、または十分コール ボリュームを処理するために同時の呼び出し元の容量ではありませんを指定するか確認してください。 電話番号を転送したり、自分の電話番号を持つ他の操作をする場合は、[組織の電話番号の管理](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)を参照してください。

> [!NOTE]
> さらに追加で電話番号が必要な場合は、「[一般法人向け Office 365 のサポートへのお問い合わせ - 管理者向けヘルプ](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)」をご覧ください。 
  
## <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。
[Office 365 での電話システムで利用できる機能](here-s-what-you-get-with-phone-system.md)

[国および地域ごとの電話会議および通話プランの利用可能性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

## <a name="feedback"></a>フィードバックですか。
製品に関するフィードバックを提供するには、かをお知らせいただいて、取り組み方は、 [Skype](https://www.skypefeedback.com)を参照してください。