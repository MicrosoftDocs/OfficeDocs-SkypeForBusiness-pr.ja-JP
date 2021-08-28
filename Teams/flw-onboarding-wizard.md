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
description: Frontline Worker オンボード ウィザードを使用して、組織内のフロントライン ワーカーやマネージャーに合わせてカスタマイズされた Teams でエクスペリエンスをすばやくデプロイする方法について学習します。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: da44a5eb25e56a974214472782e424cda735b6dc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58636805"
---
# <a name="use-the-frontline-worker-onboarding-wizard-to-get-your-frontline-workforce-up-and-running"></a>Frontline Worker オンボード ウィザードを使用して、フロント ラインの従業員を稼働させます。

> [!NOTE]
> この記事では、まだリリースされていない機能について説明します。 近日公開予定です。 管理者は、メッセージ センター ([Microsoft 365 管理センター](https://portal.office.com/adminportal/home)) でこの機能のリリース日を確認できます。 Teams 機能の最新情報を入手するには、「[Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)」を参照してください。

## <a name="overview"></a>概要

フロント ライン ワーカーのオンボーディング ウィザードは、Microsoft 365 管理センターに対するフロントライン ワーカーのオンボードを簡略化します。 ウィザードを使用すると、最前線の従業員に合わせてMicrosoft Teamsエクスペリエンスをすばやくデプロイできます。 ウィザードを使用すると、組織内のフロントライン ワーカー向Teamsのパイロット 展開を簡単に開始できます。

ウィザードでは、フロントライン ワーカーのチームが設定され、各チーム メンバーにライセンスと [ポリシー](manage-policy-packages.md) パッケージが割り当てされます。 チームを最初から作成するか、チーム テンプレート[](get-started-with-teams-templates-in-the-admin-console.md)から作成し、ユーザーを追加してロールを割り当てることができます。 ロールによって、ウィザードが各ユーザーに割り当てるポリシー パッケージが決定されます。

ウィザードは、少なくとも 1 つの F ライセンスを持つすべてのMicrosoft 365使用できます。 組織全体の異なる場所またはサイトで、Teamsに展開する必要がある回数、ウィザードを実行できます。

> [!NOTE]
> このウィザードを使用すると、フロント ライン ワーカーをすばやくオンボードして、TeamsをMicrosoft 365 管理センター。 スクリプトを使用してフロントライン Teamsにデプロイする方法の詳細については[、「Frontline Worker](flw-scripted-deployment.md)の大規模な Teams をプロビジョニングする方法」を参照してください。

## <a name="run-the-wizard"></a>ウィザードを実行する

1. 左側のナビゲーションで、[セットアップ][をMicrosoft 365 管理センター](https://admin.microsoft.com/)選択 **します**。 [アプリと **メール] セクションに移動** し **、[Get your frontline workforce up and running]** の [表示] を **選択します**。 ここでは、フロントライン ワーカーが提供する機能Microsoft 365詳細を確認できます。

2. 準備ができたら、[開始] を **選択して** ウィザードを実行します。

3. チームの名前を入力し、プライバシー設定を選択して、1 人または複数のチーム所有者を追加します。 次に、最初からチームを作成するか、チーム テンプレートからチームを作成するかを選択します。 チーム テンプレートには定義済みのチャネルとタブが含まれています。このタブは、特定のビジネス 上の必要性やプロジェクトに合ってチームを最適化します。

4. ユーザーをチームに追加します。 グループを追加することもできます。 グループを追加する場合は、グループ自体ではなく、グループ内の各ユーザーにライセンスとポリシー パッケージが直接割り当てられるので、ご安心ください。

5. 各チーム メンバーに次のいずれかのロールを割り当てます。

    - Frontline worker
    - Frontline Manager
    - なし

    Frontline worker または Frontline Manager ロールを割り当てると、そのユーザーは自分のロールに合わせてカスタマイズされた Teamsエクスペリエンスを受け取る可能性があります。 これには、正常なフロントライン ワーカーとマネージャーのコミュニケーションとコラボレーションのための事前固定アプリとポリシーが含まれます。

    次に、各チーム Microsoft 365 F ライセンスを割り当てる。 十分なライセンスを持ってない場合は、[ライセンスの追加購入] を選択 **して、ライセンス** を追加購入できます。  

6. ウィザードの完了後にステータス メールを受け取るユーザーを選択します。 電子メールには、ウィザードがチームの作成、チーム メンバーの追加、および各チーム メンバーへのライセンスとポリシー パッケージの割り当てによって実行されたアクションに関する成功と失敗の情報 &mdash; が含まれています。 この情報を使用して、発生する可能性があるエラーのトラブルシューティングを行います。

7. 選択内容を確認し、[確認] を **選択します**。

    ウィザードによってチームが作成され、ライセンスとポリシー パッケージがチーム メンバーに割り当てされます。 完了まで数分かかる場合があります。その後、選択した受信者はステータス メールを受信します。

8. 途中ですが、まだ完了していません。 次に、この記事の [「ウィザードを実行した後の操作](#what-to-do-after-running-the-wizard) 」セクションを参照してください。

## <a name="what-to-do-after-running-the-wizard"></a>ウィザードの実行後の操作

ウィザードを実行した後は、次の点が重要です。

- フロントラインの従業員とマネージャーに、そのユーザーにライセンスが割り当てられているTeamsします。
- 共有デバイスを使用している場合は、それらのデバイスTeamsインストールされていることを確認します。 組織で "自分のデバイスを持ち込む" モデルを使用している場合は、フロントラインの従業員とマネージャーに、デバイスにデバイスをダウンロードしてインストールする必要Teams知らせる必要があります。

フロントラインの従業員が Teams を初めて開くと、Teams 内のすべてのチャットとチャネル、通話、タスク管理を含む、カスタマイズされた最初の実行エクスペリエンスが提供されます。

## <a name="related-articles"></a>関連記事

- [Teams でポリシー パッケージを管理する](manage-policy-packages.md)
- [管理センターでチーム テンプレートTeams使用する](get-started-with-teams-templates-in-the-admin-console.md)