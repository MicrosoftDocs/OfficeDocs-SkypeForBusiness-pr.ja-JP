---
title: Microsoft Teams 管理センターでカスタムアプリをアップロードする
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
description: Microsoft Teams 管理センターでカスタムアプリを組織のアプリストアにアップロードする方法について説明します。
ms.openlocfilehash: 68d7dbc16ca3aa6258fd5f976688240095226934
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552851"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>アプリパッケージをアップロードしてカスタムアプリを公開する

> [!NOTE]
> カスタム Teams アプリを公開すると、組織のアプリストア内のユーザーがそのアプリを利用できるようになります。 カスタムアプリを公開する方法は2つあります。また、アプリの入手方法によって異なります。 **この記事では、開発者から送信されたアプリパッケージ (.zip 形式) をアップロードして、カスタムアプリを公開する方法について説明**します。 その他の方法 (カスタムアプリを承認する) は、開発者が Teams アプリ申請 API を使用してアプリの<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">管理</a>ページに直接アプリを送信するときに使用されます。 このメソッドの詳細については、「 <a href="https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps" target="_blank">Teams アプリ申請 API を通じて送信されたカスタムアプリを公開</a>する」を参照してください。

この記事では、チームアプリを開発から展開に移動する方法についてのエンドツーエンドのガイダンスについて説明します。 このガイダンスは、アプリの Teams の側面を中心としており、管理者と IT プロフェッショナルを対象としています。 Teams アプリの開発の詳細については、 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">teams の開発者向けドキュメント</a>を参照してください。

![開発から展開までのアプリの概要](media/upload-custom-apps.png)

## <a name="develop"></a>開発

### <a name="create-your-app"></a>アプリを作成する

Microsoft Teams の開発者は、開発者が独自のアプリとサービスを統合して生産性を向上させ、意思決定を迅速化し、既存のコンテンツとワークフローを取り巻くコラボレーションを作成することが容易になります。 Teams プラットフォームで構築されたアプリは、Teams クライアントとサービスとワークフローの間のブリッジであり、コラボレーションプラットフォームのコンテキストに直接移行します。 詳細については、「 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams の開発者向けドキュメント</a>」を参照してください。

## <a name="validate"></a>有効性

### <a name="get-the-app-package"></a>アプリパッケージを取得する

アプリを運用環境で使う準備ができたら、開発者はアプリパッケージを生成する必要があります。 そのためには、<a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">アプリ Studio</a>を使うことができます。 ファイルを .zip 形式で送信します。

Microsoft は、<a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">これらのガイドライン</a>を使用して、アプリがグローバルチームアプリストアの品質とセキュリティ標準に準拠していることを確認します。

### <a name="allow-trusted-users-to-upload-custom-apps"></a>信頼されたユーザーによるカスタムアプリのアップロードを許可する

プロダクションテナントでアプリが正常に動作していることを検証するには、ユーザー自身や信頼されたユーザーが、プロダクションテナントでカスタムアプリをアップロードすることを許可する必要があります。 これを行うには、<a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">アプリセットアップポリシー</a>を使います。

> [!NOTE]
> 自分や信頼されたユーザーであっても、検証のためにアプリを運用テナントにアップロードすることを希望している場合は、この手順をスキップし、「セクションの[アップロード](#upload)と[設定および管理](#set-up-and-manage)」の手順に従って、unvalidated アプリを組織のアプリストアに公開してください。 その後、そのアプリへのアクセスを、信頼できる自分とユーザーのみに制限します。 次に、これらのユーザーは、組織のアプリストアからアプリを取得して検証を実行することができます。 アプリを検証した後で、同じアクセス許可ポリシーを使用して access を開き、運用のためにアプリをロールアウトします。

信頼されたユーザーに対してカスタムアプリのアップロードを許可するには、次の手順を実行します。

1. [**カスタムアプリの組織全体での操作を許可する**] 設定をオンにします。 その手順は次のとおりです。
    1. Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**の管理] に移動し、  >  **Manage apps**[**組織全体のアプリの設定**] をクリックします。
    2. [**カスタムアプリ**] の下で、[**カスタムアプリでの操作を許可**する] をオンにし、[**保存**] をクリックします。
2. グローバルアプリセットアップポリシーで [**カスタムアプリのアップロード**] 設定をオフにします。 その手順は次のとおりです。
    1. Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**  >  **セットアップポリシー**] に移動し、[**グローバル (組織全体の既定)** ] ポリシーをクリックします。
    2. [**カスタムアプリのアップロード**] をオフにして、[**保存**] をクリックします。
3. カスタムアプリをアップロードして、信頼されたユーザーのセットに割り当てることができる新しいアプリのセットアップポリシーを作成します。 その手順は次のとおりです。
    1. Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**  >  **セットアップポリシー**] に移動し、[**追加**] をクリックします。 新しいポリシーに名前と説明を付け、[**カスタムアプリのアップロード**] をオンにして、[**保存**] をクリックします。
    2. 作成した新しいポリシーを選択し、[**ユーザーの管理**] をクリックします。 ユーザーを検索し、[**追加**] をクリックして、[**適用**] をクリックします。 この手順を繰り返して、すべての信頼できるユーザーにポリシーを割り当てます。

        ![[アプリセットアップポリシーの追加] ページのスクリーンショット](media/manage-your-lob-apps-new-app-setup-policy.png)

    これらのユーザーは、アプリマニフェストをアップロードして、アプリが運用テナントで正常に動作していることを確認できます。

## <a name="upload"></a>アルバム

組織の app store のユーザーがアプリを利用できるようにするには、アプリをアップロードします。 これは、Microsoft Teams 管理センターの [<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">アプリの管理</a>] ページで行うことができます。

1. Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**の管理] に移動  >  **Manage apps**します。
2. [**アップロード**] をクリックし、[**ファイルの選択**] をクリックして、開発者から受け取ったアプリパッケージを選択します。

   ![管理センターでのアプリのアップロードのスクリーンショット](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a>設定と管理

### <a name="control-access-to-the-app"></a>アプリへのアクセスを制御する

既定では、組織内のすべてのユーザーが、組織のアプリストアのアプリにアクセスできます。 アプリを使う権限を持つユーザーを制限および制御するには、アプリのアクセス許可ポリシーを作成して割り当てることができます。 詳細については、「 <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Teams でアプリのアクセス許可ポリシーを管理</a>する」を参照してください。

### <a name="pin-and-install-the-app-for-users-to-discover"></a>ユーザーが検出できるようにアプリを固定してインストールする

既定では、ユーザーがアプリを見つけるには、組織のアプリストアに移動し、それを参照または検索する必要があります。 ユーザーがアプリを簡単に利用できるようにするために、アプリを Teams のアプリバーにピン留めすることができます。 これを行うには、アプリのセットアップポリシーを作成し、ユーザーに割り当てます。 詳細については、「 <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Teams でアプリセットアップポリシーを管理</a>する」を参照してください。

## <a name="discover-and-adopt"></a>発見と採用

アプリへのアクセス許可を持つユーザーは、そのアプリを組織のアプリストアで見つけることができます。 [アプリ] ページで [ ***組織名に合わせ*て作成**済み] に移動して、組織のカスタムアプリを見つけます。

![公開されたアプリが表示されている [アプリ] ページのスクリーンショット ](media/custom-app-lifecycle-discovery.png)

アプリのセットアップポリシーを作成して割り当てた場合、アプリは、ポリシーが割り当てられたユーザーに対して簡単にアクセスできるように、Teams のアプリバーに固定されます。

## <a name="update"></a>更新する

アプリを更新するには、開発者はセクション「[開発](#develop)と[検証](#validate)」の手順に従って続行する必要があります。

Microsoft Teams 管理センターの [アプリの管理] ページでアプリを更新することができます。 これを行うには、Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**の管理] に移動  >  **Manage apps**します。 アプリ名をクリックし、[**更新**] をクリックします。 この操作を行うと既存のアプリが置き換えられ、アプリのすべてのアクセス許可ポリシーとアプリのセットアップポリシーは、更新されたアプリに適用されたままになります。

### <a name="end-user-update-experience"></a>エンドユーザーによる更新エクスペリエンス

ほとんどの場合、アプリの更新が完了すると、新しいバージョンはエンドユーザーに対して自動的に表示されます。 ただし、 <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams マニフェスト</a>には、ユーザーの承認を必要とする次のような更新があります。

* ボットが追加または削除された
* 既存のボットの "botId" プロパティが変更されました
* 既存のボットの "isNotificationOnly" プロパティが変更されました
* ボットの "supportsFiles" プロパティが変更されました
* メッセージング拡張機能が追加または削除されました
* 新しいコネクタが追加されました
* 新しい静的タブが追加されました
* 新しい [構成可能] タブが追加されました
* "WebApplicationInfo" 内のプロパティが変更されました

![新しいバージョンが利用可能なアプリが表示されているアプリの一覧のスクリーンショット](media/manage-your-custom-apps-update1.png)

![アプリのアップグレードオプションのスクリーンショット](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>関連項目

- [Teams アプリ申請 API を通じて送信されたカスタムアプリを公開する](submit-approve-custom-apps.md)
- [Microsoft Teams 管理センターでアプリを管理する](manage-apps.md)
- [Teams のカスタム アプリのポリシーと設定を管理する](teams-custom-app-policies-and-settings.md)
- [Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)
- [Teams のアプリのセットアップ ポリシーを管理する](teams-app-setup-policies.md)
