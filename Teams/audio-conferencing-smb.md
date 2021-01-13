---
title: 中小企業向け電話会議をセットアップする
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: jonorton, tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: '電話を使って会議にコールインする必要があるユーザーのために、中小企業で電話会議を設定する方法について説明します。 '
ms.openlocfilehash: 80e372e62ffdac9907521eb9426b465c9d0b6e92
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821287"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a>中小企業向け電話会議をセットアップする

電話会議では、モバイル デバイスやコンピューターから Teams アプリを使用する代わりに、電話を使って Teams 会議にコールインできます。  

最大 300 人のユーザーを持つ中小企業で、現在電話会議のライセンスを持っている場合は、電話会議を 1 年間無料で利用できます。 この無料特典は、2020 年 10 月 1 日から利用できます。

電話会議アドオン ライセンスは、Microsoft 365 Business Basic、Business Standard、Business Premium、Enterprise E1、または Enterprise E3 のライセンスを持つユーザーに適用できます。 詳細については、「Teams アドオン ライセンス [」を参照してください。](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

> [!NOTE]
> Enterprise E5 または Microsoft 365 Business Voice を使用している場合、これらのライセンスには電話会議が既に含まれるため、無料の電話会議サービスを使用することはできません。

この記事では、電話会議のセットアップ方法について説明します。 電話会議のセットアップは、ミーティングのスケジュールを設定するユーザーまたはミーティングを主催するユーザーにのみ必要です。 会議にコールインする会議の出席者は、ライセンスや他のセットアップを必要としません。 詳細については、「電話会議 [」を参照してください](audio-conferencing-in-office-365.md)。

## <a name="set-up-audio-conferencing"></a>電話会議をセットアップする

電話会議をセットアップすると、電話番号が会議ブリッジに自動的に割り当てられるので、会議出席依頼で使用できます。 会議ブリッジの既定の番号として割り当てられている電話番号は、組織の国または地域の電話番号になります。 この電話番号は有料電話番号で、長距離料金が適用される場合があります。

> [!NOTE]
> 無料電話番号を使用する場合も、いくつかの追加手順が必要です。 会議ブリッジの電話番号の詳細については、この記事の後半にある [電話会議の](#audio-conferencing-phone-numbers) 電話番号を参照してください。

### <a name="step-1-get-audio-conferencing-licenses"></a>手順 1: 電話会議ライセンスを取得する

会議を開催するユーザーごとに 1 つの電話会議ライセンスを取得します。 これを行うには、Microsoft 365 管理センターを使用します。

1. Microsoft 365 管理センターで、[課金購入サービス] に移動し、ページの下部にある [アドオン]  >  **を選択します**。
2. **Microsoft 365 電話会議導入プロモーション** の詳細を選択し、[今すぐ取得]  >  **を選択します**。
3. 会議の開催者に必要なライセンスの数を入力し、注文を完了します。

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="電話会議導入プロモーション ライセンスのスクリーンショット":::

    > [!NOTE]
    > このライセンスを持たなかったすべてのユーザーに電話会議ライセンスを自動的に割り当てるかどうかに応じて、[ライセンスを持たなかったすべてのユーザーに自動的に割り当てる] をオフまたは選択します。

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a>手順 2: 会議を開催するユーザーに電話会議ライセンスを割り当てる

会議を開催する各ユーザーにライセンスを割り当てる。 これを行うには、Microsoft 365 管理センターを使用します。

#### <a name="assign-a-license-to-one-user"></a>1 人のユーザーにライセンスを割り当てる

1. Microsoft 365 管理センターで、[アクティブなユーザー]**に**  >  **移動します**。  
2. ライセンスを割り当てるユーザーの行を選択し、ウィンドウで [ライセンスとアプリ **] を選択します**。
3. **[Microsoft 365 電話会議] チェック** ボックスをオンにし、[変更の保存]**を選択します**。

#### <a name="assign-a-license-to-multiple-users"></a>複数のユーザーにライセンスを割り当てる

1. Microsoft 365 管理センターで、[アクティブなユーザー]**に**  >  **移動します**。  
2. ライセンスを割り当てるユーザーの横にある円を選択し、[製品ライセンスの管理] **を選択します**。
3. [製品ライセンス **の管理] ウィンドウで、[** 追加の割り当 **て] を選択します**。
4. **[Microsoft 365 電話会議] チェック** ボックスをオンにし、[変更の保存]**を選択します**。  

## <a name="schedule-teams-meetings-in-outlook"></a>Outlook で Teams 会議をスケジュールする

会議の開催者は、Outlook で会議をスケジュールできます。 Outlook で [予定表] に **移動** し、[新しい Teams 会議] **ボタンを選択** します。 会議のダイヤルイン番号と会議 ID は、会議の出席者に送信される会議出席依頼に自動的に追加されます。 詳細については、「Outlook で [Teams 会議をスケジュールする」を参照してください](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)。

> [!NOTE]
> 必要に応じて、会議出席依頼をカスタマイズして、会社のロゴ、サポート Web サイトへのリンク、法的免責事項、テキストのみフッターを追加できます。 詳細については、「会議出席依頼を [カスタマイズする」を参照してください](meeting-settings-in-teams.md#customize-meeting-invitations)。

## <a name="audio-conferencing-phone-numbers"></a>電話会議の電話番号

会議ブリッジに使用できる番号には、2 種類があります。 共有番号 **(この** 記事の「電話会議 [](#set-up-audio-conferencing)の設定」セクションに示す) または専用の **番号を使用できます**。 それぞれの詳細を次に示します。

### <a name="shared-numbers"></a>共有番号

共有番号は、すべての組織で共有されている番号です。 共有電話番号は有料電話番号で、電話会議を設定すると自動的に割り当てられます。

会議ブリッジに割り当てられている既定の番号を表示するには、Microsoft Teams 管理センターの左側のナビゲーションで [会議会議ブリッジ] に移動し、最も近い場所の番号を検索します。  >  

### <a name="dedicated-numbers"></a>専用の番号

専用の番号は、ユーザーだけが利用できる数値です。 専用の番号には、有料電話番号またはフリーダイヤル番号を指定できます。 専用の番号を使用するには、まず番号を取得し、それを会議ブリッジに割り当て、その番号を会議の開催者ごとに割り当てる必要があります。

専用の番号を取得するには、いくつかの方法があります。 Microsoft から番号を取得するか、既存の番号を現在のサービス プロバイダーから Microsoft に転送 (ポート) することができます。 この方法の詳細については、「サービス番号を取得する [」を参照してください](getting-service-phone-numbers.md)。

無料電話番号を使用する場合は、会議を開催する各ユーザーにコミュニケーション クレジット のライセンスを割り当てる必要があります。 詳細については、組織の [コミュニケーション クレジットのセットアップに関するページを参照してください](set-up-communications-credits-for-your-organization.md)。

番号を作成した後、それを会議ブリッジに割り当てる。 これを行うには、Microsoft Teams 管理センターを使用します。

1. Microsoft Teams 管理センターの左側のナビゲーションで、会議ブリッジ **に**  >  **移動します**。
2. [追加 **]** を選択し、有料電話番号 **または** フリー **ダイヤル番号を選択します**。
3. [電話番号 **の追加] ウィンドウで** 番号を選択し、[適用] を選択 **します**。

次に、会議を開催する各ユーザーに番号を割り当てる。 これを行うには、Microsoft Teams 管理センターを使用します。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[ユーザー] を選択し、ユーザーの表示名をクリックして、[編集] を選択 **します**。
2. [**電話会議**]**の横** にある [編集]を選択し、[電話会議] ウィンドウで、有料電話番号または無料電話番号の一覧から番号を選択し、[適用] を選択 **します**。

## <a name="related-topics"></a>関連項目

- [電話会議](audio-conferencing-in-office-365.md)
- [Teams の電話会議をセットアップする](set-up-audio-conferencing-in-teams.md)
- [電話会議の電話番号](phone-numbers-for-audio-conferencing-in-teams.md)
- [電話会議に関するよくある質問](audio-conferencing-common-questions.md)
- [サービス番号の取得](getting-service-phone-numbers.md)
- [Teams アドオン ライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [ユーザーにライセンスを割り当てる](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
