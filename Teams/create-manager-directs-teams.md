---
title: Microsoft Teams で People Manager チームを作成する
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: PowerShell スクリプトを使用して、各マネージャーのチームをチーム メンバーとして作成する方法について説明します。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fa7c82ec584791107e5d269ee40bccba272d20b4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094413"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Microsoft Teams で People Manager チームを作成する


"空白のスレート" (チームまたはチャネルなし) で起動するのではなく、Microsoft Teams を展開する場合は、チームとチャネルの基本フレームワークを設定することを強く推奨します。 これにより、ユーザーが既存のチームでチャネルを作成する必要があるときに多数のチームを作成する "チームの広がり" を防ぐのに役立ちます。 よく設計されたチームとチャネル構造の使用を開始するために、各マネージャーの直販レポートをチーム メンバーとして使用して、最初と 2 行目の各担当者のチームを作成する PowerShell スクリプトを作成しました。 これは "ポイントインタイム" スクリプトです (ユーザーが組織に追加または削除されると、チームまたはチャネルは自動的に更新されません)。 ただし、最初から Teams の構造に何らかの注文を課すのに使用できる貴重なツールです。 このスクリプトは Azure アカウントを読AD、マネージャーとその直下のレポートの一覧を取得します。 このリストを使用して、ユーザー マネージャーごとに 1 つのチームを作成します。 

## <a name="how-to-use-the-powershell-script"></a>PowerShell スクリプトの使い方 

まず、 [エクスポート](scripts/powershell-script-create-teams-from-managers-export-managers.md) マネージャーとその直販スクリプトを実行します [(Connect-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0) および [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell モジュールを既に実行している場合)。 エクスポート *マネージャーとその直* 職スクリプトでは、すべてのマネージャーが直販レポートを含むタブ区切りファイル (ExportedManagerDirects.txt) を作成します。 

次に、新しい [People Manager チームの作成スクリプトを実行します](scripts/powershell-script-create-teams-from-managers-new-teams.md)。 このスクリプトは、ExportedManagerDirects.txt ファイルを読み取り、各マネージャーのチームを作成し、そのマネージャーの直下の部下をメンバーとして作成します。 マネージャーまたは直職が Teams に対して有効になっていない場合、スクリプトはそれらをスキップし、チームを作成しません。 (レポートを確認し、必要なユーザーに対して Teams を有効にした後、スクリプトを再実行します。 スクリプトでは、既にチームを作成しているマネージャーの 2 番目のチームは作成されません)。

チームごとに、スクリプトによって [全般] チャネルと [楽しみのために] チャネルが作成されます。 

## <a name="best-practices"></a>ベスト プラクティス

- 各メンバー マネージャーに、チームごとに [全般] チャネルにタブとして組織のクライシス コミュニケーション Web サイトを追加します。 

- 2020 年 3 月 8 日のブログ投稿「Microsoft Teams + Power Platform を使用してクライシス コミュニケーションを調整する」を参照して、新しいクライシス コミュニケーション アプリ [を確認してください](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)。

## <a name="related-topics"></a>関連項目

[チームを編成するためのベスト プラクティス](best-practices-organizing.md)

[Teams で組織全体にわたるチームを作成する](create-an-org-wide-team.md)