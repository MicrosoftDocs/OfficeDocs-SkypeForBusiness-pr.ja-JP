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
description: Teams の新しい番号を取得、移植、または転送する方法と、ユーザーに変更を表示する方法について説明します。
ms.openlocfilehash: d92d48f95e620767148d3917a78d1e72c87f0645
ms.sourcegitcommit: fd56fb16ed60b027d3f8de96711d143825f9c184
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2023
ms.locfileid: "69835490"
---
# <a name="getting-phone-numbers-for-your-users"></a>ユーザー用に電話番号を取得する

[] 組織内でユーザーが電話を発着信できるように設定するには、組織のための電話番号を取得する必要があります。
  
ユーザー番号を取得するには、次の 3 つの方法があります。

- **Microsoft Teams 管理センターを使用します。** 一部の国と地域では、Microsoft Teams 管理センターを使用してユーザーの番号を取得できます。 「 [ユーザーの新しい電話番号を取得する」を参照してください](#get-new-phone-numbers-for-your-users)。

- **既存の番号を移行する。** 現在のサービス プロバイダーまたは電話会社から既存の番号を移植または転送できます。 詳細については、「 [Teams に電話番号を転送する](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 」または [「組織の電話番号を管理する」を参照してください](/microsoftteams/manage-phone-numbers-for-your-organization)。  
  
- **新しい番号には申請書を使用します。** (国や地域によっては) Microsoft Teams 管理センターを使用して新しい電話番号を取得できない場合や、特定の電話番号や市域コードが必要な場合があります。 詳細については、「[組織のために電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)」をご覧ください。
  
> [!NOTE]
> 組織の電話番号の設定に関するヘルプが必要な場合は、[ビジネス製品のサポート連絡先 - 管理ヘルプにお問い合わせください](/microsoft-365/admin/contact-support-for-business-products)。

## <a name="get-new-phone-numbers-for-your-users"></a>ユーザーの電話番号を取得する

**Microsoft Teams 管理センターの使用**

これらの変更を行うには、Teams サービス管理者であることが必要です。 「[Teams 管理者ロールを使用してチームを管理する](./using-admin-roles.md)」をご覧いただき、管理者ロールとアクセス許可を取得する方法について読んでください。

1. [Microsoft Teams 管理センター](https://go.microsoft.com/fwlink/p/?linkid=2066851)にサインインします。

2. 左側のナビゲーションで、[ **音声** > **電話番号**] に移動し、[ **追加**] を選択します。

3. 注文の名前を入力し、説明を追加します。

4. [場所と数量] ページで、次の操作を行います。
    1. [ **国または地域**] で、国または地域を選択します。
    2. [ **数値の種類**] で、[ **ユーザー (サブスクライバー)]** を選択します。
    3. [ **場所] で**、場所を選択します。 新しい場所を作成する必要がある場合は、[ **場所の追加**] を選択します。
    4. [ **地域コード**] で、エリア コードを選択します。
    5. [ **数量]** で、組織に必要な数値の数を入力し、[ **次へ** ] を選択して番号を選択します。

5. 目的の番号を選択します。 電話番号を選択して注文するには、10 分かかります。 10 分以上かかる場合、電話番号は番号のプールに返されます。

6. 注文の準備ができたら、[注文] を選択 **します**。

    > [!IMPORTANT]
    > ユーザー (サブスクライバー) の電話番号の数は、割り当てた **国内通話プラン** ライセンスと **国際通話プラン** ライセンスの合計数に 1.1 を掛け、さらに 10 個の電話番号を乗算したものに等しくなります。 たとえば、国内通話プランや国際通話プランで合計 50 人のユーザーがいる場合は、 **65** の電話番号 **(50 x 1.1 + 10)** を取得できます。 従量課金制通話プランがある場合は、割り当てられたライセンスごとに 1 つの電話番号のみを取得できることに注意してください。
    >
    > 詳細については、「取得 [できる電話番号の数](./how-many-phone-numbers-can-you-get.md)」を参照してください。 これより多くの電話番号を取得する必要がある場合は、[ビジネス製品のサポート連絡先 - 管理ヘルプにお問い合わせください](/microsoft-365/admin/contact-support-for-business-products)。
  
## <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>サービス プロバイダーまたは電話会社から電話番号を移行または転送する
  
- ユーザーに 999 個以下の電話番号が必要な場合は、Microsoft Teams 管理センターの移植ウィザードを使用します。 [「電話番号を Teams に転送する](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md)」の手順に従います。 このプロセスに関するサポートが必要な場合は、 [手動でポート注文を送信](phone-number-calling-plans/manually-submit-port-order.md) するか、「 [組織の電話番号を管理](/microsoftteams/manage-phone-numbers-for-your-organization) する」を参照して、正しい承認状 (LOA) をダウンロードできます。

- 999 を超える電話番号を移植する必要がある場合は、 [ポート注文を手動で送信](phone-number-calling-plans/manually-submit-port-order.md) するか、「 [組織の電話番号を管理](/microsoftteams/manage-phone-numbers-for-your-organization) する」を参照して、正しい承認状 (LOA) をダウンロードできます。 LOA ドキュメントを完了して署名し、お使いのリージョン [の TNS サービス デスク](manage-phone-numbers-for-your-organization/contact-tns-service-desk.md) にお問い合わせください。

> [!NOTE]
> 既存の電話番号を移植/転送するための LOA と追加のドキュメント要件の詳細については、「 [通話プランの電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)」を参照してください。
>
>ユーザーの 999 個以下の電話番号を移植または転送するには、Microsoft Teams 管理センターで完了した LOA と署名済みの LOA をアップロードして、さらに処理します。 
>
> 999 を超える電話番号を移植または転送する場合、または Microsoft Teams 管理センターで移植プロセスに問題が発生した場合は、お使いのリージョンの TNS Service Desk [に手動でポート注文を送信](/microsoftteams/phone-number-calling-plans/manually-submit-port-order) できます。

## <a name="view-the-phone-numbers-for-your-organization"></a>組織の電話番号を表示する

**Microsoft Teams 管理センターの使用**

管理センターの左側のナビゲーションで、[ **音声** > **電話番号** ] に移動して、場所、番号の種類、状態情報など、組織の番号を表示します。
  
## <a name="assign-phone-numbers-to-users"></a>ユーザーに電話番号を割り当てる

電話番号を取得したら、各ユーザーに番号を割り当てる必要があります。 詳細については、「ユーザーの [電話番号の割り当て、変更、または削除」を](./assign-change-or-remove-a-phone-number-for-a-user.md)参照してください。

このビデオでは、ユーザーに電話番号を割り当てる手順を示します。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE54mbS?autoplay=false]

## <a name="related-articles"></a>関連記事

[電話番号の移行に関するよくある質問](./phone-number-calling-plans/port-order-overview.md)

[通話プランで使用されるさまざまな種類の電話番号](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)

[緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
