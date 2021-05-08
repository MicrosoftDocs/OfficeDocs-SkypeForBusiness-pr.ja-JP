---
title: Skype for Business Online Connector から PowerShell モジュールTeamsに移動する
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Skype for Business Online Connector から Teams PowerShell モジュールに移動して、Teams を管理する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5a2b502edc84c853a0a140a11f8c028b7c78aca6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094128"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Skype for Business Online Connector から PowerShell モジュールTeamsに移動する

Skype for Business Online Connector の使用から Teams PowerShell モジュールに移行して Teams を管理するには、既存の PowerShell スクリプトを更新する必要があります。 この記事では、この方法について説明します。

1. 最新の PowerShell モジュールTeamsインストールします。 手順については[、「PowerShell のインストール」Microsoft Teams参照してください](teams-powershell-install.md)。
2. For Business Online コネクタSkypeをアンインストールします。 これを行うには、コントロール パネルで [プログラムと機能] に **移動** し、[オンライン] **Skype for Business、[** モジュール] Windows PowerShell 選択し、[アンインストール] を選択 **します**。 
3. PowerShell スクリプトで、 または で参照されているモジュール名を ```Import-Module``` に ```SkypeOnlineConnector``` 変更 ```LyncOnlineConnector``` します ```MicrosoftTeams``` 。

    たとえば、 に ```Import-Module -Name SkypeOnlineConnector``` 変更します ```Import-Module -Name MicrosoftTeams``` 。
4. PowerShell モジュール 2.0 Teamsを使用する場合は、New-csOnlineSession を Connect-MicrosoftTeams に変更します。 

```powershell
  # When using Teams PowerShell Module 1.1.6
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfbSession
   
   # When using Teams PowerShell Module 2.0 or later
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## <a name="related-topics"></a>関連トピック

[PowerShell Microsoft Teamsインストールする](teams-powershell-install.md)

[PowerShell Teamsを使用Teams管理する](teams-powershell-managing-teams.md)

[TeamsPowerShell のリリース ノート](teams-powershell-release-notes.md)

[Microsoft Teams コマンドレット リファレンス](/powershell/teams/?view=teams-ps)

[Skype for Business コマンドレット リファレンス](/powershell/skype/intro?view=skype-ps)