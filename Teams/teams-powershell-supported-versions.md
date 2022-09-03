---
title: Teams PowerShell モジュール - サポートされているバージョン
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Microsoft Teams の管理に使用される Teams PowerShell モジュールでサポートされているバージョンについて説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: d28e16c248957518ca16eb3eff7e082ebe6bd9bd
ms.sourcegitcommit: 9a9168d5c40bbb0cceaf3ffd11eb104c137f26b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2022
ms.locfileid: "67590324"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams PowerShell モジュール - サポートされているバージョン

4.x.x シリーズ以降の Microsoft Teams PowerShell モジュール (TPM) バージョンは、現在サポートされている唯一のバージョンです。 以前のすべてのバージョンは、2022 年 6 月 15 日以降、商用環境では完全に廃止され、&は機能しなくなります (参考用のメッセージ センターポスト - MC350371)。 

Teams PowerShell モジュールの最新バージョンに更新することをお勧めします。


## <a name="important-notes"></a>重要な注意事項

- Teams PowerShell モジュールのすべてのバージョンのリリース ノートについては、 [Teams PowerShell のリリース ノート](teams-powershell-release-notes.md)を参照してください。

- PowerShell モジュールを更新するには、モジュールのインストールに使用するのと同じ方法を使用する必要があります。 たとえば、最初に Install-Module を使用していた場合は、 [Update-Module](/powershell/module/powershellget/update-module) を使用して最新バージョンを取得する必要があります。

  ```powershell
  Update-Module MicrosoftTeams
  ```

- Teams PowerShell モジュール バージョン 1.1.6 から更新`Connect-MicrosoftTeams``New-CsOnlineSession`する場合は、.

- 更新中は、TPM 4.x.x/3.x.x.x を 3.0.0 より前のバージョンと共に使用しないことをお勧めします。 たとえば、同じ組織内のさまざまな管理者操作でバージョン 4.x.x & 2.6.0 をまとめて使用することはお勧めしません。

- 関連する変更
  - TPM 3.x.x 以降でGet-CsOnlineUser & Get-CsOnlineVoiceUserする更新 – [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) & [Get-CsOnlineVoiceUser](/powershell/module/skype/get-csonlinevoiceuser) (メッセージ センターポスト – MC340774) の詳細を参照してください。

  - 電話番号の割り当てに関する変更 - [Set-CsUser](/powershell/module/skype/set-csuser)、 [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser)、 [Set-CsOnlineApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) & [Set-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlinevoiceapplicationinstance) (メッセージ センターポスト – MC316139) の詳細。

  - Get-CsTenantのパラメーターの変更 - [Get-CsTenant](/powershell/module/skype/get-cstenant) (メッセージ センターポスト – MC365397) の詳細。
  
  - スクリプトで、PSListModifier 型パラメーターで New/Set of Policy または Configuration コマンドレットを使用する場合は、最新バージョン (4.2.0 以降) を使用することをお勧めします。 参照用のメッセージ センターの投稿 - MC397428。

  - [新規|Get]-CsCloudCallDataConnection コマンドレットがバージョン 4.6.0 以降でサポートされるようになりました (メッセージ センターポスト - MC408993)。

- TPM 4.x.x 以降を使用している間は、 [以下](#deprecated-cmdlets)で説明する非推奨またはサポートされていないコマンドレットは使用しないことをお勧めします。

## <a name="deprecated-cmdlets"></a>非推奨のコマンドレット

- 最近非推奨になったコマンドレットの一部を次に示します。 同じ詳細については、それぞれのパブリック ドキュメントを参照してください。
  - [Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  - [Get-CsOnlineDialInConferencingUserInfo](/powershell/module/skype/get-csonlinedialinconferencinguserinfo)、 [Get-CsOnlineDialInConferencingUserState](/powershell/module/skype/get-csonlinedialinconferencinguserstate)、 [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/enable-csonlinedialinconferencinguser)、 [Disable-CsOnlineDialInConferencingUser](/powershell/module/skype/disable-csonlinedialinconferencinguser)
  - [Get-CsOnlineDirectoryTenant](/powershell/module/skype/get-csonlinedirectorytenant)
  - [New-CsOnlineAudioFile](/powershell/module/skype/new-csonlineaudiofile)
  - [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint)、 [Set-CsOnlineApplicationEndpoint](/powershell/module/skype/set-csonlineapplicationendpoint)、 [New-CsOnlineApplicationEndpoint](/powershell/module/skype/new-csonlineapplicationendpoint)、 [Remove-CsOnlineApplicationEndpoint](/powershell/module/skype/remove-csonlineapplicationendpoint)、Switch-CsOnlineApplicationEndpoint
  - [Get-CsOnlineTelephoneNumberInventoryCities](/powershell/module/skype/get-csonlinetelephonenumberinventorycities), [Get-CsOnlineTelephoneNumberInventoryAreas](/powershell/module/skype/get-csonlinetelephonenumberinventoryareas), [Get-CsOnlineTelephoneNumberInventoryCountries](/powershell/module/skype/get-csonlinetelephonenumberinventorycountries)、 [Get-CsOnlineTelephoneNumberInventoryRegions](/powershell/module/skype/get-csonlinetelephonenumberinventoryregions)、 [Get-CsOnlineTelephoneNumberInventoryTypes](/powershell/module/skype/get-csonlinetelephonenumberinventorytypes)、 [Search-CsOnlineTelephoneNumberInventory](/powershell/module/skype/search-csonlinetelephonenumberinventory)、 [Select-CsOnlineTelephoneNumberInventory](/powershell/module/skype/select-csonlinetelephonenumberinventory)、 [Get-CsOnlineTelephoneNumberAvailableCount](/powershell/module/skype/get-csonlinetelephonenumberavailablecount)、 [Clear-CsOnlineTelephoneNumberReservation](/powershell/module/skype/clear-csonlinetelephonenumberreservation), [Get-CsOnlineTelephoneNumberReservationsInformation](/powershell/module/skype/get-csonlinetelephonenumberreservationsinformation), [Get-CsOnlineDirectoryTenantNumberCities](/powershell/module/skype/get-csonlinedirectorytenantnumbercities)
  - [Set-CsTeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy)、 [New-CsTeamsAppSetupPolicy](/powershell/module/skype/new-csteamsappsetuppolicy)、 [Set-CsTeamsAppPermissionPolicy](/powershell/module/skype/set-csteamsapppermissionpolicy)、 [New-CsTeamsAppPermissionPolicy](/powershell/module/skype/new-csteamsapppermissionpolicy)
  - [Test-CsOnlineLisCivicAddress](/powershell/module/skype/test-csonlineliscivicaddress)

- Microsoft Teams のシナリオでサポートされていない/関連しないコマンドレットを次に示します。
  - [Get|Set]-CsUserPstnSettings
  - [Get|Set|有効にする|Disable]-CsMeetingRoom
  - [Grant|Get|Set|新規|Remove]-CsConferencingPolicy
  - [Grant|Get|Set|新規|Remove]-CsClientPolicy
  - [Grant|Get]-CsHostedVoicemailPolicy
  - [Grant|Get|Set|新規|Remove]-CsMobilityPolicy
  - [Grant|Get]-CsVoiceRoutingPolicy
  - [Grant|Get]-CsBroadcastMeetingPolicy
  - [Grant|Get]-CsCloudMeetingPolicy
  - [Grant|Get]-CsGraphPolicy
  - [Grant|Get|Set|新規|Remove]-CsExternalUserCommunicationPolicy
  - [Grant|Get|Set]-CsIPPhonePolicy
  - Get-CsUserServicesPolicy
  - [Get|Set]-CsBroadcastMeetingConfiguration
  - [Get|Set]-CsOAuthConfiguration
  - [Get|Set]-CsMeetingConfiguration
  - [Get|Set]-CsTenantHybridConfiguration
  - [Get|Set]-CsPushNotificationConfiguration
  - [Get|Set]-CsUCPhoneConfiguration
  - Get-CsImFilterConfiguration
  - Get-CsAudioConferencingProvider
  - [Get|Set]-CsTenantPublicProvider
  - Get-CsHostingProvider
  - [Get|Set|登録|登録解除]-CsHybridPSTNAppliance
  - [Get|Set|新規|Remove]-CsHybridPSTNSite
  - [Get|Set]-CsHybridMediationServer
  - [Get|Set|新規|Remove]-CsTenantUpdateTimeWindow
  - Get-CsUserLocationStatus
  - Invoke-CsUcsRollback
  - [Get|Set|新規|Remove]-CsTeamsPinnedApp
  - [Get|Set|新規|Remove]-CsTenantCatalogApp
  - [Get|Set|新規|Remove]-CsGlobalCatalogApp
  - [Get|Set|新規|Remove]-CsDefaultCatalogApp
  - [Get|Set|新規|Remove]-CsTeamsAppPreset
  - Invoke-CsUserPreferredDataLocationSync
  - [Get|Set]-CsTeamsUpgradeStatus
  - Grant-CsPolicy
  - Set-CsOnlineDirectoryUser

## <a name="related-topics"></a>関連項目

[Teams PowerShell リリース ノート](teams-powershell-release-notes.md)

[Microsoft Teams PowerShell をインストールする](teams-powershell-install.md)

[Teams PowerShell を使用して Teams を管理する](teams-powershell-managing-teams.md)

[Microsoft Teams コマンドレット リファレンス](/powershell/module/teams)

[Skype for Business コマンドレット リファレンス](/powershell/module/skype)
