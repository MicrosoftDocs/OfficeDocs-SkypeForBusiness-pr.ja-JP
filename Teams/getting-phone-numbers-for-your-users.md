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
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 'チームに新しい番号を取得する方法、既存の番号を移行する方法、ユーザーへの変更を表示する方法について説明します。 '
ms.openlocfilehash: d2ac4a0a5e487b99cf8dbc303b85e6f4e3446ec8
ms.sourcegitcommit: d7be89019dd5a3b88b0840bddf1b88fea8598ea7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "42170753"
---
# <a name="getting-phone-numbers-for-your-users"></a>ユーザー用に電話番号を取得する

[] 組織内でユーザーが電話を発着信できるように設定するには、組織のための電話番号を取得する必要があります。
  
ユーザー番号を取得するには、次の3つの方法があります。

- **Microsoft Teams 管理センターを使用します。** 一部の国と地域では、Microsoft Teams 管理センターを使用して、ユーザーの電話番号を取得できます。 「[ユーザー用に新しい電話番号を取得する」を](#get-new-phone-numbers-for-your-users)参照してください。
    
- **既存の番号を移行する。** 現在のサービスプロバイダーまたは電話会社から既存の番号を移行または転送することができます。 詳細については、「[組織の](/microsoftteams/manage-phone-numbers-for-your-organization)電話[番号をチームに転送](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)する」または「電話番号を管理する」を参照してください。  
  
- **新しい番号には申請書を使用します。** 場合によっては (お住まいの国または地域によっては)、Microsoft Teams 管理センターを使用して新しい電話番号を取得することはできません。または、特定の電話番号または市外局番が必要です。 その場合は、フォームをダウンロードして、もう一度送信する必要があります。 詳細については「[組織の電話番号を管理](/microsoftteams/manage-phone-numbers-for-your-organization) 」を参照してください。
  
> [!NOTE]
> 組織の電話番号の設定に関するヘルプが必要な場合は、 [PSTN サービスデスクに問い合わせてください](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)。
  
## <a name="get-new-phone-numbers-for-your-users"></a>ユーザーの電話番号を取得する

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**
    
1. 左側のナビゲーションで、[**電話番号** **] に移動** > し、[**追加**] をクリックします。
2. 注文の名前を入力し、必要に応じて説明を追加します。
3. [場所と数量] ページで、次の操作を行います。
    1. [**国または地域**] で、国または地域を選択します。
    2. [**番号の種類**] で、[**ユーザー (サブスクライバー)**] を選びます。
    3. [**場所**] で、場所を選択します。 新しい場所を作成する必要がある場合は、[**場所の追加**] をクリックします。
    4. [**市外局番**] で、市外局番を選択します。 
    5. [**数量**] の下で、組織に必要な数値の数を入力し、[**次へ**] をクリックして番号を選択します。
4. 目的の番号を選択します。 電話番号を選択して注文するには、10分間かかります。 10分以上経過すると、電話番号は番号のプールに戻されます。
5. 注文する準備ができたら、[**注文**] をクリックします。

    > [!IMPORTANT]
    > (サブスクライバー) のユーザーの電話番号の数は、割り当てられた** 国内通話プラン**  / ** 国内と国際通話プラン** ライセンスの合計数に 1.1 をかけて、さらに 10 個の電話番号を足した数と同じです。 たとえば、国内通話プラン / 国内と国際通話プランの合計ユーザー数が 50 人の場合、取得できる電話番号の数は **65** 個 **(50 x 1.1 + 10)** となります。 詳細については、「[取得できる電話番号の数](/microsoftteams/how-many-phone-numbers-can-you-get)を確認する方法」を参照してください。 その他の電話番号を取得する必要がある場合は、 [PSTN サービスデスクにお問い合わせください](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)。
  
## <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>サービス プロバイダーまたは電話会社から電話番号を移行または転送する
  
- ユーザー用の電話番号を999以下にする必要がある場合は、Microsoft Teams 管理センターの [移植] ウィザードを使用します。 「[チームに電話番号を転送する](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)」の手順に従います。 お住まいの国または地域が [移植ウィザード] に表示されていない場合は、[手動でポート注文を送信](phone-number-calling-plans/manually-submit-port-order.md)するか、「[組織の電話番号の管理](/microsoftteams/manage-phone-numbers-for-your-organization)」を参照して正しい文字の承認 (loa) をダウンロードしてください。

- 999を超える電話番号を移植する必要がある場合は、[手動でポート注文を送信](phone-number-calling-plans/manually-submit-port-order.md)するか、「[組織の電話番号の管理](/microsoftteams/manage-phone-numbers-for-your-organization)」を参照して正しい文字の承認 (loa) をダウンロードしてから、 [PSTN サービスデスク](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)に送信してすべての電話番号を取得することができます。

## <a name="view-the-phone-numbers-for-your-organization"></a>組織の電話番号を表示する

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用** 

左側のナビゲーションで、[ > **電話番号**] に移動して、場所、番号の種類、状態の情報など、組織の電話**番号を表示**します。
  
## <a name="assign-phone-numbers-to-users"></a>ユーザーに電話番号を割り当てる

電話番号を取得したら、各ユーザーに電話番号を割り当てる必要があります。 「[ユーザーの電話番号の割り当て、変更、削除を行う](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user)」を参照してください。

> [!NOTE]
> その他の電話番号を取得する必要がある場合は、 [PSTN サービスデスクにお問い合わせください](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)。


## <a name="related-topics"></a>関連トピック

[電話番号の移行に関するよくある質問](/microsoftteams/transferring-phone-numbers-common-questions)

[通話プランで使用されるさまざまな種類の電話番号](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話の利用条件](/microsoftteams/emergency-calling-terms-and-conditions)

[緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
