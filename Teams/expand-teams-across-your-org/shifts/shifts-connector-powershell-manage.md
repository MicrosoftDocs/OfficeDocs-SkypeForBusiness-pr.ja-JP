---
title: PowerShell を使用して Blue Yonder Workforce Management へのシフト接続を管理する
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: PowerShell を使用して、Blue Yonder Workforce Management へのシフト接続を管理する方法について説明します。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: e666117b31064697f9ef41299574935109015aba
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593659"
---
# <a name="use-powershell-to-manage-your-shifts-connection-to-blue-yonder-workforce-management"></a>PowerShell を使用して Blue Yonder Workforce Management へのシフト接続を管理する

## <a name="overview"></a>概要

[Blue Yonder Microsoft Teams Shifts](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) コネクタを使用すると、Microsoft Teams の Shifts アプリを Blue Yonder Workforce Management (Blue Yonder WFM) と統合できます。 接続を設定すると、フロントラインワーカーは、シフト内から Blue Yonder WFM でスケジュールをシームレスに表示および管理できます。

Microsoft 365 管理センター [または PowerShell で Shifts](shifts-connector-wizard.md) コネクタ ウィザードを使用して接続を設定[](shifts-connector-blue-yonder-powershell-setup.md)できます。 接続を設定した後は、 [Shifts コネクタの PowerShell コマンドレットを使用して接続を管理します](#shifts-connector-cmdlets)。

この記事では、PowerShell を使用して次の操作を行う方法について説明します。

- [接続設定の状態を確認する](#check-connection-setup-status)
- [接続のエラー レポートを表示する](#view-an-error-report-for-a-connection)
- [接続エラーを解決する](#resolve-connection-errors)
- [接続設定を変更する](#change-connection-settings)
- [ある接続からチームのマップを解除し、別の接続にマップする](#unmap-a-team-from-one-connection-and-map-it-to-another-connection)
- [接続の同期を無効にする](#disable-sync-for-a-connection)

> [!NOTE]
> この記事では、ウィザードまたは PowerShell を使用して、Blue Yonder WFM への接続を既に設定済みである必要があります。

## <a name="before-you-begin"></a>はじめに

[!INCLUDE [shifts-connector-admin-role](../../includes/shifts-connector-admin-role.md)]

## <a name="set-up-your-environment"></a>環境を設定する

> [!NOTE]
> この記事のコマンドまたはスクリプトを実行する前に、次の手順に従って環境を設定してください。

[!INCLUDE [shifts-connector-set-up-environment](../../includes/shifts-connector-set-up-environment.md)]

## <a name="check-connection-setup-status"></a>接続設定の状態を確認する
<a name="setup_status"> </a>

メールで受信した操作 ID を使用して設定した接続の状態を確認するには、次の操作を行います。

1. [環境を設定します](#set-up-your-environment) (まだ設定していない場合)。
1. 次のコマンドを実行します。 このコマンドは、接続のチーム マッピングの全体的な状態を示します。

    ``` powershell
    Get-CsTeamsShiftsConnectionOperation -OperationId <YourOperationId>
    ```

詳細については、「 [Get-CsTeamsShiftsConnectionOperation」を参照してください](/powershell/module/teams/get-csteamsshiftsconnectionoperation?view=teams-ps)。

## <a name="view-an-error-report-for-a-connection"></a>接続のエラー レポートを表示する
<a name="error_report"> </a>

接続のエラーの詳細を表示するレポートを実行できます。 このレポートには、成功と失敗のチーム マッピングとユーザー マッピングが一覧表示されます。 また、接続に関連付けられているアカウントに関連する問題に関する情報も提供します。

1. [環境を設定します](#set-up-your-environment) (まだ設定していない場合)。
1. 接続のエラー レポートの一覧を取得します。

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. 特定のエラー レポートを表示するには、次のコマンドを実行します。

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ErrorReportId <ErrorReportId>
    ```

詳細については、「 [Get-CsTeamsShiftsConnectionErrorReport」を参照してください](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport?view=teams-ps)。

## <a name="resolve-connection-errors"></a>接続エラーを解決する

### <a name="user-mapping-errors"></a>ユーザー マッピング エラー

Blue Yonder WFM サイトの 1 人または複数のユーザーが、マップされたチームのメンバーではない場合、ユーザー マッピング エラーがTeams。 この問題を解決するには、マップされたチームのユーザーが Blue Yonder WFM サイトのユーザーと一致する必要があります。

未設定のユーザーの詳細を表示するには、 [環境を設定](#set-up-your-environment) し (まだ設定していない場合)、次のスクリプトを実行します。

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

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

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

Blue Yonder WFM サービス アカウントまたは Microsoft 365 システム アカウントの資格情報が正しくないか、必要なアクセス許可を持たなかった場合、アカウント承認エラーが発生する可能性があります。

接続の Blue Yonder WFM サービス アカウントまたは Microsoft 365 システム アカウントの資格情報を変更するには、[Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps) コマンドレットを実行するか、この記事の「接続設定の変更」セクションの [](#change-connection-settings) PowerShell スクリプトを使用します。

## <a name="change-connection-settings"></a>接続設定を変更する
<a name="change_settings"> </a>

このスクリプトを使用して、接続設定を変更します。 設定、Blue Yonder WFM サービス アカウントとパスワード、Microsoft 365、チーム マッピング、同期設定を変更できます。

同期設定には、同期頻度 (分) と、Blue Yonder WFM と Shifts の間で同期されるスケジュール データが含まれます。 スケジュール データは次のパラメーターで定義されています。このパラメーターは [、Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps) を実行して表示できます。

- **enabledConnectorScenarios** パラメーターは、Blue Yonder WFM から Shifts に同期されるデータを定義します。 オプションは `Shift`、、 `SwapRequest`、 `UserShiftPreferences`、 `OpenShift`、 `OpenShiftRequest`、 `TimeOff`、 です `TimeOffRequest`。
- **enabledWfiScenarios** パラメーターは、Shifts から Blue Yonder WFM に同期されるデータを定義します。 オプションは、 `SwapRequest`、 `OpenShiftRequest`、 `TimeOffRequest`、 です `UserShiftPreferences`。

    > [!NOTE]
    > Shifts と Blue Yonder WFM の間で、開いているシフト、オープン シフト要求、スワップ要求、またはタイムオフ要求を同期しない場合は、Shifts で機能を非表示にする別の手順があります。 このスクリプトを実行した後、この記事の後半の「オープン [](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) シフトを無効にする、シフト要求、スワップ要求、およびタイムオフ要求を開く」セクションの手順に従ってください。

> [!IMPORTANT]
> 変更しない設定の場合は、スクリプトの入力を求めるメッセージが表示されたら、元の設定を再入力する必要があります。

[環境をセットアップ](#set-up-your-environment) し (まだ設定していない場合)、次のスクリプトを実行します。

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

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

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

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>オープン シフトを無効にする、シフトを開く要求、スワップ要求、およびタイムオフ要求

> [!IMPORTANT]
> この記事の前の「接続設定の変更」セクションのスクリプトを使用するか[、Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps) コマンドレット[](#change-connection-settings)を使用して、オープン シフトの無効化、シフト要求のオープン、スワップ要求、またはタイムオフ要求を選択した場合にのみ、次の手順に従います。 この手順を完了すると、Shifts の機能が非表示になります。 この 2 番目の手順を実行しない場合でも、ユーザーには Shifts の機能が表示され、使用しようとして "サポートされていない操作" エラー メッセージが表示されます。

Shifts で開いているシフト、スワップ要求、およびタイムオフ要求を非表示にする場合は、Graph API [](/graph/api/resources/schedule?view=graph-rest-1.0) ```false``` スケジュール リソースの種類を使用して、Blue Yonder WFM サイトにマップした各チームに対して次のパラメーターを に設定します。

- シフトを開く: ```openShiftsEnabled```
- スワップ要求:  ```swapShiftsRequestsEnabled```
- [Time off requests]を選択します。 ```timeOffRequestsEnabled```

Shifts で開いているシフト要求を非表示にする場合は、Shifts 設定 に移動し、[シフトを開く] 設定 **をオフ** にします。

## <a name="unmap-a-team-from-one-connection-and-map-it-to-another-connection"></a>ある接続からチームのマップを解除し、別の接続にマップする

> [!NOTE]
> 両方Microsoft 365システム アカウントは同じである必要があります。 指定されていない場合は、"この指定されたアクター プロファイルにはチームの所有権権限が与え" というエラー メッセージが表示されます。

ある接続からチームのマッピングを解除し、別の接続にマップする場合:

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

詳細については、「 [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap?view=teams-ps)」、 [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap?view=teams-ps)、 [および New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap?view=teams-ps) を参照してください。

## <a name="disable-sync-for-a-connection"></a>接続の同期を無効にする

このスクリプトを使用して、接続の同期を無効にします。 このスクリプトは接続を削除したり削除したりしないので、念頭に置いておきます。 指定した接続について、Shifts と Blue Yonder WFM の間でデータが同期されなく、同期がオフになります。

[環境をセットアップ](#set-up-your-environment) し (まだ設定していない場合)、次のスクリプトを実行します。

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

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

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

Shifts コネクタ コマンドレットのヘルプについては、「PowerShell コマンドレット リファレンス」の **CsTeamsShiftsConnection** [Teams検索してください](/powershell/teams/intro?view=teams-ps)。 一般的に使用されるコマンドレットへのリンクを次に示します。

- [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation?view=teams-ps)
- [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance?view=teams-ps)
- [Get-CsTeamsShiftsConnectionInstance](/powershell/module/teams/get-csteamsshiftsconnectioninstance?view=teams-ps)
- [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps)
- [Remove-CsTeamsShiftsConnectionInstance](/powershell/module/teams/remove-csteamsshiftsconnectioninstance?view=teams-ps)
- [Test-CsTeamsShiftsConnectionValidate](/powershell/module/teams/test-csteamsshiftsconnectionvalidate?view=teams-ps)
- [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap?view=teams-ps)
- [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap?view=teams-ps)
- [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap?view=teams-ps)
- [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps)
- [Get-CsTeamsShiftsConnectionSyncResult](/powershell/module/teams/get-csteamsshiftsconnectionsyncresult?view=teams-ps)
- [Get-CsTeamsShiftsConnectionWfmUser](/powershell/module/teams/get-csteamsshiftsconnectionwfmuser?view=teams-ps)
- [Get-CsTeamsShiftsConnectionWfmTeam](/powershell/module/teams/get-csteamsshiftsconnectionwfmteam?view=teams-ps)
- [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport?view=teams-ps)
- [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord?view=teams-ps)

## <a name="related-articles"></a>関連記事

- [コネクタをシフトする](shifts-connectors.md)
- [Shifts コネクタ ウィザードを使用して Shifts を Blue Yonder Workforce Management に接続する](shifts-connector-wizard.md)
- [PowerShell を使用してシフトを Blue Yonder Workforce Management に接続する](shifts-connector-blue-yonder-powershell-setup.md)
- [Shifts アプリを管理する](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Teams での PowerShell の概要](../../teams-powershell-overview.md)