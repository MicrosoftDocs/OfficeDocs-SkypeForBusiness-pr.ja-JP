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
ms.openlocfilehash: 448658fb844052815e14b85e0c70a33cb737b72d
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768356"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="a176c-103">Microsoft Teams PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="a176c-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="a176c-104">Microsoft Teams PowerShell は、PowerShell コマンド ラインから直接 Teams を管理するための一連のコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="a176c-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="a176c-105">.NET Standard で記述された Teams PowerShell は、Azure Cloud Shell を含むすべてのプラットフォームで、Windows、PowerShell 6.x 以上の PowerShell 5.1 で動作します。</span><span class="sxs-lookup"><span data-stu-id="a176c-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows, PowerShell 6.x and higher on all platforms including Azure Cloud Shell.</span></span>

<span data-ttu-id="a176c-106">PowerShell の使用を開始する前に、[それをインストール](teams-powershell-install.md)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a176c-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="a176c-107">PowerShell 7 および Teams PowerShell には、既知の問題があります。</span><span class="sxs-lookup"><span data-stu-id="a176c-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="a176c-108">問題が解決されるまで PowerShell 5.1 の使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a176c-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="a176c-109">リリース</span><span class="sxs-lookup"><span data-stu-id="a176c-109">Releases</span></span>


<span data-ttu-id="a176c-110">Teams PowerShell は、2 つのリリース タイプで [PowerShell ギャラリー](https://www.powershellgallery.com/packages/MicrosoftTeams)を利用できます。</span><span class="sxs-lookup"><span data-stu-id="a176c-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="a176c-111">**一般提供 (GA)**: 本番対応のコマンドレットであり、毎月更新されます。</span><span class="sxs-lookup"><span data-stu-id="a176c-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="a176c-112">**パブリック プレビュー**: 機能にいち早くアクセスします。</span><span class="sxs-lookup"><span data-stu-id="a176c-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="a176c-113">GA よりも頻繁に更新される場合があります。</span><span class="sxs-lookup"><span data-stu-id="a176c-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="a176c-114">両方のリリースでの機能の追加と改善の詳細については、「[Teams PowerShell リリース ノート](teams-powershell-release-notes.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a176c-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="a176c-115">PowerShell で Teams を管理する</span><span class="sxs-lookup"><span data-stu-id="a176c-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="a176c-116">Teams PowerShell モジュールを使用して、Teams を完全に管理します。</span><span class="sxs-lookup"><span data-stu-id="a176c-116">You'll use Teams PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="a176c-117">[Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams/): Teams PowerShell モジュールには、チーム、チャット、およびチャネルを管理するためのコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a176c-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

> [!NOTE]
> <span data-ttu-id="a176c-118">[Teams PowerShell のパブリック リリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)バージョン 2.0 以上には、すべての Skype for Business Online Connector コマンドレットが含まれるので、Teams PowerShell 管理用の 1 つのモジュールが提供されます。</span><span class="sxs-lookup"><span data-stu-id="a176c-118">The [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) version 2.0 or higher includes all  Skype for Business Online Connector cmdlets, providing a single module for Teams PowerShell management.</span></span>

- <span data-ttu-id="a176c-119">[Skype for Business PowerShell コネクタ](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell): Skype for Business PowerShell コネクタは、Teams PowerShell モジュールの一部になりました。</span><span class="sxs-lookup"><span data-stu-id="a176c-119">[Skype for Business PowerShell Connector](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell): The Skype for Business PowerShell connector is now a part of Teams PowerShell module.</span></span>

<span data-ttu-id="a176c-120">これらのモジュールを使用して Teams を管理するための完全なガイドについては、「[Teams PowerShell で Teams を管理する](teams-powershell-managing-teams.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a176c-120">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="a176c-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a176c-121">Related topics</span></span>

[<span data-ttu-id="a176c-122">Teams Powershell のインストール</span><span class="sxs-lookup"><span data-stu-id="a176c-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="a176c-123">Teams PowerShell での Teams の管理</span><span class="sxs-lookup"><span data-stu-id="a176c-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="a176c-124">Teams PowerShell のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="a176c-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="a176c-125">Microsoft Teams コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="a176c-125">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="a176c-126">Skype for Business コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="a176c-126">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="a176c-127">Microsoft Teams の管理者ロールを使用して Teams を管理する</span><span class="sxs-lookup"><span data-stu-id="a176c-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
