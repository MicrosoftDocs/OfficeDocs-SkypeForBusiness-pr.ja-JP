---
title: Microsoft Teams PowerShell の概要
ms.reviewer: ''
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: PowerShell コントロールを使用して Microsoft Teams を管理する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 07a97ee8242da28796664892d092b503e10c59cf
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922818"
---
# <a name="microsoft-teams-powershell-overview"></a>Microsoft Teams PowerShell の概要

Microsoft Teams PowerShell モジュールは、PowerShell コマンド ラインから直接Teamsを管理するためのコマンドレットのセットです。 PowerShell には、Teamsワークロードを管理するために利用できる自動化のための強力な機能が用意されています。  

次のいずれかの方法を使用して、Microsoft Teams PowerShell モジュールを使用できます。 

- PowerShell ギャラリーを使用してMicrosoft Teams PowerShell モジュール[をインストールします](https://www.powershellgallery.com/packages/MicrosoftTeams) (推奨オプション)。 
- [手動ダウンロード](https://www.powershellgallery.com/packages/MicrosoftTeams)を使用して、Microsoft Teams PowerShell モジュールをインストールします。 

> [!NOTE]
> Microsoft Teams 4.x.x より前の PowerShell モジュール のバージョンは廃止されます。 最新バージョンに更新してください。 [PowerShell モジュール - サポートされているバージョンTeams](teams-powershell-supported-versions.md)詳しく説明します。

## <a name="features"></a>機能 

Microsoft Teams PowerShell モジュールには、次の機能が含まれています。 

- 1 つのモジュールを使用して、ユーザー、チーム、ポリシー、構成など、Teams管理のすべての側面を管理します。  
- アクセス トークンや資格情報などの認証メカニズムをサポートします。 

##  <a name="data-collection"></a>データ収集 

PowerShell モジュールの既定の設定Microsoft Teamsテレメトリ データを収集します。 Microsoft では、収集されたデータを集計して、使用率のパターンや成功度の低いコマンドレットなどの一般的な問題を特定し、Teams PowerShell エクスペリエンスを向上させるための作業に優先順位を付けます。 PowerShell モジュールMicrosoft Teams、プライベート データや個人データは収集されません。 詳細については、 [Microsoft のプライバシーに関する声明](https://privacy.microsoft.com/privacystatement)を参照してください。

## <a name="related-topics"></a>関連項目

[Teams Powershell のインストール](teams-powershell-install.md)

[Teams PowerShell での Teams の管理](teams-powershell-managing-teams.md)

[Teams PowerShell のリリース ノート](teams-powershell-release-notes.md)

[Microsoft Teams コマンドレット リファレンス](/powershell/teams/?view=teams-ps)

[Skype for Business コマンドレット リファレンス](/powershell/skype/intro?view=skype-ps)

[Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md)
