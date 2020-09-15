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
ms.openlocfilehash: a5986a730ed678d45360d89efbd35693134c2a6a
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814366"
---
# <a name="microsoft-teams-powershell-overview"></a>Microsoft Teams PowerShell の概要

Microsoft Teams PowerShell は、PowerShell コマンドラインから直接 Teams を管理するためのコマンドレットのセットです。 作成された .NET Standard では、Teams PowerShell は、Azure Shell を含むすべてのプラットフォームで PowerShell 5.1 x 以降で動作します。

PowerShell の使用を開始する前に、 [インストール](teams-powershell-install.md)する必要があります。 

> [!WARNING]
> PowerShell 7 と Teams PowerShell について、既知の問題があります。 問題が解決されるまで、PowerShell 5.1 を使うことをお勧めします。

## <a name="releases"></a>日本語


Teams PowerShell は、2種類のリリースで [PowerShell ギャラリー](https://www.powershellgallery.com/packages/MicrosoftTeams) で利用できます。

- **一般的な可用性 (GA)**: プロダクション対応のコマンドレット、毎月更新されます。

- **パブリックプレビュー**: 機能への早期アクセス。 GA よりも頻繁に更新される可能性があります。

両方のリリースの機能の追加と改善の詳細については、 [Teams PowerShell のリリースノート](teams-powershell-release-notes.md)を参照してください。


## <a name="manage-teams-with-powershell"></a>PowerShell を使用してチームを管理する

Teams PowerShell モジュールを使用して Teams を完全に管理します。

- [Microsoft Teams powershell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams/): teams powershell モジュールには、チーム、チャット、チャネルを管理するためのコマンドレットが含まれています。

> [!NOTE]
> 最新の [Teams powershell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) は、Skype For Business Online Connector と統合されており、teams powershell 管理用の1つのモジュールを提供しています。

- [Skype For Business Powershell connector](https://www.microsoft.com/download/details.aspx?id=39366): skype For business powershell コネクタは、Teams PowerShell モジュールの一部になりました。

これらのモジュールを使用してチームを管理する方法の詳細については、「 [Teams PowerShell を](teams-powershell-managing-teams.md)使用してチームを管理する」を参照してください。


## <a name="related-topics"></a>関連トピック

[Teams PowerShell のインストール](teams-powershell-install.md)

[Teams PowerShell を使用してチームを管理する](teams-powershell-managing-teams.md)

[Teams PowerShell リリースノート](teams-powershell-release-notes.md)

[Microsoft Teams コマンドレット リファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Skype for Business コマンドレット リファレンス](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md)
