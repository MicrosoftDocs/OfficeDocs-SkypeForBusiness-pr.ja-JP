---
title: サービス電話番号を取得する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, jastark, oscarr, makolomi
ms.topic: article
ms.assetid: e434aeb2-af99-40e7-981e-a474f0383734
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: Teams の電話会議、自動応答、通話キュー (サービス番号) の新しい電話番号を取得し、既存の番号を移植または転送する方法について説明します。
ms.openlocfilehash: 72436591411070ed7ffc67aab5d8d4470f39521d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092235"
---
# <a name="getting-service-phone-numbers"></a>サービス電話番号を取得する

ユーザーの電話番号[](./getting-phone-numbers-for-your-users.md)を取得する以外に、電話会議 (電話会議ブリッジ用)、自動応答、通話キュー (サービス番号とも呼ばれる) などのサービスの有料または無料電話番号を取得できます。 サービス用電話番号の同時通話容量は、ユーザーまたは登録者の電話番号より大きくなります。 たとえば、サービス番号は何百もの通話を同時に処理できるのに対し、ユーザーの電話番号は同時に数件の通話しか処理できません。
  
> [!NOTE]
> 無料電話番号を取得するには、まずコミュニケーション クレジットを設定する必要があります。 詳細については、組織の [コミュニケーション クレジットのセットアップに関するページを参照してください](./set-up-communications-credits-for-your-organization.md)。
  
サービス番号を取得するには、次の 3 つの方法があります。
  
- **Microsoft Teams 管理センターを使用します。** 一部の国と地域では、Microsoft Teams 管理センターを使用してサービス番号を取得できます。 「新 [しいサービス番号を取得する」を参照してください](#get-new-service-numbers)。

- **既存の番号を移行する。** 現在のサービス プロバイダーまたは携帯電話会社から既存の番号を移植または転送することができます。 この方法の詳細については、「[Teams に電話番号を移行](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md)」または「[組織の電話番号を管理](/microsoftteams/manage-phone-numbers-for-your-organization)」を参照してください。  
  
- **新しい番号には申請書を使用します。** (お客様の国や地域に応じて) Microsoft Teams 管理センターを使用して新しい電話番号を取得できない場合や、特定の電話番号または市番が必要になる場合があります。 その場合は、フォームをダウンロードして返送する必要があります。 詳細については「[組織の電話番号を管理](/microsoftteams/manage-phone-numbers-for-your-organization) 」を参照してください。
  
> [!NOTE]
> サービス番号は、特定の番号に対してより高い同時通話容量を取得するために必要です。 番号を転送する場合は [、PSTN](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md) サービス デスクに問い合わせ、移行するサービス番号の同時通話容量が高い確認を行います。
  
## <a name="get-new-service-numbers"></a>新しいサービス番号を取得する

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

1. 左側のナビゲーションで、[**音声電話番号]** に移動し、[追加]  >  をクリック **します**。
2. 注文の名前を入力し、説明を追加します。
3. [場所と数量] ページで、次の操作を行います。
    1. [ **国または地域] で**、国または地域を選択します。
    1. [ **番号の種類]** で、必要なサービス番号の種類を選択します。
    1. [ **場所] で** 場所を選択します。 新しい場所を作成する必要がある場合は、[場所の追加 **] をクリックします**。
    1. [ **郵便番号] で**、地域コードを選択します。 
    2. [**数量]** で、組織に必要な数値の数を入力し、[次へ] をクリックして番号を選択します。
4. 目的の数値を選択します。 電話番号を選択して注文するには、10 分かかります。 10 分以上かかる場合は、電話番号が番号のプールに返されます。
5. 注文の準備ができたら、[注文] を **クリックします**。

## <a name="port-or-transfer-existing-service-numbers"></a>既存のサービス番号を移行または転送する

現在のサービス プロバイダーまたは通信事業者から Teams に電話番号を転送するには、Microsoft Teams 管理センターの移植ウィザードを使用できます。 「電話番号を [Teams に転送する」の手順に従います](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。

お客様の国または地域が移植ウィザードに表示されていない場合は、ポート注文を[](phone-number-calling-plans/manually-submit-port-order.md)手動で送信するか、組織の電話番号[](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)の管理に移動して、お客様の国または地域を選択し、承認状 (LOA) をダウンロードできます。 LOA を使用して移行するサービス番号の種類 (有料と無料通話など) ごとに個別の番号移行注文を送信する必要があります。 LOA で、適切なサービス番号の種類を選択する必要があります。 サービス番号 (ユーザーまたはサブスクライバー番号ではなく) を転送する場合、または同時呼び出しキャパシティーが通話ボリュームを処理するのに十分ではない可能性がある場合は、必ず指定してください。  

> [!NOTE]
> これより多くの電話番号を取得する必要がある場合は [、PSTN サービス デスクにお問い合わせください](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)。

## <a name="view-the-phone-numbers-for-your-organization"></a>組織の電話番号を表示する

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する** 

左側のナビゲーションで [音声電話番号] に移動し、場所、番号の種類、状態情報など、組織の番号  >  を表示します。

## <a name="assign-service-phone-numbers"></a>サービス電話番号を割り当てる

サービス番号を取得した後、各番号を電話会議ブリッジに割り当てる。 「 [電話会議ブリッジで有料または無料電話番号を変更する」を参照してください](./change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。

## <a name="related-topics"></a>関連項目

[電話システムで利用できる機能](./here-s-what-you-get-with-phone-system.md)

[電話番号の移行に関するよくある質問](./phone-number-calling-plans/port-order-overview.md)

[通話プランで使用されるさまざまな種類の電話番号](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)

[国および地域ごとの電話会議および通話プランの利用可能性](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)