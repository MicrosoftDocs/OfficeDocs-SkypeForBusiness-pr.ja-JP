---
title: Teams アプリ申請 API を使用してカスタム アプリを送信および承認する
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
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
description: Microsoft Teams の Teams アプリ申請 API を使用して送信されたカスタム アプリを承認する方法について説明します。
ms.openlocfilehash: 60f9d78d5fdcc51d741fdbefed5c08a487910f22
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299096"
---
# <a name="publish-a-custom-app-submitted-using-the-teams-app-submission-api"></a>Teams アプリ 申請 API を使用して送信されたカスタム アプリを公開する

この記事では、Teams アプリを開発から展開、検出に順番に移行する方法に関するエンドツーエンドのガイダンスを提供します。 Teams がアプリ ライフサイクル全体で提供する接続エクスペリエンスの概要を確認し、組織のアプリ ストアでカスタム アプリを開発、展開、管理する方法を合理化します。

開発者が Teams アプリ申請 API を使用して Microsoft Teams 管理センターに直接送信して確認と承認を行う方法、組織内のユーザーのアプリを管理するポリシーを設定する方法、ユーザーが Teams でアプリを検出する方法など、ライフサイクルの各ステップについて説明します。

:::image type="content" source="media/custom-app-lifecycle.png" alt-text="開発から展開までのアプリの概要。":::

このガイダンスは、アプリの Teams の側面に焦点を当て、管理者と IT 担当者を対象としています。 Teams アプリの開発に関する詳細については、「[Teams 開発者向けドキュメント](/microsoftteams/platform)」を参照してください。

> [!NOTE]
> Teams カスタム アプリを発行すると、組織のアプリ ストア内のユーザーがそれを使用できるようになります。 カスタム アプリを発行する方法は 2 つあり、使用方法はアプリの入手方法によって異なります。 この記事では、開発者が Teams アプリ申請 API を使用して送信するカスタム アプリを承認して公開する方法について説明します。 もう 1 つの方法 (カスタム アプリのアップロード) は、開発者がアプリ パッケージを .zip 形式で送信するときに使用されます。 詳細については、「[アプリ パッケージをアップロードしてカスタム アプリを公開する](/microsoftteams/upload-custom-apps)」を参照してください。 アプリの承認ウィジェットは GCC テナントでは使用できません。

> [!IMPORTANT]
> このメソッドは GCC 環境では使用できません。 [カスタム アプリをアップロード](upload-custom-apps.md) して GCC 環境で公開します。

## <a name="develop"></a>開発

### <a name="create-the-app"></a>アプリを作成する

Microsoft Teams 開発者プラットフォームでは、開発者が簡単に独自のアプリとサービスを統合して生産性を向上させ、迅速に意思決定を行い、既存のコンテンツとワークフロー関連のコラボレーションを作成できます。 Teams プラットフォームにビルドされているアプリは、Teams クライアント、サービス、ワークフローの間のブリッジとして機能し、それらはコラボレーション プラットフォームのコンテキストに直接取り込まれます。 詳細については、「[Teams 開発者向けドキュメント](/microsoftteams/platform)」を参照してください。

### <a name="submit-the-app"></a>アプリを送信する

アプリを本番環境で使用する準備ができたら、開発者は Teams アプリ提出 API を使用してアプリを提出できます。これは、[Graph API](/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true)、Visual Studio Code などの統合開発環境 (IDE)、または Power Apps や Power Virtual Agents などのプラットフォームから呼び出すことができます。 これを行うと、Teams 管理センターの [[アプリの管理]](/microsoftteams/manage-apps) ページでアプリを使用できるようになります。ここで、アプリを確認して承認できます。

[Microsoft Graph 上に構築された](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true) Teams アプリ申請 API を使用すると、組織は任意のプラットフォームで開発し、Teams 上のカスタム アプリの申請から承認へのプロセスを自動化できます。

Visual Studio Code でのこのアプリの申請手順の例を次に示します。

:::image type="content" source="media/custom-app-lifecycle-submit-app.png" alt-text="Visual Studio Code でのアプリの申請のスクリーンショット。":::

これでは、組織のアプリ ストアにアプリがまだ公開されないことに注意してください。 この手順では、アプリを Teams 管理センターに送信し、組織のアプリ ストアへの公開を承認できます。

Graph APIを使用してアプリを送信する方法の詳細については、[こちら](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true)を参照してください。

## <a name="notify"></a>通知

開発者がレビューと承認のために新しいアプリケーションを送信するタイミングを把握できるように、通知を有効にすることができます。 開発者がアプリの更新プログラムを送信すると、通知も受け取ります。 Teams 管理センターでアプリの送信通知を有効にするには、**[通知とアラート]** > **[[ルール]](https://admin.teams.microsoft.com/notifications/rules)** > **[アプリの送信]** の順に移動します。 ステータスを **[アクティブ]** に変更してルールを有効にします。 既定では、この設定は [オフ] です。 この設定を有効にするには、グローバル管理者または Teams 管理者である必要があります。

この設定をオンにすると、**[アプリの申請]** という名前の新しいチャネルの下の **[アラートと通知の管理]** チームに通知が表示されます。 または、既存のチームとチャネルを選択して、指定したチームとチャネルに通知を配信することもできます。 これを行うには、次の手順を実行します。

1. [**アプリの申請**] ルールで、[**アクション**] の下にある **[チャネル アラート**] チェック ボックスをオンにします。
1. [**チャネルの選択]** ボタンを選択します。
1. 追加するチームを検索します。
1. 追加するチャネルを検索します。
1. **[適用]** を選択します。

   :::image type="content" source="media/channel-alert.png" alt-text="[カスタム チャネル アラート通知] チェック ボックス。" lightbox="media/channel-alert.png":::

> [!NOTE]
> **[既定のチャネル アラート]** チェック ボックスをオンにすると、**[アプリ申請]** チャネルの **[アラートと通知の管理]** チームに通知が届きます。

:::image type="content" source="media/default-channel-alert.png" alt-text="既定のチャネル アラート通知チェック ボックス。" lightbox="media/default-channel-alert.png":::

**[Webhook]** チェック ボックスをオンにした後、パブリック Webhook URL を指定して、外部 Webhook への通知を設定することもできます。 JSON 通知ペイロードが Webhook URL に送信されます。

:::image type="content" source="media/app-submission-notification.png" alt-text="アプリの申請通知。" lightbox="media/app-submission-notification.png":::

アプリ申請ルールを設定した後、指定したチャネルの通知カードを確認してアプリの詳細を表示し、[**詳細の表示**] を選択して Teams 管理センターでアプリを開くことができます。

## <a name="validate"></a>検証

Teams 管理センターの [[アプリの管理](/microsoftteams/manage-apps)] ページ (左側のナビゲーションで [**[Teams アプリ]** > **[アプリの管理]**](https://admin.teams.microsoft.com/manage-apps) に移動します) で、 組織のすべての Teams アプリを表示できます。 ページの上部にある **[保留中の承認 ]** ウィジェットでは、承認のためにカスタム アプリがいつ送信されたのかがわかります。

こ表では、新しく提出されたアプリは **[公開ステータス]** が **[提出済み]**、**[ステータス]** が **[ブロック済み]** と自動的に表示されます。 **[公開ステータス]** 列を降順で並べ替えると、アプリをすばやく見つけることができます。

:::image type="content" source="media/custom-app-lifecycle-validate-app.png" alt-text="公開ステータス。" lightbox="media/custom-app-lifecycle-validate-app.png":::

アプリ名を選択してアプリの詳細ページに移動し、アプリの詳細を表示します。 **[詳細情報]** タブでは、説明、ステータス、送信者、アプリ ID など、アプリに関する詳細情報を確認できます。

:::image type="content" source="media/custom-app-lifecycle-app-details.png" alt-text="送信されたアプリのアプリの詳細ページ。" lightbox="media/custom-app-lifecycle-app-details.png":::

Graph APIを使用して **公開ステータス** を確認する方法の詳細については、[こちら](/graph/api/appcatalogs-list-teamsapps?tabs=http&view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id&preserve-view=true)を参照してください。

## <a name="publish"></a>公開

ユーザーがアプリを利用できる準備が完了したら、アプリを公開します。

1. Teams 管理センターにサインインし、**[Teams アプリ]** > **[[アプリの管理]](https://admin.teams.microsoft.com/policies/manage-apps)** の順に移動します。
1. アプリ名を選択してアプリの詳細ページに移動し、**[公開ステータス]** ボックスで **[公開]** を選択します。

    :::image type="content" source="media/submitted-app-pending-action.png" alt-text="アプリの詳細ページの [公開] ボタン。":::

アプリを公開すると、 **[公開ステータス]** が **[公開済み]** に変わり、**[状態]** が **[許可]** に変わります。

## <a name="set-up-and-manage"></a>セットアップと管理

### <a name="control-access-to-the-app"></a>アプリへのアクセスを制御する

既定では、組織内のすべてのユーザーが、組織のアプリ ストア内のアプリにアクセスできます。 アプリ使用のアクセス許可を持つユーザーを制限および制御するために、アプリのアクセス許可ポリシーを作成して割り当てることができます。 詳細については、「[Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)」を参照してください。

### <a name="pin-and-install-the-app-for-users-to-discover"></a>ユーザーが検出できるようにアプリをピン留めしてインストールする

既定では、ユーザーが組織のアプリ ストアに移動して参照または検索する必要があるアプリを検索します。 ユーザーが簡単にアプリにアクセスできるように、Teams のアプリ バーにアプリをピン留めできます。 これを行うには、アプリのセットアップ ポリシーを作成し、ユーザーに割り当てます。 詳細については、「[Teams でアプリの設定ポリシーを管理する](teams-app-setup-policies.md)」を参照してください。

### <a name="search-the-audit-log-for-teams-app-events"></a>Teams でアプリ イベントの監査ログを検索する

監査ログを検索して、組織内のTeams アプリ アクティビティを表示できます。 監査ログを検索する方法と、監査ログに記録されている Shifts アクティビティのリストを確認するには、「[Teams 内でイベントの監査ログを検索する](audit-log-events.md)」を参照してください。

監査ログを検索できるようになるには、最初に[セキュリティ/コンプライアンス センター](https://sip.protection.office.com/) で監査をオンにする必要があります。 詳細については、「[監査ログの検索を有効または無効にする](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&preserve-view=true)」を参照してください。 利用できる監査データは、監査を有効にした時点以降のデータのみであることにご注意ください。

## <a name="discover-and-adopt"></a>検出と導入

アプリに対するアクセス許可を持つエンド ユーザーは、組織のアプリ ストアで見つけることができます。 [アプリ] ページの ***[組織名のビルド]*** に移動して、組織のカスタム アプリを見つけます。

:::image type="content" source="media/custom-app-lifecycle-discovery.png" alt-text="公開済みのアプリを示す [アプリ] ページ。" lightbox="media/custom-app-lifecycle-discovery.png":::

アプリのセットアップ ポリシーを作成して割り当てた場合、ポリシーが割り当てられたユーザーが簡単にアクセスできるように、アプリは Teams のアプリ バーにピン留めされます。

## <a name="update"></a>更新

アプリを更新するには、開発者は引き続き [開発](#develop) セクションの手順に従う必要があります。

開発者が公開されたカスタム アプリに更新プログラムを送信すると、[[アプリの管理]](/microsoftteams/manage-apps) ページの **[保留中の承認]** ウィジェットで通知を受け取ります。 テーブルで、アプリの **公開ステータス** が **[更新を送信しました]** に設定されます。 アプリの申請通知を有効にした場合は、**アプリ申請** チャネルの **管理アラートと通知** チームで通知も受け取ります。 通知カードには、Teams 管理センターのアプリに直接アクセスするためのリンクが表示されます。 アプリの申請通知を有効にする方法の詳細については、「[通知](#notify)」を参照してください。

:::image type="content" source="media/custom-app-lifecycle-update-submitted.png" alt-text="保留中の要求とアプリの状態を示す [アプリの管理] ページ。" lightbox="media/custom-app-lifecycle-update-submitted.png":::

アプリの更新プログラムを確認して公開するには:

1. Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリを管理]** の順に移動します。
1. アプリ名をクリックしてアプリの詳細ページに移動し、[**利用可能な更新プログラム**] を選択して更新プログラムの詳細を確認します。

   :::image type="content" source="media/custom-app-lifecycle-update-app.png" alt-text="アプリの詳細ページ。" lightbox="media/custom-app-lifecycle-update-app.png":::

1. 準備ができたら、**[公開]** を選択して更新プログラムを公開します。 これを行うと、既存のアプリが置き換わり、バージョン番号が更新され、 **公開ステータス** が **[公開済み]** に変更されます。 すべてのアプリのアクセス許可ポリシーとアプリのセットアップ ポリシーは、更新されたアプリに適用されたままです。

    更新プログラムを拒否した場合、以前のバージョンのアプリは公開されたままになります。

以下の点に注意してください。

* アプリが承認されると、任意のユーザーがアプリに更新プログラムを送信できます。 これは、アプリを最初に送信した開発者を含む他の開発者がアプリに更新プログラムを送信できることを意味します。
* 開発者がアプリを送信し、要求が保留中の場合、同じ開発者のみがアプリに更新プログラムを送信できます。 他の開発者は、アプリが承認された後にのみ更新プログラムを送信できます。

Graph APIを使用してアプリを更新する方法の詳細については、[こちら](/graph/api/teamsapp-update?view=graph-rest-1.0&tabs=http&preserve-view=true)を参照してください。

## <a name="related-articles"></a>関連記事

* [アプリ パッケージをアップロードしてカスタム アプリを発行する](upload-custom-apps.md)
* [Microsoft Teams 管理センターで、Teams アプリの組織向けアプリを管理します。](manage-apps.md)
* [Teams のカスタム アプリのポリシーと設定を管理する](teams-custom-app-policies-and-settings.md)
* [Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)
* [Teams のアプリのセットアップ ポリシーを管理する](teams-app-setup-policies.md)
* [Teams の監視とアラート](alerts/teams-admin-alerts.md)
* [Microsoft Graph API for Teams アプリ](alerts/teams-admin-alerts.md)
