---
title: 通話プランのサービス電話番号を取得する
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
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 新しい電話番号を取得し、Teams の電話会議、自動応答、通話キュー (サービス番号) の既存の番号を移植または転送する方法について説明します。
ms.openlocfilehash: f72e24db204a53680a3f82469a7a77ca81943d8f
ms.sourcegitcommit: 1398c778e46b0d81c9710cd70d3818a2b7af995a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2023
ms.locfileid: "69749053"
---
# <a name="service-phone-numbers-for-calling-plans"></a>通話プランのサービス電話番号

[ユーザーの電話番号を取得](./getting-phone-numbers-for-your-users.md)するだけでなく、電話会議 (会議ブリッジ用)、自動応答、通話キュー (サービス番号とも呼ばれます) などのサービスの有料電話番号または無料電話番号を取得できます。 サービス用電話番号の同時通話容量は、ユーザーまたは登録者の電話番号より大きくなります。 たとえば、サービス番号は数百の呼び出しを同時に処理できますが、ユーザーの電話番号では同時に処理できる通話は数個のみです。
  
> [!NOTE]
> フリーダイヤル番号を取得するには、まずコミュニケーション クレジットを設定する必要があります。 詳細については、「 [組織のコミュニケーション クレジットを設定する」を参照してください](./set-up-communications-credits-for-your-organization.md)。
  
サービス番号を取得するには、次の 3 つの方法があります。
  
- **Microsoft Teams 管理センターを使用します。** 一部の国と地域では、Microsoft Teams 管理センターを使用してサービス番号を取得できます。 「 [新しいサービス番号を取得する」を](#get-new-service-numbers)参照してください。

- **既存の番号を移行する。** 現在のサービス プロバイダーまたは電話会社から既存の番号を移植または転送できます。 詳細については、「 [Teams に電話番号を転送する](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 」または [「組織の電話番号を管理する」を参照してください](/microsoftteams/manage-phone-numbers-for-your-organization)。  
  
- **新しい番号には申請書を使用します。** Microsoft Teams 管理センターを使用して新しい電話番号を取得できない場合や、特定の電話番号や市域コードが必要な場合があります。 その場合は、フォームをダウンロードして返送する必要があります。 詳細については、「[組織のために電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)」をご覧ください。
  
> [!NOTE]
> 特定の番号の同時呼び出し容量を増やすことができるように、サービス番号が必要です。 当社に番号を転送する場合は、 [TNS サービス デスクに問い合わせて](manage-phone-numbers-for-your-organization/contact-tns-service-desk.md) 、転送するサービス番号の同時通話容量が高いかどうかを確認できます。
  
## <a name="get-new-service-numbers"></a>新しいサービス番号を取得する

新しいサービス番号を取得するには、Teams 管理センターで次の手順を実行します。

1. 左側のナビゲーションで、[ **音声** > **電話番号**] に移動し、[ **追加**] を選択します。

2. 注文の名前を入力し、説明を追加します。

3. [ **場所と数量** ] ページで、次の手順を実行します。
    - [ **国または地域**] で、国または地域を選択します。
    - [ **数値の種類**] で、目的のサービス番号の種類を選択します。
    - [ **場所] で**、場所を選択します。 新しい場所を作成する必要がある場合は、[ **場所の追加**] を選択します。
    - [ **地域コード**] で、エリア コードを選択します。 
    - [ **数量]** で、組織に必要な番号の数を入力し、[ **次へ** ] を選択して番号を選択します。

4. 目的の番号を選択します。 電話番号を選択して注文するには、10 分かかります。 10 分以上かかる場合、電話番号は番号のプールに返されます。

5. 注文の準備ができたら、[注文] を選択 **します**。

## <a name="port-or-transfer-existing-service-numbers"></a>既存のサービス番号を移行または転送する

現在のサービス プロバイダーまたは通信事業者から Teams に電話番号を転送するには、Microsoft Teams 管理センターの移植ウィザードを使用します。 [「電話番号を Teams に転送する](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md)」の手順に従います。

移植ウィザードで問題が発生した場合は、 [手動でポート注文を送信](phone-number-calling-plans/manually-submit-port-order.md) するか、[ [組織の電話番号の管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)] に移動し、国または地域を選択して、承認状 (LOA) をダウンロードできます。 LOA を使用して転送するサービス番号 (フリーダイヤルとフリーダイヤルなど) ごとに個別のポート注文を送信する必要があります。 LOA では、正しい種類のサービス番号を選択する必要があります。 サービス番号 (ユーザーまたはサブスクライバー番号ではなく) を転送することを指定するか、同時呼び出し容量が呼び出しボリュームを処理するのに十分でない可能性があることを確認してください。  

> [!NOTE]
> 追加の電話番号は、Microsoft Teams 管理センターで購入できます。 多数のポート (1000 以上)、複雑なポート、またはサポートが必要な場合は、 [TNS サービス デスクにお問い合わせください](manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)。

## <a name="view-the-phone-numbers-for-your-organization"></a>組織の電話番号を表示する

Teams 管理センターの左側のナビゲーションで、[ **音声** > **電話番号** ] に移動して、場所、番号の種類、状態情報など、組織の番号を表示します。

## <a name="assign-service-phone-numbers"></a>サービスの電話番号を割り当てる

サービス番号を取得したら、各番号を電話会議ブリッジに割り当てます。 [電話会議ブリッジのフリーダイヤル番号またはフリーダイヤル番号の変更に関するページを参照してください](./change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。

## <a name="related-articles"></a>関連記事

[電話システムで利用できる機能](./here-s-what-you-get-with-phone-system.md)

[電話番号の移行に関するよくある質問](./phone-number-calling-plans/port-order-overview.md)

[通話プランで使用されるさまざまな種類の電話番号](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)

[国および地域ごとの電話会議および通話プランの利用可能性](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
