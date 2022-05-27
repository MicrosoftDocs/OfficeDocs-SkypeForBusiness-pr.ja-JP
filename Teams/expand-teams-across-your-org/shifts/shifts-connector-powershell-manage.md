---
title: PowerShell を使用して、Blue Yonder Workforce Management への Shifts 接続を管理する
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: PowerShell を使用して、Blue Yonder Workforce Management への Shifts 接続を管理する方法について説明します。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: a102001c9c35b3d93467a9955329ce9d314532d0
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675369"
---
# <a name="use-powershell-to-manage-your-shifts-connection-to-blue-yonder-workforce-management"></a>PowerShell を使用して、Blue Yonder Workforce Management への Shifts 接続を管理する

## <a name="overview"></a>概要

[Blue Yonder 用の Microsoft Teams Shifts コネクタ](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder)を使用すると、Microsoft Teamsの Shifts アプリを Blue Yonder Workforce Management (Blue Yonder WFM) と統合できます。 接続を設定すると、フロントライン ワーカーは、Shifts 内から Blue Yonder WFM でスケジュールをシームレスに表示および管理できます。

Microsoft 365 管理センターまたは [PowerShell](shifts-connector-blue-yonder-powershell-setup.md) で [Shifts コネクタ ウィザード](shifts-connector-wizard.md)を使用して接続を設定できます。 接続が設定されたら、 [Shifts コネクタの PowerShell コマンドレット](#shifts-connector-cmdlets)を使用して管理します。

この記事では、PowerShell を使用して次の操作を行う方法について説明します。

- [接続セットアップの状態を確認する](#check-connection-setup-status)
- [接続のエラー レポートを表示する](#view-an-error-report-for-a-connection)
- [接続エラーを解決する](#resolve-connection-errors)
- [接続設定を変更する](#change-connection-settings)
- [ある接続からチームのマップを解除し、別の接続にマップする](#unmap-a-team-from-one-connection-and-map-it-to-another-connection)
- [接続の同期を無効にする](#disable-sync-for-a-connection)

> [!NOTE]
> この記事では、ウィザードまたは PowerShell を使用して、Blue Yonder WFM への接続を既に設定していることを前提としています。

## <a name="before-you-begin"></a>はじめに

[!INCLUDE [shifts-connector-admin-role](../../includes/shifts-connector-admin-role.md)]

## <a name="set-up-your-environment"></a>環境を設定する

> [!NOTE]
> この記事のコマンドまたはスクリプトを実行する前に、次の手順に従って環境を設定してください。

[!INCLUDE [shifts-connector-set-up-environment](../../includes/shifts-connector-set-up-environment.md)]

7. TeamsにConnectします。

    ```powershell
    Connect-MicrosoftTeams
    ```

    メッセージが表示されたら、管理者の資格情報を使用してサイン インします。 この記事のスクリプトと Shifts コネクタコマンドレットを実行するように設定しました。

## <a name="check-connection-setup-status"></a>接続セットアップの状態を確認する

<a name="setup_status"> </a>

電子メールで受信した操作 ID を使用して設定した接続の状態を確認するには、

1. [環境を設定します](#set-up-your-environment) (まだ設定していない場合)。
1. 次のコマンドを実行します。 このコマンドは、接続のチーム マッピングの全体的な状態を示します。

    ``` powershell
    Get-CsTeamsShiftsConnectionOperation -OperationId <YourOperationId>
    ```

詳細については、「 [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation)」を参照してください。

## <a name="view-an-error-report-for-a-connection"></a>接続のエラー レポートを表示する

<a name="error_report"> </a>

接続のエラーの詳細を示すレポートを実行できます。 レポートには、成功と失敗したチームとユーザーのマッピングが一覧表示されます。 また、接続に関連付けられているアカウントに関連するすべての問題に関する情報も提供されます。

1. [環境を設定します](#set-up-your-environment) (まだ設定していない場合)。
1. 接続のエラー レポートの一覧を取得します。

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. 特定のエラー レポートを表示するには、次のコマンドを実行します。

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ErrorReportId <ErrorReportId>
    ```

詳細については、「 [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport)」を参照してください。

## <a name="resolve-connection-errors"></a>接続エラーを解決する

### <a name="user-mapping-errors"></a>ユーザー マッピング エラー

Blue Yonder WFM サイトの 1 人以上のユーザーが、Teamsのマップされたチームのメンバーでない場合、ユーザー マッピング エラーが発生する可能性があります。 この問題を解決するには、マップされたチームのユーザーが Blue Yonder WFM サイトのユーザーと一致していることを確認します。

マップされていないユーザーの詳細を表示するには、(まだない場合は) [環境を設定](#set-up-your-environment) し、次のスクリプトを実行します。

```powershell
#View sync errors script
Write-Host "View sync errors"
Start-Sleep 1

#Ensure Teams module is of version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#List connection instances available
Write-Host "Listing connection instances"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Get an instance
if ($InstanceList.Count -gt 0){
    $InstanceId = Read-Host -Prompt 'Input the instance ID that you want to retrieve user sync results from'
}
else {
    throw "Instance list is empty"
}

#Get a list of the mappings
Write-Host "Listing team mappings"
$mappings = Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId
write $mappings

#For each mapping, retrieve the failed mappings
ForEach ($mapping in $mappings){
    $teamsTeamId = $mapping.TeamId
    $wfmTeamId = $mapping.WfmTeamId
    Write-Host "Failed mapped users in the mapping of ${teamsTeamId} and ${wfmTeamId}:"
    $userSyncResult = Get-CsTeamsShiftsConnectionSyncResult -ConnectorInstanceId $InstanceId -TeamId $teamsTeamId
    Write-Host "Failed AAD users:"
    write $userSyncResult.FailedAadUser
    Write-Host "Failed WFM users:"
    write $userSyncResult.FailedWfmUser
}
```

### <a name="account-authorization-errors"></a>アカウント承認エラー

Blue Yonder WFM サービス アカウントまたはMicrosoft 365システム アカウントの資格情報が正しくない場合、または必要なアクセス許可がない場合、アカウント承認エラーが発生する可能性があります。

接続の Blue Yonder WFM サービス アカウントまたはMicrosoft 365システム アカウント資格情報を変更するには、[Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance) コマンドレットを実行するか、この記事の[[接続設定の変更](#change-connection-settings)] セクションの PowerShell スクリプトを使用します。

## <a name="change-connection-settings"></a>接続設定を変更する
<a name="change_settings"> </a>

このスクリプトを使用して接続設定を変更します。 変更できる設定には、Blue Yonder WFM サービス アカウントとパスワード、Microsoft 365 システム アカウント、チーム マッピング、同期設定が含まれます。

同期設定には、同期頻度 (分単位) と、Blue Yonder WFM と Shifts の間で同期されるスケジュール データが含まれます。 スケジュール データは、 [Get-CsTeamsShiftsConnectionConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector) を実行して表示できる次のパラメーターで定義されています。

- **enabledConnectorScenarios** パラメーターは、Blue Yonder WFM から Shifts に同期されるデータを定義します。 オプションは `Shift`、 , , `SwapRequest``UserShiftPreferences`, `OpenShift`, `TimeOff``OpenShiftRequest``TimeOffRequest`, .
- **enabledWfiScenarios** パラメーターは、Shifts から Blue Yonder WFM に同期されるデータを定義します。 オプションは `SwapRequest`、 、 `OpenShiftRequest`、 `TimeOffRequest`. `UserShiftPreferences`

    > [!NOTE]
    > オープン シフト、オープン シフト要求、スワップ要求、または Shifts と Blue Yonder WFM の間で休暇要求を同期しない場合は、Shifts で機能を非表示にするには、別の手順を実行する必要があります。 このスクリプトを実行した後は、この記事の後半の「 [オープン シフトを無効にする、シフト要求を開く、要求をスワップする、および休暇要求を無効にする](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) 」セクションの手順に従っていることを確認します。

> [!IMPORTANT]
> 変更しない設定の場合は、スクリプトからメッセージが表示されたら、元の設定を再入力する必要があります。

[環境をセットアップし](#set-up-your-environment) (まだない場合)、次のスクリプトを実行します。

```powershell
#Update connector instance and mapping script
Write-Host "Update connector instance and mapping"
Start-Sleep 1

#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#Connect to MS Graph
Connect-MgGraph -Scopes "User.Read.All","Group.ReadWrite.All"

#List connector types available (comment out if not implemented for preview)
Write-Host "Listing connector types available"
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$connectors = Get-CsTeamsShiftsConnectionConnector
write $connectors
$blueYonder = $connectors | where {$_.Id -match $BlueYonderId}

#List connection instances available
Write-Host "Listing connection instances available"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Prompt for the WFM username and password
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Get the instance ID
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$InstanceId = Read-Host -Prompt 'Input the instance ID that you want to update'
$Instance = Get-CsTeamsShiftsConnectionInstance -ConnectorInstanceId $InstanceId
$Etag = $Instance.etag

#Change sync setting
$designatorName = Read-Host -Prompt "Input designated actor's user name"
$designator = Get-MgUser -UserId $designatorName
$teamsUserId = $designator.Id
$UpdatedInstanceName = Read-Host -Prompt 'Input new connection instance name'
$updatedConnectorScenarioString = Read-Host -Prompt 'Input new enabled connector scenarios'
$updatedWfiScenarioString = Read-Host -Prompt 'Input new enabled WFI scenarios'
$Delimiters = ",", ".", ":", ";", " ", "`t"
$updatedConnectorScenario = $updatedConnectorScenarioString -Split {$Delimiters -contains $_}
$updatedConnectorScenario = $updatedConnectorScenario.Trim()
$updatedConnectorScenario = $updatedConnectorScenario.Split('',[System.StringSplitOptions]::RemoveEmptyEntries)
$updatedWfiScenario = $updatedWfiScenarioString -Split {$Delimiters -contains $_}
$updatedWfiScenario = $updatedWfiScenario.Trim()
$updatedWfiScenario = $updatedWfiScenario.Split('', [System.StringSplitOptions]::RemoveEmptyEntries)
$adminApiUrl = $Instance.ConnectorSpecificSettingAdminApiUrl
$cookieAuthUrl = $Instance.ConnectorSpecificSettingCookieAuthUrl
$essApiUrl = $Instance.ConnectorSpecificSettingEssApiUrl
$federatedAuthUrl = $Instance.ConnectorSpecificSettingFederatedAuthUrl
$retailWebApiUrl = $Instance.ConnectorSpecificSettingRetailWebApiUrl
$siteManagerUrl = $Instance.ConnectorSpecificSettingSiteManagerUrl
$syncFreq = Read-Host -Prompt 'Input new sync frequency'

#Read admin email list
[psobject[]]$AdminEmailList = @()
while ($true){
$AdminEmail = Read-Host -Prompt "Enter admin's email to receive error report"
$AdminEmailList += $AdminEmail
$title    = 'Adding another email'
$question = 'Would you like to add another admin email?'
$choices  = '&Yes', '&No'
$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}
$UpdatedInstance = Set-CsTeamsShiftsConnectionInstance -ConnectorId $BlueYonderId -ConnectorInstanceId $InstanceId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -DesignatedActorId $teamsUserId -EnabledConnectorScenario $updatedConnectorScenario -EnabledWfiScenario $updatedWfiScenario -Name $UpdatedInstanceName -SyncFrequencyInMin $syncFreq -IfMatch $Etag -ConnectorAdminEmail $AdminEmailList

#Get a list of the mappings
Write-Host "Listing mappings"
$TeamMaps = Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId
write $TeamMaps

#Modify a mapping
#Remove a mapping
Write-Host "Removing a mapping"
$TeamsTeamId = Read-Host -Prompt 'Input the Teams team ID that you want to unlink'
$WfmTeamId = Read-Host -Prompt 'Input the WFM team ID that you want to unlink'
Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId
Write-Host "Success"

#Add a mapping
Write-Host "Adding a mapping"
$TeamsTeamId = Read-Host -Prompt 'Input the Teams team ID that you want to link'
$WfmTeamId = Read-Host -Prompt 'Input the WFM team ID that you want to link'
New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId -TimeZone "America/Los_Angeles" -WfmTeamId $WfmTeamId
Write-Host "Success"
```

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>オープン シフト、オープン シフト要求、スワップ要求、および休暇要求を無効にする

> [!IMPORTANT]
> この記事の「 [接続設定の変更](#change-connection-settings) 」セクションのスクリプトを使用するか、 [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance) コマンドレットを使用して、オープン シフト、オープン シフト要求、スワップ要求、または休暇要求を無効にすることを選択した場合にのみ、次の手順に従います。 この手順を完了すると、Shifts で機能が非表示になります。 この 2 番目の手順を実行しないと、Shifts で機能が表示され、使用しようとすると"サポートされていない操作" というエラー メッセージが表示されます。

Shifts でオープン シフト、スワップ要求、および休暇要求を非表示にするには、リソース[の種類をスケジュール](/graph/api/resources/schedule)Graph API使用して、Blue Yonder WFM サイトにマップした各チームに対して```false```次のパラメーターを設定します。

- 開いているシフト: ```openShiftsEnabled```
- スワップ要求:  ```swapShiftsRequestsEnabled```
- 休暇要求: ```timeOffRequestsEnabled```

Shifts で開いているシフト要求を非表示にするには、Shifts **の [設定**] に移動し、[**シフトを開く**] 設定をオフにします。

## <a name="unmap-a-team-from-one-connection-and-map-it-to-another-connection"></a>ある接続からチームのマップを解除し、別の接続にマップする

> [!NOTE]
> Microsoft 365 システム アカウントは、両方の接続で同じである必要があります。 そうでない場合は、"この指定されたアクター プロファイルにチーム所有権の特権がありません" というエラー メッセージが表示されます。

ある接続からチームのマップを解除し、別の接続にマップする場合は、次のようにします。

1. [環境を設定します](#set-up-your-environment) (まだ設定していない場合)。
1. 接続のすべてのチーム マッピングの一覧を表示します。

    ```powershell
    Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. 接続からチーム マッピングを削除します。

    ```powershell
    Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId>
    ```

1. チームを別の接続にマップします。

    ```powershell
    New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId> -WfmTeamId <SiteId> -TimeZone <TimeZone>
    ```

詳細については、「 [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap)、 [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap)、 [および New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap)」を参照してください。

## <a name="disable-sync-for-a-connection"></a>接続の同期を無効にする

このスクリプトを使用して、接続の同期を無効にします。 このスクリプトでは、接続が削除または削除されないことに注意してください。 指定した接続に対して Shifts と Blue Yonder WFM の間でデータが同期されないよう、同期がオフになります。

[環境をセットアップし](#set-up-your-environment) (まだない場合)、次のスクリプトを実行します。

```powershell
#Disable sync script
Write-Host "Disable sync"
#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#List connection instances available
Write-Host "Listing connection instances"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Get an instance
if ($InstanceList.Count -gt 0){
    $InstanceId = Read-Host -Prompt 'Input the instance ID that you want to disable sync'
    $Instance = Get-CsTeamsShiftsConnectionInstance -ConnectorInstanceId $InstanceId
    $Etag = $Instance.etag
    $InstanceName = $Instance.Name
    $DesignatedActorId = $Instance.designatedActorId
    $adminApiUrl = $Instance.ConnectorSpecificSettingAdminApiUrl
    $cookieAuthUrl = $Instance.ConnectorSpecificSettingCookieAuthUrl
    $essApiUrl = $Instance.ConnectorSpecificSettingEssApiUrl
    $federatedAuthUrl = $Instance.ConnectorSpecificSettingFederatedAuthUrl
    $retailWebApiUrl = $Instance.ConnectorSpecificSettingRetailWebApiUrl
    $siteManagerUrl = $Instance.ConnectorSpecificSettingSiteManagerUrl
    $ConnectorAdminEmail = $Instance.ConnectorAdminEmail
}
else {
    throw "Instance list is empty"
}

#Remove scenarios in the mapping
Write-Host "Disabling scenarios in the team mapping"
$UpdatedInstanceName = $InstanceName + " - Disabled"
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

$UpdatedInstance = Set-CsTeamsShiftsConnectionInstance -ConnectorId $BlueYonderId -ConnectorInstanceId $InstanceId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -DesignatedActorId $DesignatedActorId -EnabledConnectorScenario @() -EnabledWfiScenario @() -Name $UpdatedInstanceName -SyncFrequencyInMin 60 -IfMatch $Etag -ConnectorAdminEmail $ConnectorAdminEmail

if ($UpdatedInstance.Id -ne $null) {
    Write-Host "Success"
}
else {
    throw "Update instance failed"
}
```

## <a name="shifts-connector-cmdlets"></a>Shifts コネクタコマンドレット

Shifts コネクタ コマンドレットのヘルプについては、[Teams PowerShell コマンドレットリファレンス](/powershell/teams/intro)で **CsTeamsShiftsConnection** を検索してください。 一般的に使用されるコマンドレットへのリンクを次に示します。

- [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation)
- [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance)
- [Get-CsTeamsShiftsConnectionInstance](/powershell/module/teams/get-csteamsshiftsconnectioninstance)
- [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance)
- [Remove-CsTeamsShiftsConnectionInstance](/powershell/module/teams/remove-csteamsshiftsconnectioninstance)
- [Test-CsTeamsShiftsConnectionValidate](/powershell/module/teams/test-csteamsshiftsconnectionvalidate)
- [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap)
- [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap)
- [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap)
- [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector)
- [Get-CsTeamsShiftsConnectionSyncResult](/powershell/module/teams/get-csteamsshiftsconnectionsyncresult)
- [Get-CsTeamsShiftsConnectionWfmUser](/powershell/module/teams/get-csteamsshiftsconnectionwfmuser)
- [Get-CsTeamsShiftsConnectionWfmTeam](/powershell/module/teams/get-csteamsshiftsconnectionwfmteam)
- [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport)
- [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord)

## <a name="related-articles"></a>関連記事

- [コネクタをシフトする](shifts-connectors.md)
- [Shifts コネクタ ウィザードを使用して Shifts を Blue Yonder Workforce Management に接続する](shifts-connector-wizard.md)
- [PowerShell を使用してシフトを Blue Yonder Workforce Management に接続する](shifts-connector-blue-yonder-powershell-setup.md)
- [Shifts アプリを管理する](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Teams での PowerShell の概要](../../teams-powershell-overview.md)
