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
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="d4c76-103">Skype for Business Online のコネクタから Teams PowerShell モジュールに移動する</span><span class="sxs-lookup"><span data-stu-id="d4c76-103">Move from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="d4c76-104">Skype for Business Online Connector から Teams PowerShell モジュールへ移動して Teams を管理するには、既存の PowerShell スクリプトを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4c76-104">To move from using Skype for Business Online Connector to the Teams PowerShell module to manage Teams, you'll need to update your existing PowerShell scripts.</span></span> <span data-ttu-id="d4c76-105">この記事では、この方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d4c76-105">This article explains how to do this.</span></span>

1. <span data-ttu-id="d4c76-106">最新の Teams PowerShell モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d4c76-106">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="d4c76-107">手順については、「 [Microsoft Teams Powershell をインストール](teams-powershell-install.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4c76-107">For steps, see [Install Microsoft Teams Powershell](teams-powershell-install.md).</span></span>
2. <span data-ttu-id="d4c76-108">Skype For Business Online Connector をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="d4c76-108">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="d4c76-109">これを行うには、コントロールパネルの [ **プログラムと機能**] に移動し、[ **Skype for business Online]、[Windows PowerShell モジュール**] の順に選択して、[ **アンインストール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d4c76-109">To do this, in Control Panel, go **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span> 
3. <span data-ttu-id="d4c76-110">PowerShell スクリプトで、 ```Import-Module``` from または to で参照されているモジュール名を変更し ```SkypeOnlineConnector``` ```LyncOnlineConnector``` ```MicrosoftTeams``` ます。</span><span class="sxs-lookup"><span data-stu-id="d4c76-110">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from ```SkypeOnlineConnector``` or ```LyncOnlineConnector``` to ```MicrosoftTeams```.</span></span>

    <span data-ttu-id="d4c76-111">たとえば、に変更 ```Import-Module -Name SkypeOnlineConnector``` ```Import-Module -Name MicrosoftTeams``` します。</span><span class="sxs-lookup"><span data-stu-id="d4c76-111">For example, change ```Import-Module -Name SkypeOnlineConnector``` to ```Import-Module -Name MicrosoftTeams```.</span></span>

> [!NOTE]
> <span data-ttu-id="d4c76-112">管理者は、Skype for Business Online のコマンドレットを使用する前に、引き続き [新しい Csonline セッション](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) を使用してセッションをインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4c76-112">Admins should continue to use [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) and import the session before using Skype for Business Online cmdlets.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="d4c76-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4c76-113">Related topics</span></span>

[<span data-ttu-id="d4c76-114">Microsoft Teams Powershell をインストールする</span><span class="sxs-lookup"><span data-stu-id="d4c76-114">Install Microsoft Teams Powershell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="d4c76-115">Teams PowerShell を使用してチームを管理する</span><span class="sxs-lookup"><span data-stu-id="d4c76-115">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="d4c76-116">Teams PowerShell リリースノート</span><span class="sxs-lookup"><span data-stu-id="d4c76-116">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="d4c76-117">Microsoft Teams コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="d4c76-117">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="d4c76-118">Skype for Business コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="d4c76-118">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
