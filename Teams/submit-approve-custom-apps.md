---
title: Teams アプリ申請 API を使用してカスタム アプリを送信および承認する
author: cichur
ms.author: v-cichur
manager: serdars
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
localization_priority: Normal
search.appverid: MET150
description: Teams App Submission API を使用して送信されるカスタム アプリを承認する方法についてMicrosoft Teams。
ms.openlocfilehash: 8c12d93a0b4420fd248064c69308e8049dc6326f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116975"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a>Teams App Submission API を使用して送信されたカスタム アプリを発行する

## <a name="overview"></a>概要

> [!NOTE]
> カスタム アプリを発行Teams、組織のアプリ ストア内のユーザーが使用できます。 カスタム アプリを発行する方法と使用する方法は、アプリの取得方法によって異なります。 この記事では、開発者がアプリ提出 API を使用して送信するカスタム アプリを承認して発行するTeams **を中心に説明します**。 カスタム アプリをアップロードするもう 1 つの方法は、開発者がアプリ パッケージをカスタム 形式で.zipされます。 その方法の詳細については、「アプリ パッケージをアップロードして <a href="/microsoftteams/upload-custom-apps" target="_blank">カスタム アプリを発行する」を参照してください</a>。 承認アプリ ウィジェットは、テナントGCCできません。 

> [!IMPORTANT]
> この方法は現在、一部の環境GCCできません。 カスタム アプリ メソッドの *アップロードを使用する必要* があります。

この記事では、開発からデプロイから検出まで、Teamsアプリを使用する方法について、エンド to エンドのガイダンスを提供します。 Teams がアプリのライフサイクル全体にわたって提供する接続エクスペリエンスの概要を確認し、組織のアプリ ストアでカスタム アプリを開発、デプロイ、管理する方法を合理化します。

ライフサイクルの各ステップについて説明します。たとえば、開発者が Teams App Submission API を使用してカスタム アプリを Microsoft Teams 管理センターに直接送信してレビューと承認を行う方法、組織内のユーザー向けのアプリを管理するためのポリシーを設定する方法、ユーザーが Teams でアプリを検出する方法などについて説明します。

![開発からデプロイまで、アプリの概要](media/custom-app-lifecycle.png)

このガイダンスでは、アプリのTeamsに焦点を当て、管理者と IT のプロを対象にしています。 アプリの開発の詳細についてはTeams開発者向けドキュメント<a href="/microsoftteams/platform" target="_blank">をTeams参照してください</a>。

## <a name="develop"></a>開発

### <a name="create-the-app"></a>アプリを作成する

開発者Microsoft Teamsプラットフォームを使用すると、開発者は独自のアプリとサービスを簡単に統合して生産性を向上させ、意思決定を迅速に行い、既存のコンテンツやワークフローに関するコラボレーションを作成できます。 Teams プラットフォーム上に構築されたアプリは、Teams クライアントとサービスとワークフローの間のブリッジであり、コラボレーション プラットフォームのコンテキストに直接取り込む必要があります。 詳細については、開発者向けドキュメント<a href="/microsoftteams/platform" target="_blank">Teams参照してください</a>。

### <a name="submit-the-app"></a>アプリを送信する

アプリを実稼働環境で使用する準備ができたら、開発者は<a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank" target="_blank">Graph API、Visual Studio Code</a>などの統合された開発環境 (IDE)、または Power Apps や Power Virtual Agents などのプラットフォームから呼び出し可能な Teams アプリ送信 API を使用してアプリを送信できます。 これにより、管理者は Microsoft Teams 管理<a href="/microsoftteams/manage-apps" target="_blank"></a>センターの [アプリの管理] ページでアプリを利用できます。このページでは、管理者がアプリを確認および承認できます。

<a href="/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">Microsoft Graph</a>上に構築された Teams App Submission API を使用すると、組織は選択したプラットフォーム上で開発し、Teams 上のカスタム アプリの提出から承認へのプロセスを自動化できます。

このアプリの提出手順の例を次に示Visual Studio Code。

![Visual Studio Code でアプリを送信する](media/custom-app-lifecycle-submit-app.png)

これにより、組織のアプリ ストアにアプリがまだ発行されていないことに気を付ける必要があります。 この手順では、アプリを Microsoft Teams 管理センターに送信し、組織のアプリ ストアへの発行を承認できます。

Graph API を使用してアプリを送信する方法の詳細については、こちらを参照<a href="/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">してください</a>。

## <a name="validate"></a>検証

Microsoft Teams <a href="/microsoftteams/manage-apps" target="_blank"></a>管理センターの [アプリの管理] ページ (左側のナビゲーションの [Teams **アプリの** 管理] に移動します)、組織のすべての Teams アプリを  >  表示します。 ページ **の上部にある** [承認待ち] ウィジェットでは、カスタム アプリが承認のためにいつ送信されたのか確認できます。

この表では、新しく送信されたアプリの発行状態が [**送信** 済み] と [状態] が [ブロック]**に自動的****に表示されます**。 [発行状態] **列を降** 順で並べ替え、アプリをすばやく見つける。

![発行の状態 ](media/custom-app-lifecycle-validate-app.png)

アプリ名をクリックして、アプリの詳細ページに移動します。 **[About] タブ** では、アプリの詳細 (説明、状態、提出者、アプリ ID など) を表示できます。

![送信されたアプリのアプリの詳細ページ](media/custom-app-lifecycle-app-details.png)

Graph API を使用して発行の状態を確認する **方法** の詳細については、こちらを参照 <a href="/graph/api/appcatalogs-list-teamsapps?tabs=http&view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id" target="_blank">してください</a>。

## <a name="publish"></a>発行

アプリをユーザーが利用できる状態にできたら、アプリを発行します。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリを管理]** の順に移動します。
2. アプリ名をクリックしてアプリの詳細ページに移動し、[発行状態]ボックスで [発行] を **選択します**。

    アプリを発行すると、[発行中 **]** の状態が[発行済み] に変わります。[**状態**] は自動的に [許可] に **変わります**。

## <a name="set-up-and-manage"></a>セットアップと管理

### <a name="control-access-to-the-app"></a>アプリへのアクセスを制御する

既定では、組織内のすべてのユーザーは、組織のアプリ ストア内のアプリにアクセスできます。 アプリを使用するアクセス許可を持つユーザーを制限および制御するには、アプリのアクセス許可ポリシーを作成して割り当てる必要があります。 詳細については、「<a href="/microsoftteams/teams-app-permission-policies" target="_blank">Teams のアプリのアクセス許可ポリシーを管理する</a>」を参照してください。

### <a name="pin-and-install-the-app-for-users-to-discover"></a>ユーザーが検出するアプリをピン留めしてインストールする

既定では、ユーザーが組織のアプリ ストアにアクセスしてアプリを参照または検索する必要があるアプリを見つける場合。 ユーザーがアプリに簡単にアクセスするには、アプリをアプリ バーのアプリ バーにピン留Teams。 これを行うには、アプリセットアップ ポリシーを作成し、ユーザーに割り当てる必要があります。 詳細については、「<a href="/microsoftteams/teams-app-setup-policies" target="_blank">Teams でアプリの設定ポリシーを管理する</a>」を参照してください。

### <a name="search-the-audit-log-for-teams-app-events"></a>監査ログでアプリ イベントTeams検索する

監査ログを検索して、組織内のTeamsアクティビティを表示できます。 監査ログを検索する方法と、監査ログに記録されている Teams アクティビティの一覧を表示する方法の詳細については、「Teams でイベントの監査ログを検索する」<a href="/microsoftteams/audit-log-events" target="_blank">を参照してください</a>。

監査ログを検索できるようになるには、最初に<a href="https://protection.office.com" target="_blank">セキュリティ/コンプライアンス センター</a>で監査をオンにする必要があります。 詳細については、「<a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">監査ログの検索を有効または無効にする</a>」を参照してください。 利用できる監査データは、監査を有効にした時点以降のデータのみであることにご注意ください。

## <a name="discover-and-adopt"></a>検出して採用する

アプリへのアクセス許可を持つユーザーは、組織のアプリ ストアで見つけることができます。 [アプリ **] ページの *[組織名*** のビルド] に移動して、組織のカスタム アプリを見つける。

![発行済みアプリが表示されている [アプリ] ページ ](media/custom-app-lifecycle-discovery.png)

アプリセットアップ ポリシーを作成して割り当てた場合、アプリは Teams のアプリ バーにピン留めされ、ポリシーが割り当てられたユーザーに簡単にアクセスできます。

## <a name="update"></a>更新

アプリを更新するには、開発者は引き続き「開発」セクションの手順に [従う必要](#develop) があります。

開発者が公開済みカスタム アプリに更新を送信すると、[アプリの管理] ページの[承認待ち] ウィジェットで<a href="/microsoftteams/manage-apps" target="_blank">通知が表示</a>されます。 この表では、アプリ **の発行状態** が [Update submitted ] に **設定されます**。

![保留中の要求とアプリの状態を示す [アプリの管理] ページ ](media/custom-app-lifecycle-update-submitted.png)

アプリの更新プログラムを確認して発行するには:

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリを管理]** の順に移動します。
2. アプリ名をクリックしてアプリの詳細ページに移動し、[利用可能な更新] を選択して更新の詳細を確認します。

    ![アプリの詳細ページ](media/custom-app-lifecycle-update-app.png)
3. 準備ができたら、[発行] を **選択して** 更新プログラムを発行します。 これにより、既存のアプリが置き換え、バージョン番号が更新され、[発行中] の状態 **が [発行済** み] に **変更されます**。 すべてのアプリアクセス許可ポリシーとアプリ設定ポリシーは、更新されたアプリに適用されたままです。

    更新を拒否した場合、以前のバージョンのアプリは発行されたままです。

次の注意が必要です。

- アプリが承認されると、誰でもアプリに更新を送信できます。 つまり、アプリを最初に送信した開発者を含む他の開発者は、アプリに更新プログラムを送信できます。
- 開発者がアプリを送信し、要求が保留中の場合、同じ開発者だけがアプリに更新を送信できます。 他の開発者は、アプリが承認された後にのみ更新を送信できます。

Graph API を使用してアプリを更新する方法の詳細については、こちらを参照<a href="/graph/api/teamsapp-update?view=graph-rest-beta#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">してください</a>。

### <a name="update-experience-for-users"></a>ユーザーのエクスペリエンスを更新する

ほとんどの場合、アプリの更新プログラムを発行すると、ユーザーの新しいバージョンが自動的に表示されます。 ただし、完了するためにユーザーの受け入れを<a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">必要Microsoft Teamsマニフェスト</a>にはいくつかの更新があります。

* ボットが追加または削除されました
* 既存のボットの "botId" プロパティが変更されました
* 既存のボットの "isNotificationOnly" プロパティが変更されました
* ボットの "supportsFiles" プロパティが変更されました
* メッセージング拡張機能が追加または削除されました
* 新しいコネクタが追加されました
* 新しい静的タブが追加されました
* 新しい構成可能なタブが追加されました
* "webApplicationInfo" 内のプロパティが変更されました

![利用可能な新しいバージョン](media/manage-your-custom-apps-update1.png)

![アプリのアップグレード オプション](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>関連トピック

- [アプリ パッケージをアップロードしてカスタム アプリを発行する](upload-custom-apps.md)
- [管理センターでアプリMicrosoft Teams管理する](manage-apps.md)
- [Teams のカスタム アプリのポリシーと設定を管理する](teams-custom-app-policies-and-settings.md)
- [Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)
- [Teams のアプリのセットアップ ポリシーを管理する](teams-app-setup-policies.md)
- <a href="/graph/api/resources/teamsapp?view=graph-rest-beta" target="_blank">Microsoft Graph アプリ用 Teams API</a>