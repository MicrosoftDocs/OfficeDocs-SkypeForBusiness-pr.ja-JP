---
title: Teams パネルでの Microsoft Teams アプリ/基幹業務 (LOB) アプリのサポート
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 8/5/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Teams アプリ/LOB アプリのサポートについて説明します。
ms.collection:
- M365-voice
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c8d28a3f985a38e174030ddbe0e6d43e2153738
ms.sourcegitcommit: 1161cddd077056a9c1e2da99a84e35be0380b1b1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2022
ms.locfileid: "68656073"
---
# <a name="microsoft-teams-appsline-of-business-lob-app-support-on-teams-panels"></a>Teams パネルでの Microsoft Teams アプリ/基幹業務 (LOB) アプリのサポート

Teams パネルでは、 [Teams アプリ/基幹業務 (LOB) アプリの](/microsoftteams/platform/overview)サポートが追加されています。 これにより、企業は組織のニーズを満たすためにパネルに追加のエクスペリエンスを追加できます。 このリリースでは、静的 Web コンテンツがサポートされています。

> [!IMPORTANT]
> この機能は、Teams パネル デバイスを更新した後にのみ使用できます。 Teams パネル内でアプリをサポートするには、Teams アプリ バージョン 1449/1.0.97.2021070601 以降が必要です。

## <a name="teams-app-experience-on-teams-panels"></a>Teams パネルでの Teams アプリ エクスペリエンス

![ユーザーがアプリに移動できるようにするセクションを示す Teams 管理センターのスクリーンショット。](media/tac1update.png)

*Teams パネルのホーム画面には、アプリのナビゲーション オプションが含まれています。赤のスクリーンショットで囲まれています。これらはアイコンの例であり、使用できない場合があることに注意してください。*

![アプリを追加できるアプリ キャンバスのスクリーンショット。](media/appscreen.png)

*エンド ユーザーがいずれかのアプリ アイコンをタップすると、前のスクリーンショットに Teams アプリの画面が表示されます。スクリーンショットの灰色の四角形は、アプリがTeams パネルに表示される場所です。アプリ バーは固定されており、Teams パネル アプリの一部です。*

## <a name="set-up-and-manage-teams-panels-apps-in-teams-admin-center"></a>Teams 管理センターで Teams パネル アプリを設定および管理する

Microsoft Teams アプリは、重要な情報、一般的なツール、信頼できるプロセスを、ユーザーが収集、学習、作業する場所に提供します。 Teams アプリは [、統合された機能を通じて機能します](/microsoftteams/platform/concepts/capabilities-overview)。 IT 管理者は、組織の Teams パネル デバイスに含めるアプリを選択し、 [Teams 管理センター](https://admin.teams.microsoft.com/)を使用してアクセス許可をカスタマイズできます。

Teams パネルで Teams アプリを使用し、組織のニーズに基づいてユーザー エクスペリエンスをカスタマイズできるようになりました。 ユーザーがアクセスして使用できる Web アプリを決定し、アプリ ビューに優先順位を付けることができます。 現時点では、ボットやメッセージング機能などの一部のオプションはサポートされていません。 [Teams アプリの](/microsoftteams/platform/overview)詳細と、[Microsoft Teams でデバイスを管理する方法について説明します](/microsoftteams/devices/device-management)。

## <a name="manage-apps-on-teams-panels-in-teams-admin-center"></a>Teams 管理センターの Teams パネルでアプリを管理する

**注**: Teams [管理センター](https://admin.teams.microsoft.com/)にアクセスするには、グローバル管理者または Teams サービス管理者である必要があります。

エンド ユーザーは、Teams パネルにアプリを表示できますが、インストールすることはできません。 管理者は、Teams 管理センターを使用して、組織のすべての Teams アプリを表示および管理できます。 [Microsoft Teams 管理センターでアプリを管理](/microsoftteams/manage-apps)する方法の詳細については、**アプリの管理** に関するページを参照してください。 Teams 管理センター内の **[アプリの管理** ] ページでは、 [カスタム アプリ](/microsoftteams/manage-apps#publish-a-custom-app-to-your-organizations-app-store)をアップロードすることもできます。

アプリを設定したら、 [アプリのアクセス許可ポリシー](/microsoftteams/teams-app-permission-policies) と [アプリセットアップ ポリシー](/microsoftteams/teams-app-setup-policies) を使用して、組織内の特定のルーム アカウントのアプリ エクスペリエンスを構成できます。

## <a name="pin-apps-on-teams-panels-with-app-setup-policies"></a>アプリセットアップ ポリシーを使用して Teams パネルにアプリをピン留めする

Teams にはさまざまなアプリを表示する機能が用意されているため、管理者は組織にとって最も重要なアプリを決定し、クイック アクセスのために Teams パネル **の [ホーム** ] 画面にのみピン留めできます。 ピン留めされたアプリが 5 つ以上ある場合、またはピン留めされていないアプリがある場合は、[ **その他** ] 画面に表示されます。 Microsoft では、Teams パネル専用のアプリ セットアップ ポリシーでカスタム ポリシーを作成することをお勧めします。

![アプリセットアップ ポリシー ページのユーザー インターフェイスのスクリーンショット。](media/appsetup1.png)

Teams パネルに表示されるピン留めされたアプリを管理するには、組織の Teams 管理センターにサインインし、[**Teams アプリ** \> **] [セットアップ ポリシー** \> **] [新しいポリシー**\>の選択または作成 **] [ピン留めされたアプリ**] に移動します。

![ユーザー インターフェイス内のピン留めされたアプリ セクションのスクリーンショット。](media/appsetup2.png)

*この画像に含まれるアプリは例に過ぎません。使用できない場合があります。*

Microsoft では、Teams パネルで最適な Teams アプリ エクスペリエンスを得るには、[ **カスタム アプリのアップロード]** と [ **ユーザーのピン留め** ] をオフにすることをお勧めします。

アプリのピン留めの詳細については、「 [アプリのセットアップ ポリシーを管理する](/microsoftteams/teams-app-setup-policies)」を参照してください。

## <a name="manage-apps-display-order-in-teams-panels"></a>Teams パネルでアプリの表示順序を管理する

![ユーザー インターフェイス内のアプリ セクションのスクリーンショット。](media/appsetup3.png)

*この画像に含まれるアプリは例に過ぎません。使用できない場合があります。*

Teams パネルにアプリを表示する順序を管理するには、組織の Teams 管理センターにサインインし、[**Teams アプリ** \> **] [セットアップ ポリシー**\>] [**ポリシー** \> **の選択] [固定されたアプリ:** **移動/下へ]** の順に移動します。

## <a name="assigning-setup-policies-to-a-room-resource-account"></a>会議室リソース アカウントへのセットアップ ポリシーの割り当て

セットアップ ポリシーを作成した後、管理者は Teams パネルにサインインする会議室リソース アカウントにこのポリシーを割り当てる必要があります。 詳細については、「 [ユーザーとグループにポリシーを割り当てる](/microsoftteams/assign-policies-users-and-groups)」を参照してください。

## <a name="faq"></a>よくあるご質問 (FAQ)

### <a name="how-long-does-it-take-for-teams-panels-to-get-the-new-or-updated-app-setup-policies"></a>Teams パネルが新しいアプリセットアップポリシーまたは更新されたアプリ設定ポリシーを取得するまでにどのくらいの時間がかかりますか?

Teams 管理センターで新しいポリシーを編集または割り当てた後、変更が有効になるまでに最大 24 時間かかることがあります。 管理者は、パネルからサインアウト/サインインを試み、 **設定** アイコンをタップし、[ **ホーム** ] 画面に戻ってポリシーの更新を試みることができます。

### <a name="what-is-the-ordering-of-the-apps-on-the-more-screen"></a>[その他] 画面でのアプリの順序は何ですか?

[ **その他** のアプリ] ページに、ピン留めされたアプリが最初に表示されます。 その後、インストールされているその他のアプリはアルファベット順に表示されます。

### <a name="why-are-bot-apps-not-showing-up-on-teams-panels"></a>ボット アプリが Teams パネルに表示されないのはなぜですか?

現時点では、静的タブ Web コンテンツのみがサポートされています。

### <a name="why-are-native-teams-apps-such-as-calendar-and-tasks-not-appearing-on-teams-panels"></a>予定表やタスクなどのネイティブ Teams アプリが Teams パネルに表示されないのはなぜですか?

予定表やタスクなどのネイティブ Teams アプリは、Teams パネルには表示されません。

### <a name="in-the-teams-admin-center-under-the-setup-policies-section-what-is-the-difference-between-installed-apps-and-pinned-apps"></a>Teams 管理センターの [セットアップ ポリシー] セクションで、インストールされているアプリとピン留めされたアプリの違いは何ですか?

Teams パネルの場合、Microsoft ではピン留めされたアプリを使用することをお勧めします。そのため、管理者は目的のアプリを選択して順序を並べ替えることができます。

**メモ：** 一部のアプリでは、アプリのピン留めをサポートしていません。 アプリのピン留め機能を有効にするには、アプリ開発者にお問い合わせください。

### <a name="why-are-other-apps-appearing-in-the-more-screen-even-though-they-are-not-part-of-the-installed-or-pinned-apps-in-the-teams-app-setup-policy-section"></a>Teams アプリセットアップ ポリシー セクションのインストール済みアプリまたはピン留めされたアプリの一部ではないにもかかわらず、他のアプリが [その他] 画面に表示されるのはなぜですか?

以前に他のアプリ ポリシーを使用してアプリをインストールしていた場合、または Teams パネルで使用される会議室リソース アカウントの Teams デスクトップ/Web クライアントに手動でインストールした場合、管理者は Teams の会議室リソース アカウントにサインインし、アプリを右クリックして [ **アンインストール**] を選択してアプリを手動でアンインストールする必要がある場合があります。

### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>[ピン留めされたアプリの追加] ウィンドウにアプリが見つからないのはなぜですか?

アプリのセットアップ ポリシーを使用して、すべてのアプリを Teams にピン留めできるわけではありません。 一部のアプリでは、この機能がサポートされていない場合があります。 ピン留めできるアプリを見つけるには、**[ピン留めされたアプリの追加]** ウィンドウでアプリを検索します。 詳細については、「 [アプリセットアップ ポリシーの使用」の FAQ](/microsoftteams/teams-app-setup-policies#why-cant-i-find-an-app-in-the-add-pinned-apps-pane) を参照してください。

### <a name="why-am-i-seeing-an-user-pinning-pop-up-in-the-setup-policies-panel-after-i-turn-off-user-pinning"></a>[ユーザーのピン留め] をオフにした後、セットアップ ポリシー パネルに [ユーザーのピン留め] ポップアップが表示されるのはなぜですか?

![ユーザー インターフェイス内のセットアップ ポリシー セクションのスクリーンショット。ユーザーのピン留めがアクティブであることを確認するポップアップが表示されています。](media/appsetup4.png)

*この画像に含まれるアプリは例に過ぎません。使用できない場合があります。*

この動作は、共有スペース内のデバイスに対して想定され、意図しないアプリのピン留めを防ぐのに役立ちます。
