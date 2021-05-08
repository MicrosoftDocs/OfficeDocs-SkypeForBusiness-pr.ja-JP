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
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="1e410-103">Skype for Business Online Connector から PowerShell モジュールTeamsに移動する</span><span class="sxs-lookup"><span data-stu-id="1e410-103">Move from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="1e410-104">Skype for Business Online Connector の使用から Teams PowerShell モジュールに移行して Teams を管理するには、既存の PowerShell スクリプトを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e410-104">To move from using Skype for Business Online Connector to the Teams PowerShell module to manage Teams, you'll need to update your existing PowerShell scripts.</span></span> <span data-ttu-id="1e410-105">この記事では、この方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1e410-105">This article explains how to do this.</span></span>

1. <span data-ttu-id="1e410-106">最新の PowerShell モジュールTeamsインストールします。</span><span class="sxs-lookup"><span data-stu-id="1e410-106">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="1e410-107">手順については[、「PowerShell のインストール」Microsoft Teams参照してください](teams-powershell-install.md)。</span><span class="sxs-lookup"><span data-stu-id="1e410-107">For steps, see [Install Microsoft Teams Powershell](teams-powershell-install.md).</span></span>
2. <span data-ttu-id="1e410-108">For Business Online コネクタSkypeをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="1e410-108">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="1e410-109">これを行うには、コントロール パネルで [プログラムと機能] に **移動** し、[オンライン] **Skype for Business、[** モジュール] Windows PowerShell 選択し、[アンインストール] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="1e410-109">To do this, in Control Panel, go **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span> 
3. <span data-ttu-id="1e410-110">PowerShell スクリプトで、 または で参照されているモジュール名を ```Import-Module``` に ```SkypeOnlineConnector``` 変更 ```LyncOnlineConnector``` します ```MicrosoftTeams``` 。</span><span class="sxs-lookup"><span data-stu-id="1e410-110">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from ```SkypeOnlineConnector``` or ```LyncOnlineConnector``` to ```MicrosoftTeams```.</span></span>

    <span data-ttu-id="1e410-111">たとえば、 に ```Import-Module -Name SkypeOnlineConnector``` 変更します ```Import-Module -Name MicrosoftTeams``` 。</span><span class="sxs-lookup"><span data-stu-id="1e410-111">For example, change ```Import-Module -Name SkypeOnlineConnector``` to ```Import-Module -Name MicrosoftTeams```.</span></span>
4. <span data-ttu-id="1e410-112">PowerShell モジュール 2.0 Teamsを使用する場合は、New-csOnlineSession を Connect-MicrosoftTeams に変更します。</span><span class="sxs-lookup"><span data-stu-id="1e410-112">When using Teams PowerShell Module 2.0 or later, change New-csOnlineSession to Connect-MicrosoftTeams.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="1e410-113">関連トピック</span><span class="sxs-lookup"><span data-stu-id="1e410-113">Related topics</span></span>

[<span data-ttu-id="1e410-114">PowerShell Microsoft Teamsインストールする</span><span class="sxs-lookup"><span data-stu-id="1e410-114">Install Microsoft Teams Powershell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="1e410-115">PowerShell Teamsを使用Teams管理する</span><span class="sxs-lookup"><span data-stu-id="1e410-115">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="1e410-116">TeamsPowerShell のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="1e410-116">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="1e410-117">Microsoft Teams コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="1e410-117">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="1e410-118">Skype for Business コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="1e410-118">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)