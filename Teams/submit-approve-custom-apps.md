---
title: Teams アプリ申請 API を使用してカスタム アプリを送信および承認する
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: joglocke, vaibhava
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Microsoft Teamsの Teams アプリ申請 API を使用して送信されたカスタム アプリを承認する方法について説明します。
ms.openlocfilehash: c414bf8af8dc7edbea8376031592260142d67732
ms.sourcegitcommit: 39378888464ade3cb45879a449143f40f202f3e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64456920"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a>Teams アプリ申請 API を使用して送信されたカスタム アプリを発行する

## <a name="overview"></a>概要

> [!NOTE]
> カスタム Teams アプリを発行すると、組織のアプリ ストアのユーザーが利用できるようになります。 カスタム アプリを発行する方法は 2 つあります。使用方法は、アプリの入手方法によって異なります。 **この記事では、開発者が Teams アプリ申請 API を使用して送信するカスタム アプリを承認して発行する方法について説明** します。 もう 1 つの方法 (カスタム アプリのアップロード) は、開発者がアプリ パッケージを.zip形式で送信するときに使用されます。 その方法の詳細については、「 [アプリ パッケージをアップロードしてカスタム アプリを発行する」を](/microsoftteams/upload-custom-apps)参照してください。 アプリの承認ウィジェットは、GCC テナントでは使用できません。

> [!IMPORTANT]
> このメソッドは現在、GCC環境では使用できません。 カスタム アプリメソッドの *アップロードを使用する* 必要があります。

この記事では、開発からデプロイ、検出まで、Teams アプリを実行する方法に関するエンド ツー エンドのガイダンスを提供します。 組織のアプリ ストアでカスタム アプリを開発、デプロイ、管理する方法を合理化するために、アプリライフサイクル全体でTeamsが提供する接続エクスペリエンスの概要を確認します。

開発者がTeams アプリ申請 API を使用してカスタム アプリをMicrosoft Teams管理センターに直接送信して確認と承認を行う方法、組織内のユーザーのアプリを管理するポリシーを設定する方法、ユーザーがTeamsでアプリを検出する方法など、ライフサイクルの各ステップについて説明します。

![開発からデプロイまでのアプリの概要。](media/custom-app-lifecycle.png)

このガイダンスは、アプリのTeams側面に焦点を当て、管理者と IT 担当者を対象としています。 Teams アプリの開発の詳細については、[Teams開発者向けドキュメントを参照してください](/microsoftteams/platform)。

## <a name="develop"></a>開発

### <a name="create-the-app"></a>アプリを作成する

Microsoft Teams開発者プラットフォームを使用すると、開発者は独自のアプリとサービスを簡単に統合して生産性を向上させ、意思決定を迅速に行い、既存のコンテンツとワークフローに関するコラボレーションを作成できます。 Teams プラットフォーム上に構築されたアプリは、Teams クライアントとサービスとワークフローの間のブリッジであり、コラボレーション プラットフォームのコンテキストに直接取り込まれます。 詳細については、[Teams開発者向けドキュメントを参照してください](/microsoftteams/platform)。

### <a name="submit-the-app"></a>アプリを送信する

アプリを運用環境で使用する準備ができたら、開発者は、Graph API、Visual Studio Codeなどの統合開発環境 (IDE) から呼び出すことができる [Teams](/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true) App Submission API、またはPower AppsやPower Virtual Agents。 これを行うと、Teams管理センターの [[アプリの管理](/microsoftteams/manage-apps)] ページでアプリを使用できるようになります。ここで、アプリを確認して承認できます。

[Microsoft Graphに基づいて構築された](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true)Teams アプリ申請 API を使用すると、組織は任意のプラットフォームで開発し、Teams上のカスタム アプリの申請から承認へのプロセスを自動化できます。

Visual Studio Codeでは、このアプリの申請手順の例を次に示します。

![Visual Studio Codeでアプリを送信しています。](media/custom-app-lifecycle-submit-app.png)

これでは、組織のアプリ ストアにアプリがまだ発行されないことに注意してください。 この手順では、アプリをTeams管理センターに送信し、組織のアプリ ストアへの発行を承認できます。

Graph APIを使用してアプリを送信する方法の詳細については、こちらを参照[してください](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true)。

## <a name="notify"></a>通知

開発者がレビューと承認のために新しいアプリケーションを送信するタイミングを把握できるように、通知を有効にすることができます。 開発者がアプリの更新プログラムを送信すると、通知も受け取ります。 Teams管理センターでアプリの申請通知を有効にするには、[[**通知&** **alertsRulesApp** >  >  **申請**](https://admin.teams.microsoft.com/notifications/rules)] に移動し、状態を **[アクティブ]** に変更してルールをアクティブ化します。 既定では、この設定は [オフ] です。 この設定を有効にするには、グローバル管理者またはTeams管理者である必要があります。

この設定をオンにすると、アプリの申請という名前の新しいチャネルの下にある **管理者アラートと通知** チームに通知 **が表示されます**。 または、既存のチームとチャネルを選択して、指定したチームとチャネルに通知を配信することもできます。 これを行うには、次の手順を実行します。

1. **[アプリの申請**] ルールで、[**アクション**] の下にある **[チャネル アラート**] チェック ボックスをオンにします。
1. [ **チャネルの選択]** ボタンを選択します。
1. 追加するチームを検索します。
1. 追加するチャネルを検索します。
1. **[適用]** を選択します。

    ![[カスタム チャネル アラート通知] チェック ボックス。](media/channel-alert.png)

> [!NOTE]
> **[既定のチャネル アラート**] チェック ボックスをオンにすると、**アプリ申請** チャネルの **管理者アラートと通知** チームに通知が届きます。

![既定のチャネル アラート通知チェック ボックス。](media/default-channel-alert.png)

[Webhook] チェック ボックスをオンにした後、パブリック Webhook URL を指定して、外部 **Webhook** への通知を設定することもできます。 JSON 通知ペイロードが Webhook URL に送信されます。

![アプリの申請通知。](media/app-submission-notification.png)

アプリ申請ルールを設定した後、指定したチャネルの通知カードを確認してアプリの詳細を表示し、[**詳細の表示**] を選択してTeams管理センターでアプリを開くことができます。

## <a name="validate"></a>検証

Teams管理センターの [[アプリの管理](/microsoftteams/manage-apps)] ページ (左側のナビゲーションでは、[**Teams** **appsManage** >  アプリ](https://admin.teams.microsoft.com/manage-apps)に移動します)、組織のすべてのTeams アプリを表示できます。 ページの上部にある **[保留中の承認** ] ウィジェットでは、承認のためにカスタム アプリがいつ送信されたのかがわかります。

この表では、新しく送信されたアプリに、[**送信済み]** と [ブロックの **状態]** の **発行状態** が自動的に表示 **されます**。 **発行状態** 列を降順で並べ替えて、アプリをすばやく見つけることができます。

![発行状態。](media/custom-app-lifecycle-validate-app.png)

アプリ名をクリックして、アプリの詳細ページに移動します。 [ **バージョン情報** ] タブでは、説明、状態、提出者、アプリ ID など、アプリに関する詳細を表示できます。

![送信されたアプリのアプリの詳細ページ。](media/custom-app-lifecycle-app-details.png)

Graph APIを使用して **発行状態** を確認する方法の詳細については、[こちらを参照してください](/graph/api/appcatalogs-list-teamsapps?tabs=http&view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id&preserve-view=true)。

## <a name="publish"></a>公開

アプリをユーザーが使用できるようにする準備ができたら、アプリを発行します。

1. [Teams管理センター](https://admin.teams.microsoft.com/dashboard)にログインします。
1. 左側のウィンドウで、**Teams** **appsManage** >  アプリに移動します。
1. アプリ名を選択してアプリの詳細ページに移動し、[ **発行の状態** ] ボックスで [ **発行**] を選択します。

    ![アプリの詳細ページの [発行] ボタン。](media/submitted-app-pending-action.png)

アプリを発行すると、 **発行状態** が **[発行済み]** に変わり、[ **状態]** が自動的に **[許可]** に変わります。

## <a name="set-up-and-manage"></a>セットアップと管理

### <a name="control-access-to-the-app"></a>アプリへのアクセスを制御する

既定では、組織内のすべてのユーザーが、組織のアプリ ストア内のアプリにアクセスできます。 アプリを使用するアクセス許可を持つユーザーを制限および制御するには、アプリのアクセス許可ポリシーを作成して割り当てることができます。 詳細については、「[Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)」を参照してください。

### <a name="pin-and-install-the-app-for-users-to-discover"></a>ユーザーが検出できるようにアプリをピン留めしてインストールする

既定では、ユーザーが組織のアプリ ストアに移動して参照または検索する必要があるアプリを検索します。 ユーザーがアプリに簡単にアクセスできるように、アプリをTeamsのアプリ バーにピン留めできます。 これを行うには、アプリセットアップ ポリシーを作成し、ユーザーに割り当てます。 詳細については、「[Teams でアプリの設定ポリシーを管理する](teams-app-setup-policies.md)」を参照してください。

### <a name="search-the-audit-log-for-teams-app-events"></a>Teams アプリ イベントの監査ログを検索する

監査ログを検索して、組織内のTeamsアプリアクティビティを表示できます。 監査ログを検索する方法と、監査ログに記録されているTeamsアクティビティの一覧を表示する方法の詳細については、「[Teamsのイベントの監査ログを検索する](audit-log-events.md)」を参照してください。

監査ログを検索できるようになるには、最初に[セキュリティ/コンプライアンス センター](https://sip.protection.office.com/) で監査をオンにする必要があります。 詳細については、「[監査ログの検索を有効または無効にする](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&preserve-view=true)」を参照してください。 利用できる監査データは、監査を有効にした時点以降のデータのみであることにご注意ください。

## <a name="discover-and-adopt"></a>検出して採用する

アプリに対するアクセス許可を持つユーザーは、組織のアプリ ストアで見つけることができます。 [アプリ] ページの [***組織名* のビルド]** に移動して、組織のカスタム アプリを見つけます。

![発行されたアプリを示す [アプリ] ページ。](media/custom-app-lifecycle-discovery.png)

アプリセットアップ ポリシーを作成して割り当てた場合、アプリはTeamsのアプリ バーにピン留めされ、ポリシーが割り当てられたユーザーに簡単にアクセスできます。

## <a name="update"></a>更新

アプリを更新するには、開発者は引き続き [開発](#develop) セクションの手順に従う必要があります。

開発者が発行されたカスタム アプリに更新プログラムを送信すると、[アプリの [管理](/microsoftteams/manage-apps)] ページの **[保留中の承認]** ウィジェットで通知を受け取ります。 テーブルで、アプリの **発行状態** が **[送信された更新]** に設定されます。 アプリの申請通知を有効にした場合は、**アプリ申請** チャネルの下の **管理者アラートと通知** チームにも通知されます。 通知カードには、Teams管理センターのアプリに直接アクセスするためのリンクが表示されます。 アプリの申請通知を有効にする方法の詳細については、「 [通知](#notify)」を参照してください。

![保留中の要求とアプリの状態を示す [アプリの管理] ページ。](media/custom-app-lifecycle-update-submitted.png)

アプリの更新プログラムを確認して発行するには:

1. Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリを管理]** の順に移動します。
2. アプリ名をクリックしてアプリの詳細ページに移動し、[ **利用可能な更新プログラム** ] を選択して更新プログラムの詳細を確認します。

    ![アプリの詳細ページ。](media/custom-app-lifecycle-update-app.png)
3. 準備ができたら、[ **発行** ] を選択して更新プログラムを発行します。 これを行うと、既存のアプリが置き換わり、バージョン番号が更新され、 **発行状態** が **[発行済み]** に変更されます。 すべてのアプリのアクセス許可ポリシーとアプリのセットアップ ポリシーは、更新されたアプリに適用されたままです。

    更新プログラムを拒否した場合、以前のバージョンのアプリは発行されたままになります。

次の点に注意してください。

- アプリが承認されると、任意のユーザーがアプリに更新プログラムを送信できます。 これは、アプリを最初に送信した開発者を含む他の開発者がアプリに更新プログラムを送信できることを意味します。
- 開発者がアプリを送信し、要求が保留中の場合、同じ開発者のみがアプリに更新プログラムを送信できます。 他の開発者は、アプリが承認された後にのみ更新プログラムを送信できます。

Graph APIを使用してアプリを更新する方法の詳細については、こちらを参照[してください](/graph/api/teamsapp-update?view=graph-rest-1.0&tabs=http&preserve-view=true)。

## <a name="related-topics"></a>関連項目

- [アプリ パッケージをアップロードしてカスタム アプリを発行する](upload-custom-apps.md)
- [Microsoft Teams 管理センターで、Teams アプリの組織向けアプリを管理します。](manage-apps.md)
- [Teams のカスタム アプリのポリシーと設定を管理する](teams-custom-app-policies-and-settings.md)
- [Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)
- [Teams のアプリのセットアップ ポリシーを管理する](teams-app-setup-policies.md)
- [監視とアラートのTeams](alerts/teams-admin-alerts.md)
- [Teams アプリの Microsoft Graph API](alerts/teams-admin-alerts.md)
