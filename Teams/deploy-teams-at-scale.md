---
title: Microsoft Teams でフロントライン ワーカーの大規模なチームを展開する
author: LanaChin
ms.author: v-lanachin
ms.reviewer: rahuldey
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 組織内の最前線のワーカーに対して大規模にチームを展開する方法について説明します。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 655e79e70945419c446dab3d721334a1a70b0e9e
ms.sourcegitcommit: d54217d3c339fe02f83d86efe50dabe67528a14c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2022
ms.locfileid: "65947230"
---
# <a name="deploy-teams-at-scale-for-frontline-workers-in-microsoft-teams"></a>Microsoft Teams でフロントライン ワーカーの大規模なチームを展開する

> [!NOTE]
> この機能は現在プライベート プレビュー段階です。 プライベート プレビューに参加する場合は、 [dscale@microsoft.com](mailto:dscale@microsoft.com) にお問い合わせください。

## <a name="overview"></a>概要
 
組織には、フロントラインの従業員間のコミュニケーションとコラボレーションを促進するために使用する多くのチームが存在する場合があります。これらのチームは、さまざまな店舗、場所、ロールに分散されています。 現時点では、これらのチームとユーザーを大規模にデプロイ、セットアップ、管理するための簡単なソリューションはありません。

管理者が大規模にチームをデプロイおよび管理できるようにするソリューションを構築しています。

多数のチームを一度に作成および管理するために現在使用できる機能の概要と、近い将来の計画を次に示します。

||現在ご利用いただけます |2022 年後半  |
|---------|---------|---------|
|**バッチごとに作成できるチームの数**|最大 100 |最大 500|
|**チームごとに追加できるユーザーの数**|最大 25 個|最大 25 個|

大規模にチームを展開すると、次のことが可能になります。

- 事前構築済みテンプレートまたは独自のカスタム テンプレートを使用してチームを作成します。
- 所有者またはメンバーとしてチームにユーザーを追加します。
- 既存のチームにユーザーを追加または削除して、大規模なチームを管理します。
- 完了、状態、エラー (存在する場合) など、電子メールで通知を受け取ります。 チームの所有者とメンバーに通知されます。

## <a name="how-to-deploy-teams-at-scale"></a>大規模にチームを展開する方法

> [!NOTE]
> チームを展開する前に、すべてのチームの所有者が Teams ライセンスを持っていることを確認します。

一度に多数のチームをデプロイするには、次の手順に従います。

コマンドレットを ```New-CsBatchTeamsDeployment``` 使用して、作成するチームのバッチを送信します。 バッチごとにオーケストレーション ID が生成されます。 その後、コマンドレットを ```Get-CsBatchTeamsDeployment``` 使用して、各バッチの進行状況と状態を追跡できます。

1. PowerShell バージョン 7 以降をインストールします。 詳細なガイダンスについては、「 [Windows への PowerShell のインストール](/powershell/scripting/install/installing-powershell-on-windows)」を参照してください。
1. PowerShell を管理者モードで実行します。
1. 以前にインストールされた Teams PowerShell モジュールをアンインストールするには、次を実行します。

    ```powershell
    Uninstall-module -Name MicrosoftTeams -Force -Allversions
    ```

    エラー メッセージが表示された場合は、既に設定されています。 次の手順に進みます。
1. [Teams PowerShell モジュールの最新バージョンをダウンロードしてインストールします](https://www.powershellgallery.com/packages/MicrosoftTeams)。

1. Teams に接続するには、次を実行します。

    ```powershell
    Connect-MicrosoftTeams
    ```

    メッセージが表示されたら、管理者の資格情報を使用してサイン インします。

1. Teams PowerShell モジュールのコマンドの一覧を取得するには、次のコマンドを実行します。

    ```powershell
    Get-Command -Module MicrosoftTeams
    ```

    そのことを ```New-CsBatchTeamsDeployment``` 確認し、 ```Get-CsBatchTeamsDeployment``` 一覧に表示します。

1. 次を実行して、チームのバッチをデプロイします。 **UsersToNotify** パラメーターには、最大 5 つの電子メール アドレスを入力できます。

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "*Your file path*" -UsersFilePath "*Your file path*" -UsersToNotify *Email addresses* 
    ```

1. 次を実行して、送信したバッチの状態を確認します。

    ```powershell
    Get-CsBatchTeamsDeploymentStatus -OrchestrationId "OrchestrationId"
    ```

## <a name="send-us-feedback"></a>フィードバックの送信

フィードバックをお寄せください。 使いやすさ、信頼性、パフォーマンス&mdash;は、すべて歓迎します。

オーケストレーション ID とエラー ファイルがある場合 [は、dscale@microsoft.com](mailto:dscale@microsoft.com) 電子メールで送信し、オーケストレーション ID とエラー ファイルを含めます。

## <a name="related-articles"></a>関連記事

- [Teams PowerShell の概要](teams-powershell-overview.md)
