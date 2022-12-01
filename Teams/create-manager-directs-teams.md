---
title: Microsoft Teams でユーザー マネージャー チームを作成する
ms.reviewer: pbethi
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: PowerShell スクリプトを使用して、各マネージャーのチームをチーム メンバーとして作成する方法について説明します。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 89a820a1b828621df2a129b7a972408e7280b3da
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198929"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Microsoft Teams でユーザー マネージャー チームを作成する


"空白のスレート" (チームやチャネルなし) で起動するのではなく、Teams Microsoftロールアウトするときは、チームとチャネルの基本フレームワークを設定することを強くお勧めします。 これにより、既存のチームでチャネルを作成する必要があるときにユーザーが多数のチームを作成する "チームのスプロール" を防ぐことができます。 適切に設計されたチームとチャネル構造の使用を開始できるように、各マネージャーの直属のレポートをチーム メンバーとして、1 行目と 2 行目の各マネージャーのチームを作成する PowerShell スクリプトを作成しました。 これは "ポイントインタイム" スクリプトです (ユーザーが組織に追加または削除された場合、チームやチャネルは自動的に更新されません)。 ただし、最初から Teams 構造に何らかの順序を課すために使用できる貴重なツールです。 このスクリプトは、Azure AD を読み取り、マネージャーとその直属のレポートの一覧を取得します。 このリストを使用して、ユーザー マネージャーごとに 1 つのチームを作成します。 

## <a name="how-to-use-the-powershell-script"></a>PowerShell スクリプトの使用方法 

まず [、エクスポート マネージャーとそのダイレクト スクリプトを](scripts/powershell-script-create-teams-from-managers-export-managers.md) 実行します ( [Connect-AzureAd](/powershell/module/azuread/connect-azuread) モジュールと [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams) PowerShell モジュールを既に実行していることを前提としています)。 *エクスポート マネージャーとそのダイレクト* スクリプトは、すべてのマネージャーとその直属のレポートを一覧表示するタブ区切りファイル (ExportedManagerDirects.txt) を作成します。 

次に、 [新しいユーザー マネージャー チームの作成スクリプト](scripts/powershell-script-create-teams-from-managers-new-teams.md)を実行します。 このスクリプトは、ExportedManagerDirects.txt ファイルを読み取り、マネージャーの直属部下をメンバーとして、各マネージャーのチームを作成します。 マネージャーまたはダイレクトが Teams に対して有効になっていない場合、スクリプトはチームをスキップし、チームを作成しません。 (レポートを確認し、必要なユーザーに対して Teams を有効にした後、スクリプトを再実行します。 このスクリプトでは、チームが既に作成されているマネージャーの 2 番目のチームは作成されません。

各チームに対して、スクリプトによって General チャネルと "Just for fun" チャネルが作成されます。 

## <a name="best-practices"></a>ベスト プラクティス

- 各ユーザー マネージャーに、組織の危機通信 Web サイトをタブとして各チームの [全般] チャネルに追加するように依頼します。 

- 新しい Crisis Communications アプリについては、2020 年 3 月 8 日のブログ投稿「[Microsoft Teams + Power Platform を使用して危機通信を調整する](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)」を参照してください。

## <a name="related-topics"></a>関連項目

[チームを編成するためのベスト プラクティス](best-practices-organizing.md)

[Teams で組織全体にわたるチームを作成する](create-an-org-wide-team.md)