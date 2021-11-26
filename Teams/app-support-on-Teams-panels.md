---
title: Microsoft Teamsパネルでのアプリ/Line of Business (LOB) アプリのサポートTeamsする
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
ms.date: 8/5/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: アプリ/LOB アプリのTeamsについて説明します。
ms.collection:
- M365-voice
- M365-collaboration
- skype-for-business-itpro
- skype-for-business-online
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8852ef3d212d2a284f4af72662c771d4c13b13af
ms.sourcegitcommit: 7cc7e237b0da270c9cf4a3e535db16dd113e4300
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2021
ms.locfileid: "61205637"
---
# <a name="microsoft-teams-appsline-of-business-lob-app-support-on-teams-panels"></a>Microsoft Teamsパネルでのアプリ/Line of Business (LOB) アプリのサポートTeamsする

Teamsパネルでは[、Teams/Line of Business (LOB) アプリのサポートが追加されています](/microsoftteams/platform/overview)。 これにより、企業は、組織のニーズを満たすためにパネルにエクスペリエンスを追加できます。 このリリースでは、静的な Web コンテンツがサポートされます。

> [!IMPORTANT]
> この機能は、パネル デバイスを更新した後Teamsでのみ使用できます。 Teams パネル内でアプリをサポートするには、Teams アプリ バージョン 1449/1.0.97.202107060 Teams 1 以降が必要です。

## <a name="teams-app-experience-on-teams-panels"></a>Teamsパネル上のアプリTeamsエクスペリエンス

![ユーザーがアプリTeamsを許可するセクションを示す管理センターのスクリーンショット。](media/tac1update.png) 

*[Teamsパネル] ホーム画面には、赤のスクリーンショットで示されているアプリナビゲーション オプションが含まれています。これらはアイコンの例であり、使用できない場合があります。*

![アプリを追加できるアプリ キャンバスのスクリーンショット。](media/appscreen.png)

*エンド ユーザーは、アプリ アイコンのいずれかをタップすると、前のスクリーンショットにTeamsアプリの画面が表示されます。スクリーンショットの灰色の四角形は、アプリがウィンドウのTeamsです。アプリ バーは固定され、パネル アプリTeams一部です。*

## <a name="set-up-and-manage-teams-panels-apps-in-teams-admin-center"></a>管理センターでTeamsパネル アプリを設定Teams管理する 

Microsoft Teamsアプリは、ユーザーが収集、学習、作業する場所に重要な情報、一般的なツール、信頼できるプロセスを提供します。 Teamsアプリは、[統合された機能を通じて動作します](/microsoftteams/platform/concepts/capabilities-overview)。 IT 管理者は、組織の Teams パネル デバイスに含めるアプリを選択し、Teams 管理センター を使用してアクセス[許可をカスタマイズできます](https://admin.teams.microsoft.com/)。

新しいパネルでTeamsアプリTeams、組織のニーズに基づいてユーザー エクスペリエンスをカスタマイズできます。 ユーザーがアクセスして使用できる Web アプリを決定し、アプリ ビューに優先順位を付けできます。 現時点では、ボットやメッセージング機能など、一部のオプションはサポートされていません。 アプリの詳細[と Teams で](/microsoftteams/platform/overview)[デバイスを管理する方法についてMicrosoft Teams。](/microsoftteams/devices/device-management)

## <a name="manage-apps-on-teams-panels-in-teams-admin-center"></a>管理センターでTeamsパネルでTeamsを管理する

**注**: 管理センター にアクセスするには、グローバル管理者または Teams サービス管理者 [Teams必要があります](https://admin.teams.microsoft.com/)。

エンド ユーザーは、アプリを表示できますが、すべてのパネルにTeamsできます。 管理者は、管理センターから組織Teamsアプリを表示および管理Teamsできます。 [アプリの管理] ページを [使用して、Microsoft Teams管理センター](/microsoftteams/manage-apps)でアプリを管理する方法 **について確認** します。 管理 **センター内の**[アプリのTeams ページでは、カスタム アプリを [アップロードすることもできます](/microsoftteams/manage-apps#publish-a-custom-app-to-your-organizations-app-store)。

アプリを設定した後は、アプリ[](/microsoftteams/teams-app-permission-policies)のアクセス許可ポリシーと[](/microsoftteams/teams-app-setup-policies)アプリ設定ポリシーを使用して、組織内の特定のルーム アカウントのアプリ エクスペリエンスを構成できます。

## <a name="pin-apps-on-teams-panels-with-app-setup-policies"></a>アプリ設定ポリシーを使用Teamsパネルにアプリをピン留めする

Teams にはさまざまなアプリを表示する機能が用意されています。管理者は、組織にとって最も重要なアプリを決定し、すばやくアクセスするために Teams パネルのホーム画面にのみこれらをピン留めできます。 ピン留めされたアプリまたは固定されていないアプリが 5 つ以上ある場合は、[その他] 画面に **表示** されます。 Microsoft では、ユーザー設定パネル専用のカスタム アプリ セットアップ ポリシーをTeamsしています。

![アプリセットアップ ポリシー ページのユーザー インターフェイスのスクリーンショット。](media/appsetup1.png) 

Teams パネルに表示される固定アプリを管理するには、組織の Teams 管理センターにサインインし、[Teams アプリのセットアップポリシー] [選択] または [新しいポリシー固定アプリの作成] に移動します \>  \>  \> 。

![ユーザー インターフェイス内の固定されたアプリ セクションのスクリーンショット。](media/appsetup2.png) 

*この画像に含まれるアプリは例に限定され、使用できない場合があります。*

Microsoft では、カスタム アプリと **ユーザーアップロード** をオフにし、パネル上で最適なTeamsアプリエクスペリエンスをTeams勧めします。

アプリのピン留めについて詳しくは、「アプリセットアップ ポリシー [の管理」をご覧ください](/microsoftteams/teams-app-setup-policies)。

## <a name="manage-apps-display-order-in-teams-panels"></a>アプリの表示順序を管理する (Teams パネル) 

![ユーザー インターフェイス内のアプリ セクションのスクリーンショット。](media/appsetup3.png)

*この画像に含まれるアプリは例に限定され、使用できない場合があります。*

Teams パネルにアプリが表示される順序を管理するには、組織の Teams 管理センターにサインインし **、[Teams** アプリのセットアップ ポリシー] に移動します。ポリシー固定アプリを選択します。 \>  \>  \>  

## <a name="assigning-setup-policies-to-a-room-resource-account"></a>セットアップ ポリシーをルーム リソース アカウントに割り当てる

セットアップ ポリシーを作成した後、管理者は、このポリシーを、Teams パネルにサインインするルーム リソース アカウントに割り当てる必要があります。 詳細については、「ユーザーとグループにポリシー [を割り当てる」を参照してください](/microsoftteams/assign-policies-users-and-groups)。

## <a name="faq"></a>よくあるご質問 (FAQ)

### <a name="how-long-does-it-take-for-teams-panels-to-get-the-new-or-updated-app-setup-policies"></a>新しいまたは更新されたアプリTeamsを取得するには、パネルにどのくらいの時間が必要ですか?

Teams 管理センターで新しいポリシーを編集または割り当てると、変更が有効なまで最大 24 時間かかる場合があります。 管理者は、パネルからサインアウト/サインインを試み **、設定** アイコンをタップして、[ホーム] 画面に戻ってポリシーを更新できます。

### <a name="what-is-the-ordering-of-the-apps-on-the-more-screen"></a>[その他] 画面でのアプリの順序は何ですか?

[その **他のアプリ** ] ページで、ピン留めされたアプリが最初に表示されます。 その後、インストールされているその他のアプリはアルファベット順に表示されます。

### <a name="why-are-bot-apps-not-showing-up-on-teams-panels"></a>ボット アプリが一部のパネルに表示Teams理由

現時点では、静的タブの Web コンテンツだけがサポートされています。

### <a name="why-are-native-teams-apps-such-as-calendar-and-tasks-not-appearing-on-teams-panels"></a>予定表やタスクTeamsなどのネイティブ アプリが、他のパネルに表示されないTeams。

予定表Teamsタスクなどのネイティブ アプリは、一部のパネルTeamsされません。

### <a name="in-the-teams-admin-center-under-the-setup-policies-section-what-is-the-difference-between-installed-apps-and-pinned-apps"></a>[Teams センターの [セットアップ ポリシー] セクションで、インストールされているアプリとピン留めされたアプリの違いは何ですか?

パネルTeams、Microsoft ではピン留めされたアプリの使用をお勧めします。そのため、管理者は目的のアプリを選択し、順序を変更できます。

**注:** 一部のアプリでは、アプリのピン留めがサポートされていません。 アプリのピン留め機能を有効にするには、アプリ開発者にお問い合わせください。

### <a name="why-are-other-apps-appearing-in-the-more-screen-even-though-they-are-not-part-of-the-installed-or-pinned-apps-in-the-teams-app-setup-policy-section"></a>[Teams アプリセットアップ ポリシー] セクションのインストール済みアプリまたはピン留めされたアプリの一部ではないにもかかわらず、他のアプリが [その他] 画面に表示される理由

アプリが他のアプリ ポリシーを使用して以前にインストールされた場合、または Teams パネルで使用されるルーム リソース アカウントの Teams デスクトップ/Web クライアントに手動でインストールされている場合、管理者は Teams のルーム リソース アカウントにサインインし、アプリを右クリックしてアプリを手動でアンインストールし、[アンインストール] を選択する必要 **があります。**

### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>[ピン留めされたアプリの追加] ウィンドウにアプリが見当たらない理由

すべてのアプリをアプリ セットアップ ポリシーをTeamsにピン留めすることはできません。 一部のアプリでは、この機能がサポートされていない場合があります。 ピン留めできるアプリを見つけるには、[ピン留めされたアプリの追加] **ウィンドウでアプリを検索** します。 詳細については、「アプリセットアップ ポリシー [の操作」の FAQ を参照してください](/microsoftteams/teams-app-setup-policies#why-cant-i-find-an-app-in-the-add-pinned-apps-pane)。

### <a name="why-am-i-seeing-an-user-pinning-pop-up-in-the-setup-policies-panel-after-i-turn-off-user-pinning"></a>"ユーザーピン留め" をオフにした後、セットアップ ポリシー パネルに "ユーザーピン留め" ポップアップが表示される理由

![ユーザー のピン留めがアクティブな状態を確認するポップアップが表示された、ユーザー インターフェイス内のセットアップ ポリシー セクションのスクリーンショット。](media/appsetup4.png)

*この画像に含まれるアプリは例に限定され、使用できない場合があります。* 

この動作は、共有空間内のデバイスに対して想定され、意図しないアプリのピン留めを防ぐのに役立ちます。
