---
title: ユーザー用に電話番号を取得する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'チームに新しい番号を取得する方法、既存の番号を移行する方法、ユーザーへの変更を表示する方法について説明します。 '
ms.openlocfilehash: c9cf47abe056e98fdc1ee92d520ba52675216430
ms.sourcegitcommit: 2f12e0d4dc2ef8e848a63bf3a9c63e07e4439cf5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35588216"
---
# <a name="getting-phone-numbers-for-your-users"></a>ユーザー用に電話番号を取得する

[] 組織内でユーザーが電話を発着信できるように設定するには、組織のための電話番号を取得する必要があります。
  
ユーザー番号を取得するには、次の3つの方法があります。

- **Microsoft Teams 管理センターを使用します。** 一部の国/地域では、Microsoft Teams 管理センターを使用して、ユーザーの電話番号を取得することができます。 「[ユーザー用に新しい電話番号を取得する」を](#get-new-phone-numbers-for-your-users)参照してください。
    
- **既存の番号を移行する。** 現在のサービスプロバイダーまたは電話会社から既存の番号を移行または転送することができます。 そのための詳細については、「 [Office 365 に電話番号を転送](/microsoftteams/transfer-phone-numbers-to-office-365)する」または「[組織の電話番号を管理](/microsoftteams/manage-phone-numbers-for-your-organization)する」を参照してください。  
  
- **新規の番号を取得するには、リクエスト フォームを使用してください。** (お住まいの国/地域によっては)、Microsoft Teams 管理センターを使用して新しい電話番号を取得することはできません。または、特定の電話番号または市外局番が必要です。 その場合は、フォームをダウンロードして、もう一度送信する必要があります。 詳細については「[組織の電話番号を管理](/microsoftteams/manage-phone-numbers-for-your-organization) 」を参照してください。
  
> [!NOTE]
> 組織の電話番号の設定に関するヘルプが必要な場合は、 [PSTN サービスデスクに問い合わせてください](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)。
  
## <a name="get-new-phone-numbers-for-your-users"></a>ユーザーの電話番号を取得する

![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン
    
1. 左側のナビゲーションで、[ **** > **電話番号**] に移動し、[**新しい番号を取得**] をクリックします。
2. 注文の名前を入力し、必要に応じて説明を追加します。
3. [場所と数量] ページで、次の操作を行います。
    1. [**国または地域**] で、国または地域を選択します。
    1. [**番号の種類**] で、目的の番号の種類を選択します。
    1. [**場所**] で、場所を選択します。 新しい場所を作成する必要がある場合は、[**場所の追加**] をクリックします。
    1. [**市外局番**] で、市外局番を選択します。 
    2. [**数量**] の下で、組織に必要な数値の数を入力し、[**次へ**] をクリックして番号を選択します。
4. 目的の番号を選択します。 電話番号を選択して注文するには、10分間かかります。 10分以上経過すると、電話番号は番号のプールに戻されます。
5. 注文する準備ができたら、[**注文**] をクリックします。
    
    > [!IMPORTANT]
    > (サブスクライバー) のユーザーの電話番号の数は、割り当てられた** 国内通話プラン**  / ** 国内と国際通話プラン** ライセンスの合計数に 1.1 をかけて、さらに 10 個の電話番号を足した数と同じです。 たとえば、国内通話プラン / 国内と国際通話プランの合計ユーザー数が 50 人の場合、取得できる電話番号の数は **65** 個 **(50 x 1.1 + 10)** となります。 詳細については、「[取得できる電話番号の数](/microsoftteams/how-many-phone-numbers-can-you-get)を確認する方法」を参照してください。 その他の電話番号を取得する必要がある場合は、 [PSTN サービスデスクにお問い合わせください](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)。
  
   **使用中のサービス プロバイダーまたは携帯電話会社から電話番号を移行する**
  
- ユーザー用の電話番号を999以下にする必要がある場合は、Microsoft Teams 管理センターで従来のポータルを使用できます。 「 [Office 365 に電話番号を転送](/microsoftteams/transfer-phone-numbers-to-office-365)する」の手順に従って、電話番号を Teams に転送します。
    
- 999を超える電話番号を移植する必要がある場合は、「 [Service Manager でサービス要求を管理](https://docs.microsoft.com/system-center/scsm/service-requests)する」を参照して、「ポート注文サービスの依頼または注文を送信する」を参照してください。これらのすべての電話番号を Office 365 に移植します。
    
## <a name="show-phone-numbers-for-your-organization"></a>組織の電話番号を表示する

![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン 

左側のナビゲーションで、[ **** > **電話番号**] に移動して、場所、番号の種類、状態の情報など、組織の電話番号を表示します。
  
## <a name="what-else-do-you-need-to-know-about-users-phone-numbers"></a>ユーザーの電話番号に関するその他の情報
    
- 電話番号を取得したら、各ユーザーに電話番号を割り当てる必要があります。 「[ユーザーの電話番号の割り当て、変更、削除を行う](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user)」を参照してください。
    
- Microsoft Teamd 管理センターの [**電話番号**] ページを使用して、[**電話番号**] 列に使用可能な電話番号の一覧を表示し、[**状態**] 列で電話番号が割り当てられているかどうかを確認して、[**場所**」列の電話番号。 

> [!NOTE]
> その他の電話番号を取得する必要がある場合は、 [PSTN サービスデスクにお問い合わせください](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)。
    
## <a name="related-topics"></a>関連トピック

[電話番号の移行に関するよくある質問](/microsoftteams/transferring-phone-numbers-common-questions)

[通話プランで使用されるさまざまな種類の電話番号](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[[[Skype for Business 新しい電話番号の申請](/microsoftteams/manage-phone-numbers-for-your-organization)] に移動することによって、電話番号を取得するために利用できるすべてのフォームを一覧表示してダウンロードすることができます。](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話の利用条件](/microsoftteams/emergency-calling-terms-and-conditions)

[緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
