---
title: Microsoft Teamsパネルでのアプリ/Line of Business (LOB) Teamsサポート
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
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 56c26cef98e316a821f31d3baa014cd1e9f9695743c34493c8880ac85f232830
ms.sourcegitcommit: 0e9516c51105e4d89c550d2ea2bd8e7649a1163b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2021
ms.locfileid: "54591221"
---
# <a name="microsoft-teams-appsline-of-business-lob-app-support-on-teams-panels"></a>Microsoft Teamsパネルでのアプリ/Line of Business (LOB) Teamsサポート

Teamsパネルでは、TEAMS/Line of Business (LOB) アプリのサポートが追加されています。 これにより、企業は、組織のニーズを満たすためにパネルに追加のエクスペリエンスを追加できます。 このリリースでは、静的 Web コンテンツがサポートされています。

> [!IMPORTANT]
> この機能は、パネル デバイスTeams更新した後にのみ使用できます。 Teams パネル内でアプリをサポートするには、Teams アプリ バージョン 1449/1.0.97.2021070601 以降が必要です。

## <a name="set-up-and-manage-teams-panels-apps-in-teams-admin-center"></a>管理センターでTeamsパネル アプリをTeams管理する 

Microsoft Teamsアプリは、重要な情報、一般的なツール、信頼できるプロセスを、ユーザーが収集、学習、作業する場所に提供します。 Teamsアプリは統合[された機能で動作します](/platform/concepts/capabilities-overview)。 IT 管理者は、組織の Teams パネル デバイスに含めるアプリを選択し、Teams 管理センターを介してアクセス許可をカスタマイズできます。

これで、ユーザー パネルTeamsアプリTeams、組織のニーズに基づいてユーザー エクスペリエンスをカスタマイズできます。 ユーザーがアプリ ビューにアクセスして使用し、優先度を設定できる Web アプリを決定できます。 ボットやメッセージング機能など、一部のオプションは現時点ではサポートされていません。 アプリの詳細とTeamsでデバイスを管理する方法についてMicrosoft Teams。

## <a name="manage-apps-on-teams-panels-in-teams-admin-center"></a>管理センターのTeamsパネルでアプリTeams管理する

**注**: 管理センターにアクセスするには、グローバル管理者または Teamsサービス管理者Teams必要があります。

エンド ユーザーは、ユーザーパネルにアプリを表示できますが、インストールTeamsできます。 管理者は、管理センターから組織Teamsアプリを表示およびTeamsできます。 [アプリの管理] ページを使用して、Microsoft Teams管理センターでアプリを管理する方法 **について詳しくは、ご覧** ください。 管理 **センター内の**[アプリのTeams] ページでは、カスタム アプリを [アップロードすることもできます](/manage-apps#publish-a-custom-app-to-your-organizations-app-store)。

アプリを設定した後、アプリの[](/teams-app-permission-policies)アクセス許可ポリシーとアプリ[](/teams-app-setup-policies)セットアップ ポリシーを使用して、組織内の特定のルーム アカウントのアプリ エクスペリエンスを構成できます。

## <a name="pin-apps-on-teams-panels-with-app-setup-policies"></a>アプリセットアップ ポリシーを使用Teamsパネルにアプリをピン留めする

Teamsにはさまざまなアプリを表示する機能が用意されていますので、管理者は組織にとって最も重要なアプリを決定し、Teams パネルのホーム画面でのみピン留めしてすばやくアクセスできます。 ピン留めされたアプリまたはピン留めされていないアプリが 5 つ以上ある場合は、[その他] 画面に **表示** されます。 Microsoft では、ユーザー設定パネル専用のカスタム アプリセットアップ ポリシー Teams勧めします。

![アプリのセットアップ ポリシー ページのユーザー インターフェイスのスクリーンショット。](media/appsetup1.png) 

Teams パネルに表示される固定アプリを管理するには、組織の Teams 管理センターにサインインし **、[Teams** アプリのセットアップ ポリシー] [新しいポリシーのピン留めされたアプリを選択または作成する] に移動します。 \>  \>  \> 

![ユーザー インターフェイス内のピン留めされたアプリ セクションのスクリーンショット。](media/appsetup2.png) 

Microsoft では、カスタム アプリのアップロード **をオフ** にし、ユーザーのピン留めを許可して、Teamsのアプリ エクスペリエンスをTeams勧めします。 

アプリのピン留めについて詳しくは、「アプリセットアップ [ポリシーの管理」をご覧ください](/teams-app-setup-policies)。

## <a name="manage-apps-display-order-in-teams-panels"></a>アプリの表示順序を管理する (Teamsパネル) 

![ユーザー インターフェイス内の [アプリ] セクションのスクリーンショット。](media/appsetup3.png) 

Teams パネルにアプリを表示する順序を管理するには、組織の Teams 管理センターにサインインし **、[Teams** アプリのセットアップ ポリシー] [ポリシーピン留めされたアプリを選択します。 \>  \>  \>  

## <a name="assigning-setup-policies-to-a-room-resource-account"></a>セットアップ ポリシーをルーム リソース アカウントに割り当てる

セットアップ ポリシーを作成した後、管理者は、このポリシーを、管理者パネルにサインインするルーム リソース アカウントに割り当てるTeamsがあります。 詳細については、「ユーザーとグループに [ポリシーを割り当てる」を参照してください](/assign-policies-users-and-groups)。

## <a name="faq"></a>よくあるご質問 (FAQ)

### <a name="how-long-does-it-take-for-teams-panels-to-get-the-new-or-updated-app-setup-policies"></a>新しいまたは更新されたアプリのセットアップ Teamsを取得するには、パネルにどのくらいの時間が必要ですか?

管理センターで新しいポリシーを編集または割り当Teams、変更を有効にするには最大 24 時間かかる場合があります。 管理者は、パネルからサインアウト/サインインを試み **、設定** アイコンをタップし、ホーム画面に戻ってポリシーを更新できます。

### <a name="what-is-the-ordering-of-the-apps-on-the-more-screen"></a>[その他] 画面のアプリの順序は何ですか?

[その他 **のアプリ** ] ページで、ピン留めされたアプリが最初に表示されます。 その後、インストールされている他のアプリはアルファベット順に表示されます。

### <a name="why-are-bot-apps-not-showing-up-on-teams-panels"></a>ボット アプリがデバイス パネルに表示されないTeams。

現時点では、静的タブの Web コンテンツだけがサポートされています。

### <a name="why-are-native-teams-apps-such-as-calendar-and-tasks-not-appearing-on-teams-panels"></a>カレンダーやタスクTeamsなど、ネイティブ アプリがアプリ パネルに表示されないTeams。

予定表Teamsタスクなどのネイティブ アプリは、ユーザーパネルTeamsされません。

### <a name="in-the-teams-admin-center-under-the-setup-policies-section-what-is-the-difference-between-installed-apps-and-pinned-apps"></a>管理センター Teams[セットアップ ポリシー] セクションで、インストールされているアプリとピン留めされたアプリの違いは何ですか?

パネルTeams、ピン留めされたアプリの使用をお勧めします。そのため、管理者は目的のアプリを選択し、順序を変更できます。

**注:** 一部のアプリでは、アプリのピン留めがサポートされていません。 アプリのピン留め機能を有効にするには、アプリ開発者にお問い合わせください。

### <a name="why-are-other-apps-appearing-in-the-more-screen-even-though-they-are-not-part-of-the-installed-or-pinned-apps-in-the-teams-app-setup-policy-section"></a>[アプリのセットアップ ポリシー] セクションのインストール済みアプリまたはピン留めされたアプリの一部ではない場合でも、他のアプリが [その他] 画面Teams表示される理由

Teams パネルで使用されるルーム リソース アカウントの Teams デスクトップ/Web クライアントにアプリが以前にインストールされている場合、管理者は Teams のルーム リソース アカウントにサインインし、アプリを右クリックして手動でアンインストールし、[アンインストール] を選択する必要があります。 

### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>[ピン留めされたアプリの追加] ウィンドウにアプリが見当たらない理由

アプリセットアップ ポリシーを使用して、Teamsにピン留めできるアプリはありません。 一部のアプリでは、この機能がサポートされていない場合があります。 ピン留めできるアプリを検索するには、[ピン留めされたアプリの追加 **] ウィンドウでアプリを検索** します。 詳細については、「アプリセットアップ ポリシー [の操作」の FAQ を参照してください](/teams-app-setup-policies#why-cant-i-find-an-app-in-the-add-pinned-apps-pane)。

### <a name="why-am-i-seeing-an-allow-user-pinning-pop-up-in-the-setup-policies-panel-after-i-turn-off-allow-user-pinning"></a>[ユーザーのピン留めを許可する] をオフにした後、セットアップ ポリシー パネルに "ユーザーピン留めを許可する" ポップアップが表示される理由

![ユーザー のピン留めがアクティブな状態を確認するポップアップが表示された、ユーザー インターフェイス内のセットアップ ポリシー セクションのスクリーンショット。](media/appsetup4.png) 

この動作は、共有領域内のデバイスで予期される動作であり、意図しないアプリのピン留めを防ぐのに役立ちます。
