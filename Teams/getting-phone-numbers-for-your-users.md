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
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Teams の新しい番号、ポート番号、または既存の番号を転送する方法と、ユーザーに変更を表示する方法について学習します。
ms.openlocfilehash: 09b42acef400f28760c50cd8a570f5c1cb1e3392
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012111"
---
# <a name="getting-phone-numbers-for-your-users"></a>ユーザー用に電話番号を取得する

[] 組織内でユーザーが電話を発着信できるように設定するには、組織のための電話番号を取得する必要があります。
  
ユーザー番号を取得するには、次の 3 つの方法があります。

- **Microsoft Teams 管理センターを使用します。** 一部の国と地域では、Microsoft Teams 管理センターを使用してユーザーの番号を取得できます。 「 [ユーザーの新しい電話番号を取得する」を参照してください](#get-new-phone-numbers-for-your-users)。

- **既存の番号を移行する。** 現在のサービス プロバイダーまたは携帯電話会社から既存の番号を移植または転送できます。 この方法の詳細については、「[Teams に電話番号を移行](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md)」または「[組織の電話番号を管理](/microsoftteams/manage-phone-numbers-for-your-organization)」を参照してください。  
  
- **新しい番号には申請書を使用します。** (お客様の国または地域によっては) Microsoft Teams 管理センターを使用して新しい電話番号を取得できない場合や、特定の電話番号または市番が必要な場合があります。 詳細については「[組織の電話番号を管理](/microsoftteams/manage-phone-numbers-for-your-organization) 」を参照してください。
  
> [!NOTE]
> 組織の電話番号の設定に関するヘルプが必要な場合は、一部のビジネス向け製品に関するサポート連絡先 - 管理者向けヘルプ [にお問い合わせください](/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online)。
  
## <a name="get-new-phone-numbers-for-your-users"></a>ユーザーの電話番号を取得する

![Microsoft Teams ロゴを示すアイコン。](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**

これらの変更を行うには、Teams サービス管理者であることが必要です。 「[Teams 管理者ロールを使用してチームを管理する](./using-admin-roles.md)」をご覧いただき、管理者ロールとアクセス許可を取得する方法について読んでください。

1. Microsoft Teams 管理センターに移動します。

2. 左側のナビゲーションで、[音声電話番号]**に**  >  **移動し、[** 追加] を **クリックします**。

3. 注文の名前を入力し、説明を追加します。

4. [場所と数量] ページで、次の操作を行います。
    1. [ **国または地域] で**、国または地域を選択します。
    2. [数値 **の種類] で**、[ユーザー **(サブスクライバー) ] を選択します**。
    3. [場所 **] で** 場所を選択します。 新しい場所を作成する必要がある場合は、[場所の追加 **] をクリックします**。
    4. [ **地域コード] で**、エリア コードを選択します。
    5. [**数量]** で、組織に必要な数値を入力し、[次へ]をクリックして番号を選択します。

5. 目的の数値を選択します。 電話番号を選択して注文するには 10 分かかります。 10 分以上かかる場合は、電話番号が数値のプールに返されます。

6. 注文の準備ができたら、[注文] を **クリックします**。

    > [!IMPORTANT]
    > (サブスクライバー) のユーザーの電話番号の数は、割り当てられた **国内通話プラン**  / **国内と国際通話プラン** ライセンスの合計数に 1.1 をかけて、さらに 10 個の電話番号を足した数と同じです。 たとえば、国内通話プラン / 国内と国際通話プランの合計ユーザー数が 50 人の場合、取得できる電話番号の数は **65** 個 **(50 x 1.1 + 10)** となります。 詳細については、「 [取得できる電話番号の数」を参照してください](./how-many-phone-numbers-can-you-get.md)。 これより多くの電話番号を取得する必要がある場合は、ビジネス製品のサポート担当者に問い [合わせ - 管理者向けヘルプ に問い合わせください](/microsoft-365/admin/contact-support-for-business-products?tabs=online&view=o365-worldwide)。
  
## <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>サービス プロバイダーまたは電話会社から電話番号を移行または転送する
  
- ユーザーに 999 以下の電話番号が必要な場合は、Microsoft Teams 管理センターの移植ウィザードを使用します。 「電話番号を [Teams に転送する」の手順に従います](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。 お客様の国または地域が移植ウィザードに表示されていない場合は、手動でポート[](phone-number-calling-plans/manually-submit-port-order.md)注文を送信するか、「組織の[](/microsoftteams/manage-phone-numbers-for-your-organization)電話番号を管理する」を参照して、正しい承認状 (LOA) をダウンロードできます。

- 999 を超える電話番号を移行する必要がある場合は[](phone-number-calling-plans/manually-submit-port-order.md)、手動で移行注文を送信[](/microsoftteams/manage-phone-numbers-for-your-organization)するか、「組織の電話番号を管理する」を参照して正しい承認状 (LOA) をダウンロードし[、PSTN](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)サービス デスクに送信してすべての番号を転送することができます。

## <a name="view-the-phone-numbers-for-your-organization"></a>組織の電話番号を表示する

![Microsoft Teams ロゴを示すアイコン。](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**

管理センターの左側のナビゲーションで、[音声電話番号]に移動して、場所、番号の種類、状態情報など、組織の番号  >  を表示します。
  
## <a name="assign-phone-numbers-to-users"></a>ユーザーに電話番号を割り当てる

電話番号を取得した後は、各ユーザーに番号を割り当てる必要があります。 詳細 [については、「ユーザーの電話番号を割り当て、変更、または削除する」](./assign-change-or-remove-a-phone-number-for-a-user.md) を参照してください。

> [!NOTE]
> これより多くの電話番号を取得する必要がある場合は、ビジネス製品のサポート担当者に問い [合わせ - 管理者向けヘルプ に問い合わせください](/microsoft-365/admin/contact-support-for-business-products?tabs=online&view=o365-worldwide)。

## <a name="related-topics"></a>関連項目

[電話番号の移行に関するよくある質問](./phone-number-calling-plans/port-order-overview.md)

[通話プランで使用されるさまざまな種類の電話番号](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)

[緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)