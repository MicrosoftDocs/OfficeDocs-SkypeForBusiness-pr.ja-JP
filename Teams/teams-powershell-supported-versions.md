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
description: PowerShell モジュールでサポートされているバージョンについてTeams管理に使用される PowerShell モジュールMicrosoft Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3fc980420b53d850c48e680d25bdbf6ec437e8f8
ms.sourcegitcommit: d3d3d5a70a69359fc71f072ad6c651556f4eda00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2022
ms.locfileid: "63783967"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams PowerShell モジュール - サポートされているバージョン

Microsoft Teams 4.x.x シリーズ以上の PowerShell モジュール (TPM) バージョンは、今後サポートされる唯一のバージョンです。 以前のバージョンはすべて提供提供のパス上に表示されます。 PowerShell モジュールを最新バージョンTeams更新をお勧めします。



## <a name="new-organizations"></a>新しい組織

Teams に新しくオンボードする組織は、2022 年 4 月 1 日から 4.x.x シリーズ以上の Teams PowerShell モジュールのみを使用できます。



## <a name="current-organizations-non-tpm-active"></a>現在の組織 (非 TPM アクティブ)

過去 3 か月間 (Jan'22 – Mar'22) に Teams PowerShell モジュールを使用していない組織は、2022 年 4 月 1 日から 4.x.x シリーズ以上の Teams PowerShell モジュールのみを使用できます。



## <a name="current-organizations-tpm-active"></a>現在の組織 (TPM アクティブ)

過去 3 か月間 (Jan'22 – Mar'22) に Teams PowerShell モジュールを使用している組織は、2022 年 6 月 15 日から 4.x.x シリーズ以上の Teams PowerShell モジュールのみを使用できます。 



## <a name="important-notes"></a>重要な注意事項

- PowerShell モジュールのすべてのバージョンTeamsリリース ノートは、[PowerShell のリリース Teamsを参照してください](teams-powershell-release-notes.md)。

- PowerShell モジュールを更新するには、モジュールのインストールに使用したのと同じ方法を使用する必要があります。 たとえば、最初に Install-Module を使用した場合は、 [Update-Module](/powershell/module/powershellget/update-module) を使用して最新バージョンを取得する必要があります。  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   PowerShell モジュール バージョン 1.1.6 Teamsから更新する場合は、 ではなく を使用するスクリプト`Connect-MicrosoftTeams`を更新します`New-CsOnlineSession`。

-   更新中は、3.0.0 より前のバージョンと共に TPM 4.x.x/3.x.x を使用しない方が推奨されます。 たとえば、同じ組織内の異なる管理操作にバージョン 4.x.x & 2.6.0 を組み合わせて使用する場合は、お勧めしません。 

- 関連する変更
  * TPM 3.x.x 以上の Get-CsOnlineUser & Get-CsOnlineVoiceUser の更新プログラム – 詳細については、「[Get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlineuser) &  (メッセージ センターの投稿 – MC340774)」を参照してください。[](/powershell/module/skype/get-csonlinevoiceuser)

  * 電話 番号の割り当てに関する変更 - [Set-CsUser](/powershell/module/skype/set-csuser)、[Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser)、[Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) &  の詳細 (メッセージ センターの投稿 – MC316139)[](/powershell/module/skype/set-csonlinevoiceapplicationinstance)



## <a name="related-topics"></a>関連項目

[Teams PowerShell のリリース ノート](teams-powershell-release-notes.md)

[PowerShell Microsoft Teamsインストールする](teams-powershell-install.md)

[PowerShell Teamsを使用Teams管理する](teams-powershell-managing-teams.md)

[Microsoft Teams コマンドレット リファレンス](/powershell/module/teams) 

[Skype for Business コマンドレット リファレンス](/powershell/module/skype) 
