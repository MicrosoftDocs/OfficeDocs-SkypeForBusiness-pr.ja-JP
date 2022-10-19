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
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Teams の既存の番号を取得、移植、転送する方法、およびユーザーに変更を表示する方法について説明します。
ms.openlocfilehash: 0e9b3c13c62c2adb5a3fa6a7dbe7665e9346a08d
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2022
ms.locfileid: "68583868"
---
# <a name="getting-phone-numbers-for-your-users"></a>ユーザー用に電話番号を取得する

[] 組織内でユーザーが電話を発着信できるように設定するには、組織のための電話番号を取得する必要があります。
  
ユーザー番号を取得するには、次の 3 つの方法があります。

- **Microsoft Teams 管理センターを使用します。** 一部の国と地域では、Microsoft Teams 管理センターを使用してユーザーの番号を取得できます。 [ユーザーの新しい電話番号の取得に関するページを参照してください](#get-new-phone-numbers-for-your-users)。

- **既存の番号を移行する。** 現在のサービス プロバイダーまたは電話会社から既存の番号を移植または転送できます。 この方法の詳細については、「[Teams に電話番号を移行](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md)」または「[組織の電話番号を管理](/microsoftteams/manage-phone-numbers-for-your-organization)」を参照してください。  
  
- **新しい番号には申請書を使用します。** Microsoft Teams 管理 センターを使用して新しい電話番号を取得できない場合や、特定の電話番号または市外局番が必要になる場合があります。 詳細については「[組織の電話番号を管理](/microsoftteams/manage-phone-numbers-for-your-organization) 」を参照してください。
  
> [!NOTE]
> 組織の電話番号の設定に関するヘルプが必要な場合は、[ビジネス向け製品のサポート連絡先 - 管理ヘルプにお問い合わせください](/microsoft-365/admin/contact-support-for-business-products)。

## <a name="get-new-phone-numbers-for-your-users"></a>ユーザーの電話番号を取得する

**Microsoft Teams 管理センターの使用**

これらの変更を行うには、Teams サービス管理者であることが必要です。 「[Teams 管理者ロールを使用してチームを管理する](./using-admin-roles.md)」をご覧いただき、管理者ロールとアクセス許可を取得する方法について読んでください。

1. Microsoft Teams 管理 センターに移動します。

2. 左側のナビゲーションで、[ **音声** > **電話番号**] に移動し、[ **追加**] を選択します。

3. 注文の名前を入力し、説明を追加します。

4. [場所と数量] ページで、次の操作を行います。
    1. [ **国または地域]** で、国または地域を選択します。
    2. [ **数値の種類**] で、[ **ユーザー (サブスクライバー)]** を選択します。
    3. [ **場所]** で場所を選択します。 新しい場所を作成する必要がある場合は、[ **場所の追加]** を選択します。
    4. [ **市外局番**] で、市外局番を選択します。
    5. [ **数量]** で、組織に必要な番号の数を入力し、[ **次へ** ] を選択して番号を選択します。

5. 目的の数値を選択します。 電話番号を選択して注文するには、10 分かかります。 10 分以上かかる場合は、電話番号が番号のプールに返されます。

6. 注文の準備ができたら、[ **注文] を** 選択します。

    > [!IMPORTANT]
    > ユーザー (サブスクライバー) の電話番号の数は、割り当てた **国内通話プラン** と **国際通話プラン** のライセンスの合計数に 1.1 を掛け、さらに 10 個の電話番号を加算した数と等しくなります。 たとえば、国内通話プランまたは国際通話プランで合計 50 人のユーザーがいる場合は、 **65** の電話番号 **(50 x 1.1 + 10) を** 取得できます。 従量課金制通話プランをお持ちのお客様は、ライセンスごとに 1 つの電話番号しか取得できません。
    >
    > 詳細については、「電話番号 [を取得できる電話番号の数](./how-many-phone-numbers-can-you-get.md)」を参照してください。 これより多くの電話番号を取得する必要がある場合は、[ビジネス向け製品のサポート連絡先 - 管理ヘルプにお問い合わせください](/microsoft-365/admin/contact-support-for-business-products)。
  
## <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>サービス プロバイダーまたは電話会社から電話番号を移行または転送する
  
- ユーザーの電話番号が 999 以下の場合は、Microsoft Teams 管理 センターの移植ウィザードを使用します。 Teams に電話番号を [転送するの手順に](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md)従います。 移植ウィザードに国または地域が表示されていない場合は、 [手動でポート注文を送信](phone-number-calling-plans/manually-submit-port-order.md) するか、 [組織の電話番号を管理](/microsoftteams/manage-phone-numbers-for-your-organization) して正しい承認状 (LOA) をダウンロードする方法に関するページを参照してください。

- 999 を超える電話番号を移植する必要がある場合は、 [手動でポート注文を送信](phone-number-calling-plans/manually-submit-port-order.md) するか、 [組織の電話番号の管理](/microsoftteams/manage-phone-numbers-for-your-organization) を参照して正しい承認状 (LOA) をダウンロードし [、それを TNS サービス デスク](manage-phone-numbers-for-your-organization/contact-tns-service-desk.md) に送信して、すべての番号を転送できます。

## <a name="view-the-phone-numbers-for-your-organization"></a>組織の電話番号を表示する

**Microsoft Teams 管理センターの使用**

管理センターの左側のナビゲーションで **、Voice** > **Phone 番号** に移動して、場所、番号の種類、状態情報など、組織の番号を表示します。
  
## <a name="assign-phone-numbers-to-users"></a>ユーザーに電話番号を割り当てる

電話番号を取得したら、各ユーザーに番号を割り当てる必要があります。 詳細については [、「ユーザーの電話番号を割り当てる、変更する、または削除](./assign-change-or-remove-a-phone-number-for-a-user.md) する」を参照してください。

> [!NOTE]
> これより多くの電話番号を取得する必要がある場合は、[ビジネス向け製品のサポート連絡先 - 管理ヘルプにお問い合わせください](/microsoft-365/admin/contact-support-for-business-products)。

このビデオでは、ユーザーに電話番号を割り当てる手順を示します。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE54mbS?autoplay=false]

## <a name="related-articles"></a>関連記事

[電話番号の移行に関するよくある質問](./phone-number-calling-plans/port-order-overview.md)

[通話プランで使用されるさまざまな種類の電話番号](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)

[緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
