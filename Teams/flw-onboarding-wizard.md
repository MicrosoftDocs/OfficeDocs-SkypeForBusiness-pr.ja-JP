---
title: Frontline Worker オンボード ウィザードを使用して、フロント ラインの従業員を稼働させます。
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Frontline Worker オンボード ウィザードを使用して、組織内のフロントラインワーカーとマネージャーに合わせて調整された Teams でエクスペリエンスをすばやくデプロイする方法について学習します。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 060604853b29111372a605ff0ad6212ba1e56a8a
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2021
ms.locfileid: "60046423"
---
# <a name="use-the-frontline-worker-onboarding-wizard-to-get-your-frontline-workforce-up-and-running"></a>Frontline Worker オンボード ウィザードを使用して、フロント ラインの従業員を稼働させます。

> [!NOTE]
> この機能がまだ表示されていない場合は、 現在ロールアウトされている最中で、お客様の組織ではまだ利用できない可能性があります。 Teams 機能の最新情報を入手するには、「[Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)」を参照してください。

## <a name="overview"></a>概要

フロントライン ワーカーのオンボーディング ウィザードは、Microsoft 365 管理センターにフロントライン ワーカーを簡単にオンボードできます。 ウィザードを使用すると、最前線の従業員に合わせてMicrosoft Teamsエクスペリエンスをすばやくデプロイできます。 ウィザードを使用すると、組織内のフロントライン ワーカー向Teamsパイロット デプロイを簡単に開始できます。

ウィザードでは、フロントライン ワーカーのチームが設定され、各チーム メンバーにライセンスと [ポリシー](manage-policy-packages.md) パッケージが割り当てされます。 チームを最初から作成するか、チーム テンプレート[](get-started-with-teams-templates-in-the-admin-console.md)から作成し、ユーザーを追加してロールを割り当てることができます。 ロールによって、ウィザードが各ユーザーに割り当てるポリシー パッケージが決定されます。

現時点では、ウィザードを実行するごとに 100 人のユーザーの追加がサポートされています。 現在、1 回の実行に対するユーザー数の増加に取り組む予定です。 最新の更新プログラムについては、こちらを参照してください。

ウィザードは、少なくとも 1 つの F ライセンスを持つすべてのMicrosoft 365使用できます。 ウィザードは、組織全体の異なる場所またはサイトで、Teamsに展開する必要がある回数実行できます。

> [!NOTE]
> このウィザードを使用すると、フロントライン ワーカーをすぐにオンボードして、TeamsをMicrosoft 365 管理センター。 スクリプトを使用してフロントライン Teamsにデプロイする方法の詳細については[、「Frontline Worker](flw-scripted-deployment.md)の大規模な Teams をプロビジョニングする方法」を参照してください。

## <a name="run-the-wizard"></a>ウィザードを実行する

1. 左側のナビゲーションで、[セットアップ][をMicrosoft 365 管理センター](https://admin.microsoft.com/)選択 **します**。 [アプリと **メール] セクションに移動** し **、[Get your frontline workforce up and running]** の [表示] を **選択します**。 ここでは、フロント ライン ワーカーが提供する機能Microsoft 365詳細を確認できます。

    :::image type="content" source="media/flw-onboarding-wizard-get-started.png" alt-text="Microsoft 365 管理センター の Frontline Worker オンボーディング エクスペリエンスの詳細ページのスクリーンショット":::

2. 準備ができたら、[開始] を **選択して** ウィザードを実行します。

3. チームの名前を入力し、1 人または複数のチーム所有者を追加して、プライバシー設定を選択します。 次に、最初からチームを作成するか、チーム テンプレートからチームを作成するかを選択します。 チーム テンプレートには定義済みのチャネルとタブが含まれています。このタブは、特定のビジネス 上の必要性やプロジェクトに合ってチームを最適化します。

    :::image type="content" source="media/flw-onboarding-wizard-set-up-team.png" alt-text="ウィザードの [チームの設定] ページのスクリーンショット":::

4. ユーザーをチームに追加します。 グループを追加することもできます。 グループを追加する場合は、グループ自体ではなく、グループ内の各ユーザーにライセンスとポリシー パッケージが直接割り当てられるので、ご安心ください。

    :::image type="content" source="media/flw-onboarding-wizard-add-users.png" alt-text="ユーザーとグループをチームに追加するウィザードの [ユーザーの追加] ページのスクリーンショット":::

5. 各チーム メンバーに、Frontline Worker、Frontline Manager、None のいずれかのロールを割り当てます。 
  
    :::image type="content" source="media/flw-onboarding-wizard-assign-roles.png" alt-text="チーム メンバーにロール、場所、ライセンスを割り当てるウィザードの [ジョブ ロールの割り当て] ページのスクリーンショット":::

    Frontline Worker または Frontline Manager ロールを割り当てると、そのユーザーはポリシー パッケージを受け取る必要があります。 ポリシー パッケージは、ロールに合わせてTeamsエクスペリエンスを作成します。 このエクスペリエンスには、正常なフロントライン ワーカーとマネージャーのコミュニケーションとコラボレーションのための事前固定アプリとポリシーが含まれます。

    次に、場所を選択し、各チーム Microsoft 365 F ライセンスを割り当てる。 十分なライセンスを持ってない場合は、[ライセンスの追加購入] を選択 **して、ライセンス** を追加購入できます。  

6. ウィザードの完了後にステータス メールを受け取るユーザーを選択します。 電子メールには、ウィザードがチームの作成、チーム メンバーの追加、および各チーム メンバーへのライセンスとポリシー パッケージの割り当てによって実行されたアクションに関する成功と失敗の情報 &mdash; が含まれています。 この情報を使用して、発生する可能性があるエラーのトラブルシューティングを行います。

    :::image type="content" source="media/flw-onboarding-wizard-email-recipients.png" alt-text="ウィザードの [状態のメール受信者の追加] ページのスクリーンショット":::

7. 選択内容を確認し、[確認] を **選択します**。

    :::image type="content" source="media/flw-onboarding-wizard-review-team.png" alt-text="チーム設定を確認するウィザードの [チームのレビュー] ページのスクリーンショット":::

    ウィザードによってチームが作成され、ライセンスとポリシー パッケージがチーム メンバーに割り当てされます。 完了まで数分かかる場合があります。その後、選択した受信者はステータス メールを受信します。

8. 途中ですが、まだ完了していません。 次に、この記事の [「ウィザードを実行した後の操作](#what-to-do-after-running-the-wizard) 」セクションを参照してください。

## <a name="what-to-do-after-running-the-wizard"></a>ウィザードの実行後の操作

ウィザードを実行した後は、次の点が重要です。

- フロントラインの従業員とマネージャーに、その従業員にライセンスが割り当てられているTeamsします。
- 共有デバイスを使用している場合は、それらのTeamsにインストールされていることを確認します。 組織で "自分のデバイスを持ち込む" モデルを使用している場合は、フロントラインの従業員とマネージャーに、デバイスにデバイスをダウンロードしてインストールする必要Teams知らせる必要があります。

フロントラインの従業員が Teams を初めて開くと、チャットとチャネル、通話、タスク管理を含む、カスタマイズされた最初の実行エクスペリエンスが Teams 内で提供されます。

## <a name="related-articles"></a>関連記事

- [Teams でポリシー パッケージを管理する](manage-policy-packages.md)
- [管理センターでチーム テンプレートTeams使用する](get-started-with-teams-templates-in-the-admin-console.md)
