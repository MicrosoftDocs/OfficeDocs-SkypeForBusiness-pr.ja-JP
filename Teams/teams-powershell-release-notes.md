---
title: Microsoft Teams PowerShell リリースノート
ms.reviewer: brandber
author: BrandBer
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Teams PowerShell での最新の変更について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: cda7c9db774632317cb568a6b448b4fc04b3b5ff
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944123"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft Teams PowerShell リリースノート

このページでは、一般的な可用性とパブリックプレビューリリースの両方について、最新の Teams PowerShell の変更ログが提供されます。

## <a name="release-notes"></a>リリースノート

> [!NOTE]
> **-** 下の [バージョンの列でプレビューすると、Teams PowerShell public preview の更新が示されます。

| 日付 | バージョン | 更新プログラム |
|------- | -------------------- | ------------------------------ |
| 2020年6月 | [1.1.0-プレビュー](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.0-preview) | <li>Skype for Business Online のコネクタの統合<li>取得-チームの最適化<li>信頼性の向上</li> |
| 2020年6月 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>コマンドレットのプリロードを追加しました<li>.Net Framework の最適化</li>   |
| 2020年4月 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Authenticode とアセンブリの署名<li>Get-CsPolicyPackage を追加しました<li>Get-CsUserPolicyPackage を追加しました<li>Get-CsUserPolicyPackageRecommendation を追加しました<li>Grant-CsUserPolicyPackage を追加しました<li>新しく追加されました-CsBatchPolicyPackageAssignmentOperation<li>Set-TeamArchivedState を追加しました<li>追加された設定-TeamPicture<li>Teams のヘルプを削除しました</li>  |
| 2020 年 3 月 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>新しく追加されました-CsBatchPolicyAssignmentOperation</li> |
| 2020年2月 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>取得-チームの最適化</li>  |

### <a name="cmdlet-availability"></a>コマンドレットの可用性

> [!NOTE]
> 以下の表に示す一覧には、Teams PowerShell モジュールのネイティブ部分のコマンドレットのみが含まれています。 S[Kype Business Online Connector モジュール](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)の Teams コマンドレットは表示されません。 ただし、これらのコマンドレットは、チーム PowerShell にネイティブに移行されるため、このテーブルに追加します。

| コマンドレット | パブリックプレビューで利用可能 | GA で利用可能 |
| -| -- | --|
| [TeamChannelUser の追加](https://docs.microsoft.com/powershell/module/teams/add-teamchanneluser?view=teams-ps) | はい | **いいえ** |
| [Add-TeamUser](https://docs.microsoft.com/powershell/module/teams/add-teamuser?view=teams-ps) | はい | はい |
| [Add-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/add-teamsappinstallation?view=teams-ps) | はい | **いいえ**|
| [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) | はい | はい |
| [Disconnect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/disconnect-microsoftteams?view=teams-ps) | はい | はい |
| [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation?view=teams-ps) | はい | はい |
| [Get-CsGroupPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignmentoperation?view=teams-ps) | はい | **いいえ** |
| [Get-Csonline Powershellendpoint](https://docs.microsoft.com/powershell/module/teams/get-csonlinepowershellendpoint?view=teams-ps) | はい | **いいえ** |
| [Get-CsPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-cspolicypackage?view=teams-ps) | はい | はい |
| [CsUserPolicyAssignment を取得する](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment?view=teams-ps) | はい | はい |
| [Get-CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackage?view=teams-ps) | はい | はい |
| [Get-CsUserPolicyPackageRecommendation](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackagerecommendation?view=teams-ps) | はい | はい |
| [Get-Team](https://docs.microsoft.com/powershell/module/teams/get-team?view=teams-ps) | はい | はい |
| [Get-TeamChannel](https://docs.microsoft.com/powershell/module/teams/get-teamchannel?view=teams-ps) | はい | はい|
| [ユーザーの取得-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/get-teamchanneluser?view=teams-ps) | はい | はい|
| [Get-TeamUser](https://docs.microsoft.com/powershell/module/teams/get-teamuser?view=teams-ps) | はい | はい |
| [チームの取得アプリ](https://docs.microsoft.com/powershell/module/teams/get-teamsapp?view=teams-ps) | はい | はい |
| [Get-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/get-teamsappinstallation?view=teams-ps) | はい | はい |
| [Grant-CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/grant-csuserpolicypackage?view=teams-ps) | はい | はい |
| [新規-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) | はい | はい |
| [新しい CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps) | はい | **いいえ** |
| [新規-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation?view=teams-ps) | はい | はい |
| [新しい Csonline セッション](https://docs.microsoft.com/powershell/module/teams/new-csonlinesession?view=teams-ps) | はい | **いいえ** |
| [New-Team](https://docs.microsoft.com/powershell/module/teams/new-team?view=teams-ps) | はい | はい |
| [New-TeamChannel](https://docs.microsoft.com/powershell/module/teams/new-channel?view=teams-ps) | はい | はい |
| [新しい-TeamsApp](https://docs.microsoft.com/powershell/module/teams/new-teamsapp?view=teams-ps) | はい | はい |
| [CsGroupPolicyAssignment の削除](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment?view=teams-ps) | はい | **いいえ** |
| [Remove-Team](https://docs.microsoft.com/powershell/module/teams/remove-team?view=teams-ps) | はい | はい |
| [Remove-TeamChannel](https://docs.microsoft.com/powershell/module/teams/remove-teamchannel?view=teams-ps) | はい | はい |
| [TeamChannelUser の削除](https://docs.microsoft.com/powershell/module/teams/remove-teamchanneluser?view=teams-ps) | はい | はい |
| [-TeamsApp の削除](https://docs.microsoft.com/powershell/module/teams/remove-teamsapp?view=teams-ps) | はい | はい |
| [Remove-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/remove-teamsappinstallation?view=teams-ps) | はい | **いいえ** |
| [-TeamTargetingHierarchy を削除します](https://docs.microsoft.com/powershell/module/teams/remove-teamtargetinghierarchy?view=teams-ps) | はい | **いいえ**|
| [Remove-TeamUser](https://docs.microsoft.com/powershell/module/teams/remove-teamuser?view=teams-ps) | はい | はい |
| [設定-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment?view=teams-ps) | はい | **いいえ** |
| [Set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps) | はい | はい |
| [Set-TeamArchivedState](https://docs.microsoft.com/powershell/module/teams/set-teamarchivedstate?view=teams-ps) | はい | はい |
| [Set-TeamChannel](https://docs.microsoft.com/powershell/module/teams/set-teamchannel?view=teams-ps) | はい | はい |
| [Set-TeamPicture](https://docs.microsoft.com/powershell/module/teams/set-teampicture?view=teams-ps) | はい | はい |
| [Set-TeamsApp](https://docs.microsoft.com/powershell/module/teams/set-teamapp?view=teams-ps) | はい | はい |
| [Set-TeamTargetingHierarchy](https://docs.microsoft.com/powershell/module/teams/set-teamtargetinghierarchy?view=teams-ps) | はい | **いいえ** |
| [更新-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/update-teamappinstallation?view=teams-ps) | はい | **いいえ** |

## <a name="related-topics"></a>関連項目

[Teams での PowerShell の概要](teams-powershell-overview.md)

[Teams PowerShell のインストール](teams-powershell-install.md)

[Teams PowerShell を使用してチームを管理する](teams-powershell-managing-teams.md)

[Microsoft Teams コマンドレット リファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Skype for Business コマンドレット リファレンス](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
