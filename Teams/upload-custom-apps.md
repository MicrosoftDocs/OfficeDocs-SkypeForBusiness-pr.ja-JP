---
title: アップロード管理センターでカスタム アプリをMicrosoft Teamsする
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
description: カスタム アプリを管理センターの組織のアプリ ストアにアップロードMicrosoft Teams説明します。
ms.openlocfilehash: 9473c8e2fc4284c4ca205666152ef183b0210841
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115525"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>アプリ パッケージをアップロードしてカスタム アプリを発行する

> [!NOTE]
> カスタム アプリを発行Teams、組織のアプリ ストア内のユーザーが使用できます。 カスタム アプリを発行する方法と使用する方法は、アプリの取得方法によって異なります。 **この記事では、** 開発者から送信されたアプリ パッケージ (.zip 形式) をアップロードして、カスタム アプリを発行する方法について説明します。 カスタム アプリを承認するもう 1 つの方法は、開発者がアプリの管理ページに<a href="/microsoftteams/manage-apps" target="_blank"></a>アプリを直接送信するときに、Teams アプリ送信 API を使用します。 その方法の詳細については、「アプリ送信 API を使用して送信されたカスタム アプリを発行Teams<a href="/microsoftteams/submit-approve-custom-apps" target="_blank">参照してください</a>。

この記事では、開発からデプロイから検出まで、Teamsアプリを使用する方法について、エンド to エンドのガイダンスを提供します。 このガイダンスでは、アプリのTeamsに焦点を当て、管理者と IT のプロを対象にしています。 アプリの開発の詳細については、Teams 開発者向けドキュメント<a href="/microsoftteams/platform" target="_blank">Teams参照してください</a>。

![開発からデプロイまで、アプリの概要](media/upload-custom-apps.png)

## <a name="develop"></a>開発

### <a name="create-your-app"></a>アプリを作成する

開発者Microsoft Teamsプラットフォームを使用すると、開発者は独自のアプリとサービスを簡単に統合して生産性を向上させ、意思決定を迅速に行い、既存のコンテンツやワークフローに関するコラボレーションを作成できます。 Teams プラットフォーム上に構築されたアプリは、Teams クライアントとサービスとワークフローの間のブリッジであり、コラボレーション プラットフォームのコンテキストに直接取り込む必要があります。 詳細については、開発者向けドキュメント<a href="/microsoftteams/platform" target="_blank">Teams参照してください</a>。

## <a name="validate"></a>検証

### <a name="get-the-app-package"></a>アプリ パッケージを取得する

アプリを実稼働環境で使用する準備ができたら、開発者はアプリ パッケージを生成する必要があります。 その場合 <a href="/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">、App Studio</a> を使用できます。 ユーザーは、ファイルを別の形式.zipします。

Microsoft では<a href="/microsoftteams/platform/publishing/office-store-approval" target="_blank">、これらのガイドラインを使用</a>して、アプリがグローバルなアプリ ストアの品質とセキュリティ基準に準拠Teamsします。

### <a name="allow-trusted-users-to-upload-custom-apps"></a>信頼できるユーザーにカスタム アプリのアップロードを許可する

アプリが実稼働テナントで正しく動作しているのを検証するには、自分や信頼できるユーザーがカスタム アプリを実稼働テナントにアップロードできる必要があります。 これを行 <a href="/microsoftteams/teams-app-setup-policies" target="_blank">うには、アプリセットアップ ポリシー</a> を使用します。

> [!NOTE]
> 検証のためにアプリを実稼働テナントにアップロードする場合は、この手順をスキップし[、「アップロード」](#upload)セクションと「セットアップと管理」セクションの手順に従って、検証されていないアプリを[](#set-up-and-manage)組織のアプリ ストアに発行できます。 その後、そのアプリへのアクセスを自分と信頼できるユーザーにのみ制限します。 これらのユーザーは、検証を実行するために、組織のアプリ ストアからアプリを取得できます。 アプリが検証された後、同じアクセス許可ポリシーを使用して、アクセス権を開き、アプリを実稼働環境で使用するためにロールアウトします。

信頼できるユーザーにカスタム アプリのアップロードを許可するには、次の手順に従います。

1. [カスタム アプリ **との対話を許可する] 組織全体** のアプリ設定を有効にします。 その手順は次のとおりです。
    1. 管理センターの左側の Microsoft Teamsナビゲーションで、[Teams **アプリ** の管理] に移動し、[組織全体のアプリ設定]  >  **をクリックします**。
    2. [ **カスタム アプリ] で**、[カスタム アプリとの対話を許可する] **をオンに** し、[保存] を **クリックします**。
2. グローバル アプリセットアップ **ポリシーアップロードカスタム** アプリの設定をオフにします。 その手順は次のとおりです。
    1. Microsoft Teams 管理センターの左側のナビゲーションで、[Teams **アプリ** のセットアップ ポリシー] に移動し、[グローバル (組織全体の既定) ポリシー]  >  **をクリック** します。
    2. カスタム アプリ **をアップロードをオフにし、[** 保存] を **クリックします**。
3. カスタム アプリをアップロードして信頼できるユーザーのセットに割り当て可能な新しいアプリ セットアップ ポリシーを作成します。 その手順は次のとおりです。
    1. 管理センターの左側のナビゲーションMicrosoft Teamsアプリのセットアップ Teams **に** 移動し、[追加]  >  をクリック **します**。 新しいポリシーに名前と説明を付け、カスタム アップロード **を有効に** し、[保存] を **クリックします**。
    2. 作成した新しいポリシーを選択し、[ユーザーの管理] **をクリックします**。 ユーザーを検索し、[追加] **をクリックして**、[適用] を **クリックします**。 この手順を繰り返して、信頼できるすべてのユーザーにポリシーを割り当てる。

        ![[アプリのセットアップ ポリシーの追加] ページのスクリーンショット](media/manage-your-lob-apps-new-app-setup-policy.png)

    これらのユーザーは、アプリ マニフェストをアップロードして、アプリが実稼働テナントで正しく動作しているのを検証できます。

## <a name="upload"></a>アップロード

組織のアプリ ストア内のユーザーがアプリを利用するには、アプリをアップロードします。 管理センターの [<a href="/microsoftteams/manage-apps" target="_blank">アプリの管理</a>] ページMicrosoft Teamsできます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリを管理]** の順に移動します。
2. **[アップロード]** をクリックし **、[ファイルの** 選択] をクリックし、開発者から受け取ったアプリ パッケージを選択します。

   ![管理センターでのアプリのアップロードのスクリーンショット](media/manage-your-lob-apps-upload-new-app.png) 

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

![発行されたアプリを示す [アプリ] ページのスクリーンショット ](media/custom-app-lifecycle-discovery.png)

アプリセットアップ ポリシーを作成して割り当てた場合、アプリは Teams のアプリ バーにピン留めされ、ポリシーが割り当てられたユーザーに簡単にアクセスできます。

## <a name="update"></a>更新

アプリを更新するには、開発者は引き続き「開発と検証」セクションの[手順](#develop)[に](#validate)従う必要があります。

アプリは、管理センターの [アプリの管理] ページMicrosoft Teams更新できます。 これを行うには、管理センターの左側のナビゲーションMicrosoft Teamsアプリの管理Teams **に**  >  **移動します**。 アプリ名をクリックし、[更新] を **クリックします**。 これにより、既存のアプリが置き換え、すべてのアプリアクセス許可ポリシーとアプリセットアップ ポリシーが、更新されたアプリに適用されたままです。

### <a name="end-user-update-experience"></a>エンド ユーザーの更新エクスペリエンス

ほとんどの場合、アプリの更新を完了すると、エンド ユーザーに対して新しいバージョンが自動的に表示されます。 ただし、完了するためにユーザーの受け入れを<a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">必要Microsoft Teamsマニフェスト</a>にはいくつかの更新があります。

* ボットが追加または削除されました
* 既存のボットの "botId" プロパティが変更されました
* 既存のボットの "isNotificationOnly" プロパティが変更されました
* ボットの "supportsFiles" プロパティが変更されました
* メッセージング拡張機能が追加または削除されました
* 新しいコネクタが追加されました
* 新しい静的タブが追加されました
* 新しい構成可能なタブが追加されました
* "webApplicationInfo" 内のプロパティが変更されました

![新しいバージョンが利用可能なアプリを示すアプリの一覧のスクリーンショット](media/manage-your-custom-apps-update1.png)

![アプリのアップグレード オプションのスクリーンショット](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>関連トピック

- [Teams App Submission API を使用して送信されたカスタム アプリを発行する](submit-approve-custom-apps.md)
- [管理センターでアプリMicrosoft Teams管理する](manage-apps.md)
- [Teams のカスタム アプリのポリシーと設定を管理する](teams-custom-app-policies-and-settings.md)
- [Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)
- [Teams のアプリのセットアップ ポリシーを管理する](teams-app-setup-policies.md)