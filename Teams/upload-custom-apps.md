---
title: Microsoft Teams管理センターでカスタム アプリをアップロードする
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
description: Microsoft Teams管理センターの組織のアプリ ストアにカスタム アプリをアップロードする方法について説明します。
ms.openlocfilehash: e27bd96477846ae3a74b1b405519e2a2c833ec39
ms.sourcegitcommit: c7b95254dec4420ba0a697fd49d11b448364c919
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2022
ms.locfileid: "63442263"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>アプリ パッケージをアップロードしてカスタム アプリを発行する

> [!NOTE]
> カスタム Teams アプリを発行すると、組織のアプリ ストアのユーザーが利用できるようになります。 カスタム アプリを発行する方法は 2 つあります。使用方法は、アプリの入手方法によって異なります。 **この記事では、開発者から送信されるアプリ パッケージ (.zip 形式) をアップロードしてカスタム アプリを発行する方法について説明** します。 カスタム アプリを承認するもう 1 つの方法は、開発者がアプリ申請 API を使用してアプリを[管理ページに](manage-apps.md)直接送信するときに使用Teams。 その方法の詳細については、「[Teams App Submission API を使用して送信されたカスタム アプリを発行する」を](submit-approve-custom-apps.md)参照してください。

この記事では、開発からデプロイ、検出まで、Teams アプリを実行する方法に関するエンド ツー エンドのガイダンスを提供します。 このガイダンスは、アプリのTeams側面に焦点を当て、管理者と IT 担当者を対象としています。 Teams アプリの開発の詳細については、[Teams開発者向けドキュメントを参照してください](/microsoftteams/platform/)。

![開発からデプロイまでのアプリの概要。](media/upload-custom-apps.png)

## <a name="develop"></a>開発

### <a name="create-your-app"></a>アプリを作成する

Microsoft Teams開発者プラットフォームを使用すると、開発者は独自のアプリとサービスを簡単に統合して生産性を向上させ、意思決定を迅速に行い、既存のコンテンツとワークフローに関するコラボレーションを作成できます。 Teams プラットフォーム上に構築されたアプリは、Teams クライアントとサービスとワークフローの間のブリッジであり、コラボレーション プラットフォームのコンテキストに直接取り込まれます。 詳細については、[Teams開発者向けドキュメントを参照してください](/microsoftteams/platform/)。

## <a name="validate"></a>検証

### <a name="get-the-app-package"></a>アプリ パッケージを取得する

アプリを運用環境で使用する準備ができたら、開発者はアプリ パッケージを作成する必要があります。 その場合は [、App Studio を](/microsoftteams/platform/concepts/build-and-test/app-studio-overview) 使用できます。 ファイルは.zip形式で送信されます。

Microsoft は[、これらのガイドライン](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines)を使用して、アプリがグローバル Teams アプリ ストアの品質とセキュリティの標準に準拠していることを確認します。

### <a name="allow-trusted-users-to-upload-custom-apps"></a>信頼されたユーザーにカスタム アプリのアップロードを許可する

アプリが運用テナントで正しく動作していることを検証するには、自分または信頼できるユーザーが運用テナントにカスタム アプリをアップロードできるようにする必要があります。 これを行うには [、アプリセットアップ ポリシー](teams-app-setup-policies.md) を使用します。

> [!NOTE]
> 検証のためにアプリを運用テナントにアップロードすることに問題がある場合は、自分や信頼できるユーザーであっても、この手順をスキップし、[アップロード](#upload)の手順に従ってセクションを[設定および管理し](#set-up-and-manage)、検証されていないアプリを組織のアプリ ストアに発行することができます。 次に、そのアプリへのアクセスを、自分と信頼できるユーザーのみに制限します。 これらのユーザーは、組織のアプリ ストアからアプリを取得して検証を実行できます。 アプリが検証されたら、同じアクセス許可ポリシーを使用してアクセスを開き、運用環境で使用するためにアプリをロールアウトします。

信頼されたユーザーがカスタム アプリをアップロードできるようにするには、次の手順に従います。

1. [ **カスタム アプリとの対話を許可する** ] 組織全体のアプリ設定をオンにします。 その手順は次のとおりです。
    1. Microsoft Teams管理センターの左側のナビゲーションで、**Teams** **appsManage** >  アプリに移動し、[**組織全体のアプリ設定**] をクリックします。
    2. [ **カスタム アプリ**] で、[ **カスタム アプリとの対話を許可する**] をオンにし、[ **保存**] をクリックします。
2. グローバル アプリ設定ポリシー **で、アップロードカスタム** アプリ設定をオフにします。 その手順は次のとおりです。
    1. Microsoft Teams管理センターの左側のナビゲーションで、**Teams appsSetup** >  **ポリシー** に移動し、**グローバル (組織全体の既定)** ポリシーをクリックします。
    2. **カスタム アプリアップロード** オフにし、[**保存**] をクリックします。
3. カスタム アプリのアップロードを許可する新しいアプリセットアップ ポリシーを作成し、信頼できるユーザーのセットに割り当てます。 その手順は次のとおりです。
    1. Microsoft Teams管理センターの左側のナビゲーションで、**Teams appsSetup** >  **ポリシー** に移動し、[**追加**] をクリックします。 新しいポリシーに名前と説明を付けて、**カスタム アプリアップロード** オンにし、[**保存**] をクリックします。
    2. 作成した新しいポリシーを選択し、[ **ユーザーの管理**] をクリックします。 ユーザーを検索し、[ **追加]** をクリックして、[ **適用**] をクリックします。 この手順を繰り返して、信頼できるすべてのユーザーにポリシーを割り当てます。

        ![[アプリセットアップ ポリシーの追加] ページのスクリーンショット](media/manage-your-lob-apps-new-app-setup-policy.png)

    これらのユーザーは、アプリ マニフェストをアップロードして、アプリが運用テナントで正しく動作していることを検証できるようになりました。

## <a name="upload"></a>アップロード

組織のアプリ ストアのユーザーがアプリを使用できるようにするには、アプリをアップロードします。 これを行うには、Microsoft Teams管理センターの [[アプリの管理](manage-apps.md)] ページで行います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリを管理]** の順に移動します。
2. **アップロード** 選択し、**アップロード** をクリックして、開発者から受け取ったアプリ パッケージを選択して、[**開く**] を選択します。

   ![管理センターでアプリをアップロードするスクリーンショット。](media/manage-your-lob-apps-upload-new-app.png)

## <a name="set-up-and-manage"></a>セットアップと管理

### <a name="control-access-to-the-app"></a>アプリへのアクセスを制御する

既定では、組織内のすべてのユーザーが、組織のアプリ ストア内のアプリにアクセスできます。 アプリを使用するアクセス許可を持つユーザーを制限および制御するには、アプリのアクセス許可ポリシーを作成して割り当てることができます。 詳細については、「[Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)」を参照してください。

### <a name="pin-and-install-the-app-for-users-to-discover"></a>ユーザーが検出できるようにアプリをピン留めしてインストールする

既定では、ユーザーが組織のアプリ ストアに移動して参照または検索する必要があるアプリを検索します。 ユーザーがアプリに簡単にアクセスできるように、アプリをTeamsのアプリ バーにピン留めできます。 これを行うには、アプリセットアップ ポリシーを作成し、ユーザーに割り当てます。 詳細については、「[Teams でアプリの設定ポリシーを管理する](teams-app-setup-policies.md)」を参照してください。

### <a name="search-the-audit-log-for-teams-app-events"></a>Teams アプリ イベントの監査ログを検索する

監査ログを検索して、組織内のTeamsアプリアクティビティを表示できます。 監査ログを検索する方法と、監査ログに記録されているTeamsアクティビティの一覧を表示する方法の詳細については、「[Teamsのイベントの監査ログを検索する](audit-log-events.md)」を参照してください。

監査ログを検索できるようになるには、最初に[セキュリティ/コンプライアンス センター](https://sip.protection.office.com/homepage) で監査をオンにする必要があります。 詳細については、「[監査ログの検索を有効または無効にする](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide)」を参照してください。 利用できる監査データは、監査を有効にした時点以降のデータのみであることにご注意ください。

## <a name="discover-and-adopt"></a>検出して採用する

アプリに対するアクセス許可を持つユーザーは、組織のアプリ ストアで見つけることができます。 [アプリ] ページの [***組織名* のビルド]** に移動して、組織のカスタム アプリを見つけます。

![公開されたアプリを示す [アプリ] ページのスクリーンショット。](media/custom-app-lifecycle-discovery.png)

アプリセットアップ ポリシーを作成して割り当てた場合、アプリはTeamsのアプリ バーにピン留めされ、ポリシーが割り当てられたユーザーに簡単にアクセスできます。

## <a name="update"></a>更新

アプリを更新するには、開発者は引き続き [開発](#develop) と [検証](#validate) のセクションの手順に従う必要があります。

アプリは、Microsoft Teams管理センターの [アプリの管理] ページで更新できます。 これを行うには、Microsoft Teams管理センターの左側のナビゲーションで、**Teams** **appsManage** >  アプリに移動します。 アプリ名をクリックし、[ **更新**] をクリックします。 これにより、既存のアプリが置き換わり、更新されたアプリに対してすべてのアプリアクセス許可ポリシーとアプリセットアップ ポリシーが適用されたままになります。

### <a name="end-user-update-experience"></a>エンド ユーザー更新エクスペリエンス

ほとんどの場合、アプリの更新が完了すると、エンド ユーザーに対して新しいバージョンが自動的に表示されます。 ただし、ユーザーの同意を完了する必要がある[Microsoft Teams マニフェスト](/microsoftteams/platform/resources/schema/manifest-schema)にいくつかの更新プログラムがあります。

* ボットが追加または削除されました
* 既存のボットの "botId" プロパティが変更されました
* 既存のボットの "isNotificationOnly" プロパティが変更されました
* ボットの SupportsCalling、SupportsVideo、および SupportsFiles 機能が追加されました
* メッセージング拡張機能が追加されました
* 新しいコネクタが追加されました
* "Authorization" 内のアクセス許可が追加または変更されました

![新しいバージョンが利用可能なアプリを示すアプリの一覧のスクリーンショット。](media/manage-your-custom-apps-update1.png)

![アプリのアップグレード オプションのスクリーンショット。](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>関連項目

* [Teams アプリ申請 API を使用して送信されたカスタム アプリを発行する](submit-approve-custom-apps.md)

* [Microsoft Teams 管理センターで、Teams アプリの組織向けアプリを管理します。](manage-apps.md)
* [Teams のカスタム アプリのポリシーと設定を管理する](teams-custom-app-policies-and-settings.md)

* [Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)
* [Teams のアプリのセットアップ ポリシーを管理する](teams-app-setup-policies.md)
