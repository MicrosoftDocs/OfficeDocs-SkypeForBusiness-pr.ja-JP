---
title: 中小企業向けに音声会議を設定する
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: '電話を使用して会議に呼び出す必要があるユーザーに対して、小規模または中規模のビジネスで電話会議を設定する方法について説明します。 '
ms.openlocfilehash: 91db0bc151d48b2aa7e9557fff7157626ca4ef4f
ms.sourcegitcommit: 296fbefe0481c0b8b94aee925118474375cdf138
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2022
ms.locfileid: "65016589"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a>中小企業向けに音声会議を設定する

電話会議を使用すると、モバイル デバイスやコンピューターでTeams アプリを使用する代わりに、電話を使用して会議をTeamsに呼び出すことができます。  

最大 300 人のユーザーを持つ小規模または中規模のビジネスで、現在電話会議ライセンスがない場合は、電話会議を 1 年間無料で入手できます。 この無料プランは、2020 年 10 月 1 日から提供されています。

電話会議アドオン ライセンスは、Microsoft 365 Business Basic、Business Standard、Business プレミアム、Enterprise E1、または Enterprise E3 ライセンスを持つユーザーに適用できます。 詳細については、[アドオン ライセンスのTeamsに関するページを](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)参照してください

> [!NOTE]
> E5 またはMicrosoft 365 Business Voice Enterpriseしている場合、これらのライセンスには電話会議が既に含まれているため、無料の電話会議オファーを使用することはできません。

この記事では、電話会議を設定する方法について説明します。 電話会議のセットアップは、ミーティングのスケジュールを設定するユーザーまたはミーティングを主催するユーザーにのみ必要です。 会議に呼び出す会議出席者には、ライセンスやその他の設定は必要ありません。 詳細については、「 [電話会議](audio-conferencing-in-office-365.md)」を参照してください。

## <a name="set-up-audio-conferencing"></a>電話会議をセットアップする

電話会議を設定すると、会議の招待状で使用できるように、電話番号が会議ブリッジに自動的に割り当てられます。 会議ブリッジの既定の番号として割り当てられている電話番号は、組織の国または地域の電話番号になります。 この電話番号は有料電話番号で、長い距離の料金が適用される場合があります。

> [!NOTE]
> フリーダイヤル番号を使用することもできます。これには、いくつかの追加手順が必要です。 会議ブリッジの電話番号の詳細については、この記事の後半の [「電話会議の電話番号](#audio-conferencing-phone-numbers) 」を参照してください。

### <a name="step-1-get-audio-conferencing-licenses"></a>手順 1: 電話会議ライセンスを取得する

会議を主導する各ユーザーに対して 1 つの電話会議ライセンスを取得します。 これを行うには、Microsoft 365 管理センターを使用します。

1. Microsoft 365 管理センター **で** **BillingPurchase** >  サービスに移動し、ページの下部にある **[アドオン**] を選択します。
2. **[電話会議の導入のプロモーション** > **を** Microsoft 365]、[**今すぐ取得**] の順に選択します。
3. 会議の開催者に必要なライセンスの数を入力し、注文を完了します。

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="電話会議導入プロモーション ライセンスのスクリーンショット。":::

    > [!NOTE]
    > このライセンスを持 **っていないすべてのユーザーに** 電話会議ライセンスを自動的に割り当てるかどうかに応じて、[ライセンスのないすべてのユーザーに自動的に割り当てる] をオフまたは選択します。

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a>手順 2: 会議をリードするユーザーに電話会議ライセンスを割り当てる

会議を主導する各ユーザーにライセンスを割り当てます。 これを行うには、Microsoft 365 管理センターを使用します。

#### <a name="assign-a-license-to-one-user"></a>1 人のユーザーにライセンスを割り当てる

1. Microsoft 365 管理センターで、**UsersActive** >  ユーザーに移動 **します**。  
2. ライセンスを割り当てるユーザーの行を選択し、ウィンドウで **[ライセンスとアプリ**] を選択します。
3. **[Microsoft 365電話会議**] チェック ボックスをオンにし、[**変更の保存]** を選択します。

#### <a name="assign-a-license-to-multiple-users"></a>複数のユーザーにライセンスを割り当てる

1. Microsoft 365 管理センターで、**UsersActive** >  ユーザーに移動 **します**。  
2. ライセンスを割り当てるユーザーの横にある円を選択し、[ **製品ライセンスの管理**] を選択します。
3. [ **製品ライセンスの管理** ] ウィンドウで、[ **その他の割り当て**] を選択します。
4. **[Microsoft 365電話会議**] チェック ボックスをオンにし、[**変更の保存]** を選択します。  

## <a name="schedule-teams-meetings-in-outlook"></a>OutlookでTeams会議をスケジュールする

会議の開催者は、Outlookで会議をスケジュールできるようになりました。 Outlookで、[**予定表**] に移動し、[**新しいTeams会議**] ボタンを選択します。 会議のダイヤルイン番号と会議 ID は、会議出席者に送信される会議出席依頼に自動的に追加されます。 詳細については、「[OutlookでTeams会議をスケジュール](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)する」を参照してください。

> [!NOTE]
> 必要に応じて、会議出席依頼をカスタマイズして、会社のロゴ、サポート Web サイトへのリンク、免責事項、テキストのみのフッターを追加できます。 詳細については、「 [会議出席依頼をカスタマイズする](meeting-settings-in-teams.md#customize-meeting-invitations)」を参照してください。

## <a name="audio-conferencing-phone-numbers"></a>電話会議の電話番号

会議ブリッジに使用できる番号には、2 種類あります。 **共有番号** (この記事の「[電話会議のセットアップ](#set-up-audio-conferencing)」セクションで説明したように) または **専用番号** を使用できます。 それぞれの詳細については、以下をご覧ください。

### <a name="shared-numbers"></a>共有番号

共有番号は、すべての組織で共有される数値です。 共有番号は有料電話番号であり、電話会議を設定すると自動的に割り当てられます。

会議ブリッジに割り当てられている既定の番号を表示するには、Microsoft Teams管理センターの左側のナビゲーションで **MeetingsConference** >  ブリッジに移動し、最も近い場所の番号を見つけます。

### <a name="dedicated-numbers"></a>専用番号

専用番号は、ユーザーのみが使用できる番号です。 専用番号には、有料電話番号またはフリーダイヤル番号を指定できます。 専用の番号を使用するには、まず番号を取得し、会議ブリッジに割り当ててから、会議を主導する各ユーザーに番号を割り当てる必要があります。

専用番号を取得するには、いくつかの方法があります。 Microsoft から番号を取得するか、現在のサービス プロバイダーから Microsoft に既存の番号を転送 (ポート) できます。 これを行う方法の詳細については、「 [サービス番号の取得](getting-service-phone-numbers.md)」を参照してください。

フリーダイヤル番号を使用する場合は、まず会議を主導する各ユーザーに通信クレジット ライセンスを割り当てる必要があることに注意してください。 詳細については、「 [組織の通信クレジットを設定する」を参照してください](set-up-communications-credits-for-your-organization.md)。

電話番号を取得したら、それを会議ブリッジに割り当てます。 これを行うには、Microsoft Teams管理センターを使用します。

1. Microsoft Teams管理センターの左側のナビゲーションで、**MeetingsConference** >  ブリッジに移動します。
2. [ **追加]** を選択し、 **有料電話番号** または **フリーダイヤル番号を** 選択します。
3. [ **電話番号の追加] ウィンドウで、番号** を選択し、[ **適用**] を選択します。

#### <a name="assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>会議をリードするユーザーにダイヤルイン電話番号を割り当てる

「[Microsoft Teamsの招待に含まれる電話番号を設定する](set-the-phone-numbers-included-on-invites-in-teams.md)」を参照してください。

> [!NOTE]
> *TeamsAudioconferencingpolicy* に電話番号を追加し、ポリシーをユーザーに割り当てることで電話番号を設定することもできます。 ポリシーに追加された有料電話番号とフリーダイヤル電話番号は、電話会議設定ウィンドウでユーザーに対して個別に設定された電話番号よりも優先されます。 *Teamsaudioconferencingpolicy* に電話番号が追加されていない場合は、電話会議の設定ウィンドウでユーザーに個別に設定された電話番号が会議出席依頼Microsoft Teamsに表示されます。 [有料電話番号とフリーダイヤル番号の電話会議ポリシー設定](audio-conferencing-toll-free-numbers-policy.md) の詳細については、以下をご覧ください。

## <a name="related-topics"></a>関連項目

- [電話会議](audio-conferencing-in-office-365.md)
- [Teamsの電話会議を設定する](set-up-audio-conferencing-in-teams.md)
- [電話会議の電話番号](phone-numbers-for-audio-conferencing-in-teams.md)
- [電話会議に関するよくある質問](audio-conferencing-common-questions.md)
- [サービス番号の取得](getting-service-phone-numbers.md)
- [アドオン ライセンスをTeamsする](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [ユーザーにライセンスを割り当てる](/microsoft-365/admin/manage/assign-licenses-to-users)
