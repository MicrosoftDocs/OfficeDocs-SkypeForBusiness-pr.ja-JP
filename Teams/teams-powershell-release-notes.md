---
title: Microsoft Teams PowerShell リリース ノート
ms.reviewer: gothambi
author: BrandBer
ms.author: gothambi
manager: naanur
ms.date: 11/30/2021
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: PowerShell の最新の変更Teams説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: ebaa5a3f5da4371da7fc2e6362a099756fabcda8
ms.sourcegitcommit: be8b820caf4b5a1a91ad444ba93da1df20bf63ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2021
ms.locfileid: "61257308"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft Teams PowerShell リリース ノート

このページでは、一般公開Teams両方の PowerShell 変更ログの最新バージョンを提供します。

## <a name="release-notes"></a>リリース ノート

> [!NOTE]
> **-preview** in the version column below は、PowerShell パブリック Teams更新プログラムを表します。

| 日付 | バージョン | 更新プログラム |
|------- | -------------------- | ------------------------------ |
| 2021 年 11 月 | [3.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0) |<li>まもなくMicrosoft Teams 3.x.x シリーズの PowerShell モジュール のバージョンがサポートされる唯一のバージョンになります。 以前のバージョンはすべて非推奨パス上に表示されます。</li><li> [BREAKING CHANGE] Get-CsOnlineUser Get-CsOnlineVoiceUser: TeamsOnly テナントには次の変更が適用されます。<ul><li>これらのコマンドレットは、以前の実装から新しい API に移行されました。</li><li>(-Identity パラメーターを使用): TeamsOnly テナントでは、Teamsに関連しなくなった属性は非推奨です。 また、一部の属性の名前が変更または置換されました [。Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser?view=skype-ps) と [Get-CsOnlineVoiceUser](/powershell/module/skype/get-csonlinevoiceuser?view=skype-ps)に関するページを参照してください。</li><li>Get-CsOnlineUser (-Filter パラメーターを使用): AssignedPlans と EnterpriseVoice に基づくフィルター処理の書式設定が変更されました。 また、フィルター可能な属性は、TeamsOnly ユーザーに対して一時的に (使用状況に基づいて) 制限されています [。Get-CsOnlineVoiceUser](/powershell/module/skype/get-csonlinevoiceuser?view=skype-ps)に関するページを参照してください。</li><li>これらのコマンドレットは段階的にロールアウトされ、一部のテナントでは CY21 の終了までにロールアウトが完了するまで、これらの変更が発生し続けなくなってきます。</ul></li><li>[BREAKING CHANGE]Get-CsTenant: Teams の世界では関連しなくなった属性は、TeamsOnly テナントでは非推奨です[。Get-CsTenant](/powershell/module/skype/get-cstenant?view=skype-ps)に関するページを参照してください。</li><li> 75 以上の Grant-Cs Policy コマンドレット (すべてのパラメーター セット) の最新バージョン \<Name\> をリリースします。 これらは、リモート処理に対応するのと同様に動作すると予想されます。 最新バージョンは段階的にロールアウトされます。そのため、一部のテナントには以前のリモート処理バージョンが表示されます (ロールアウトが完了するまで)。</li><li> 75 以上の Remove-Cs Policy コマンドレットの最新バージョンを \<Name\> リリースします。 これらは、リモート処理に対応するのと同様に動作すると予想されます。 最新バージョンは段階的にロールアウトされます。そのため、一部のテナントには以前のリモート処理バージョンが表示されます (ロールアウトが完了するまで)。</li><li> [Set \| Remove]-CsPhoneNumberAssignment コマンドレットをリリースします。 これらのコマンドレットは段階的にロールアウトされます。そのため、一部のテナントでは、(ロールアウトが完了するまで) 使用できる既存のコマンドレットを参照するエラー メッセージが表示されます。</li><li> [Set \| New]-CsTeamsEmergencyCallingPolicy コマンドレットの新しいパラメーター EnhancedEmergencyServiceDisclaimer をリリースします。<li> [Get \| Add \| Remove]-TeamChannelUser コマンドレットをリリースします。</li><li> このコマンドレットExport-CsOnlineAudioFileリリースします。</li><li> [Get \| Import \| Remove]-CsOnlineAudioFile コマンドレットのエラー処理を修正しました。</li><li>エラー処理Get-Team修正。 Teams データのフェッチに失敗した場合にエラー メッセージを出力します。</li><li>更新プログラムのConnect-MicrosoftTeams - AccessTokens の有効期限の差が増加します。</li>
| 2021 年 11 月 | [2.6.2-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.6.2-preview) |<li>75 以上の Grant-Cs Policy コマンドレット (すべてのパラメーター セット) の最新バージョン \<Name\> をリリースします。 これらは、リモート処理に対応する場合と同様に動作すると想定されます。 最新バージョンは段階的に展開され、フライトされていないテナントには古いリモート処理バージョンが表示されます。</li><li>75 以上の Remove-Cs Policy コマンドレットの最新バージョンを \<Name\> リリースします。 これらは、リモート処理に対応する場合と同様に動作すると想定されます。 最新バージョンは段階的に展開され、フライトされていないテナントには古いリモート処理バージョンが表示されます。</li><li>このコマンドレットSet-CsUserCallingSettingsリリースします。 このコマンドレットは、最終的に GA モジュールでリリースされます。 プレビュー モジュールでの試用版のリリース。</li><li>このコマンドレットExport-CsOnlineAudioFileリリースします。</li><li>[Get \| Import \| Remove]-CsOnlineAudioFile コマンドレットのエラー処理を修正しました。</li>
| 2021 年 10 月 | [2.6.1-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.6.1-preview) |<li>[Set \| Remove]-CsPhoneNumberAssignment コマンドレットをリリースします。 これらのコマンドレットは段階的に展開されます。そのため、一部のテナントでは、(ロールアウトが完了するまで) 使用できる既存のコマンドレットを参照するエラー メッセージが表示されます。</li><li>コマンドレットGet-CsOnlineTelephoneNumberCountryおよびGet-CsOnlineTelephoneNumberTypeリリースします。</li><li>[Set \| New]-CsTeamsEmergencyCallingPolicy コマンドレットの新しいパラメーター EnhancedEmergencyServiceDisclaimer をリリースします。</li><li>このコマンドレットGet-CsUserCallingSettingsリリースします。 このコマンドレットは、最終的に GA モジュールでリリースされます。 プレビュー モジュールでの試用版のリリース。</li>
| 2021 年 9 月 | [2.6.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.6.0) |<li>別のカスタム PowerShell モジュールの入れ子になったモジュールを作成した場合に MicrosoftTeams モジュールの参照が失敗するバグを修正しました。 MicrosoftTeams コマンドレットは、別のモジュールの入れ子になったモジュールでも使用できます。</li><li>[Get \| New \| Complete \| Clear]-CsOnlineTelephoneNumberOrder コマンドレットをリリースします。</li><li>コマンドレットGet-CsOnlineTelephoneNumberCountryおよびGet-CsOnlineTelephoneNumberTypeリリースします。</li><li>これらのコマンドレットの新しいパラメーターをリリースします: Get-CsOnlineApplicationInstance、New-CsExternalAccessPolicy、New-CsTeamsAppSetupPolicy、New-CsTeamsCallingPolicy、New-CsTeamsCallParkPolicy、New-CsTeamsMeetingPolicy、 New-CsTeamsMessagingPolicy、Set-CsTeamsAppSetupPolicy、Set-CsTeamsCallParkPolicy、Set-CsTeamsGuestMessagingConfiguration、Set-CsTeamsMeetingPolicy、Set-CsTenantFederationConfiguration、Set-CsExternalAccessPolicy、Set-CsTeamsCallingPolicy。</li><li>サインイン試行が正しくない場合に、Connect-MicrosoftTeamsを再試行するときに発生したエラーを修正します。</li><li>新しいバージョンごとに PowerShell ギャラリーでモジュールのリリース ノートを使用できる更新プログラム。</li>
| 2021 年 9 月 | [2.5.2-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.5.2-preview) |<li>注: このバージョンからリリース ノートは、リリース ノートの提供遅延を減らすために、モジュール自体と共に PowerShell ギャラリーにも公開されます。</li><li>[Get \| Set \| Grant New \| \| Remove]-CsTeamsEnhancedEncryptionPolicy コマンドレットをリリースします。</li><li>[Get \| Set \| New \| Remove]-CsTenantBlockedNumberExceptionPattern コマンドレットを削除します。</li><li>別のカスタム PowerShell モジュールの入れ子になったMicrosoft Teamsモジュールの参照が失敗するバグを修正しました。 これで、Microsoft Teamsモジュールの入れ子になったモジュールでも、このコマンドレットを使用できます。</li><li>[Get \| New \| Complete \| Clear]-CsOnlineTelephoneNumberOrder コマンドレットをリリースします。</li><li>コマンドレットGet-CsOnlineTelephoneNumberCountryおよびGet-CsOnlineTelephoneNumberTypeリリースします。</li><li>サインイン試行が間違った後、Connect-MicrosoftTeamsを再試行するときに発生したエラーを修正します。</li><li>プライベート チャネルAdd-TeamChannelUser失敗Remove-TeamChannelUserとエラーを修正しました。</li>
| 2021 年 8 月 | [2.5.1](https://www.powershellgallery.com/packages/MicrosoftTeams/2.5.1) |<li>リソースのアクセス トークン ログインConnect-MicrosoftTeamsリソース固有のトークンごとに個別のパラメーターではなく、統合トークン配列を使用する必要があります。 詳細については、 [Connect-MicrosoftTeams を参照してください](/powershell/module/teams/connect-microsoftteams)。</li><li>Cloudshell でのログインの対話型Connect-MicrosoftTeamsエラーが修正されました。 既定では、再認証を求めるメッセージが表示されるのではなく、ユーザーのログイン ID が使用されます。</li><li>TeamsUnassignedNumberTreatment コマンドレットを使用できます。</li><li>Get-CsOnlineDialInConferencingBridgeコマンドレットSet-CsOnlineDialInConferencingBridge以前の実装から新しい API に移行されました。</li><li>最新バージョンの Get-CsTenantと Get-CsOnlineUser (-identity パラメーターのみ) がリリースされました。 非推奨のプロパティを出力しなくなったので、リモート処理に対応するプロパティと比較して、いくつかの書式設定が変更されます。</li><li>注: New-Team更新プログラムは 2.5.0 から元に戻され、新しい変更を回避するために以前のバージョンが提供されています。</li>|
| 2021 年 7 月 | [2.4.1-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.4.1-preview) |<li>コマンドレットに変更を許可します。</li><li>新しい音声関連のコマンドレットがリリースされます。</li><li>-Cs* コマンドレットの証明書拇印認証の削除。</li><li>すべてのコマンドレットのログ ファイルのログ記録を修正しました。</li><li>*TeamChannelUser コマンドレットに関する問題を修正しました。</li>|
| 2021 年 6 月 | [2.4.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.4.0-preview) |<li>最新バージョンの Get-CsTenant、Get-CsOnlineUser (-identity パラメーターのみ)、Get-CsOnlineDialInConferencingLanguagesSupported、Import-CsOnlineAudioFile のリリースのみをプレビューします。</li><li>最新のバージョンのGet-CsOnlineDialInConferencingLanguagesSupportedとImport-CsOnlineAudioFileリモート処理に対応するバージョンと同様/同じように動作する必要があります。</li><li>最新バージョンの Get-CsTenantと Get-CsOnlineUser (-identity パラメーターを使用して実行する場合) は、非推奨のプロパティを出力しない。</li><li>最新バージョンの Get-CsTenant と Get-CsOnlineUser (-identity パラメーターを使用して実行する場合) は、リモート処理カウンターパーツと比較して、いくつかの書式設定が変更されます。</li><li>[Get \| Set \| Grant New \| \| Remove]-CsTeamsAudioConferencingPolicy コマンドレットをリリースします。</li><li>コマンドレットGet-CsOnlineAudioFileおよびRemove-CsOnlineAudioFileリリースします。</li><li>Set-TeamTargetingHierarchy、Remove-TeamTargetingHierarchy、Get-TeamTargetingHierarchyStatus は、ユーザーがGCCできます。</li><li>Get-TeamTargetingHierarchyStatus コマンドによって呼び出されたエンドポイントを修正します。</li>|
| 2021 年 5 月 | [2.3.2-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.2-preview) |<li>Connect-MicrosoftTeams を使用した AccessToken ログインのサポート。 トークンの配列を受け入れる -AccessTokens パラメーターを追加しました。 AccessTokens Teamsを使用する場合は、MSGraph とリソース トークンが必要です。</li><li>AadAccessToken パラメーターと MsAccessToken パラメーターを削除しました。</li>|
| 2021 年 5 月 | [2.3.1](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.1) |<li>から更新します。NETCore 2.1 から 3.1</li><li>ユーザーとグループの複数の geo リージョンを取得するコマンドレットを追加しました</li><li>-AccountId とアカウント ID を使用する統合 Windows 認証のConnect-MicrosoftTeams</li><li>TeamsCallHoldPolicy コマンドレットが利用可能に</li><li>多くのコマンドの入力パラメーターと出力形式の更新</li><li>リモート処理コマンド中の大きな待機時間の問題を修正しました</li><li>GA カスタム パッケージ機能</li>|
| 2021 年 4 月 | [2.2.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.2.0-preview) | <li>-AccountId を Windows-MicrosoftTeams と組み合Connect統合認証を修正しました。</li><li>ユーザーに送信できる変更通知イベントの合計の詳細を取得するコマンドレットを追加しました。</li><li>ユーザーとグループのマルチ geo リージョンを取得するコマンドレットを追加しました。</li><li>TeamsEnvironment 名に渡される値の処理では、大文字と小文字が区別されます。 これは修正されました。</li><li>単体テストを容易にするためのモジュール内のリモート セッション管理の主なリファクタリング。 テナント管理者の機能の変更は行う必要はありません。</li>|
| 2021 年 4 月 | [2.1.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.1.0-preview) | <li>一部のリモート処理コマンドレット (Get-CsTeamsNetworkRoamingPolicy、Get-CsTeamsMeetingPolicy、Get-CsTeamsMessagingPolicy など) の出力書式を修正しました。</li><li>ポリシー管理コマンドレットのパラメーター 一覧を更新しました。</li>|
| 2021 年 3 月 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>認証と承認に MSAL を&する</li> <li>Connect-MicrosoftTeamsは、すべてのコマンドレットのエントリ ポイントです。</li><li>New-csOnlineSession は使用できなくなりました。 Connect-MicrosoftTeams に置き換えました。</li><li>Enable-csonlinesessionforreconnection は不要です。 この機能は、PowerShell モジュールでTeams実装されています。</li> <li>リファクタリングされたポリシー パッケージ コマンドレットとグループ パッケージの割り当ての追加</li><li>このコマンドレットの大幅なパフォーマンスGet-Team強化</li> <li>既存のコマンドレットのログ記録とデバッグ オプションの改善 </li> <li>テンプレート管理コマンドレットを追加しました</li> <li>非推奨のNew-CsOnlineSession</li>|
| 2021 年 2 月 | [1.1.11-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>テンプレート管理コマンドレットを追加しました</li><li>このコマンドレットの Mezzo とバッチ処理Get-Team強化</li> <li>既存のコマンドレットのログ記録とデバッグ オプションの改善 </li> <li>リファクタリングされたポリシー パッケージコマンドレット</li>|
| 2020 年 12 月 | [1.1.10-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>再試行回数とスリープ時間が長い New-team コマンドレットの更新</li>|
| 2020 年 12 月 | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Skype for Business Online 統合の更新プログラム</li><li>重複するプロンプトが表示される問題を修正Connect-Microsoft Teams</li>|
| 2020 年 11 月 | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>カスタム ポリシー パッケージ コマンドレットを追加します。</li><li>ターゲット階層のアップロード コマンドの修正</li>|
| 2020 年 11 月 | [1.1.7-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>認証と承認に MSAL を&する</li><li>リファクタリングされたポリシー パッケージ コマンドレットとグループ パッケージの割り当ての追加</li><li>非同期モデルを使用するためにリファクタリングされたターゲット階層のアップロード コマンド</li> <li>ユーザーは、-credential パラメーターを使用しない場合、初期認証中に 2 回メッセージが表示されます。 ユーザーは、-credential パラメーターを使用して資格情報を渡して、プロンプトが重複しないようにすることができます。 この動作は、次のリリースで修正される予定です。</li> |
| 2020 年 9 月 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Skype for Business Online Connector の統合</li> |
| 2020 年 9 月 | [1.1.5-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Skype for Business Online Connector の統合</li> |
| 2020 年 7 月 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>グループ ポリシー割 [り当てコマンドレットを追加しました](./assign-policies-users-and-groups.md#assign-a-policy-to-a-group)</li> |
| 2020 年 6 月 | [1.1.3-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Skype for Business Online Connector の統合<li>Get-Team最適化<li>信頼性の向上</li> |
| 2020 年 6 月 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>コマンドレットのプリロードを追加しました<li>.NET Framework最適化</li>   |
| 2020 年 4 月 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Authenticode とアセンブリの署名<li>追加Get-CsPolicyPackage<li>追加Get-CsUserPolicyPackage<li>追加Get-CsUserPolicyPackageRecommendation<li>追加Grant-CsUserPolicyPackage<li>追加New-CsBatchPolicyPackageAssignmentOperation<li>追加Set-TeamArchivedState<li>追加Set-TeamPicture<li>削除Get-TeamHelp</li>  |
| 2020 年 3 月 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>追加New-CsBatchPolicyAssignmentOperation</li> |
| 2020 年 2 月 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team最適化</li>  |

## <a name="related-topics"></a>関連トピック

[Teams PowerShell の概要](teams-powershell-overview.md)

[Teams Powershell のインストール](teams-powershell-install.md)

[Teams PowerShell での Teams の管理](teams-powershell-managing-teams.md)

[Microsoft Teams コマンドレット リファレンス](/powershell/teams/)

[Skype for Business コマンドレット リファレンス](/powershell/skype/intro)
