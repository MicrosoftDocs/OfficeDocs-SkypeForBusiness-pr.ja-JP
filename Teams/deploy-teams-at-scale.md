---
title: Microsoft Teamsで現場のワーカーに大規模にチームをデプロイする
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
ms.openlocfilehash: 561eaf310201b99ada9cce4dde49746d58d77088
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2022
ms.locfileid: "66046026"
---
# <a name="deploy-teams-at-scale-for-frontline-workers-in-microsoft-teams"></a>Microsoft Teamsで現場のワーカーに大規模にチームをデプロイする

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
- 完了、状態、エラー (存在する場合) など、電子メールで通知を受け取ります。 展開するチームの各バッチの状態について、最大 5 人のユーザーに通知することができます。 チームの所有者とメンバーは、チームに追加されると自動的に通知されます。

## <a name="how-to-deploy-teams-at-scale"></a>大規模にチームを展開する方法

> [!NOTE]
> チームを展開する前に、すべてのチームの所有者がTeamsライセンスを持っていることを確認します。

一度に多数のチームをデプロイするには、次の手順に従います。

### <a name="step-1-prepare-your-csv-files"></a>手順 1: CSV ファイルを準備する

デプロイするチームのバッチごとに、次の 2 つの CSV ファイルを作成する必要があります。

- **作成するチームを定義する CSV ファイル**。 このファイルには、最初の列から始まる次の順序で、これらの必要な列が含まれている必要があります。

    |列名  |説明  |
    |---------|---------|
    |**チーム名**|チームの名前。|
    |**既存のチーム ID**|既存のチームにユーザーを追加または削除する場合は、チームのチーム ID を指定します。|
    |**可視 性**|チームがパブリック (組織内のすべてのユーザーが参加可能) かプライベート (ユーザーが参加するにはチーム所有者の承認が必要) かどうか。 オプションは **パブリック** と **プライベートです**。|
    |**チーム テンプレート ID**|事前構築済みテンプレートまたはカスタム テンプレートからチームを作成する場合は、チーム テンプレート ID を指定します。 事前構築済みのチーム テンプレートと ID の一覧については、[Teams管理センターの](get-started-with-teams-templates-in-the-admin-console.md)チーム テンプレートに関する概要を参照してください。 標準の既定のチーム テンプレートを使用する場合は、この空白のままにします。|

- **追加するユーザーを各チームにマップする CSV ファイル**。 このファイルには、最初の列から始まる次の順序で、これらの必要な列が含まれている必要があります。

    |列名  |説明  |
    |---------|---------|
    |**ユーザーの完全な名前**|ユーザーの表示名。|
    |**ユーザー UPN または ID**|ユーザーのユーザー プリンシパル名 (UPN) または ID。 たとえば、averyh@contoso.com。|
    |**チーム名**|チームの名前。|
    |**ActionType**|ユーザーをチームに追加するか、チームから削除するか。 オプションは **AddMember** と **RemoveMember です**。|
    |**所有者またはメンバー**|ユーザーがチーム所有者かチーム メンバーか。 オプションは **所有者** と **メンバーです**。|

#### <a name="examples"></a>例

次の例を使用して、CSV ファイルを作成します。 ここでは、ファイル、Teams.csv、Users.csvという名前を付けました。

**Teams.csv**

|チーム名|既存のチーム ID|可視 性|チーム テンプレート ID|
|---------|---------|---------|---------|
|Contoso Microsoft Store 1||公共|com.microsoft.teams.template.retailStore|
|Contoso Microsoft Store 2||公共|com.microsoft.teams.template.retailStore|
|Contoso Microsoft Store 3||公共|com.microsoft.teams.template.retailStore|
|Contoso Microsoft Store 4||公共|com.microsoft.teams.template.retailStore|
|Contoso Microsoft Store 5||公共|com.microsoft.teams.template.ManageAProject|
|Contoso Microsoft Store 6||公共|com.microsoft.teams.template.ManageAProject|
|Contoso Microsoft Store 7||公共||
|Contoso Microsoft Store 8||プライベート|com.microsoft.teams.template.OnboardEmployees|
|Contoso Microsoft Store 9||プライベート|com.microsoft.teams.template.OnboardEmployees|
|Contoso Microsoft Store 10||プライベート|com.microsoft.teams.template.OnboardEmployees|

**Users.csv**

|ユーザーの完全な名前 |ユーザー UPN または ID|チーム名|ActionType|所有者またはメンバー|
|---------|---------|---------|---------|---------|
|Avery Howard|averyh@contoso.com|Contoso Microsoft Store 1|AddMember|所有者|
|Casey Jensen|caseyj@contoso.com|Contoso Microsoft Store 2|AddMember|所有者|
|ジェシー Irwin|jessiei@contoso.com|Contoso Microsoft Store 3|AddMember|所有者|
|Manjeet Bhatia|manjeetb@contoso.com|Contoso Microsoft Store 4|AddMember|所有者|
|ミカメラ リー|mikaelal@contoso.com|Contoso Microsoft Store 5|AddMember|所有者|
|モルガン Conners|morganc@contoso.com|Contoso Microsoft Store 6|AddMember|メンバー|
|オスカーワード|oscarw@contoso.com|Contoso Microsoft Store 7|AddMember|メンバー|
|レネ・ペトニア|renep@contoso.com|Contoso Microsoft Store 8|AddMember|メンバー|
|シドニー マトロス|sydneym@contoso.com|Contoso Microsoft Store 9|AddMember|メンバー|
|紫色のマルチネス|violetm@contoso.com|Contoso Microsoft Store 10|AddMember|メンバー|

### <a name="step-2-deploy-your-teams"></a>手順 2: チームをデプロイする

CSV ファイルを作成したので、環境を設定してチームをデプロイする準備ができました。

コマンドレットを ```New-CsBatchTeamsDeployment``` 使用して、作成するチームのバッチを送信します。 バッチごとにオーケストレーション ID が生成されます。 その後、コマンドレットを ```Get-CsBatchTeamsDeployment``` 使用して、各バッチの進行状況と状態を追跡できます。

1. PowerShell バージョン 7 以降をインストールします。 詳細なガイダンスについては、「[Windowsへの PowerShell のインストール](/powershell/scripting/install/installing-powershell-on-windows)」を参照してください。
1. PowerShell を管理者モードで実行します。
1. 次の手順を実行して、以前にインストールした powerShell モジュールTeamsアンインストールします。

    ```powershell
    Uninstall-module -Name MicrosoftTeams -Force -Allversions
    ```

    エラー メッセージが表示された場合は、既に設定されています。 次の手順に進みます。
1. [Teams PowerShell モジュールの最新バージョンを](https://www.powershellgallery.com/packages/MicrosoftTeams)ダウンロードしてインストールします。

1. 次のコマンドを実行して、Teamsに接続します。

    ```powershell
    Connect-MicrosoftTeams
    ```

    メッセージが表示されたら、管理者の資格情報を使用してサイン インします。

1. 次のコマンドを実行して、Teams PowerShell モジュールのコマンドの一覧を取得します。

    ```powershell
    Get-Command -Module MicrosoftTeams
    ```

    そのことを ```New-CsBatchTeamsDeployment``` 確認し、 ```Get-CsBatchTeamsDeployment``` 一覧に表示します。

1. 次を実行して、チームのバッチをデプロイします。 このコマンドでは、CSV ファイルへのパスと、この展開について通知する最大 5 人の受信者の電子メール アドレスを指定します。

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "Your CSV file path" -UsersFilePath "Your CSV file path" -UsersToNotify "Email addresses" 
    ```

    次に例を示します。

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "C:\dscale\Teams.csv" -UsersFilePath "C:\dscale\Users.csv" -UsersToNotify "adminteams@contoso.com,adelev@contoso.com"
    ```

    受信者は、展開の状態に関する電子メール通知を受け取ります。 電子メールには、送信したバッチのオーケストレーション ID と、発生した可能性のあるエラーが含まれています。

1. 次を実行して、送信したバッチの状態を確認します。

    ```powershell
    Get-CsBatchTeamsDeploymentStatus -OrchestrationId "OrchestrationId"
    ```

## <a name="send-us-feedback"></a>フィードバックの送信

フィードバックをお寄せください。 使いやすさ、信頼性、パフォーマンス&mdash;は、すべて歓迎します。

オーケストレーション ID とエラー ファイルがある場合 [は、dscale@microsoft.com](mailto:dscale@microsoft.com) 電子メールで送信し、オーケストレーション ID とエラー ファイルを含めます。

## <a name="related-articles"></a>関連記事

- [Teams PowerShell の概要](teams-powershell-overview.md)
