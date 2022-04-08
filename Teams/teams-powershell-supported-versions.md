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
ms.openlocfilehash: c9eb6754a9fa89d1298e22f6c713e8c4d28d5861
ms.sourcegitcommit: 708b489a7dca7fd9e5e9b1ec88c9aba79ecafe5f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2022
ms.locfileid: "64712961"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams PowerShell モジュール - サポートされているバージョン

4.x.x シリーズ以上の PowerShell モジュール (TPM) バージョンMicrosoft Teams、今後サポートされる唯一のバージョンになります。 以前のすべてのバージョンは廃止パスにあります。 PowerShell モジュールTeams最新バージョンに更新することをお勧めします。



## <a name="new-organizations"></a>新しい組織

新しくTeamsにオンボードした組織は、2022 年 4 月 1 日から 4.x.x シリーズ以上の PowerShell モジュールTeamsのみ使用できます。



## <a name="current-organizations-non-tpm-active"></a>現在の組織 (TPM 以外のアクティブ)

過去 3 か月間 (1 月 22 日から 3 月 22 日) Teams PowerShell モジュールを使用していない組織は、2022 年 4 月 1 日から 4.x.x シリーズ以上の powerShell モジュールTeamsのみ使用できます。



## <a name="current-organizations-tpm-active"></a>現在の組織 (TPM アクティブ)

過去 3 か月間 (1 月 22 日から 3 月 22 日) Teams PowerShell モジュールを使用している組織は、2022 年 6 月 15 日から 4.x.x シリーズ以上の powerShell モジュールTeamsのみ使用できます。 参照用のメッセージ センターの投稿 - MC350371。 



## <a name="important-notes"></a>重要な注意事項

- Teams PowerShell モジュールのすべてのバージョンのリリース ノートについては、[powerShell のリリース ノートTeams](teams-powershell-release-notes.md)参照してください。

- PowerShell モジュールを更新するには、モジュールのインストールに使用するのと同じ方法を使用する必要があります。 たとえば、最初に Install-Module を使用していた場合は、 [Update-Module](/powershell/module/powershellget/update-module) を使用して最新バージョンを取得する必要があります。  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   PowerShell モジュール バージョン 1.1.6 Teamsから更新する場合は、スクリプトを更新して`Connect-MicrosoftTeams``New-CsOnlineSession`、 .

-   更新中は、TPM 4.x.x/3.x.x.x を 3.0.0 より前のバージョンと共に使用しないことをお勧めします。 たとえば、同じ組織内のさまざまな管理者操作でバージョン 4.x.x & 2.6.0 をまとめて使用することはお勧めしません。 

- 関連する変更
  * TPM 3.x.x 以降のGet-CsOnlineUser & Get-CsOnlineVoiceUserの更新 – [Get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlineuser) &  (メッセージ センターポスト – MC340774) の詳細。[](/powershell/module/skype/get-csonlinevoiceuser)

  * 電話番号の割り当てに関する変更 - [Set-CsUser](/powershell/module/skype/set-csuser)、[Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser)、[Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) &  (メッセージ センターポスト – MC316139) の詳細[](/powershell/module/skype/set-csonlinevoiceapplicationinstance)



## <a name="deprecated-cmdlets"></a>非推奨のコマンドレット

最近非推奨になったコマンドレット、またはMicrosoft Teamsシナリオでサポートされていないコマンドレットの一部を次に示します。 同じ詳細については、それぞれのパブリック ドキュメントを参照してください。 

- [Get-CsUserPstnSettings](/powershell/module/skype/get-csuserpstnsettings)、 [Set-CsUserPstnSettings](/powershell/module/skype/set-csuserpstnsettings)
- [Get-CsOnlineDialInConferencingUserInfo](/powershell/module/skype/get-csonlinedialinconferencinguserinfo)、 [Get-CsOnlineDialInConferencingUserState](/powershell/module/skype/get-csonlinedialinconferencinguserstate)、 [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/enable-csonlinedialinconferencinguser)、 [Disable-CsOnlineDialInConferencingUser](/powershell/module/skype/disable-csonlinedialinconferencinguser)
- [Get-CsMeetingRoom](/powershell/module/skype/get-csmeetingroom)、 [Set-CsMeetingRoom](/powershell/module/skype/set-csmeetingroom)、 [Enable-CsMeetingRoom](/powershell/module/skype/enable-csmeetingroom)、 [Disable-CsMeetingRoom](/powershell/module/skype/disable-csmeetingroom)
- [Get-CsOnlineDirectoryTenant](/powershell/module/skype/get-csonlinedirectorytenant)
- [New-CsOnlineAudioFile](/powershell/module/skype/new-csonlineaudiofile)
- [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint)、 [Set-CsOnlineApplicationEndpoint](/powershell/module/skype/set-csonlineapplicationendpoint)、 [New-CsOnlineApplicationEndpoint](/powershell/module/skype/new-csonlineapplicationendpoint)、 [Remove-CsOnlineApplicationEndpoint](/powershell/module/skype/remove-csonlineapplicationendpoint)
- [Get-CsOnlineTelephoneNumberInventoryCities](/powershell/module/skype/get-csonlinetelephonenumberinventorycities), [Get-CsOnlineTelephoneNumberInventoryAreas](/powershell/module/skype/get-csonlinetelephonenumberinventoryareas), [Get-CsOnlineTelephoneNumberInventoryCountries](/powershell/module/skype/get-csonlinetelephonenumberinventorycountries)、 [Get-CsOnlineTelephoneNumberInventoryRegions](/powershell/module/skype/get-csonlinetelephonenumberinventoryregions)、 [Get-CsOnlineTelephoneNumberInventoryTypes](/powershell/module/skype/get-csonlinetelephonenumberinventorytypes)、 [Search-CsOnlineTelephoneNumberInventory](/powershell/module/skype/search-csonlinetelephonenumberinventory)、 [Select-CsOnlineTelephoneNumberInventory](/powershell/module/skype/select-csonlinetelephonenumberinventory)、 [Get-CsOnlineTelephoneNumberAvailableCount](/powershell/module/skype/get-csonlinetelephonenumberavailablecount)、 [Clear-CsOnlineTelephoneNumberReservation](/powershell/module/skype/clear-csonlinetelephonenumberreservation), [Get-CsOnlineTelephoneNumberReservationsInformation](/powershell/module/skype/get-csonlinetelephonenumberreservationsinformation), [Get-CsOnlineDirectoryTenantNumberCities](/powershell/module/skype/get-csonlinedirectorytenantnumbercities)  



## <a name="related-topics"></a>関連項目

[PowerShell リリース ノートをTeamsする](teams-powershell-release-notes.md)

[PowerShell Microsoft Teamsインストールする](teams-powershell-install.md)

[Teams PowerShell でTeamsを管理する](teams-powershell-managing-teams.md)

[Microsoft Teams コマンドレット リファレンス](/powershell/module/teams) 

[Skype for Business コマンドレット リファレンス](/powershell/module/skype) 
