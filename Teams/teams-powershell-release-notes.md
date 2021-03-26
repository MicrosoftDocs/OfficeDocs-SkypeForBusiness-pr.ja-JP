---
title: Microsoft Teams PowerShell のリリース ノート
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
description: Teams PowerShell の最新の変更について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe53da388c4f10561106bb0b2bec9d1e2898e563
ms.sourcegitcommit: bd7847de9d1402476f8faaeae2ff97ec60d86a1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "51262632"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft Teams PowerShell のリリース ノート

このページには、一般提供リリースとパブリック プレビュー リリースの両方の最新の Teams PowerShell 変更ログが表示されます。

## <a name="release-notes"></a>リリース ノート

> [!NOTE]
> **下のバージョン** 列の -preview は、Teams PowerShell パブリック プレビューの更新を表しています。

| 日付 | バージョン | 更新プログラム |
|------- | -------------------- | ------------------------------ |
| 2021 年 3 月 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>認証認証に MSAL を&する</li> <li>Connect-MicrosoftTeamsは、すべてのコマンドレットのエントリ ポイントです。</li><li>New-csOnlineSession は使用できなくなりました。 Connect-MicrosoftTeams に置き換えられた。</li><li>Enable-csonlinesessionforreconnection は不要です。 この機能は、Teams PowerShell モジュールでネイティブに実装されています。</li> <li>リファクタリングされたポリシー パッケージコマンドレットとグループ パッケージ割り当ての追加</li><li>Get-Team コマンドレットの大幅Get-Team強化</li> <li>既存のコマンドレットのログ記録とデバッグ オプションの改善 </li> <li>テンプレート管理コマンドレットが追加されました</li> <li>サービスの廃止New-CsOnlineSession</li>|
| 2021 年 2 月 | [1.1.11-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>テンプレート管理コマンドレットが追加されました</li><li>Get-Team コマンドレットの mezzo とバッチ処理の拡張機能</li> <li>既存のコマンドレットのログ記録とデバッグ オプションの改善 </li> <li>リファクタリングされたポリシー パッケージコマンドレット</li>|
| 2020 年 12 月 | [1.1.10-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>再試行回数とスリープ時間が長い New-team コマンドレットの更新</li>|
| 2020 年 12 月 | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Skype for Business Online 統合の更新プログラム</li><li>Teams での重複プロンプトのConnect-Microsoft修正</li>|
| 2020 年 11 月 | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>カスタム ポリシー パッケージコマンドレットを追加する</li><li>ターゲット階層のアップロード コマンドの修正</li>|
| 2020 年 11 月 | [1.1.7-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>認証認証に MSAL を&する</li><li>リファクタリングされたポリシー パッケージコマンドレットとグループ パッケージ割り当ての追加</li><li>非同期モデルを使用するためにリファクタリングされたターゲット階層のアップロード コマンド</li> <li>ユーザーが -credential パラメーターを使用しない場合、最初の認証中に 2 回メッセージが表示されます。 ユーザーは、-credential パラメーターを使用して資格情報を渡して、プロンプトが重複しないようにすることができます。 この動作は次のリリースで修正される予定です。</li> |
| 2020 年 9 月 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Skype for Business Online Connector の統合</li> |
| 2020 年 9 月 | [1.1.5-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Skype for Business Online Connector の統合</li> |
| 2020 年 7 月 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>グループ ポリシー [割り当てコマンドレットが追加されました](./assign-policies.md#assign-a-policy-to-a-group)</li> |
| 2020 年 6 月 | [1.1.3-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Skype for Business Online Connector の統合<li>Get-Team最適化<li>信頼性の向上</li> |
| 2020 年 6 月 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>コマンドレットのプリロードが追加されました<li>.Net Framework の最適化</li>   |
| 2020 年 4 月 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Authenticode とアセンブリの署名<li>追加Get-CsPolicyPackage<li>追加Get-CsUserPolicyPackage<li>追加Get-CsUserPolicyPackageRecommendation<li>追加Grant-CsUserPolicyPackage<li>追加New-CsBatchPolicyPackageAssignmentOperation<li>追加Set-TeamArchivedState<li>追加Set-TeamPicture<li>削除Get-TeamHelp</li>  |
| 2020 年 3 月 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>追加New-CsBatchPolicyAssignmentOperation</li> |
| 2020 年 2 月 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team最適化</li>  |

### <a name="cmdlet-availability"></a>コマンドレットの可用性

> [!NOTE]
> 次の表の一覧には、Teams PowerShell モジュールのネイティブの一部であるコマンドレットだけが含まれています。 S[kype for Business Online Connector モジュールの Teams コマンドレットは](/powershell/skype/intro?view=skype-ps) 表示されません。 ただし、これらのコマンドレットは Teams PowerShell にネイティブで移行されるので、このテーブルに追加します。

| コマンドレット | パブリック プレビューで利用可能 | GA で利用可能 |
| -| -- | --|
| [Add-TeamChannelUser](/powershell/module/teams/add-teamchanneluser?view=teams-ps) | はい | **いいえ** |
| [Add-TeamUser](/powershell/module/teams/add-teamuser?view=teams-ps) | はい | はい |
| [Add-TeamsAppInstallation](/powershell/module/teams/add-teamsappinstallation?view=teams-ps) | はい | **いいえ**|
| [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) | はい | はい |
| [Disconnect-MicrosoftTeams](/powershell/module/teams/disconnect-microsoftteams?view=teams-ps) | はい | はい |
| [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation?view=teams-ps) | はい | はい |
| [Get-CsGroupPolicyAssignmentOperation](/powershell/module/teams/get-csgrouppolicyassignment?view=teams-ps) | はい | **いいえ** |
| [Get-CsOnlinePowerShellEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint?view=skype-ps) | はい | はい |
| [Get-CsPolicyPackage](/powershell/module/teams/get-cspolicypackage?view=teams-ps) | はい | はい |
| [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment?view=teams-ps) | はい | はい |
| [Get-CsUserPolicyPackage](/powershell/module/teams/get-csuserpolicypackage?view=teams-ps) | はい | はい |
| [Get-CsUserPolicyPackageRecommendation](/powershell/module/teams/get-csuserpolicypackagerecommendation?view=teams-ps) | はい | はい |
| [Get-Team](/powershell/module/teams/get-team?view=teams-ps) | はい | はい |
| [Get-TeamChannel](/powershell/module/teams/get-teamchannel?view=teams-ps) | はい | はい|
| [Get-TeamChannelUser](/powershell/module/teams/get-teamchanneluser?view=teams-ps) | はい | **いいえ** |
| [Get-TeamUser](/powershell/module/teams/get-teamuser?view=teams-ps) | はい | はい |
| [Get-TeamsApp](/powershell/module/teams/get-teamsapp?view=teams-ps) | はい | はい |
| [Get-TeamsAppInstallation](/powershell/module/teams/get-teamsappinstallation?view=teams-ps) | はい | **いいえ** |
| [Grant-CsUserPolicyPackage](/powershell/module/teams/grant-csuserpolicypackage?view=teams-ps) | はい | はい |
| [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) | はい | はい |
| [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps) | はい | はい |
| [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation?view=teams-ps) | はい | はい |
| [New-CsOnlineSession](/powershell/module/skype/new-csonlinesession?view=skype-ps) | はい | はい |
| [New-Team](/powershell/module/teams/new-team?view=teams-ps) | はい | はい |
| [New-TeamChannel](/powershell/module/teams/new-teamchannel?view=teams-ps) | はい | はい |
| [New-TeamsApp](/powershell/module/teams/new-teamsapp?view=teams-ps) | はい | はい |
| [Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment?view=teams-ps) | はい | はい |
| [Remove-Team](/powershell/module/teams/remove-team?view=teams-ps) | はい | はい |
| [Remove-TeamChannel](/powershell/module/teams/remove-teamchannel?view=teams-ps) | はい | はい |
| [Remove-TeamChannelUser](/powershell/module/teams/remove-teamchanneluser?view=teams-ps) | はい | **いいえ** |
| [Remove-TeamsApp](/powershell/module/teams/remove-teamsapp?view=teams-ps) | はい | はい |
| [Remove-TeamsAppInstallation](/powershell/module/teams/remove-teamsappinstallation?view=teams-ps) | はい | **いいえ** |
| [Remove-TeamTargetingHierarchy](./set-up-your-team-hierarchy.md#remove-your-hierarchy) | はい | **いいえ**|
| [Remove-TeamUser](/powershell/module/teams/remove-teamuser?view=teams-ps) | はい | はい |
| [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment?view=teams-ps) | はい | **いいえ** |
| [Set-Team](/powershell/module/teams/set-team?view=teams-ps) | はい | はい |
| [Set-TeamArchivedState](/powershell/module/teams/set-teamarchivedstate?view=teams-ps) | はい | はい |
| [Set-TeamChannel](/powershell/module/teams/set-teamchannel?view=teams-ps) | はい | はい |
| [Set-TeamPicture](/powershell/module/teams/set-teampicture?view=teams-ps) | はい | はい |
| [Set-TeamsApp](/powershell/module/teams/set-teamapp?view=teams-ps) | はい | はい |
| [Set-TeamTargetingHierarchy](/powershell/module/teams/set-teamtargetinghierarchy?view=teams-ps) | はい | **いいえ** |
| [Update-TeamsAppInstallation](/powershell/module/teams/update-teamappinstallation?view=teams-ps) | はい | **いいえ** |
| [Enable-CsOnlineSessionForReconnection](/skypeforbusiness/set-up-your-computer-for-windows-powershell/diagnose-problems-with-the-skype-for-business-online-connector) | **いいえ** | **いいえ** |


## <a name="related-topics"></a>関連トピック

[Teams PowerShell の概要](teams-powershell-overview.md)

[Teams Powershell のインストール](teams-powershell-install.md)

[Teams PowerShell での Teams の管理](teams-powershell-managing-teams.md)

[Microsoft Teams コマンドレット リファレンス](/powershell/teams/?view=teams-ps)

[Skype for Business コマンドレット リファレンス](/powershell/skype/intro?view=skype-ps)
