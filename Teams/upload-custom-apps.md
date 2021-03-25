---
title: Microsoft Teams 管理センターでカスタム アプリをアップロードする
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
description: Microsoft Teams 管理センターで組織のアプリ ストアにカスタム アプリをアップロードする方法について説明します。
ms.openlocfilehash: 9473c8e2fc4284c4ca205666152ef183b0210841
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115525"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>アプリ パッケージをアップロードしてカスタム アプリを発行する

> [!NOTE]
> カスタム Teams アプリを発行すると、組織のアプリ ストアのユーザーが利用できます。 カスタム アプリを発行するには 2 つの方法があります。その使い方は、アプリの取得方法によって異なります。 **この記事では、開発者** から送信されたアプリ パッケージ (.zip 形式) をアップロードしてカスタム アプリを発行する方法について説明します。 もう 1 つの方法であるカスタム アプリの承認は、開発者が Teams アプリ提出<a href="/microsoftteams/manage-apps" target="_blank"></a>API を使用してアプリを [アプリの管理] ページに直接送信するときに使用します。 この方法の詳細については、「Teams アプリ提出 API を通じて送信されたカスタム アプリを発行する」 <a href="/microsoftteams/submit-approve-custom-apps" target="_blank">を参照してください</a>。

この記事では、Teams アプリを開発から展開から検出に導く方法について、エンドツーエンドのガイダンスを提供します。 このガイダンスでは、アプリの Teams の側面に重点を当て、管理者と IT のプロを対象にしています。 Teams アプリの開発の詳細については、Teams の開発者向け <a href="/microsoftteams/platform" target="_blank">ドキュメントを参照してください</a>。

![開発から展開まで、アプリの概要](media/upload-custom-apps.png)

## <a name="develop"></a>開発

### <a name="create-your-app"></a>アプリを作成する

Microsoft Teams 開発者プラットフォームを使用すると、開発者は独自のアプリとサービスを簡単に統合して生産性を向上させ、意思決定を迅速に行い、既存のコンテンツとワークフローに関する共同作業を作成できます。 Teams プラットフォーム上に構築されたアプリは、Teams クライアントとサービスとワークフローの間のブリッジであり、コラボレーション プラットフォームのコンテキストに直接取り込むのです。 詳細については、Teams の開発者向け <a href="/microsoftteams/platform" target="_blank">ドキュメントを参照してください</a>。

## <a name="validate"></a>検証

### <a name="get-the-app-package"></a>アプリ パッケージを取得する

アプリを実稼働環境で使用する準備ができたら、開発者はアプリ パッケージを作成する必要があります。 その場合 <a href="/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">、App Studio</a> を使用できます。 ファイルが .zip 形式で送信されます。

Microsoft では <a href="/microsoftteams/platform/publishing/office-store-approval" target="_blank">、これらのガイドラインを使用</a> して、アプリがグローバルな Teams アプリ ストアの品質とセキュリティ標準に準拠します。

### <a name="allow-trusted-users-to-upload-custom-apps"></a>信頼できるユーザーにカスタム アプリのアップロードを許可する

実稼働テナントでアプリが正しく動作している検証を行う場合は、自分または信頼できるユーザーが実稼働テナントにカスタム アプリをアップロードできる必要があります。 これを行 <a href="/microsoftteams/teams-app-setup-policies" target="_blank">うには、アプリセットアップ</a> ポリシーを使用します。

> [!NOTE]
> 検証のために実稼働テナントにアプリをアップロードしても問題が解決しない場合は、この手順をスキップし、「アップロードとセットアップ、管理」セクションの手順に従って[](#upload)、組織[](#set-up-and-manage)のアプリ ストアに評価されていないアプリを発行します。 その後、そのアプリへのアクセスを自分と信頼するユーザーにのみ制限します。 これらのユーザーは、組織のアプリ ストアからアプリを取得して検証を実行できます。 アプリが検証された後は、同じアクセス許可ポリシーを使用してアクセスを開き、実稼働用にアプリをロールアウトします。

信頼できるユーザーがカスタム アプリをアップロードするには、次の手順を実行します。

1. カスタム アプリの **組織全体のアプリの操作を許可** する設定を有効にします。 その手順は次のとおりです。
    1. Microsoft Teams 管理センターの左側のナビゲーションで **、Teams** アプリの [アプリの管理] に移動し、[組織全体のアプリ設定] を  >  **クリックします**。
    2. [ **カスタム アプリ] で**、[カスタム アプリとの **対話を許可する] を** オンにし、[保存] を **クリックします**。
2. グローバル アプリ セットアップ **ポリシーの [カスタム アプリの** アップロード] 設定をオフにします。 その手順は次のとおりです。
    1. Microsoft Teams 管理センターの左側のナビゲーションで **、Teams アプリ** のセットアップ ポリシーに移動し、グローバル (組織全体の既定) ポリシー  >  **をクリック** します。
    2. [カスタム アプリ **のアップロード] をオフにし、[** 保存] を **クリックします**。
3. カスタム アプリのアップロードを許可する新しいアプリ セットアップ ポリシーを作成し、信頼できるユーザーのセットに割り当てる。 その手順は次のとおりです。
    1. Microsoft Teams 管理センターの左側のナビゲーションで **、Teams アプリのセットアップ** ポリシーに移動し、[追加]  >  をクリック **します**。 新しいポリシーに名前と説明を付け、[カスタム アプリのアップロード] をオンにし、[保存] をクリック **します**。
    2. 作成した新しいポリシーを選択し、[ユーザーの管理] を **クリックします**。 ユーザーを検索し、[追加] を **クリックし**、[適用] を **クリックします**。 すべての信頼できるユーザーにポリシーを割り当てるには、この手順を繰り返します。

        ![[アプリセットアップ ポリシーの追加] ページのスクリーンショット](media/manage-your-lob-apps-new-app-setup-policy.png)

    これらのユーザーは、アプリ マニフェストをアップロードして、実稼働テナントでアプリが正しく動作しているのを確認できます。

## <a name="upload"></a>アップロード

組織のアプリ ストアのユーザーがアプリを利用するには、アプリをアップロードします。 これは、Microsoft Teams 管理センター <a href="/microsoftteams/manage-apps" target="_blank">の [</a> アプリの管理] ページで行います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリを管理]** の順に移動します。
2. [ **アップロード]** をクリックし **、[ファイルの選択**] をクリックして、開発者から受け取ったアプリ パッケージを選択します。

   ![管理センターでのアプリのアップロードのスクリーンショット](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a>セットアップと管理

### <a name="control-access-to-the-app"></a>アプリへのアクセスを制御する

既定では、組織内のすべてのユーザーは、組織のアプリ ストアでアプリにアクセスできます。 アプリを使用するアクセス許可を持つユーザーを制限および制御するには、アプリのアクセス許可ポリシーを作成して割り当てる必要があります。 詳細については、「<a href="/microsoftteams/teams-app-permission-policies" target="_blank">Teams のアプリのアクセス許可ポリシーを管理する</a>」を参照してください。

### <a name="pin-and-install-the-app-for-users-to-discover"></a>ユーザーが検出するアプリをピン留めしてインストールする

既定では、ユーザーが組織のアプリ ストアにアクセスしてアプリを参照または検索する必要があるアプリを見つける場合。 ユーザーが簡単にアプリにアクセスするには、アプリを Teams のアプリ バーにピン留めします。 これを行うには、アプリセットアップ ポリシーを作成し、ユーザーに割り当てる必要があります。 詳細については、「<a href="/microsoftteams/teams-app-setup-policies" target="_blank">Teams でアプリの設定ポリシーを管理する</a>」を参照してください。

### <a name="search-the-audit-log-for-teams-app-events"></a>Teams アプリ イベントの監査ログを検索する

監査ログを検索して、組織内の Teams アプリのアクティビティを表示できます。 監査ログを検索する方法と、監査ログに記録されている Teams アクティビティの一覧を表示する方法の詳細については <a href="/microsoftteams/audit-log-events" target="_blank">、「Teams</a>でイベントの監査ログを検索する」を参照してください。

監査ログを検索できるようになるには、最初に<a href="https://protection.office.com" target="_blank">セキュリティ/コンプライアンス センター</a>で監査をオンにする必要があります。 詳細については、「<a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">監査ログの検索を有効または無効にする</a>」を参照してください。 利用できる監査データは、監査を有効にした時点以降のデータのみであることにご注意ください。

## <a name="discover-and-adopt"></a>検出して採用する

アプリへのアクセス許可を持つユーザーは、組織のアプリ ストアで見つける可能性があります。 [アプリ **] ページの *[組織*** 名のビルド] に移動して、組織のカスタム アプリを見つける。

![公開済みアプリを示す [アプリ] ページのスクリーンショット ](media/custom-app-lifecycle-discovery.png)

アプリセットアップ ポリシーを作成して割り当てた場合、アプリは Teams のアプリ バーにピン留めされ、ポリシーが割り当てられたユーザーが簡単にアクセスできます。

## <a name="update"></a>更新

アプリを更新するには、開発と検証のセクションの手順に引き[](#develop)続き[従う](#validate)必要があります。

Microsoft Teams 管理センターの [アプリの管理] ページでアプリを更新できます。 これを行うには、Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの [アプリの **管理] に**  >  **移動します**。 アプリ名をクリックし、[更新] を **クリックします**。 この設定を行った場合、既存のアプリが置き換わるので、すべてのアプリのアクセス許可ポリシーとアプリセットアップ ポリシーは、更新されたアプリに適用されたままです。

### <a name="end-user-update-experience"></a>エンド ユーザーの更新エクスペリエンス

ほとんどの場合、アプリの更新を完了すると、エンド ユーザーに新しいバージョンが自動的に表示されます。 ただし、Microsoft <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Teams</a> マニフェストには、完了するためにユーザーの同意が必要な更新プログラムがあります。

* ボットが追加または削除されました
* 既存のボットの "botId" プロパティが変更されました
* 既存のボットの "isNotificationOnly" プロパティが変更されました
* ボットの "supportsFiles" プロパティが変更されました
* メッセージング拡張機能が追加または削除されました
* 新しいコネクタが追加されました
* 新しい静的タブが追加されました
* 新しい構成可能なタブが追加されました
* "webApplicationInfo" 内のプロパティが変更されました

![新しいバージョンが利用可能なアプリを示すアプリ一覧のスクリーンショット](media/manage-your-custom-apps-update1.png)

![アプリのアップグレード オプションのスクリーンショット](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>関連項目

- [Teams アプリ提出 API を通じて送信されたカスタム アプリを発行する](submit-approve-custom-apps.md)
- [Microsoft Teams 管理センターでアプリを管理する](manage-apps.md)
- [Teams のカスタム アプリのポリシーと設定を管理する](teams-custom-app-policies-and-settings.md)
- [Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)
- [Teams のアプリのセットアップ ポリシーを管理する](teams-app-setup-policies.md)