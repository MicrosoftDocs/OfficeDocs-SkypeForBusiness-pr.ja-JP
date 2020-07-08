---
title: Firstline Workers 用に規模に応じて Microsoft Teams をプロビジョニングする
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: keschm
description: Firstline Worker 用に Microsoft Teams を展開またはプロビジョニングするスクリプトの使用する際のガイダンス。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a57de3528ac9ef0f950c7034b3c6ee3860b53ea
ms.sourcegitcommit: ad82786076cc965e75b1ec5ffd4bc9bf75437340
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "45028173"
---
# <a name="how-to-provision-teams-at-scale-for-firstline-workers"></a>現場担当者向けにTeams 大規模にプロビジョニングする方法

Microsoft Teams に多数のユーザーをすばやく登録し、作業を効率化する必要がありますか? 次の手順を実行して、ID のプロビジョニング、Teams のプロビジョニング、関連するすべてのポリシーの割り当てをすばやく行い、エンド ユーザー エクスペリエンスを制御できます。

このチュートリアルでは、以下の操作を実行する方法を説明します。

- 多数のユーザーを作成します。
- 多数のチームを作成し、適切なチャネルを設定します。
- 規模に応じてライセンスを割り当てます。
- 適切な Teams メッセージング ポリシー、アプリ セットアップ ポリシー、アプリ アクセス許可ポリシーを作成します。
- ユーザーにこれらのポリシーを規模に応じて適用します。
- 指定されたチームに多数のユーザーを割り当てます。

> [!NOTE]
> この情報を確認して、支援が必要であったり、質問があったりする場合は、[**こちらをクリック**](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRyMDv-1voW9MqL7zkQ11DzBUREZaU1E0WEk5T0NYS0NDSkFMSDROUUdYMC4u)して、ホワイト グローブ サポートにアクセスしてください。

## <a name="prerequisites"></a>前提条件

[この場所](https://aka.ms/flwteamsscale)から資産をダウンロードします。

> [!IMPORTANT]
> 上記のリンクに掲載されているスクリプトは、Microsoft が現状のまま提供しているもので、個別のニーズに合わせて変更する必要があります。

## <a name="technical-requirements"></a>技術的要件

- テナントには、Microsoft Teams を含む適切な数の使用可能なライセンスが必要です。 これらのライセンスをまだお持ちでない場合は、無料試用版のサブスクリプションについて、[Teams Exploratory](teams-exploratory.md) をご確認ください。
- これらの手順を実行するユーザーには、Azure AD で、グローバル管理者、ユーザー管理者、Teams サービス管理者の役割が割り当てられている必要があります。
- ユーザーには、ローカル コンピューターにソフトウェアをインストールして構成する権限が必要です。

## <a name="step-by-step-process-overview"></a>手順を追ったプロセスの概要

1. **環境を設定する**
    1. サンプルの PowerShell スクリプトとドキュメントが含まれている GitHub レポジトリからダウンロードする
    1. ローカル環境を構成する
    1. 資格情報を設定する
    1. PowerShell モジュールと環境変数を構成する
1. **チームを作成して設定する**
    1. チームを作成する
    1. チームを作成する手順
    1. チームのチャネルを作成する
1. **チームのポリシーを作成する**
    1. チームのメッセージング ポリシーを作成する
    1. Teams アプリのセットアップ ポリシーを作成する
    1. Teams アプリのアクセス許可ポリシーを作成する
1. **ユーザーとセキュリティ グループ**
    1. ユーザーとセキュリティ グループを作成する
    1. グループベースのライセンスを通じてユーザーにライセンスを割り当てる
1. **ユーザーとポリシーを割り当てる**
    1. チームにユーザーを割り当てる
    1. ユーザーにチーム ポリシーを割り当てる
    1. オプション: グループ メンバーシップの種類の変換
1. **テストと検証**
    1. テスト ユーザーで Teams にログインする
    1. エラーをチェックする
    1. エラー処理
1. **参照情報**

## <a name="set-up-your-environment"></a>環境を設定する

次の手順で、環境を設定できます。

### <a name="download-from-the-github-repository-containing-sample-powershell-scripts-and-documentation"></a>サンプルの PowerShell スクリプトとドキュメントが含まれている GitHub レポジトリからダウンロードする

続行する前に、[この場所](https://aka.ms/flwteamsscale)からスクリプトをダウンロードする必要があります。

### <a name="configure-the-local-environment"></a>ローカル環境を構成する

ローカル環境変数を設定すると、ここで参照するスクリプトを相対パスを使用して実行できます。 rootPath は、このリポジトリのクローンを作成した場所のルートであり、tenantName は**yourTenant.onmicrosoft.com** の形式です (https は含めません)。

1. PowerShell セッションを開き、複製された git リポジトリ内の [scripts] フォルダーに移動します。
1. 次のスクリプトを実行します。.\SetConfig.ps1 -tenantName [your tenant name] -rootPath "full path to the root of the git repo"。

例: .\SetConfig.ps1 -tenantName contoso.onmicrosoft.com -rootPath "C:\data\source\FLWTeamsScale"

### <a name="setup-credentials"></a>資格情報を設定する

> [!IMPORTANT]
> これらのスクリプトでの資格情報の管理方法は、使用環境に適していない場合があります。要件を満たすために簡単に変更することができます。 会社の基準と慣行に常に準拠して、サービス アカウントと管理されている ID をセキュリティで保護します。

このスクリプトは、$ENV:LOCALAPPDATA\keys (AppData\Local フォルダー) 内に xml ファイルとして格納されている資格情報を使用します。 **BulkAddFunctions.psm1** モジュールのヘルパー関数 **Set-Creds** を呼び出して、これらのスクリプトの実行に使用する資格情報を設定する必要があります。 この手法により、ローカル ストアで資格情報を維持しながら、さまざまなサービス エンドポイントすべてに対して認証を行う必要がなくなります。 各スクリプト内から、適切な資格情報が **Get-Creds** ヘルパー関数で読み取られ、それらの認証情報はさまざまなサービスへの接続に使用されます。

**Set-Creds** を呼び出すと、$ENV:LOCALAPPDATAkeys に書き込まれる XML ファイル名を指定するよう求めるメッセージが表示されます。 サービスごとに資格情報が異なる場合があります。 たとえば、Microsoft Teams、AzureAD、MSonline に異なる資格情報がある場合、**Set-Creds** を複数回実行して、各資格情報ファイルを独自の意味のある名前を付けて保存できます。

例: Set-Creds msol-cred.xml Set-Creds azuread-cred.xml Set-Creds teams-cred.xml

スクリプト **SetCreds.ps1** を実行して、資格情報を保存します。 "操作 "Export-Clixml" の実行中です..." というメッセージが表示されます。承認するには 'Y' を入力します。

> [!NOTE]
> 資格情報に使用されるアカウントでは、多要素認証 (MFA) を要求することはできません。

次に、さまざまなスクリプトが保存された資格情報を使用して認証する方法の例を示します。

```azurepowershell
# Connect to MicrosoftTeams
$teams_cred = Get-Creds teams-cred.xml
Connect-MicrosoftTeams -Credential $teams_cred
```

### <a name="configure-powershell-modules-and-environmental-variables"></a>PowerShell のモジュールと環境変数を構成する

Azure AD、MSAL、MSCloudUtils、MicrosoftTeams などのいくつかの PowerShell モジュールをインストールして接続する必要があります。

1. リポジトリの [scripts] フォルダーで **ConfigurePowerShellModules.ps1** を見つけます。
1. PowerShell から、**ConfigurePowerShellModules.ps1** スクリプトを実行します。

## <a name="create-and-set-up-teams"></a>チームを作成して設定する

Firstline Worker と通信して共同作業を行うには、最初に一連のチームを確立し、これらのチームに標準チャネルを追加する必要があります。これについては、次に説明します。

### <a name="create-teams"></a>チームを作成する

チームは、組織内のユーザー、コンテンツ、ツールの集合です。 ほとんどの Firstline Worker 中心の組織では、チームを実際の場所に固定するのがベスト プラクティスです。 たとえば、次の各チームがあります。

- ストア
- 配布センター
- 製造工場
- 病院
- 食品店

*ベスト プラクティス ディスカッション*: チームを設計するときは、[Teams の制限と仕様](limits-specifications-teams.md)に留意することが重要です。 小規模な組織では、組織全体のチームを使用してコミュニケーションを合理化し、物理的な場所の構造を補完できます。 構造化された物理的な場所のチームの命名規則により、他のユーザーは、複数チームに対して同時にクロス投稿を使って、社内コミュニケーションを容易に行うことができます。 たとえば、名前に US が含まれるすべてのチームを検索してクロス投稿し、米国のすべての場所を対象にすることができます。 クロス投稿の詳細については、[こちら](https://support.office.com/article/cross-post-a-channel-conversation-in-teams-9c1252a3-67ef-498e-a7c1-dd7147b3d295)をご覧ください。

#### <a name="steps-to-create-teams"></a>チームを作成する手順

1. リポジトリの [data] フォルダーで、**TeamsInformation.csv** ファイルを見つけます。
1. 組織固有の情報を使用して、**TeamsInformation.csv** ファイル内の情報を更新します。 上記のベスト プラクティスに留意してください。
1. **CreateTeams. ps1** スクリプトを見つけます。
1. PowerShell から **CreateTeams.ps1** スクリプトを実行します。

### <a name="create-channels-for-teams"></a>チームのチャネルを作成する

チャネルは、特定のトピック、プロジェクト、分野などごとに会話を整理するチーム内の専用セクションです。 すべてのチームは自動的に全般チャネルを取得しますが、そこからビジネス ニーズに応じて構造をカスタマイズできます。 たとえば、チャネル構造には以下が追加されます。

- **製造** - 安全、ライン 1、ライン 2、社内コミュニケーション、トレーニング
- **食料品** - パン屋、農産物、肉、社内コミュニケーション、トレーニング
- **医療** - 看護師、医師、重症管理室 1、重症管理室 2
- **サービス業** - フロント デスク、メンテナンス、ハウスキーピング、ベルボーイ、社内コミュニケーション、トレーニング
- **小売店** - 店頭、バックヤード、社内コミュニケーション、トレーニング

> [!NOTE]
> チャネルをセキュリティの境界と見なすべきではありません。 これらは、共同作業を行うために、作業者を整理する手段です。

*ベスト プラクティス ディスカッション*: チャネル構造を設計するとき、特に多数のユーザーを登録する必要がある場合は、シンプルなものにすることが重要です。 トレーニングの必要性を最小限に抑えるために、あらゆる状況、役割、またはトピックのチャネルを作成しようとする衝動を抑えてください。 最大 3 ～ 5 チャネルから開始してください。 必要に応じて、追加のチャネルを簡単に作成できます。 実際には、全般チャネルだけを使用しても問題ありません。

#### <a name="steps-to-create-channels-for-teams"></a>チームのチャネルを作成する手順

1. リポジトリの [scripts] フォルダーで、**TeamsChannels.csv** ファイルを見つけます。
1. 組織固有の情報を使用して、**Teams Information.csv** ファイルを更新します。 上記のベスト プラクティスに留意してください。
1. リポジトリの [scripts] フォルダーで、**CreateTeamsChannels.ps1** スクリプトを見つけます。
1. PowerShell から **CreateTeamsChannels.ps1** スクリプトを実行します。

## <a name="create-teams-policies"></a>チーム ポリシーを作成する

管理者は、Microsoft Teams でチーム ポリシーを使用して、組織内のユーザーが閲覧できる内容や実行できる操作を制御できます。 たとえば、多数のユーザーを登録するとき、エンド ユーザー エクスペリエンスを簡素化するために、デスクトップまたは Web ブラウザーの左のレールにピン留めするアプリケーション、またはモバイル デバイスの下部バーにピン留めするアプリケーションを制御できます。 これらのポリシーには PowerShell で作成できるものと、Teams 管理コンソールで手動で作成する必要があるものがあります。

*ベスト プラクティス ディスカッション*: 次の各ポリシーについて、実際には 2 つのポリシーを作成することを選択しています。1 つは Firstline Workers 用で、もう 1 つは Firstline Manager 用です。 必要な数だけ作成できます。 ほとんどのお客様にとって、最初に各グループに同じ設定を適用した場合でも、2 つから開始することをお勧めします。 Teams での経験が増えるにつれて、彼らの経験をさらに差別化することを選択できます。すでに作成されている 2 つの個別のポリシーがあると、それがさらに簡単になります。

### <a name="create-teams-message-policies"></a>チームのメッセージング ポリシーを作成する

メッセージング ポリシーを使用して、Microsoft Teams のユーザーが、チャットおよびチャネルのどのメッセージング機能を使用できるかを制御します。

*ベスト プラクティス ディスカッション*: 自動的に作成される既定のグローバル ポリシーを使用できますが、Firstline Managers と Firstline Worker にロックダウンされたシンプルで差別化されたエクスペリエンスを提供するために、以下の手順を使用してカスタム ポリシーを作成することを選択しました。

#### <a name="steps-to-create-teams-message-policies"></a>チームのメッセージング ポリシーを作成する手順

1. リポジトリの [scripts] フォルダーで、**TeamsMessagingPolicies.csv** ファイルを見つけます。
1. 組織固有の情報を使用して、**TeamsMessagingPolicies.csv** ファイルを更新します。 さまざまなオプションのいくつかの詳細については、[こちら](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams#messaging-policy-settings)をご覧ください。
1. リポジトリの [scripts] フォルダーで、**CreateTeamsMessagePolicies.ps1** スクリプトを見つけます。
1. PowerShell から **CreateTeamsMessagePolicies.ps1** スクリプトを実行します。

### <a name="create-teams-app-setup-policies"></a>Teams アプリのセットアップ ポリシーを作成する

管理者は、アプリ セットアップポリシーを使用して、次の操作を行うことができます。

- Teams をカスタマイズして、ユーザーにとって最も重要なアプリを強調表示します。 ピン留めするアプリを選択し、表示する順序を設定します。 アプリをピン留めすると、サード パーティ製のアプリや組織内の開発者が作成したアプリなど、組織内のユーザーが必要とするアプリを提示できます。
- ユーザーがアプリを Teams にピン留めできるかどうかを制御します。

アプリは、アプリ バーにピン留めされます。 このバーは、Teams デスクトップ クライアントの横側および Teams モバイル クライアント (iOS および Android) の下側に表示されます。

|Teams デスクトップ クライアント  |         |Teams モバイル クライアント  |
|---------|---------|---------|
|![*アプリ* バーにアプリがピン留めされた Teams デスクトップ クライアントのスクリーンショット。](media/FLW-Teams-Desktop-Client.png)         |         |![*下部の* バーにアプリがピン留めされた Teams デスクトップ クライアントのスクリーンショット。](media/FLW-Teams-Mobile-Client.png) |

*ベスト プラクティス ディスカッション*: アプリの設定ポリシーは、Microsoft Teams 管理センターで管理します。 PowerShell を使用して作成することはできません。 グローバル (組織全体の既定) ポリシーを使用することも、カスタム ポリシーを作成してユーザーに割り当てることもできます。 カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に割り当てられます。 ここでは、Firstline Workers と Firstline Managers に 2 つの新しいポリシーを作成し、多数のユーザーの同時登録を容易にする、よりシンプルで合理的なエクスペリエンスを提供します。 ビジネスニーズに合わせて、エクスペリエンスをカスタマイズすることができます。

#### <a name="create-the-firstline-manager-app-setup-policy"></a>Firstline Manager アプリのセットアップポリシーを作成する

ビジネス ニーズに合わせて、次の設定をカスタマイズすることができます。 ベスト プラクティスに基づいて、大規模な新規ユーザーの登録を容易にするために、いくつかの推奨オプションを選択しました。 詳細については、[こちら](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy)をクリックしてください。

1. Microsoft Teams 管理センターの左側のナビゲーションで、 **[Teams アプリ]** > **[ポリシーの設定]** の順に移動します。
2.  **[追加]** をクリックします。  
3. ポリシーの名前と説明を入力します。 例: **Firstline Manager アプリのセットアップポリシー**。
![Firstline Manager アプリのセットアップポリシーの画像。](media/FLW-FLM-App-Setup-Policy.png)

4. **[カスタム アプリのアップロード]** をオフにします。
5. **[ユーザーのピン留めを許可]** をオフにします。
![ユーザーのピン留めを許可の切り替えの画像。](media/FLW-Allow-User-Pinning.png)

6. 一覧表示されていない場合は、**Shifts** アプリを追加します。 **Shifts** の詳細については、[ここ](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)をクリックしてください。
![[追加] ボタンの横に Shifts アプリが表示されているピン留めされたアプリ画面を追加します。](media/FLW-Add-Pinned-Apps.png)

7. 通話が表示されている場合は削除します。 注: この機能を削除しても、ユーザーに対して無効になることはありませんが、アプリ バーに表示されないので、エンド ユーザー エクスペリエンスが簡素化されます。
8. アプリを次の順序で配置して、Teams アプリ バーでの順序を指定し、 **[保存]** をクリックします。
    1. アクティビティ
    1. チャット
    1. Teams
    1. カレンダー
    1. ![マネージャー アプリ リストのスクリーンショットを順番に](media/FLW-Manager-Pinned-Apps.png)シフトします。

#### <a name="create-the-firstline-worker-app-setup-policy"></a>Firstline Worker アプリのセットアップ ポリシーを作成する

ビジネス ニーズに合わせて、次の設定をカスタマイズすることができます。 ベスト プラクティスに基づいて、大規模な新規ユーザーの登録を容易にするために、いくつかの推奨オプションを選択しました。 詳細については、[こちら](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy)をクリックしてください。

1. Microsoft Teams 管理センターの左側のナビゲーションで、 **[Teams アプリ]** > **[ポリシーの設定]** の順に移動します。
2.  **[追加]** をクリックします。
3. ポリシーの名前と説明を入力します。 例: **Firstline Worker アプリのセットアップポリシー**。
![Firstline Worker アプリのセットアップポリシーの画像。](media/FLW-FLW-App-Setup-Policy.png)

4. **[カスタム アプリのアップロード]** をオフにします。
5. **[ユーザーのピン留めを許可]** をオフにします。
![ユーザーのピン留めを許可の切り替えの画像。](media/FLW-Allow-User-Pinning.png)

6. 一覧表示されていない場合は、**Shifts** アプリを追加します。 **Shifts** の詳細については、ここをクリックしてください。
![[追加] ボタンの横に Shifts アプリが表示されているピン留めされたアプリ画面を追加します。](media/FLW-Add-Pinned-Apps.png)

7. 会議と通話が表示されている場合は削除します。 注: これらの機能を削除しても、ユーザーに対して無効になることはありませんが、アプリ バーに表示されないので、エンド ユーザー エクスペリエンスが簡素化されます。
8. アプリを次の順序で配置して、Teams アプリ バーでの順序を指定し、 **[保存]** をクリックします。
    1. アクティビティ
    1. チャット
    1. Teams
    1. ![ワーカー アプリ リストのスクリーンショットを順番に](media/FLW-Worker-Pinned-Apps.png)シフトします。

### <a name="create-teams-app-permission-policies"></a>Teams アプリのアクセス許可ポリシーを作成する

管理者であれば、アプリのアクセス許可ポリシーを使用して、組織の Microsoft Teams ユーザーが使用できるアプリを制御できます。 すべてのアプリ、または Microsoft、第三者、お客様の組織によって公開されている特定のアプリを許可またはブロックすることができます。 アプリをブロックした場合、ポリシーを持つユーザーは、Teams アプリ ストアからアプリをインストールできません。 これらのポリシーを管理するには、グローバル管理者または Teams サービス管理者である必要があります。

*ベスト プラクティス ディスカッション*: アプリの設定ポリシーは、Microsoft Teams 管理センターで管理します。 PowerShell を使用して作成することはできません。 グローバル (組織全体の既定) ポリシーを使用することも、カスタム ポリシーを作成してユーザーに割り当てることもできます。 カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。 ここでは、Firstline Workers と Firstline Managers に 2 つの新しいポリシーを作成し、多数のユーザーの同時登録を容易にする、より安全で合理的なエクスペリエンスを提供します。 もちろん、ビジネスニーズに合わせて、エクスペリエンスをカスタマイズすることができます。

#### <a name="create-the-firstline-manager-app-permission-policy"></a>Firstline Manager アプリのアクセス許可ポリシーを作成する

ビジネス ニーズに合わせて、次の設定をカスタマイズすることができます。 これらは、ベスト プラクティスに基づいて、大規模な新規ユーザーの登録を容易にするためのいくつかの推奨オプションです。 詳細については、[こちら](teams-app-permission-policies.md)をクリックしてください。

1. Microsoft Teams 管理センターの左側のナビゲーションで、 **[Teams アプリ]** > **[アクセス許可ポリシー]** の順に移動します。
2.  **[追加]** をクリックします。
![Microsoft、サード パーティ、テナントのアプリのセクションを含む、[アプリのアクセス許可ポリシーの追加] ページを示します。](media/FLW-add-app-permission-policy.png)

3. ポリシーの名前と説明を入力します。 例: Firstline Manager アプリのアクセス許可ポリシー。
4. [Microsoft アプリ] の下で、**[すべてのアプリを許可]** を選択します。
5. [サード パーティ製のアプリ] の下で、[**すべてのアプリを許可**] を選択します。
6. [テナント アプリ] の下で、**[すべてのアプリを許可]** を選択します。
7.  **[保存]** をクリックします。

#### <a name="create-the-firstline-worker-app-permission-policy"></a>Firstline Worker アプリのアクセス許可ポリシーを作成する

ビジネス ニーズに合わせて、次の設定をカスタマイズすることができます。 これらは、ベスト プラクティスに基づいて、大規模な新規ユーザーの登録を容易にするためのいくつかの推奨オプションです。 詳細については、[こちら](teams-app-permission-policies.md)をクリックしてください。

1. Microsoft Teams 管理センターの左側のナビゲーションで、 **[Teams アプリ]** > **[アクセス許可ポリシー]** の順に移動します。
2.  **[追加]** をクリックします。
![Microsoft、サード パーティ、テナントのアプリのセクションを含む、[アプリのアクセス許可ポリシーの追加] ページを示します。](media/FLW-add-app-permission-policy.png)

3. ポリシーの名前と説明を入力します。 例: Firstline Worker アプリのアクセス許可ポリシー。
4. [Microsoft アプリ] の下で、**[すべてのアプリを許可]** を選択します。
5. [サード パーティ製のアプリ] の下で、**[すべてのアプリをブロック]** を選択します。
6. [テナント アプリ] の下で、**[すべてのアプリを許可]** を選択します。
7.  **[保存]** をクリックします。

## <a name="users-and-security-groups"></a>ユーザーとセキュリティ グループ

### <a name="create-users-and-security-groups"></a>ユーザーとセキュリティ グループを作成する

Teams で大量のユーザーと共同作業するには、最初に Azure AD でユーザーを作成する必要があります。 多数のユーザーをプロビジョニングする方法はたくさんありますが、以下を強調しておきます。

- これらのユーザーが、次の人事システムのいずれかに既に存在している場合は、次のリンクを使用してユーザーのプロビジョニングを設定します。
  - SAP SuccessFactors - [チュートリアル: SAP SuccessFactors を Active Directory ユーザー プロビジョニングに構成します](https://docs.microsoft.com/azure/active-directory/saas-apps/sap-successfactors-inbound-provisioning-tutorial)。
  - Workday - [チュートリアル: Workday を自動ユーザー プロビジョニング用に構成します](https://docs.microsoft.com/azure/active-directory/saas-apps/workday-inbound-tutorial)。
- 他のシステムにユーザー情報がある場合は、次の手順に進みます。

これらのユーザーをより効果的に大規模に管理するには、Firstline Workers と Firstline Managers の 2 つのセキュリティ グループを作成し、次の手順に従って、これらのユーザーをセキュリティ グループに直接プロビジョニングする必要があります。

1. リポジトリの [scripts] フォルダーで、**Users.csv** ファイルを見つけます。
1. 組織固有の情報を使用して、**Users.csv** ファイルを更新します。
    1. 既定で、提供されるスクリプトは、初回ログイン時に変更する必要のある一時的なパスワードを持つユーザーを作成します。 既定のパスワードを使用しない場合は、**CreateUsers.ps1** スクリプトを編集して要件に合わせます。
    1. SecurityGroup フィールドを更新して、前に作成した適切な名前を反映させます。
1. リポジトリの [scripts] フォルダーで、**SecurityGroups.csv** ファイルを見つけます。
1. 組織固有のセキュリティ グループ情報を使用して、**SecurityGroups.csv** ファイルを更新します。
    1. **MessagePolicy**、**AppPermissionPolicy**、**AppSetupPolicy** フィールドを更新して、前に作成した適切なポリシーにマップしてください。
    1. **LicensePlan** フィールドを更新して、これらのユーザーに付与する予定のライセンスを反映してください。 製品名とサービス プラン識別子の詳細については、[こちら](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)のドキュメントをご覧ください。
1. PowerShell から、資産の **CreateUsers.ps1** スクリプトを実行します。

### <a name="assign-licensing-to-users-via-group-based-licensing"></a>グループベースのライセンスを通じてユーザーにライセンスを割り当てる

Microsoft 365、Office 365、Enterprise Mobility + Security、Dynamics 365 などの Microsoft 有料クラウドサービス、およびその他の同様の製品にはライセンスが必要です。 これらのライセンスは、これらのサービスにアクセスする必要がある各ユーザーに割り当てられます。 ライセンスを管理するために、管理者は、管理ポータル (Office または Azure) と PowerShell コマンドレットのいずれかを使用します。 Azure Active Directory (Azure AD) は、すべての Microsoft クラウド サービスの ID 管理をサポートする基盤となるインフラストラクチャです。 Azure AD には、ユーザーのライセンスの割り当て状態に関する情報が格納されます。

規模に応じてライセンスを有効にするために、Azure AD にはグループベースのライセンスが含まれています。このため、この記事の前半でセキュリティ グループを作成しました。 1 つ以上の製品ライセンスをグループに割り当てることができます。 Azure AD では、グループのメンバー全員にライセンスが割り当てられていることを確認します。 グループに参加する新しいメンバー全員に、適切なライセンスが割り当てられます。 グループを脱退するメンバーからライセンスが削除されます。 このライセンス管理により、PowerShell を介してライセンス管理を自動化し、組織および部門構造の変更をユーザーごとに反映する必要がなくなります。

## <a name="assign-users-and-policies"></a>ユーザーとポリシーを割り当てる

### <a name="assign-users-to-teams"></a>チームにユーザーを割り当てる

ユーザーを作成してチームを作成したので、今度はすべてのユーザーを適切なチームに配置します。

1. レポジトリの [data] フォルダーで、**Users.csv** ファイルを見つけて、このファイルのチームに正確にマップしてください。
1. PowerShell から、レポジトリの [scripts] フォルダーで、**AssignPoliciestoUsers.ps1** スクリプトを実行します。

### <a name="assign-teams-policies-to-users"></a>ユーザーにチーム ポリシーを割り当てる

Teams でユーザー エクスペリエンスを変更するためのユーザーとポリシーを作成したので、次に、それらのポリシーを正しいユーザーに割り当てます。

1. レポジトリの [data] フォルダーで、**SecurityGroups.csv** ファイルを見つけて、グループにポリシーを正確にマップしてください。
1. PowerShell から、レポジトリの [data] フォルダーで、**AssignPoliciestoUsers.ps1** スクリプトを実行します。

### <a name="optional-convert-group-membership-type"></a>オプション: グループ メンバーシップの種類の変換

> [!NOTE]
> この手順は、Azure AD P1 以上のユーザーが対象です。

Azure AD P1 以上のライセンスを取得した場合、割り当て済みのメンバーシップを使用する代わりに動的グループ メンバーシップを使用することができます。 チームを作成したスクリプトにより、メンバーシップの種類が「割り当て済み」の Office グループも作成されています。そのメンバーは明示的に追加する必要があります。

動的メンバーシップーを使用すると、ユーザーがチームのメンバーであるかどうかを判断するためのルールが記述されます。

> [!NOTE]
> このスクリプトを実行すると、グループの現在のメンバーシップが削除されます (所有者を除く)。メンバーシップ同期ジョブが実行されると新しいメンバーが追加されます。

1. リポジトリの [data] フォルダーで、**migrateGroups.csv** ファイルを見つけます。
1. 移行先のグループを使用して、CSV ファイル **migrateGroups.csv** を、動的メンバーシップのルールと共に更新します。
1. リポジトリの [scripts] フォルダーで、**ConvertGroupMembershipType.ps1** ファイルを見つけます。
1. PowerShell から、スクリプト **ConvertGroupMembershipType.ps1** を実行します。

## <a name="test-and-validate"></a>テストと検証

### <a name="login-to-teams-with-a-test-user"></a>テスト ユーザーで Teams にログインする

すべての手順を完了したので、完了した作業を確認します。

1. 作成されたユーザーには、CreateUsers.ps1 内の初期パスワードが設定されます。これは、最初のログイン時に変更する必要があります。
1. Teams のルックアンドフィールが期待どおりであることを確認します。 そうでない場合、**[チームポリシーを作成する]** と **[ユーザーにチーム ポリシーを割り当てる]** のセクションを確認してください。
1. ユーザーが正しいチームに属していることを確認します。 そうでない場合、**[ユーザーを作成し設定する]** と **[チームにユーザーを割り当てる]** のセクションを確認してください。

> [!NOTE]
> Firstline の従業員のプロビジョニングが、ID とアクセスの管理チームによって管理されている場合は、従業員の資格情報を提供するために、管理チームのプロセスに従う必要があります。

### <a name="check-for-errors"></a>エラーをチェックする

以前のスクリプトを実行したときに、リポジトリのコピーのログ フォルダーにある .csv ファイルにエラーまたは例外が書き込まれました。 このファイルは、発生する可能性がある問題を調査するために使用できます。

例外の例としては、テナントに既に存在するチームを作成しようとした場合があります。

1. [**Logs**] フォルダーを見つけ、それに含まれている .csv ファイルを確認します。 例外がない場合は、ここに例外ファイルが見つからない可能性があります。

### <a name="error-handling"></a>エラー処理

これらのスクリプトのサンプルでは、最小限のエラー処理が実装されています。 try ブロックまたは catch ブロックがあります。トリガーされた場合、catch ブロック内の変数にエラーを格納します。 追加のエラー処理は、お客様の意向に従って実装してください。

## <a name="further-reading"></a>参考資料

- [新しいチーム チャネル (Powershell)](https://docs.microsoft.com/powershell/module/teams/new-teamchannel?view=teams-ps)
- [新しい Teams メッセージング ポリシー (Powershell)](https://docs.microsoft.com/powershell/module/skype/new-csteamsmessagingpolicy?view=skype-ps)
- [Microsoft Teams でユーザーにライセンスを割り当てる](assign-policies.md#install-and-connect-to-the-microsoft-teams-powershell-module)
- [Office 365 PowerShell を使用してライセンスやユーザー アカウントを割り当てる](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)
