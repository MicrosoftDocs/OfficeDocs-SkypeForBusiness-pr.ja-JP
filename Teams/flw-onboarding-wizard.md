---
title: 現場担当者オンボード ウィザードを使用して、現場の従業員を稼働させます
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Frontline Worker オンボード ウィザードを使用して、組織内の現場のワーカーとマネージャーに合わせて調整されたTeamsでエクスペリエンスをすばやく展開する方法について説明します。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: ac4db418927c34920614c65d6f94a400ff116a91
ms.sourcegitcommit: 480046a53dfb6e6cf867e1920f8fb43dda9d3774
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2022
ms.locfileid: "64703683"
---
# <a name="use-the-frontline-worker-onboarding-wizard-to-get-your-frontline-workforce-up-and-running"></a>現場担当者オンボード ウィザードを使用して、現場の従業員を稼働させます

## <a name="overview"></a>概要

Microsoft 365 管理センターのフロントライン Worker オンボード ウィザードを使用すると、フロントライン ワーカーを組織に簡単にオンボードできます。 ウィザードを使用すると、現場の従業員に合わせて調整されたMicrosoft Teamsにエクスペリエンスをすばやくデプロイできます。 ウィザードを使用すると、組織内のフロントライン ワーカーのTeamsのパイロット展開を簡単に開始できます。

ウィザードは、フロントライン ワーカーのチームを設定し、各チーム メンバーにライセンスと [ポリシー パッケージ](manage-policy-packages.md) を割り当てます。 チームを最初から作成するか、チーム [テンプレート](get-started-with-teams-templates-in-the-admin-console.md)から作成し、ユーザーを追加してロールを割り当てることができます。 このロールによって、ウィザードが各ユーザーに割り当てるポリシー パッケージが決まります。

現在、ウィザードでは、実行するたびに 100 人のユーザーを追加できます。 間もなく 1 回の実行あたりのユーザー数を増やすことに取り組んでいます。 最新の更新プログラムについては、こちらを参照してください。

このウィザードは、少なくとも 1 つの [F ライセンス](https://www.microsoft.com/microsoft-365/enterprise/frontline)を持つすべての組織で使用できます。 ウィザードは、組織内のさまざまな場所またはサイトの現場の従業員にTeamsをロールアウトするために必要な回数だけ実行できます。

ウィザードを実行して現場の従業員をオンボードする方法の概要については、この短いビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWN6oh]

> [!NOTE]
> このウィザードを使用すると、現場の従業員をMicrosoft 365 管理センターを通じてTeamsにすばやくオンボードできます。 スクリプトを使用してTeamsを現場の従業員[にデプロイする方法については、「Frontline Workers の大規模なTeamsをプロビジョニングする方法](flw-scripted-deployment.md)」を参照してください。

> [!NOTE]
> ウィザードでは、 [秘密度ラベル](sensitivity-labels.md) はまだサポートされていません。 組織でチームを作成するために秘密度ラベルが必要な場合は、ウィザードがMicrosoft 365 管理センターに表示されません。

## <a name="run-the-wizard"></a>ウィザードを実行する

1. [Microsoft 365 管理センター](https://admin.microsoft.com/)の左側のナビゲーションで、[セットアップ] を選択 **します**。 **[アプリとメール**] セクションに移動し、[**現場の従業員を稼働** させる] で [表示] を選択 **します**。 ここでは、Microsoft 365 for frontline workersが提供する機能の詳細を確認できます。

    :::image type="content" source="media/flw-onboarding-wizard-get-started.png" alt-text="Microsoft 365 管理センターの Frontline Worker オンボード エクスペリエンスの詳細ページのスクリーンショット" lightbox="media/flw-onboarding-wizard-get-started.png":::

2. 準備ができたら、**概要** を選択してウィザードを実行します。

3. チームの名前を入力し、1 人以上のチーム所有者を追加して、プライバシー設定を選択します。 次に、チームをゼロから作成するか、チーム テンプレートから作成するかを選択します。 チーム テンプレートには、特定のビジネス ニーズまたはプロジェクトに合わせてチームを最適化する定義済みのチャネルとタブが用意されています。

    :::image type="content" source="media/flw-onboarding-wizard-set-up-team.png" alt-text="ウィザードの [チームのセットアップ] ページのスクリーンショット" lightbox="media/flw-onboarding-wizard-set-up-team.png":::

4. チームにユーザーを追加します。 グループを追加することもできます。 グループを追加する場合は、グループ自体ではなく、グループ内の各ユーザーにライセンスとポリシー パッケージが直接割り当てられていることに注意してください。

    :::image type="content" source="media/flw-onboarding-wizard-add-users.png" alt-text="チームにユーザーとグループを追加するウィザードの [ユーザーの追加] ページのスクリーンショット" lightbox="media/flw-onboarding-wizard-add-users.png":::

5. 各チーム メンバーに次のいずれかのロールを割り当てます。Frontline Worker、Frontline Manager、None。 
  
    :::image type="content" source="media/flw-onboarding-wizard-assign-roles.png" alt-text="チーム メンバーにロール、場所、ライセンスを割り当てるウィザードの [ジョブ ロールの割り当て] ページのスクリーンショット" lightbox="media/flw-onboarding-wizard-assign-roles.png":::

    Frontline Worker または Frontline Manager ロールを割り当てることで、そのユーザーはポリシー パッケージを受け取ります。 ポリシー パッケージは、ロールに合わせて調整されたTeamsでエクスペリエンスを作成します。 このエクスペリエンスには、正常な現場のワーカーとマネージャーのコミュニケーションとコラボレーションのための事前ピン留めされたアプリとポリシーが含まれます。

    次に、場所を選択し、Microsoft 365 F ライセンスを各チーム メンバーに割り当てます。 十分なライセンスがない場合は、[ **ライセンスの購入** ] を選択してライセンスを追加購入できます。  

6. ウィザードの完了後に状態メールを受け取るユーザーを選択します。 電子メールには、チームの作成&mdash;、チーム メンバーの追加、各チーム メンバーへのライセンスとポリシー パッケージの割り当てによって実行されるアクションに関する成功と失敗の情報が含まれています。 この情報を使用して、発生する可能性があるエラーのトラブルシューティングを行います。

    :::image type="content" source="media/flw-onboarding-wizard-email-recipients.png" alt-text="ウィザードの [状態メール受信者の追加] ページのスクリーンショット" lightbox="media/flw-onboarding-wizard-email-recipients.png":::

7. 選択内容を確認し、[ **確認**] を選択します。

    :::image type="content" source="media/flw-onboarding-wizard-review-team.png" alt-text="チームの設定を確認するウィザードの [チームの確認] ページのスクリーンショット" lightbox="media/flw-onboarding-wizard-review-team.png":::

    ウィザードによってチームが作成され、チーム メンバーにライセンスとポリシー パッケージが割り当てられます。 完了までに数分かかる場合があります。その後、選択した受信者が状態メールを受信します。

8. あなたは途中ですが、まだ完了していません。 次に、この記事の [ウィザードを実行した後の操作](#what-to-do-after-running-the-wizard) に関するセクションを確認します。

## <a name="what-to-do-after-running-the-wizard"></a>ウィザードの実行後の操作

ウィザードを実行した後は、次のことを行う必要があります。

- フロントラインのワーカーとマネージャーに、その従業員にライセンスTeams割り当てられていることを知らせます。
- 組織で共有デバイスを使用している場合は、Teamsがそれらのデバイスにインストールされていることを確認します。 チームに追加したユーザーには、Teamsを開くよう求めるウェルカム メールが届きます。
- 組織で "Bring your own device" (BYOD) モデルを使用している場合は、チームに追加した各ユーザーに、デバイスにTeamsをダウンロードしてインストールする必要があることを知らせます。 また、Teamsのダウンロードを求めるウェルカム メールも送信されます。

    > [!NOTE]
    > F1 ライセンスには電子メール アクセスが含まれていないため、F1 ライセンスを持つユーザーはウェルカム メールを受け取りません。  

フロントラインの従業員が初めてTeamsを開くと、チャットやチャネル、通話、タスク管理など、Teams内のすべてのカスタマイズされた初回実行エクスペリエンスが提供されます。

## <a name="related-articles"></a>関連記事

- [Teams でポリシー パッケージを管理する](manage-policy-packages.md)
- [Teams管理センターでチーム テンプレートを使用する](get-started-with-teams-templates-in-the-admin-console.md)
