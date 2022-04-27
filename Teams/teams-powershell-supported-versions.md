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
description: Microsoft Teamsの管理に使用されるTeams PowerShell モジュールでサポートされているバージョンについて説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: c97e3c840452a20be60d6f27e2bf4c3375322be1
ms.sourcegitcommit: bd05783dfb33a63e0eb083a2135f97d110dc81a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2022
ms.locfileid: "65059418"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams PowerShell モジュール - サポートされているバージョン

4.x.x シリーズ以降の powerShell モジュール (TPM) バージョンMicrosoft Teams、今後サポートされる唯一のバージョンになります。 以前のすべてのバージョンは廃止パスにあります。 PowerShell モジュールTeams最新バージョンに更新することをお勧めします。



## <a name="new-organizations"></a>新しい組織

新しくTeamsにオンボードした組織は、2022 年 4 月 1 日から 4.x.x シリーズ以降の powerShell モジュールTeamsのみ使用できます。



## <a name="current-organizations-non-tpm-active"></a>現在の組織 (TPM 以外のアクティブ)

過去 3 か月間 (1 月 22 日から 3 月 22 日) Teams PowerShell モジュールを使用していない組織は、2022 年 4 月 1 日から 4.x.x シリーズ以降のTeams PowerShell モジュールのみを使用できます。



## <a name="current-organizations-tpm-active"></a>現在の組織 (TPM アクティブ)

過去 3 か月間 (1 月 22 日から 3 月 22 日) にTeams PowerShell モジュールを使用している組織は、2022 年 6 月 15 日から 4.x.x シリーズ以降のTeams PowerShell モジュールのみを使用できます。 参照用のメッセージ センターの投稿 - MC350371。 



## <a name="important-notes"></a>重要な注意事項

- Teams PowerShell モジュールのすべてのバージョンのリリース ノートについては、[powerShell のリリース ノートTeams](teams-powershell-release-notes.md)参照してください。

- PowerShell モジュールを更新するには、モジュールのインストールに使用するのと同じ方法を使用する必要があります。 たとえば、最初に Install-Module を使用していた場合は、 [Update-Module](/powershell/module/powershellget/update-module) を使用して最新バージョンを取得する必要があります。  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   PowerShell モジュール バージョン 1.1.6 Teamsから更新する場合は、スクリプトを更新して`Connect-MicrosoftTeams``New-CsOnlineSession`、 .

-   更新中は、TPM 4.x.x/3.x.x.x を 3.0.0 より前のバージョンと共に使用しないことをお勧めします。 たとえば、同じ組織内のさまざまな管理者操作でバージョン 4.x.x & 2.6.0 をまとめて使用することはお勧めしません。 

- 関連する変更
  * TPM 3.x.x 以降でのGet-CsOnlineUser & Get-CsOnlineVoiceUserの更新 – [Get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlineuser) &  (メッセージ センターポスト – MC340774) の詳細。[](/powershell/module/skype/get-csonlinevoiceuser)

  * 電話番号の割り当てに関する変更 - [Set-CsUser](/powershell/module/skype/set-csuser)、[Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser)、[Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) &  (メッセージ センターポスト – MC316139) の詳細。[](/powershell/module/skype/set-csonlinevoiceapplicationinstance)
  
  * Get-CsTenantのパラメーターの変更 - [Get-CsTenant](/powershell/module/skype/get-cstenant) の詳細。  

-   TPM 4.x.x 以降を使用している間は、 [以下](#deprecated-cmdlets)で説明する非推奨またはサポートされていないコマンドレットは使用しないことをお勧めします。 



## <a name="deprecated-cmdlets"></a>非推奨のコマンドレット

- 最近非推奨になったコマンドレットの一部を次に示します。 同じ詳細については、それぞれのパブリック ドキュメントを参照してください。 
  * [Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  * [Get-CsOnlineDialInConferencingUserInfo](/powershell/module/skype/get-csonlinedialinconferencinguserinfo)、 [Get-CsOnlineDialInConferencingUserState](/powershell/module/skype/get-csonlinedialinconferencinguserstate)、 [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/enable-csonlinedialinconferencinguser)、 [Disable-CsOnlineDialInConferencingUser](/powershell/module/skype/disable-csonlinedialinconferencinguser)
  * [Get-CsOnlineDirectoryTenant](/powershell/module/skype/get-csonlinedirectorytenant)
  * [New-CsOnlineAudioFile](/powershell/module/skype/new-csonlineaudiofile)
  * [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint)、 [Set-CsOnlineApplicationEndpoint](/powershell/module/skype/set-csonlineapplicationendpoint)、 [New-CsOnlineApplicationEndpoint](/powershell/module/skype/new-csonlineapplicationendpoint)、 [Remove-CsOnlineApplicationEndpoint](/powershell/module/skype/remove-csonlineapplicationendpoint)
  * [Get-CsOnlineTelephoneNumberInventoryCities](/powershell/module/skype/get-csonlinetelephonenumberinventorycities), [Get-CsOnlineTelephoneNumberInventoryAreas](/powershell/module/skype/get-csonlinetelephonenumberinventoryareas), [Get-CsOnlineTelephoneNumberInventoryCountries](/powershell/module/skype/get-csonlinetelephonenumberinventorycountries)、 [Get-CsOnlineTelephoneNumberInventoryRegions](/powershell/module/skype/get-csonlinetelephonenumberinventoryregions)、 [Get-CsOnlineTelephoneNumberInventoryTypes](/powershell/module/skype/get-csonlinetelephonenumberinventorytypes)、 [Search-CsOnlineTelephoneNumberInventory](/powershell/module/skype/search-csonlinetelephonenumberinventory)、 [Select-CsOnlineTelephoneNumberInventory](/powershell/module/skype/select-csonlinetelephonenumberinventory)、 [Get-CsOnlineTelephoneNumberAvailableCount](/powershell/module/skype/get-csonlinetelephonenumberavailablecount)、 [Clear-CsOnlineTelephoneNumberReservation](/powershell/module/skype/clear-csonlinetelephonenumberreservation), [Get-CsOnlineTelephoneNumberReservationsInformation](/powershell/module/skype/get-csonlinetelephonenumberreservationsinformation), [Get-CsOnlineDirectoryTenantNumberCities](/powershell/module/skype/get-csonlinedirectorytenantnumbercities)  
  * [Set-CsTeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy)、 [New-CsTeamsAppSetupPolicy](/powershell/module/skype/new-csteamsappsetuppolicy)、 [Set-CsTeamsAppPermissionPolicy](/powershell/module/skype/set-csteamsapppermissionpolicy)、 [New-CsTeamsAppPermissionPolicy](/powershell/module/skype/new-csteamsapppermissionpolicy)
  * [Test-CsOnlineLisCivicAddress](/powershell/module/skype/test-csonlineliscivicaddress)


- Microsoft Teamsシナリオでサポートされていないコマンドレットと関連するコマンドレットを次に示します。 
  * [Get|Set]-CsUserPstnSettings
  * [Get|Set|有効にする|Disable]-CsMeetingRoom
  * [Grant|Get|Set|新規|Remove]-CsConferencingPolicy
  * [Grant|Get|Set|新規|Remove]-CsClientPolicy
  * [Grant|Get]-CsHostedVoicemailPolicy
  * [Grant|Get|Set|新規|Remove]-CsMobilityPolicy
  * [Grant|Get] CsVoiceRoutingPolicy
  * [Grant|Get]-CsBroadcastMeetingPolicy
  * [Grant|Get]-CsCloudMeetingPolicy
  * [Grant|Get]-CsGraphPolicy
  * [Grant|Get|Set|新規|Remove]-CsExternalUserCommunicationPolicy
  * [Grant|Get|Set]-CsIPPhonePolicy
  * Get-CsUserServicesPolicy
  * [Get|Set]-CsBroadcastMeetingConfiguration
  * [Get|Set]-CsOAuthConfiguration
  * [Get|Set]-CsMeetingConfiguration
  * [Get|Set]-CsTenantHybridConfiguration
  * [Get|Set]-CsPushNotificationConfiguration
  * [Get|Set]-CsUCPhoneConfiguration
  * Get-CsImFilterConfiguration
  * Get-CsAudioConferencingProvider
  * [Get|Set]-CsTenantPublicProvider
  * Get-CsHostingProvider
  * [Get|Set|登録|登録解除]-CsHybridPSTNAppliance
  * [Get|Set|新規|Remove]-CsHybridPSTNSite
  * [Get|Set]- CsHybridMediationServer
  * [Get|Set|新規|Remove]-CsTenantUpdateTimeWindow
  * Get-CsUserLocationStatus
  * Invoke-CsUcsRollback
  * [Get|Set|新規|Remove]-CsTeamsPinnedApp
  * [Get|Set|新規|Remove]-CsTenantCatalogApp
  * [Get|Set|新規|Remove]-CsGlobalCatalogApp
  * [Get|Set|新規|Remove]-CsDefaultCatalogApp
  * [Get|Set|新規|Remove]-CsTeamsAppPreset



## <a name="related-topics"></a>関連項目

[PowerShell リリース ノートをTeamsする](teams-powershell-release-notes.md)

[PowerShell Microsoft Teamsインストールする](teams-powershell-install.md)

[Teams PowerShell でTeamsを管理する](teams-powershell-managing-teams.md)

[Microsoft Teams コマンドレット リファレンス](/powershell/module/teams) 

[Skype for Business コマンドレット リファレンス](/powershell/module/skype) 
