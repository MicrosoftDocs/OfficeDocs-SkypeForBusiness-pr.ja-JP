---
title: Microsoft Teams 管理センターでカスタム アプリをアップロードする
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
description: Microsoft Teams 管理センターの組織のアプリ ストアにカスタム アプリをアップロードする方法について説明します。
ms.openlocfilehash: 8f7968a53b70ac8ffa871d03adacd648ec047c52
ms.sourcegitcommit: 70185cd963c5a9d539e65e302d4230018209ecae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2022
ms.locfileid: "66958052"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>アプリ パッケージをアップロードしてカスタム アプリを発行する

> [!NOTE]
> カスタム Teams アプリを発行すると、組織のアプリ ストア内のユーザーが利用できるようになります。 カスタム アプリを発行する方法は 2 つあります。使用方法は、アプリの入手方法によって異なります。 **この記事では、開発者から送信されるアプリ パッケージ (.zip 形式) をアップロードしてカスタム アプリを発行する方法について説明** します。 カスタム アプリを承認するもう 1 つの方法は、開発者が Teams アプリ申請 API を使用してアプリを [[アプリの管理](manage-apps.md) ] ページに直接送信するときに使用されます。 その方法の詳細については、「 [Teams アプリ申請 API を使用して送信されたカスタム アプリを発行する」を](submit-approve-custom-apps.md)参照してください。

この記事では、Teams アプリを開発から展開、検出に移行する方法に関するエンドツーエンドのガイダンスを提供します。 このガイダンスは、アプリの Teams の側面に焦点を当て、管理者と IT 担当者を対象としています。 Teams アプリの開発の詳細については、 [Teams 開発者向けドキュメントを参照してください](/microsoftteams/platform/)。

![開発からデプロイまでのアプリの概要。](media/upload-custom-apps.png)

## <a name="create-your-app"></a>アプリを作成する

Microsoft Teams 開発者プラットフォームを使用すると、開発者は独自のアプリとサービスを簡単に統合して生産性を向上させ、意思決定を迅速に行い、既存のコンテンツとワークフローに関するコラボレーションを作成できます。 Teams プラットフォーム上に構築されたアプリは、Teams クライアントとサービスとワークフローの間のブリッジであり、コラボレーション プラットフォームのコンテキストに直接取り込まれます。 詳細については、 [Teams 開発者向けドキュメントを参照してください](/microsoftteams/platform/)。

## <a name="validate"></a>検証

### <a name="get-the-app-package"></a>アプリ パッケージを取得する

アプリを運用環境で使用する準備ができたら、開発者はアプリ パッケージを作成する必要があります。 [App Studio を](/microsoftteams/platform/concepts/build-and-test/app-studio-overview)使用できます。 ファイルは.zip形式で送信されます。

Teams ストア内のすべてのアプリは、グローバル Teams [アプリ](overview-of-app-validation.md) ストアの品質とセキュリティの標準に準拠するために必須のアプリ検証に合格します。 さらに、Microsoft は、アプリ開発者に対して、コンプライアンス、セキュリティ、およびプライバシーの制御の強化を示すオプション [のアプリ コンプライアンス プログラム](overview-of-app-certification.md) に参加することを強くお勧めします。 詳細については、 [Teams アプリの検証ガイドラインに関するページを](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines)参照してください。

### <a name="allow-trusted-users-to-upload-custom-apps"></a>信頼されたユーザーにカスタム アプリのアップロードを許可する

アプリが運用テナントで正しく動作していることを検証するには、自分または信頼できるユーザーが運用テナントにカスタム アプリをアップロードできるようにする必要があります。 これを行うには [、アプリセットアップ ポリシー](teams-app-setup-policies.md) を使用します。

> [!NOTE]
> 検証のためにアプリを運用テナントにアップロードすることに問題がある場合は、この手順をスキップし、[ [アップロード](#upload) と [セットアップと管理](#set-up-and-manage) ] セクションの手順に従って、検証されていないアプリを組織のアプリ ストアに発行できます。 次に、そのアプリへのアクセスを、自分と信頼できるユーザーのみに制限します。 これらのユーザーは、組織のアプリ ストアからアプリを取得して検証を実行できます。 アプリが検証されたら、同じアクセス許可ポリシーを使用してアクセスを開き、運用環境で使用するためにアプリをロールアウトします。

信頼されたユーザーがカスタム アプリをアップロードできるようにするには、次の手順に従います。

1. [ **カスタム アプリとの対話を許可する** ] 組織全体のアプリ設定をオンにします。 その手順は次のとおりです。

    1. Microsoft Teams 管理センターの左側のナビゲーションで、**Teams アプリ** の **[アプリ** > の管理] に移動し、[**組織全体のアプリ設定**] をクリックします。

    1. [ **カスタム アプリ**] で、[ **カスタム アプリとの対話を許可する**] をオンにし、[ **保存**] をクリックします。

1. グローバル アプリ設定ポリシーの **[カスタム アプリのアップロード** ] 設定をオフにします。 その手順は次のとおりです。

    1. Microsoft Teams 管理センターの左側のナビゲーションで、 **Teams アプリ** > **のセットアップ ポリシー** に移動し、 **グローバル (組織全体の既定)** ポリシーをクリックします。

    1. **[カスタム アプリのアップロード**] をオフにし、[保存] をクリック **します**。

1. カスタム アプリのアップロードを許可する新しいアプリセットアップ ポリシーを作成し、信頼できるユーザーのセットに割り当てます。 その手順は次のとおりです。

    1. Microsoft Teams 管理センターの左側のナビゲーションで、 **Teams アプリ** > **のセットアップ ポリシー** に移動し、[ **追加**] をクリックします。 新しいポリシーに名前と説明を付けて、[ **カスタム アプリのアップロード**] をオンにし、[保存] をクリック **します**。

    1. 作成した新しいポリシーを選択し、[ **ユーザーの管理**] をクリックします。 ユーザーを検索し、[ **追加]** をクリックして、[ **適用**] をクリックします。 この手順を繰り返して、信頼できるすべてのユーザーにポリシーを割り当てます。

       ![[アプリセットアップ ポリシーの追加] ページのスクリーンショット](media/manage-your-lob-apps-new-app-setup-policy.png)

これらのユーザーは、アプリ マニフェストをアップロードして、アプリが運用テナントで正しく動作していることを検証できるようになりました。

## <a name="upload"></a>アップロード

組織のアプリ ストアのユーザーがアプリを使用できるようにするには、アプリをアップロードします。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**Teams アプリ** の **[管理アプリ](https://admin.teams.microsoft.com/policies/manage-apps)** > に移動します。
1. [ **アップロード**] を選択し、[ **アップロード**] をクリックし、開発者から受け取ったアプリ パッケージを選択して、[ **開く**] を選択します。

   ![管理センターでアプリをアップロードするスクリーンショット。](media/manage-your-lob-apps-upload-new-app.png)

## <a name="set-up-and-manage"></a>セットアップと管理

### <a name="control-access-to-the-app"></a>アプリへのアクセスを制御する

既定では、組織内のすべてのユーザーが、組織のアプリ ストア内のアプリにアクセスできます。 アプリを使用するアクセス許可を持つユーザーを制限および制御するには、アプリのアクセス許可ポリシーを作成して割り当てることができます。 詳細については、「[Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)」を参照してください。

### <a name="pin-and-install-the-app-for-users-to-discover"></a>ユーザーが検出できるようにアプリをピン留めしてインストールする

既定では、ユーザーが組織のアプリ ストアに移動して参照または検索する必要があるアプリを検索します。 ユーザーが簡単にアプリにアクセスできるように、Teams のアプリ バーにアプリをピン留めできます。 これを行うには、アプリセットアップ ポリシーを作成し、ユーザーに割り当てます。 詳細については、「[Teams でアプリの設定ポリシーを管理する](teams-app-setup-policies.md)」を参照してください。

### <a name="search-the-audit-log-for-teams-app-events"></a>Teams アプリ イベントの監査ログを検索する

監査ログを検索して、組織内の Teams アプリのアクティビティを表示できます。 Teams アクティビティの監査の詳細については、「Teams [のイベントの監査ログを検索する](audit-app-management-activities.md)」を参照してください。

監査ログを検索できるようになるには、最初に[セキュリティ/コンプライアンス センター](https://sip.protection.office.com/homepage) で監査をオンにする必要があります。 詳細については、「[監査ログの検索を有効または無効にする](/microsoft-365/compliance/turn-audit-log-search-on-or-off)」を参照してください。 利用できる監査データは、監査を有効にした時点以降のデータのみであることにご注意ください。

## <a name="discover-and-adopt"></a>検出して採用する

アプリに対するアクセス許可を持つエンド ユーザーは、組織のアプリ ストアで見つけることができます。 [アプリ] ページの [***組織名* のビルド]** に移動して、組織のカスタム アプリを見つけます。

:::image type="content" source="media/custom-app-lifecycle-discovery.png" alt-text="組織向けに発行されたカスタム アプリを示す Teams ストアのスクリーンショット" lightbox="media/custom-app-lifecycle-discovery.png":::

アプリセットアップ ポリシーを作成して割り当てた場合、ポリシーが割り当てられたユーザーが簡単にアクセスできるように、アプリは Teams のアプリ バーにピン留めされます。

## <a name="update"></a>更新

アプリを更新するには、「アプリの作成と[検証](#validate)」セクションの手順[に](#create-your-app)従います。

アプリは、Microsoft Teams 管理センターの [アプリの管理] ページで更新できます。 これを行うには、Microsoft Teams 管理センターの左側のナビゲーションで、**Teams アプリ** の **[アプリ** > の管理] に移動します。 アプリ名をクリックし、[ **更新**] をクリックします。 これにより、既存のアプリが置き換わり、更新されたアプリに対してすべてのアプリアクセス許可ポリシーとアプリセットアップ ポリシーが適用されたままになります。

### <a name="end-user-update-experience"></a>エンド ユーザー更新エクスペリエンス

ほとんどの場合、アプリの更新が完了すると、エンド ユーザーに対して新しいバージョンが自動的に表示されます。 詳細については、 [エンド ユーザーの更新エクスペリエンスに関する記事を](apps-update-experience.md)参照してください。

## <a name="remove"></a>削除

アプリを削除するには、次の手順に従います。

1. Teams 管理センターにサインインします。
1. **Teams アプリ** > の **[[アプリの管理]](https://admin.teams.microsoft.com/policies/manage-apps)** ページにアクセスします。
1. アプリの名前をクリックして、アプリの詳細ページを開きます。
1. アプリ バナーの横にある **[アクション** の削除]  >  を選択 **します**。
1. ダイアログで、[削除] を選択 **します**。

## <a name="related-articles"></a>関連記事

* [Teams アプリ申請 API を使用して送信されたカスタム アプリを発行する](submit-approve-custom-apps.md)
* [Microsoft Teams 管理センターで、Teams アプリの組織向けアプリを管理します。](manage-apps.md)
* [Teams のカスタム アプリのポリシーと設定を管理する](teams-custom-app-policies-and-settings.md)
* [Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)
* [Teams のアプリのセットアップ ポリシーを管理する](teams-app-setup-policies.md)
