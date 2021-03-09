---
title: Microsoft Teams PowerShell の概要
ms.reviewer: ''
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: PowerShell コントロールを使用して Microsoft Teams を管理する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6c2c626d61a10437fc5bb349dd128415d64448a7
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569023"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="fe915-103">Microsoft Teams PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="fe915-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="fe915-104">Microsoft Teams PowerShell は、PowerShell コマンド ラインから直接 Teams を管理するための一連のコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="fe915-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="fe915-105">.NET Standard で記述された Teams PowerShell は、Azure Cloud Shell を含むすべてのプラットフォームで、Windows、PowerShell 6.x 以上の PowerShell 5.1 で動作します。</span><span class="sxs-lookup"><span data-stu-id="fe915-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows, PowerShell 6.x and higher on all platforms including Azure Cloud Shell.</span></span>

<span data-ttu-id="fe915-106">PowerShell の使用を開始する前に、[それをインストール](teams-powershell-install.md)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe915-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="fe915-107">PowerShell 7 および Teams PowerShell には、既知の問題があります。</span><span class="sxs-lookup"><span data-stu-id="fe915-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="fe915-108">問題が解決されるまで PowerShell 5.1 の使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fe915-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="fe915-109">リリース</span><span class="sxs-lookup"><span data-stu-id="fe915-109">Releases</span></span>


<span data-ttu-id="fe915-110">Teams PowerShell は、2 つのリリース タイプで [PowerShell ギャラリー](https://www.powershellgallery.com/packages/MicrosoftTeams)を利用できます。</span><span class="sxs-lookup"><span data-stu-id="fe915-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="fe915-111">**一般提供 (GA)**: 本番対応のコマンドレットであり、毎月更新されます。</span><span class="sxs-lookup"><span data-stu-id="fe915-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="fe915-112">**パブリック プレビュー**: 機能にいち早くアクセスします。</span><span class="sxs-lookup"><span data-stu-id="fe915-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="fe915-113">GA よりも頻繁に更新される場合があります。</span><span class="sxs-lookup"><span data-stu-id="fe915-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="fe915-114">両方のリリースでの機能の追加と改善の詳細については、「[Teams PowerShell リリース ノート](teams-powershell-release-notes.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fe915-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="fe915-115">PowerShell で Teams を管理する</span><span class="sxs-lookup"><span data-stu-id="fe915-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="fe915-116">Teams PowerShell モジュールを使用して、Teams を完全に管理します。</span><span class="sxs-lookup"><span data-stu-id="fe915-116">You'll use Teams PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="fe915-117">[Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams/): Teams PowerShell モジュールには、チーム、チャット、およびチャネルを管理するためのコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fe915-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

> [!NOTE]
> <span data-ttu-id="fe915-118">[Teams PowerShell の](https://www.powershellgallery.com/packages/MicrosoftTeams/)パブリック リリース バージョン 1.1.6 以降は、Skype for Business Online Connector と統合され、Teams PowerShell 管理用の 1 つのモジュールが提供されます。</span><span class="sxs-lookup"><span data-stu-id="fe915-118">The [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) version 1.1.6 or later is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

- <span data-ttu-id="fe915-119">[Skype for Business PowerShell コネクタ](https://www.microsoft.com/download/details.aspx?id=39366): Skype for Business PowerShell コネクタは、Teams PowerShell モジュールの一部になりました。</span><span class="sxs-lookup"><span data-stu-id="fe915-119">[Skype for Business PowerShell Connector](https://www.microsoft.com/download/details.aspx?id=39366): The Skype for Business PowerShell connector is now a part of Teams PowerShell module.</span></span>

<span data-ttu-id="fe915-120">これらのモジュールを使用して Teams を管理するための完全なガイドについては、「[Teams PowerShell で Teams を管理する](teams-powershell-managing-teams.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fe915-120">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="fe915-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="fe915-121">Related topics</span></span>

[<span data-ttu-id="fe915-122">Teams Powershell のインストール</span><span class="sxs-lookup"><span data-stu-id="fe915-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="fe915-123">Teams PowerShell での Teams の管理</span><span class="sxs-lookup"><span data-stu-id="fe915-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="fe915-124">Teams PowerShell のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="fe915-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="fe915-125">Microsoft Teams コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="fe915-125">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="fe915-126">Skype for Business コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="fe915-126">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="fe915-127">Microsoft Teams の管理者ロールを使用して Teams を管理する</span><span class="sxs-lookup"><span data-stu-id="fe915-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
