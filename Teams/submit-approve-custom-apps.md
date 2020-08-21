---
title: Teams アプリの送信 API を使用してカスタム アプリを送信および承認する
author: lanachin
ms.author: v-lanac
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
description: Microsoft Teams の Teams App Submission API を使用して送信されたカスタム アプリを承認する方法について説明します。
ms.openlocfilehash: bdd13dbe4db46110250ea380eebd0ea1d011a322
ms.sourcegitcommit: bb5229c9f7999358dcf0ba185ecfd7c881627a38
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46824918"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a>Teams アプリ申請 API から送信されたカスタム アプリを公開する

## <a name="overview"></a>概要

> [!NOTE]
> カスタム Teams アプリを公開すると、組織のアプリ ストアのユーザーが使用できます。 カスタム アプリを発行する方法は 2 つありますが、アプリの入手方法は異なります。 **この記事では、開発者が Teams App Submission API**を通じて提出するカスタム アプリを承認および公開する方法について説明します。 他の方法ではカスタム アプリをアップロードする方法は、開発者からアプリ パッケージを .zip 形式で送信するときに使用されます。 この方法の詳細については、「アプリ <a href="https://docs.microsoft.com/microsoftteams/upload-custom-apps" target="_blank">パッケージをアップロードしてカスタム アプリを公開する」を参照してください</a>。
 
この記事では、Teams アプリを開発から発見まで、開発から発見までの方法について、エンドでのガイダンスを提供します。 Teams が組織のアプリ ストアでカスタム アプリを開発、展開、管理する方法を効率化する方法を合理化する、アプリのライフサイクル全体で Teams が提供する接続エクスペリエンスの概要を説明します。

ライフサイクルの各手順について説明します。デベロッパーが Teams App Submission API を使用してカスタム アプリを Microsoft Teams 管理センターに直接送信して、確認および承認する方法、組織内のユーザー用のアプリを管理するポリシーの設定方法、ユーザーが Teams で見つけた方法についても説明します。

![開発から展開に向かってアプリの概要](media/custom-app-lifecycle.png)

このガイダンスはアプリの Teams の側の側で注行し、管理者と IT プロフョッショナル向けです。 Teams アプリの開発について詳しくは <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">、Teams 開発者のドキュメントを参照してください</a>。

## <a name="develop"></a>開発

### <a name="create-the-app"></a>アプリを作成する

Microsoft Teams 開発者プラットフォームを使用すると、開発者は、生産性を向上させ、優れた事例を上げ、既存のコンテンツとワークフローに関するコラボレーションを作成することが簡単にできるようになります。 Teams プラットフォームに組み込まれたアプリは、Teams クライアントとサービスとワークフローの間にブリッジされ、コラボレーション プラットフォームのコンテキストに直接取り込みます。 詳細については、Teams 開発者の <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">ドキュメントを参照してください</a>。

### <a name="submit-the-app"></a>アプリを送信する

アプリが実用環境で使用できるようになったら、デベロッパーは Teams アプリ提出 API からアプリを提出できます。これを使用すると、グラフ API から呼び出すことができます。これには <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">、グラフ API</a>から、統合開発環境 (IDE) (Visual Studio コードなどの統合開発環境 (IDE) や Power Apps や Power 仮想エージェントなどのプラットフォームを行うことができます。 これにより、アプリは Microsoft Teams 管理<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a>センターの [アプリの管理] ページで利用できるようになります。このページは管理者が確認して承認することができます。これを行うことができます。 

<a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">Microsoft Graph</a>上に組み込まれた Teams アプリの提出 API を使用すると、組織は選択したプラットフォームで開発し、Teams 上のカスタム アプリの申請を自動化できます。

以下に、このアプリの送信手順の例は、コード コーVisual Studioです。

![[ビデオ コード] でアプリを送信するVisual Studioスクリーンショット](media/custom-app-lifecycle-submit-app.png)

アプリは、まだ組織のアプリ ストアに発行されないのでご確認ください。 この手順では、アプリを Microsoft Teams 管理センターに送信します。アプリは、組織のアプリ ストアに発行する承認を承認できます。

Graph API を使用してアプリを送信する方法の詳細については、ここを <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">参照してください</a>。

## <a name="validate"></a>検証

Microsoft Teams<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">管理センター</a>の [アプリの管理] ページ (左側のナビゲーションの **[Teams アプリ**  >  **の**管理] に移動)、組織のすべての Teams アプリを表示できます。 ページ **の上部にある** [承認保留] ウィジェットによって、カスタム アプリが承認のために送信された時点を知ることができます。

テーブルでは、新しく送信されたアプリに自動的に [送信済み]**Publishing status**および [**Submitted**禁止済み] の [**送信済**み] の [発行状況 **] が自動的に表示されます**。 [発行状況 **] 列を** 降順で並べ替えると、アプリをすばやく見つけることができます。

![保留中の要求とアプリの状態を示す [アプリの管理] ページのスクリーンショット ](media/custom-app-lifecycle-validate-app.png)

アプリ名をクリックしてアプリの詳細ページに移動します。 [ユーザー **情報]** タブでは、説明、状態、送信者、アプリ ID など、アプリの詳細を確認できます。

![送信されたアプリのアプリの詳細ページのスクリーンショット](media/custom-app-lifecycle-app-details.png)

グラフ API を使用して発行状況を確認する方法の **詳細については、** ここを <a href="https://docs.microsoft.com/graph/api/teamsapp-list?view=graph-rest-1.0&tabs=http#example-3-list-applications-with-a-given-id-and-return-the-submission-review-state" target="_blank">参照してください</a>。

## <a name="publish"></a>公開

アプリをユーザーが使いやすくする準備ができたら、アプリを発行します。

1. Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの管理**アプリ**  >  **に移動します**。
2. アプリ名をクリックしてアプリの詳細ページに移動し、[発行] **ス** テータス ボックスで [発行] を選 **びます**。

    アプリを発行すると、発行状況が **[発** 行済み] **に変** 化し **、状態が** [許可] に **自動的に変更されます**。

## <a name="set-up-and-manage"></a>セットアップと管理

### <a name="control-access-to-the-app"></a>アプリへのアクセスを制御する

既定では、組織内のすべてのユーザーは、組織のアプリ ストア内のアプリにアクセスできます。 アプリを使用するアクセス許可を持つユーザーを制限および制御するには、アプリのアクセス許可ポリシーを作成して割り当てることができます。 詳細については <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">、Teams でアプリのアクセス許可ポリシーを管理する方法に関するセクションを参照してください</a>。

### <a name="pin-and-install-the-app-for-users-to-discover"></a>ユーザーが見つけたいアプリをピン留みしてインストールする

既定では、ユーザーが組織のアプリ ストアにアクセスして参照または検索する必要があるアプリを見つけるために既定で使用できます。 ユーザーがアプリに簡単にアクセスできるようにするには、アプリを Teams のアプリ バーにピンピン表示することができます。 これを行うには、アプリのセットアップ ポリシーを作成してユーザーに割り当てます。 詳細については <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">、Teams でアプリのセットアップ ポリシーを管理する方法を参照してください</a>。

### <a name="search-the-audit-log-for-teams-app-events"></a>監査ログで Teams アプリのイベントを検索する

監査ログを検索して、組織内の Teams アプリ アクティビティを表示できます。 監査ログを検索する方法と監査ログに記録されている Teams アクティビティの一覧を表示する方法については <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">、「Teams での</a>イベントを検索する」を参照してください。

監査ログを検索する前に、まず監査ログをセキュリティ <a href="https://protection.office.com" target="_blank">センターから有効に &する必要があります</a>。 詳細については、「 <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">監査ログの検索を有効または無効にする」を参照してください</a>。 監査データは監査を有効にした時点からのみ利用できる点にごごご確認ください。

## <a name="discover-and-adopt"></a>検出とアドプット

アプリに対するアクセス許可を持つユーザーは、組織のアプリ ストアでそのアプリを見つけることができます。 [アプリ **] ページ *で組織名の*** 組み込みに移動して、組織のカスタム アプリを見つけます。

![公開済みアプリを示す [アプリ] ページのスクリーンショット ](media/custom-app-lifecycle-discovery.png)

アプリセットアップ ポリシーを作成して割り当てた場合、そのアプリは Teams のアプリ バーにピンンンされ、ポリシーが割り当てられたユーザーに簡単にアクセスできるようになります。

## <a name="update"></a>更新する

アプリを更新するには、開発者は引き続き [開発] セクションの手順に [従う必要](#develop) があります。

公開済みカスタム アプリの更新を開発者が送信すると、[アプリの管理] ページの [承認**Pending approval**保留中] ウィジェットに<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">、ポ</a>ップアップが表示されます。 表では、アプリ **の [発行状況** ] が [更新] **に設定されます**。

![保留中の要求とアプリの状態を示す [アプリの管理] ページのスクリーンショット ](media/custom-app-lifecycle-update-submitted.png)

アプリの更新を確認して公開するには:

1. Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの管理**アプリ**  >  **に移動します**。
2. アプリ名をクリックしてアプリの詳細ページに移動し、[ **更新プログラム] を** 選択して更新プログラムの詳細を確認します。

    ![保留中の要求とアプリの状態を示す [アプリの管理] ページのスクリーンショット ](media/custom-app-lifecycle-update-app.png)
3. 準備ができたら、[公開] **を選択して** 更新プログラムを公開します。 この操作を行うと、既存のアプリが置き換えられます。バージョン番号が更新され、 **発行状況が [発行済** み **] に変更されます**。 すべてのアプリのアクセス許可ポリシーとアプリのセットアップ ポリシーは、更新されたアプリで適用されたままです。

    更新プログラムを拒否すると、以前のバージョンのアプリが公開されたままです。

次の操作を行う必要があります。

- アプリが承認されると、すべてのユーザーがアプリの更新を送信できます。 つまり、元にアプリを送信したデベロッパーなど、他のデベロッパーは、アプリの更新を送信できます。
- 開発者がアプリを送信し、要求が保留中の場合、同じ開発者のみがアプリの更新を送信できます。 他のデベロッパーは、アプリが承認された後でのみ更新プログラムを送信できます。

グラフ API を使用してアプリを更新する方法の詳細については、ここを <a href="https://docs.microsoft.com/graph/api/teamsapp-update?view=graph-rest-1.0#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">参照してください</a>。

### <a name="update-experience-for-users"></a>ユーザー向けの更新操作

ほとんどの場合、アプリの更新プログラムを発行すると、新しいバージョンがユーザーに自動的に表示されます。 ただし、ユーザーが完了する必要がある Microsoft Teams マニ <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">フェ</a> ストには、次のような更新があります。

* ボットが追加または削除されました
* 既存のボットの "botId" プロパティが変更されました
* 既存のボットの "isNotificationOnly" プロパティが変更されました
* ボットの "supportsFiles" プロパティが変更されました
* メッセージングの拡張機能が追加または削除されました
* 新しいコネクタが追加されました
* 新しい統計タブが追加されました
* 新しい構成可能なタブが追加されました
* "webApplicationInfo" 内のプロパティが変更されました

![新しいバージョンが使用可能なアプリを示すスクリーンショット](media/manage-your-custom-apps-update1.png)

![アプリのアップグレード オプションのスクリーンショット](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>関連項目

- [アプリ パッケージをアップロードしてカスタム アプリを発行する](upload-custom-apps.md)
- [Microsoft Teams 管理センターでアプリを管理する](manage-apps.md)
- [Teams のカスタム アプリのポリシーと設定を管理する](teams-custom-app-policies-and-settings.md)
- [Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)
- [Teams のアプリのセットアップ ポリシーを管理する](teams-app-setup-policies.md)
- <a href="https://docs.microsoft.com/graph/api/resources/teamsapp?view=graph-rest-1.0" target="_blank">Teams アプリ用の Microsoft Graph API</a>
