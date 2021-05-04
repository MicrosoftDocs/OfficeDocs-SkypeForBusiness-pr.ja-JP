---
title: Microsoft TeamsPowerShell のリリース ノート
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
description: PowerShell の最新の変更点Teams説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 382d11ba8a2a388b70df5675275f21faae5db37c
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130306"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft TeamsPowerShell のリリース ノート

このページでは、一般Teamsパブリック プレビュー リリースの両方に関する最新の PowerShell 変更ログを提供します。

## <a name="release-notes"></a>リリース ノート

> [!NOTE]
> **次の** バージョン列の -preview は、PowerShell パブリック プレビュー Teams更新プログラムを表します。

| 日付 | バージョン | 更新プログラム |
|------- | -------------------- | ------------------------------ |
| 2021 年 4 月 | [2.3.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.0) | <li>ユーザーとグループのマルチ geo リージョンを取得するコマンドレットを追加しました</li><li>-AccountId と一緒に使用する統合 Windows 認証のConnect-MicrosoftTeams</li><li>TeamsCallHoldPolicy コマンドレットが利用可能に</li><li>多くのコマンドの入力パラメーターと出力形式の更新</li><li>コマンドのリモート処理中に大きな待機時間の問題が修正されます。</li><li>GA カスタム パッケージの機能</li>|
| 2021 年 4 月 | [2.2.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.2.0-preview) | <li>MicrosoftTeams で -AccountId Windowsを使用する統合認証Connect修正。</li><li>ユーザーに送信できる変更通知イベントの合計の詳細を取得するコマンドレットを追加しました。</li><li>ユーザーとグループのマルチ geo リージョンを取得するコマンドレットを追加しました。</li><li>TeamsEnvironment 名に渡される値の処理では、大文字と小文字が区別されます。 これは修正されました。</li><li>ユニット テストを容易にするためのモジュール内のリモート セッション管理の主なリファクタリング。 テナント管理者の機能変更は行う必要はありません。</li>|
| 2021 年 4 月 | [2.1.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.1.0-preview) | <li>既存のコマンドレット (Get-CsTeamsNetworkRoamingPolicy、Get-CsTeamsMeetingPolicy、Get-CsTeamsMessagingPolicy など) の書式設定を修正しました。</li><li>ポリシー管理コマンドレットのパラメーター リストを更新しました。</li>|
| 2021 年 3 月 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>認証と承認に MSAL を&する</li> <li>Connect-MicrosoftTeamsは、すべてのコマンドレットのエントリ ポイントです。</li><li>New-csOnlineSession は使用できなくなりました。 これは、MicrosoftTeams Connectに置き換えされました。</li><li>Enable-csonlinesessionforreconnection は不要です。 この機能は、PowerShell モジュールのTeams実装されています。</li> <li>リファクタリングされたポリシー パッケージコマンドレットとグループ パッケージの割り当てを追加する</li><li>このコマンドレットの大幅なパフォーマンスGet-Team強化</li> <li>既存のコマンドレットのログ記録とデバッグオプションの改善 </li> <li>テンプレート管理コマンドレットを追加しました</li> <li>非推奨のNew-CsOnlineSession</li>|
| 2021 年 2 月 | [1.1.11-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>テンプレート管理コマンドレットを追加しました</li><li>このコマンドレットの Mezzo とバッチ処理Get-Team強化</li> <li>既存のコマンドレットのログ記録とデバッグオプションの改善 </li> <li>リファクタリングされたポリシー パッケージコマンドレット</li>|
| 2020 年 12 月 | [1.1.10-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>再試行回数とスリープ時間が長い New-team コマンドレットの更新</li>|
| 2020 年 12 月 | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>オンライン統合Skype for Business更新プログラム</li><li>重複するプロンプトが表示される問題を修正Connect-Microsoft Teams</li>|
| 2020 年 11 月 | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>カスタム ポリシー パッケージ コマンドレットを追加します。</li><li>ターゲット階層のアップロード コマンドの修正</li>|
| 2020 年 11 月 | [1.1.7-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>認証と承認に MSAL を&する</li><li>リファクタリングされたポリシー パッケージコマンドレットとグループ パッケージの割り当てを追加する</li><li>非同期モデルを使用するリファクタリングされたターゲット階層のアップロード コマンド</li> <li>ユーザーは、-credential パラメーターを使用しない初期認証中に 2 回プロンプトが表示されます。 ユーザーは、-credential パラメーターを使用して資格情報を渡して、プロンプトが重複しないようにすることができます。 この動作は、次のリリースで修正される予定です。</li> |
| 2020 年 9 月 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Skype for Businessオンライン コネクタの統合</li> |
| 2020 年 9 月 | [1.1.5-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Skype for Businessオンライン コネクタの統合</li> |
| 2020 年 7 月 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>グループ ポリシーの [割り当てコマンドレットを追加しました](./assign-policies.md#assign-a-policy-to-a-group)</li> |
| 2020 年 6 月 | [1.1.3-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Skype for Businessオンライン コネクタの統合<li>Get-Team最適化<li>高められた信頼性</li> |
| 2020 年 6 月 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>コマンドレットの事前読み込みを追加しました<li>.Net Framework の最適化</li>   |
| 2020 年 4 月 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Authenticode とアセンブリの署名<li>追加されたGet-CsPolicyPackage<li>追加されたGet-CsUserPolicyPackage<li>追加されたGet-CsUserPolicyPackageRecommendation<li>追加されたGrant-CsUserPolicyPackage<li>追加されたNew-CsBatchPolicyPackageAssignmentOperation<li>追加されたSet-TeamArchivedState<li>追加されたSet-TeamPicture<li>削除されたGet-TeamHelp</li>  |
| 2020 年 3 月 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>追加されたNew-CsBatchPolicyAssignmentOperation</li> |
| 2020 年 2 月 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team最適化</li>  |

## <a name="related-topics"></a>関連トピック

[Teams PowerShell の概要](teams-powershell-overview.md)

[Teams Powershell のインストール](teams-powershell-install.md)

[Teams PowerShell での Teams の管理](teams-powershell-managing-teams.md)

[Microsoft Teams コマンドレット リファレンス](/powershell/teams/?view=teams-ps)

[Skype for Business コマンドレット リファレンス](/powershell/skype/intro?view=skype-ps)
