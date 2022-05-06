---
title: Microsoft Teamsで People Manager チームを作成する
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: PowerShell スクリプトを使用して、各マネージャーのチームをチーム メンバーとして直接作成する方法について説明します。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cad2ed4fdbcec7f13f5b2e932d34395fe4b4c339
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628359"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Microsoft Teamsで People Manager チームを作成する


"空白のスレート" (チームまたはチャネルなし) で起動するのではなく、Microsoft Teamsをロールアウトする場合は、チームとチャネルの基本フレームワークを設定することを強くお勧めします。 これは、ユーザーが既存のチームでチャネルを作成する必要があるときに多数のチームを作成する "チームスプロール" を防ぐのに役立ちます。 適切に設計されたチームとチャネルの構造を開始するために、各マネージャーの直属のレポートをチーム メンバーとして使用して、第 1 および第 2 行の各ユーザー マネージャーのチームを作成する PowerShell スクリプトを作成しました。 これは "ポイントインタイム" スクリプトです (ユーザーが組織に追加または削除されたときに、チームやチャネルが自動的に更新されることはありません)。 しかし、最初からTeams構造に何らかの順序を付けるために使用できる貴重なツールです。 このスクリプトは、Azure ADを読み取り、マネージャーとその直属のレポートの一覧を取得します。 この一覧を使用して、ユーザー マネージャーごとに 1 つのチームを作成します。 

## <a name="how-to-use-the-powershell-script"></a>PowerShell スクリプトを使用する方法 

[まず、エクスポート マネージャーとそのダイレクト スクリプト](scripts/powershell-script-create-teams-from-managers-export-managers.md) ([Connect-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0) および [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell モジュールを既に実行していることを前提としています) を実行します。 *エクスポート マネージャーとそのダイレクト* スクリプトは、すべてのマネージャーをダイレクト レポートで一覧表示するタブ区切りファイル (ExportedManagerDirects.txt) を作成します。 

次に、 [新しいユーザー マネージャー チームの作成スクリプト](scripts/powershell-script-create-teams-from-managers-new-teams.md)を実行します。 このスクリプトは、ExportedManagerDirects.txt ファイルを読み取り、マネージャーごとのチームを作成し、そのマネージャーの直属部下をメンバーとして作成します。 マネージャーまたはダイレクトがTeamsに対して有効になっていない場合、スクリプトはこれらをスキップし、チームを作成しません。 (レポートを確認し、必要なユーザーのTeamsを有効にした後、スクリプトを再実行します。 このスクリプトでは、既にチームを作成しているマネージャーの 2 番目のチームは作成されません)。

各チームに対して、スクリプトによって General チャネルと "Just for fun" チャネルが作成されます。 

## <a name="best-practices"></a>ベスト プラクティス

- 各チームの全般チャネルに、組織の危機通信 Web サイトをタブとして追加するように各ユーザー マネージャーに依頼します。 

- 2020 年 3 月 8 日のブログ投稿「[Microsoft Teams + Power Platform を使用して危機の通信を調整する](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)」を参照して、新しい Crisis Communications アプリを確認してください。

## <a name="related-topics"></a>関連項目

[チームを編成するためのベスト プラクティス](best-practices-organizing.md)

[Teams で組織全体にわたるチームを作成する](create-an-org-wide-team.md)