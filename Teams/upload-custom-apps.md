---
title: Microsoft Teams 管理センターでカスタム アプリをアップロードする
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
ms.localizationpriority: high
search.appverid: MET150
description: Microsoft Teams 管理センターの組織のアプリ ストアにカスタム アプリをアップロードする方法について説明します。
ms.openlocfilehash: d95635546da7337c9c18ee0fddf7b40a5bf061c3
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2022
ms.locfileid: "67397118"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>アプリ パッケージをアップロードしてカスタム アプリを発行する

> [!NOTE]
> Teams カスタム アプリを発行すると、組織のアプリ ストア内のユーザーがそれを使用できるようになります。 カスタム アプリを発行する方法は 2 つあり、使用方法はアプリの入手方法によって異なります。 **この記事では、開発者から送信されるアプリ パッケージ (.zip 形式) をアップロードしてカスタム アプリを発行する方法について説明します**。 カスタム アプリを承認するもう 1 つの方法は、開発者が Teams アプリ申請 API 経由でアプリを [[アプリの管理]](manage-apps.md) ページに直接送信するときに使用されます。 この方法の詳細については、「[Teams アプリ 申請 API を使用して送信されたカスタム アプリを発行する](submit-approve-custom-apps.md)」をご覧ください。

この記事では、Teams アプリを開発から展開、検出に順番に移行する方法に関するエンドツーエンドのガイダンスを提供します。 このガイダンスは、アプリの Teams の側面に焦点を当て、管理者と IT 担当者を対象としています。 Teams アプリの開発に関する詳細については、「[Teams 開発者向けドキュメント](/microsoftteams/platform/)」を参照してください。

![開発から展開までのアプリの概要。](media/upload-custom-apps.png)

## <a name="create-your-app"></a>アプリを作成する

Microsoft Teams 開発者プラットフォームでは、開発者が簡単に独自のアプリとサービスを統合して生産性を向上させ、迅速に意思決定を行い、既存のコンテンツとワークフロー関連のコラボレーションを作成できます。 Teams プラットフォームにビルドされているアプリは、Teams クライアント、サービス、ワークフローの間のブリッジとして機能し、それらはコラボレーション プラットフォームのコンテキストに直接取り込まれます。 詳細については、「[Teams 開発者向けドキュメント](/microsoftteams/platform/)」を参照してください。

## <a name="validate"></a>検証

### <a name="get-the-app-package"></a>アプリ パッケージを取得する

アプリを運用環境で使用する準備ができたら、開発者はアプリ パッケージを作成する必要があります。 [App Studio](/microsoftteams/platform/concepts/build-and-test/app-studio-overview) を使用できます。 ファイルは .zip 形式で送信されます。

Teams ストア内のすべてのアプリは、グローバル Teams アプリ ストアの品質とセキュリティ基準に準拠するために必須の[アプリ検証](overview-of-app-validation.md)に合格します。 さらに、Microsoft は、アプリ開発者がコンプライアンス、セキュリティ、およびプライバシー制御の強化を示すオプションの[アプリ コンプライアンス プログラム](overview-of-app-certification.md)に参加することを強くお勧めします。 詳細については、「[Teams アプリの検証ガイドライン](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines)」を参照してください。

### <a name="allow-trusted-users-to-upload-custom-apps"></a>信頼されたユーザーがカスタム アプリをアップロードできるようにする

アプリが運用テナントで正しく動作していることを検証するには、自分または信頼できるユーザーが運用テナントにカスタム アプリをアップロードできるようにする必要があります。 これを行うには、[アプリのセットアップ ポリシー](teams-app-setup-policies.md) を使用します。

> [!NOTE]
> 自分自身または信頼されたユーザーによるものであっても、検証のためにアプリを運用テナントにアップロードすることに問題がある場合は、この手順をスキップし、[[アップロード]](#upload) および [[セットアップと管理]](#set-up-and-manage) セクションの手順に従って、未検証のアプリを組織のアプリ ストアに発行できます。 次に、そのアプリへのアクセスを、自分と信頼できるユーザーのみに制限します。 これらのユーザーは、組織のアプリ ストアからアプリを取得して検証を実行できます。 アプリが検証されたら、同じアクセス許可ポリシーを使用してアクセスを開き、運用環境で使用するためにアプリをロールアウトします。

信頼されたユーザーがカスタム アプリをアップロードできるようにするには、次の手順に従います。

1. 組織全体の **[カスタム アプリとの対話を許可する]** アプリ設定をオンにします。 その手順は次のとおりです。

    1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリの管理]** に移動します。その後、**[組織全体のアプリ設定]** を選択します。

    1. [ **カスタム アプリ**] で、[ **カスタム アプリとの対話を許可する**] をオンにし、[保存] を選択 **します**。

1. グローバル アプリ設定ポリシーで、**[カスタム アプリのアップロード]** 設定をオフにします。 その手順は次のとおりです。

    1. Microsoft Teams 管理センターの左側のナビゲーションで、 **Teams アプリ** > **のセットアップ ポリシー** に移動し、 **グローバル (組織全体の既定)** ポリシーを選択します。

    1. **[カスタム アプリのアップロード**] をオフにし、[保存] を選択 **します**。

1. カスタム アプリのアップロードを許可する新しいアプリのセットアップ ポリシーを作成し、信頼できるユーザーのセットに割り当てます。 その手順は次のとおりです。

    1. Microsoft Teams 管理センターの左側のナビゲーションで、 **Teams アプリ** > **のセットアップ ポリシー** に移動し、[ **追加**] を選択します。 新しいポリシーに名前と説明を付けて、[ **カスタム アプリのアップロード**] をオンにし、[保存] を選択 **します**。

    1. 作成した新しいポリシーを選択し、[ **ユーザーの管理**] を選択します。 ユーザーを検索し、[ **追加**] を選択して、[ **適用**] を選択します。 この手順を繰り返して、信頼できるすべてのユーザーにポリシーを割り当てます。

       :::image type="content" source="media/manage-your-lob-apps-new-app-setup-policy.png" alt-text="[アプリセットアップ ポリシーの追加] ページのスクリーンショット。":::

これらのユーザーは、アプリ マニフェストをアップロードして、アプリが運用テナントで正しく動作していることを検証できるようになりました。

## <a name="upload"></a>アップロード

組織のアプリ ストアのユーザーがアプリを使用できるようにするには、アプリをアップロードします。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[[アプリを管理]](https://admin.teams.microsoft.com/policies/manage-apps)** の順に移動します。

1. [ **アップロード**] を選択し、[ **アップロード**] を選択し、開発者から受け取ったアプリ パッケージを選択して、[ **開く**] を選択します。

   ![管理センターでのカスタム アプリのアップロードのスクリーンショット。](media/manage-your-lob-apps-upload-new-app.png)

## <a name="set-up-and-manage"></a>セットアップと管理

### <a name="control-access-to-the-app"></a>アプリへのアクセスを制御する

既定では、組織内のすべてのユーザーが、組織のアプリ ストア内のアプリにアクセスできます。 アプリ使用のアクセス許可を持つユーザーを制限および制御するために、アプリのアクセス許可ポリシーを作成して割り当てることができます。 詳細については、「[Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)」を参照してください。

### <a name="pin-and-install-the-app-for-users-to-discover"></a>ユーザーが検出できるようにアプリをピン留めしてインストールする

既定では、ユーザーが組織のアプリ ストアに移動して参照または検索する必要があるアプリを検索します。 ユーザーが簡単にアプリにアクセスできるように、Teams のアプリ バーにアプリをピン留めできます。 アプリをピン留めするには、アプリセットアップ ポリシーを作成し、ユーザーに割り当てます。 詳細については、「[Teams でアプリの設定ポリシーを管理する](teams-app-setup-policies.md)」を参照してください。

### <a name="search-the-audit-log-for-teams-app-events"></a>Teams でアプリ イベントの監査ログを検索する

監査ログを検索して、組織内のTeams アプリ アクティビティを表示できます。 Teams アクティビティの監査に関する詳細については、「[Teams でイベントの監査ログを検索する](audit-app-management-activities.md)」を参照してください。

監査ログを検索できるようになるには、最初に[セキュリティ/コンプライアンス センター](https://sip.protection.office.com/homepage) で監査をオンにする必要があります。 詳細については、「[監査ログの検索を有効または無効にする](/microsoft-365/compliance/turn-audit-log-search-on-or-off)」を参照してください。 利用できる監査データは、監査を有効にした時点以降のデータのみであることにご注意ください。

## <a name="discover-and-adopt"></a>検出と導入

アプリに対するアクセス許可を持つエンド ユーザーは、組織のアプリ ストアで見つけることができます。 [アプリ] ページの ***[組織名のビルド]*** に移動して、組織のカスタム アプリを見つけます。

:::image type="content" source="media/custom-app-lifecycle-discovery.png" alt-text="組織向けに発行されたカスタム アプリを示す Teams ストアのスクリーンショット" lightbox="media/custom-app-lifecycle-discovery.png":::

アプリのセットアップ ポリシーを作成して割り当てた場合、ポリシーが割り当てられたユーザーが簡単にアクセスできるように、アプリは Teams のアプリ バーにピン留めされます。

## <a name="update-a-custom-app"></a>カスタム アプリを更新する

アプリを更新するには、「[アプリの作成](#create-your-app)と[検証](#validate)」セクションの手順に従います。

Microsoft Teams 管理センターの [アプリを管理] ページでアプリを更新できます。 アプリを更新するには、Microsoft Teams 管理センターの左側のナビゲーションで、**Teams アプリ** > の **[アプリの管理**] に移動します。 アプリ名を選択し、[ **更新**] を選択します。 アプリを更新すると、既存のアプリが置き換わり、更新されたアプリに対してすべてのアプリアクセス許可ポリシーとアプリセットアップ ポリシーが適用されたままになります。

### <a name="end-user-update-experience"></a>エンド ユーザー更新エクスペリエンス

ほとんどの場合、アプリの更新が完了すると、エンド ユーザーに対して新しいバージョンが自動的に表示されます。 詳細については、「[エンド ユーザーの更新エクスペリエンス](apps-update-experience.md)」を参照してください。

## <a name="remove-a-custom-app-from-your-organizations-store"></a>組織のストアからカスタム アプリを削除する

アプリを削除するには、次の手順に従います。

1. Teams 管理センターにサインインします。
1. **[Teams アプリ]** > **[[アプリの管理]](https://admin.teams.microsoft.com/policies/manage-apps)** ページの順にアクセスします。
1. アプリの名前をクリックして、アプリの詳細ページを開きます。
1. アプリ バナーの横にある **[アクション** の削除]  >  を選択 **します**。
1. ダイアログで、**[削除]** を選択します。

## <a name="related-articles"></a>関連記事

* [Teams アプリ 申請 API を使用して送信されたカスタム アプリを発行する](submit-approve-custom-apps.md)
* [Microsoft Teams 管理センターで、Teams アプリの組織向けアプリを管理します。](manage-apps.md)
* [Teams のカスタム アプリのポリシーと設定を管理する](teams-custom-app-policies-and-settings.md)
* [Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)
* [Teams のアプリのセットアップ ポリシーを管理する](teams-app-setup-policies.md)
