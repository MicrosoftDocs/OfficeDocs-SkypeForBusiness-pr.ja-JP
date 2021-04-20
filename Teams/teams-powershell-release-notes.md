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
ms.openlocfilehash: da52be2d586bec681a753f22a3db0b2aaf839496
ms.sourcegitcommit: b782ca2ef946ae25e847c2d1847a89993a8edef8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "51886726"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft Teams PowerShell のリリース ノート

このページには、一般提供リリースとパブリック プレビュー リリースの両方の最新の Teams PowerShell 変更ログが表示されます。

## <a name="release-notes"></a>リリース ノート

> [!NOTE]
> **下の** バージョン列の -preview は、Teams PowerShell パブリック プレビューの更新プログラムを表しています。

| 日付 | バージョン | 更新プログラム |
|------- | -------------------- | ------------------------------ |
| 2021 年 4 月 | [2.2.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.2.0-preview) | <li>Connect-MicrosoftTeams で -AccountId を使用するための統合 Windows 認証の修正。</li><li>ユーザーに送信できる変更通知イベントの合計の詳細を取得するコマンドレットが追加されました。</li><li>ユーザーとグループの複数地域の領域を取得するコマンドレットが追加されました。</li><li>TeamsEnvironment 名に渡される値の処理では、大文字と小文字が区別されます。 この問題は修正されました。</li><li>ユニット テストを容易にするためにモジュール内のリモート セッション管理の大きなリファクタリング。 テナント管理者の機能変更はありません。</li>|
| 2021 年 4 月 | [2.1.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.1.0-preview) | <li>既存のコマンドレットの書式設定が修正されました (たとえば、Get-CsTeamsNetworkRoamingPolicy、Get-CsTeamsMeetingPolicy、Get-CsTeamsMessagingPolicy など)。</li><li>ポリシー管理コマンドレットのパラメーター リストが更新されました。</li>|
| 2021 年 3 月 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>認証認証に MSAL を&する</li> <li>Connect-MicrosoftTeamsは、すべてのコマンドレットのエントリ ポイントです。</li><li>New-csOnlineSession は使用できなくなりました。 これは Connect-MicrosoftTeams に置き換えられた。</li><li>Enable-csonlinesessionforreconnection は不要です。 この機能は、Teams PowerShell モジュールでネイティブに実装されています。</li> <li>リファクタリングされたポリシー パッケージコマンドレットとグループ パッケージ割り当ての追加</li><li>Get-Team コマンドレットの大幅Get-Team強化</li> <li>既存のコマンドレットのログ記録とデバッグ オプションの改善 </li> <li>テンプレート管理コマンドレットが追加されました</li> <li>サービスの廃止New-CsOnlineSession</li>|
| 2021 年 2 月 | [1.1.11-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>テンプレート管理コマンドレットが追加されました</li><li>Get-Team コマンドレットの Mezzo とバッチ処理の拡張機能</li> <li>既存のコマンドレットのログ記録とデバッグ オプションの改善 </li> <li>リファクタリングされたポリシー パッケージコマンドレット</li>|
| 2020 年 12 月 | [1.1.10-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>再試行回数とスリープ時間が長い New-team コマンドレットの更新</li>|
| 2020 年 12 月 | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Skype for Business Online との統合に関する更新プログラム</li><li>Teams での重複プロンプトのConnect-Microsoft修正</li>|
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

## <a name="related-topics"></a>関連トピック

[Teams PowerShell の概要](teams-powershell-overview.md)

[Teams Powershell のインストール](teams-powershell-install.md)

[Teams PowerShell での Teams の管理](teams-powershell-managing-teams.md)

[Microsoft Teams コマンドレット リファレンス](/powershell/teams/?view=teams-ps)

[Skype for Business コマンドレット リファレンス](/powershell/skype/intro?view=skype-ps)
