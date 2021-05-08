---
title: Microsoft Teams で People Manager チームを作成する
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


"空白のスレート" (チームやチャネルなし) で起動するのではなく、Microsoft Teams を展開する場合は、チームとチャネルの基本フレームワークを設定することを強く推奨します。 これは、ユーザーが既存のチームでチャネルを作成する必要があるときに多数のチームを作成する "チームの広がり" を防ぐのに役立ちます。 うまく設計されたチームとチャネルの構造を使い始めるのに役立つ PowerShell スクリプトを作成しました。このスクリプトでは、各マネージャーの直下の部下をチーム メンバーとして、1 番目と 2 番目の各担当者マネージャーのチームを作成します。 これは "ポイントインタイム" スクリプトです (ユーザーが組織に追加または削除されると、チームやチャネルは自動的に更新されません)。 ただし、最初からシステム構造に何らかの順序を付けるTeamsツールです。 このスクリプトは、Azure ADを読み取り、マネージャーとその直下のレポートの一覧を取得します。 このリストを使用して、People マネージャーごとに 1 つのチームを作成します。 

## <a name="how-to-use-the-powershell-script"></a>PowerShell スクリプトの使い方 

まず、エクスポート マネージャーとその直接[スクリプトを実行](scripts/powershell-script-create-teams-from-managers-export-managers.md)します ([これは、Connect-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0)モジュールと[Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell モジュールを既に実行済みである場合)。 エクスポート *マネージャーとその* 直接スクリプトでは、すべてのマネージャーを直接レポートと一覧表示するタブ区切りファイル (ExportedManagerDirects.txt) が作成されます。 

次に、新しい [People マネージャー チームの作成スクリプト を実行します](scripts/powershell-script-create-teams-from-managers-new-teams.md)。 このスクリプトは、ExportedManagerDirects.txt ファイルを読み取り、各マネージャーのチームを作成し、そのマネージャーの直接レポートをメンバーとして使用します。 管理者または監督が管理者に対して有効になっていないTeamsスクリプトはそれらをスキップし、チームを作成しません。 (レポートを確認し、必要なユーザーに対して Teamsを有効にした後、スクリプトを再実行します。 スクリプトでは、既にチームを作成しているマネージャーの 2 つ目のチームは作成されません)。

各チームについて、スクリプトは General チャネルと "Just for fun" チャネルを作成します。 

## <a name="best-practices"></a>ベスト プラクティス

- 各チームの [全般] チャネルにタブとして組織の危機コミュニケーション Web サイトを追加して、各人のマネージャーに問い合わせください。 

- 2020 年 3 月 8 日のブログ投稿「Microsoft Teams + Power Platform を使用して危機的な通信を調整する」を参照して、新しいクライ[シス コミュニケーション アプリを確認してください](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)。

## <a name="related-topics"></a>関連トピック

[チームを編成するためのベスト プラクティス](best-practices-organizing.md)

[Teams で組織全体にわたるチームを作成する](create-an-org-wide-team.md)