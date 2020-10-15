---
title: Skype for Business Online のコネクタから Teams PowerShell モジュールに移動する
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Skype for Business Online のコネクタから Teams PowerShell モジュールに移動して、チームを管理する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e1838540e57cd91578e898818e2ed12e7b63a78
ms.sourcegitcommit: 51d94d621e3411f35622e852b699275f526600dd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469668"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Skype for Business Online のコネクタから Teams PowerShell モジュールに移動する

Skype for Business Online Connector から Teams PowerShell モジュールへ移動して Teams を管理するには、既存の PowerShell スクリプトを更新する必要があります。 この記事では、この方法について説明します。

1. 最新の Teams PowerShell モジュールをインストールします。 手順については、「 [Microsoft Teams Powershell をインストール](teams-powershell-install.md)する」を参照してください。
2. Skype For Business Online Connector をアンインストールします。 これを行うには、コントロールパネルの [ **プログラムと機能**] に移動し、[ **Skype for business Online]、[Windows PowerShell モジュール**] の順に選択して、[ **アンインストール**] を選択します。 
3. PowerShell スクリプトで、 ```Import-Module``` from または to で参照されているモジュール名を変更し ```SkypeOnlineConnector``` ```LyncOnlineConnector``` ```MicrosoftTeams``` ます。

    たとえば、に変更 ```Import-Module -Name SkypeOnlineConnector``` ```Import-Module -Name MicrosoftTeams``` します。

> [!NOTE]
> 管理者は、Skype for Business Online のコマンドレットを使用する前に、引き続き [新しい Csonline セッション](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) を使用してセッションをインポートする必要があります。 

## <a name="related-topics"></a>関連項目

[Microsoft Teams Powershell をインストールする](teams-powershell-install.md)

[Teams PowerShell を使用してチームを管理する](teams-powershell-managing-teams.md)

[Teams PowerShell リリースノート](teams-powershell-release-notes.md)

[Microsoft Teams コマンドレット リファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Skype for Business コマンドレット リファレンス](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
