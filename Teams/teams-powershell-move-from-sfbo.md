---
title: Skype for Business Online Connector から Teams PowerShell モジュールに移動する
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Skype for Business Online Connector から Teams PowerShell モジュールに移動して Teams を管理する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32029de1ec33ee89c8dba30d8368131b291fc3f8
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569083"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Skype for Business Online Connector から Teams PowerShell モジュールに移動する

Skype for Business Online Connector を使用して Teams PowerShell モジュールに移行して Teams を管理するには、既存の PowerShell スクリプトを更新する必要があります。 この記事では、この方法について説明します。

1. 最新の Teams PowerShell モジュールをインストールします。 手順については [、「Microsoft Teams PowerShell をインストールする」を参照してください](teams-powershell-install.md)。
2. Skype for Business Online Connector をアンインストールします。 これを行うには、コントロール パネルで[インストール] に移動しプログラムと機能 **Skype for Business Online、Windows PowerShellモジュール**、[アンインストール] の順に選択 **します**。 
3. PowerShell スクリプトで、参照されるモジュール名を変更 ```Import-Module``` ```SkypeOnlineConnector``` ```LyncOnlineConnector``` します ```MicrosoftTeams``` 。

    たとえば、次の値に ```Import-Module -Name SkypeOnlineConnector``` 変更します ```Import-Module -Name MicrosoftTeams``` 。
4. Teams PowerShell モジュール 2.0 以降を使用している場合は、New-csOnlineSession を Connect-MicrosoftTeams に変更します。 

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

## <a name="related-topics"></a>関連項目

[Microsoft Teams PowerShell をインストールする](teams-powershell-install.md)

[Teams PowerShell で Teams を管理する](teams-powershell-managing-teams.md)

[Teams PowerShell のリリース ノート](teams-powershell-release-notes.md)

[Microsoft Teams コマンドレット リファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Skype for Business コマンドレット リファレンス](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
