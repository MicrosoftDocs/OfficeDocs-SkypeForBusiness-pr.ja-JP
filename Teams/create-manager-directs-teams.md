---
title: Microsoft Teams で people manager teams を作成する
ms.reviewer: pbethi
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: PowerShell スクリプトを使用して、チームメンバーとしての各マネージャー用にチームを作成する方法について説明します。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb6cd6ed74bebd0cbd729b828c152b9f04d1fc1f
ms.sourcegitcommit: cfaae3ecbf853766de788b4825a86e04f68868ca
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2020
ms.locfileid: "42796225"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Microsoft Teams で people manager teams を作成する


"空のスレート" (チームまたはチャネルなし) で起動するのではなく、Microsoft Teams を展開する場合は、チームとチャネルの基本フレームワークを設定することを強くお勧めします。 これにより、ユーザーが既存のチームでチャネルを作成する必要があるときに、ユーザーが多数のチームを作成できるようになります。 適切に設計されたチームとチャネル構造を使って作業を開始するには、第1行と2行の people マネージャーのチームを作成して、各マネージャーの直属の部下をチームメンバーとして作成する PowerShell スクリプトを作成しました。 これは "ポイントインタイム" スクリプトです (ユーザーが組織に追加または削除されたときに、チームやチャネルが自動的に更新されることはありません)。 ただし、チームの構造について、最初からいくつかの注文を課すために使用できる便利なツールです。 このスクリプトは Azure AD を読み取り、マネージャーとその直属の部下の一覧を取得します。 このリストを使って、people マネージャーごとに1つのチームを作成します。 

## <a name="how-to-use-the-powershell-script"></a>PowerShell スクリプトの使い方 

まず、[エクスポートマネージャーとそのリダイレクトスクリプト](scripts/powershell-script-create-teams-from-managers-export-managers.md)を実行します (これは、 [AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0)と[connect-microsoft teams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps)の PowerShell モジュールを既に実行していることを前提としています)。 *エクスポートマネージャーとそのリダイレクト*スクリプトは、タブ区切りファイル (ExportedManagerDirects) を作成して、すべての管理者に直属の部下を一覧表示します。 

次に、[[新しい people manager teams の作成] スクリプト](scripts/powershell-script-create-teams-from-managers-new-teams.md)を実行します。 このスクリプトは、ExportedManagerDirects ファイルを読み取り、そのマネージャーの直属の部下としてメンバーとしてチームを作成します。 いずれかのマネージャーまたはダイレクトが Teams で有効になっていない場合は、スクリプトはスキップし、チームは作成されません。 (レポートを確認し、必要なユーザーのチームをオンにした後でスクリプトを再実行します。 スクリプトでは、チームが既に作成されている管理者に対して、2つ目のチームは作成されません。

各チームの場合、スクリプトによって一般的なチャネルと "楽しい" のチャネルが作成されます。 

## <a name="best-practices"></a>ベスト プラクティス

- 各メンバーマネージャーに、組織の危機管理 web サイトをタブとして各チームの [全般] チャネルに追加するように依頼します。 

- 次の「2020年3月8日のブログ投稿: [Microsoft Teams + Power Platform を使った危機通信の調整](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)」を参照して、新しい危機通信アプリを確認してください。

## <a name="related-topics"></a>関連項目

[チームを編成するためのベストプラクティス](best-practices-organizing.md)

[Teams で組織全体にわたるチームを作成する](create-an-org-wide-team.md)
