---
title: 中小規模企業向けの電話会議をセットアップする
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: jonorton, tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: '会議へのコールインに電話を使用する必要があるユーザー向けに、中小規模企業で電話会議を設定する方法について説明します。 '
ms.openlocfilehash: b692654a0a874ea0c07f074daefe203aef2f80bc
ms.sourcegitcommit: 764605e226bc7d9cf45e9833c758d30da29132c1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2020
ms.locfileid: "48594648"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a>中小規模企業向けの電話会議をセットアップする

電話会議を使用すると、ユーザーは、モバイルデバイスまたは自分のコンピューターから teams アプリを使っていなくても、電話を使用して Teams 会議にコールインすることができます。  

中小規模企業で、最大300人のユーザーがいて、現在電話会議のライセンスを持っていない場合は、1年間は電話会議を無料で受けることができます。 この無料キャンペーンは、2020年10月1日から利用できます。

電話会議アドオンライセンスは、Microsoft 365 Business Basic、Business Standard、Business Premium、enterprise E1、Enterprise E3 のライセンスを所有しているユーザーに適用することができます。 詳細については、「 [Teams アドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。

> [!NOTE]
> Enterprise E5 または Microsoft 365 ビジネス Voip を使用している場合、これらのライセンスには電話会議が既に含まれているため、無料の電話会議プランは使用できません。

この記事では、電話会議をセットアップする方法について説明します。 電話会議のセットアップは、ミーティングのスケジュールを設定するユーザーまたはミーティングを主催するユーザーにのみ必要です。 会議へのコールインを行う会議出席者は、ライセンスまたはその他の設定を必要としません。 詳細については、「 [電話会議](audio-conferencing-in-office-365.md)」を参照してください。

## <a name="set-up-audio-conferencing"></a>電話会議をセットアップする

電話会議をセットアップすると、電話番号が会議の出席依頼で使用できるように、会議ブリッジに自動的に割り当てられます。 会議ブリッジの既定の番号として割り当てられている電話番号は、組織の国または地域のいずれかになります。 この電話番号は有料番号であり、長距離通話料金が適用されることがあります。

> [!NOTE]
> また、無料番号を使用して、いくつかの手順を追加する必要があります。 会議ブリッジの電話番号の詳細については、この記事の後半の「 [電話会議の電話番号](#audio-conferencing-phone-numbers) 」を参照してください。

### <a name="step-1-get-audio-conferencing-licenses"></a>手順 1: 電話会議ライセンスを取得する

会議を開催する各ユーザーに対して1つの電話会議ライセンスを取得します。 この操作を行うには、Microsoft 365 管理センターを使用します。

1. Microsoft 365 管理センターで、[**課金**  >  **サービス**] に移動し、ページの下部にある [**アドオン**] を選択します。
2. [ **Microsoft 365 電話会議の導入キャンペーン**の詳細] を選択し  >  **Details**、[**今すぐ取得**] を選択します。
3. 会議の開催者に必要なライセンスの数を入力して、注文を完了します。

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="電話会議の採用プロモーションライセンスのスクリーンショット":::

    > [!NOTE]
    > [このライセンスを持っていないすべてのユーザーに電話会議ライセンスを自動的に割り当てる] のいずれかを選択して、[ **ライセンスのないすべてのユーザーに自動的に割り当てる**] チェックボックスをオンまたはオフにします。

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a>手順 2: 会議をリードするユーザーに電話会議ライセンスを割り当てる

会議を開催する各ユーザーにライセンスを割り当てます。 この操作を行うには、Microsoft 365 管理センターを使用します。

#### <a name="assign-a-license-to-one-user"></a>1人のユーザーにライセンスを割り当てる

1. Microsoft 365 管理センターで、[アクティブな**ユーザー**] に移動  >  **Active users**します。  
2. ライセンスを割り当てるユーザーの行を選び、ウィンドウで [ **ライセンスとアプリ**] を選びます。
3. [ **Microsoft 365 電話会議** ] チェックボックスをオンにして、[ **変更の保存**] を選択します。

#### <a name="assign-a-license-to-multiple-users"></a>複数のユーザーにライセンスを割り当てる

1. Microsoft 365 管理センターで、[アクティブな**ユーザー**] に移動  >  **Active users**します。  
2. ライセンスを割り当てるユーザーの横にある円を選択し、[ **製品ライセンスの管理**] を選択します。
3. [ **製品ライセンスの管理** ] ウィンドウで、[ **その他の割り当て**] を選択します。
4. [ **Microsoft 365 電話会議** ] チェックボックスをオンにして、[ **変更の保存**] を選択します。  

## <a name="schedule-teams-meetings-in-outlook"></a>Outlook で Teams の会議をスケジュールする

会議の開催者が Outlook で会議をスケジュールできるようになりました。 Outlook で [ **予定表**] に移動し、[ **新しいチーム会議** ] ボタンを選択します。 会議のダイヤルイン番号と会議 ID が、会議出席者に送信された会議出席依頼に自動的に追加されます。 詳細については、「 [Outlook で Teams 会議のスケジュールを設定](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)する」を参照してください。

> [!NOTE]
> 必要に応じて、会議出席依頼をカスタマイズして、会社のロゴ、サポート web サイトおよび法的免責事項へのリンク、テキストのみのフッターを追加することができます。 詳細については、「 [会議出席依頼をカスタマイズ](meeting-settings-in-teams.md#customize-meeting-invitations)する」を参照してください。

## <a name="audio-conferencing-phone-numbers"></a>電話会議の電話番号

電話会議ブリッジに使用できる番号には2種類あります。 **共有番号**(この記事の前半の「[電話会議の設定](#set-up-audio-conferencing)」のセクションの場合)、または**専用の番号**を使うことができます。 それぞれの詳細については、こちらを参照してください。

### <a name="shared-numbers"></a>共有番号

共有番号は、すべての組織で共有される番号です。 共有番号は有料番号で、電話会議のセットアップ時に自動的に割り当てられます。

会議ブリッジに割り当てられている既定の電話番号を確認するには、Microsoft Teams 管理センターの左側のナビゲーションで、[**会議**  >  **会議ブリッジ**] に移動して、最寄りの場所の番号を見つけます。

### <a name="dedicated-numbers"></a>専用電話番号

専用番号は、ユーザーだけが使用できる番号です。 専用電話番号には、有料番号または無料電話番号を使用できます。 専用の番号を使用するには、最初に番号を取得し、それを会議ブリッジに割り当てる必要があります。その後、会議を開催する各ユーザーに番号を割り当てます。

専用の電話番号を取得するには、いくつかの方法があります。 Microsoft から電話番号を取得するか、現在のサービスプロバイダーから Microsoft に既存の番号を移行 (移植) することができます。 この方法について詳しくは、「 [サービス番号を取得](getting-service-phone-numbers.md)する」をご覧ください。

無料電話番号を使用する場合は、まず会議を開催する各ユーザーに通信クレジットのライセンスを割り当てる必要があることに注意してください。 詳細については、「 [組織のためにコミュニケーションクレジット](set-up-communications-credits-for-your-organization.md)をセットアップする」を参照してください。

番号を取得したら、それを会議ブリッジに割り当てます。 この操作を行うには、Microsoft Teams 管理センターを使用します。

1. Microsoft Teams 管理センターの左のナビゲーションで、[**会議**  >  **会議ブリッジ**] に移動します。
2. [ **追加**] を選択し、[ **有料電話番号** ] または [無料 **電話番号**] を選択します。
3. [ **電話番号の追加** ] ウィンドウで番号を選択し、[ **適用**] を選択します。

次に、会議を開催する各ユーザーに番号を割り当てます。 この操作を行うには、Microsoft Teams 管理センターを使用します。

1. Microsoft Teams 管理センターの左のナビゲーションで、[ **ユーザー**] を選択し、ユーザーの表示名をクリックして、[ **編集**] を選択します。
2. [電話会議] の横にある [ **編集**] を選択し、[電話会議] ウィンドウで、[有料電話番号] または [無料電話番号] の   一覧から番号を選択し、[ **Audio Conferencing** **Audio Conferencing**    **Toll number**    **Toll-free**   **適用**] を選択します。

## <a name="related-topics"></a>関連トピック

- [電話会議](audio-conferencing-in-office-365.md)
- [Teams の電話会議をセットアップする](set-up-audio-conferencing-in-teams.md)
- [電話会議の電話番号](phone-numbers-for-audio-conferencing-in-teams.md)
- [電話会議に関するよくある質問](audio-conferencing-common-questions.md)
- [サービス番号の取得](getting-service-phone-numbers.md)
- [Teams アドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [ライセンスをユーザーに割り当てる](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
