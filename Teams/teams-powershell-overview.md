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
ms.openlocfilehash: 5385430c7db8aab0adf1efbaec546134e9adf388
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "44943990"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="a9767-103">Microsoft Teams PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="a9767-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="a9767-104">Microsoft Teams PowerShell は、PowerShell コマンドラインから直接 Teams を管理するためのコマンドレットのセットです。</span><span class="sxs-lookup"><span data-stu-id="a9767-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="a9767-105">作成された .NET Standard では、Teams PowerShell は、Azure Shell を含むすべてのプラットフォームで PowerShell 5.1 x 以降で動作します。</span><span class="sxs-lookup"><span data-stu-id="a9767-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows,PowerShell 6.x and higher on all platforms including Azure Shell.</span></span>

<span data-ttu-id="a9767-106">PowerShell の使用を開始する前に、[インストール](teams-powershell-install.md)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9767-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="a9767-107">PowerShell 7 と Teams PowerShell について、既知の問題があります。</span><span class="sxs-lookup"><span data-stu-id="a9767-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="a9767-108">問題が解決されるまで、PowerShell 5.1 を使うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a9767-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="a9767-109">日本語</span><span class="sxs-lookup"><span data-stu-id="a9767-109">Releases</span></span>


<span data-ttu-id="a9767-110">Teams PowerShell は、2種類のリリースで[PowerShell ギャラリー](https://www.powershellgallery.com/packages/MicrosoftTeams)で利用できます。</span><span class="sxs-lookup"><span data-stu-id="a9767-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="a9767-111">**一般的な可用性 (GA)**: プロダクション対応のコマンドレット、毎月更新されます。</span><span class="sxs-lookup"><span data-stu-id="a9767-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="a9767-112">**パブリックプレビュー**: 機能への早期アクセス。</span><span class="sxs-lookup"><span data-stu-id="a9767-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="a9767-113">GA よりも頻繁に更新される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a9767-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="a9767-114">両方のリリースの機能の追加と改善の詳細については、 [Teams PowerShell のリリースノート](teams-powershell-release-notes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9767-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="a9767-115">PowerShell を使用してチームを管理する</span><span class="sxs-lookup"><span data-stu-id="a9767-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="a9767-116">次の両方の PowerShell モジュールを使用して、Teams を完全に管理します。</span><span class="sxs-lookup"><span data-stu-id="a9767-116">You'll use both of these PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="a9767-117">[Microsoft Teams powershell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams/): teams powershell モジュールには、チーム、チャット、チャネルを管理するためのコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a9767-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

- <span data-ttu-id="a9767-118">[Skype For Business powershell モジュール](https://www.microsoft.com/download/details.aspx?id=39366): Skype For business powershell モジュールには、会議、電話システム、ポリシーの機能を管理するためのコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a9767-118">[Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366): The Skype for Business PowerShell module contains the cmdlets to manage meetings, phone system, and policies features.</span></span>

<span data-ttu-id="a9767-119">これらのモジュールを使用してチームを管理する方法の詳細については、「 [Teams PowerShell を](teams-powershell-managing-teams.md)使用してチームを管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9767-119">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a9767-120">最新の[Teams powershell パブリックプレビューリリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)は、Skype For Business Online Connector と統合されており、teams PowerShell 管理用の1つのモジュールを提供しています。</span><span class="sxs-lookup"><span data-stu-id="a9767-120">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a9767-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9767-121">Related topics</span></span>

[<span data-ttu-id="a9767-122">Teams PowerShell のインストール</span><span class="sxs-lookup"><span data-stu-id="a9767-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="a9767-123">Teams PowerShell を使用してチームを管理する</span><span class="sxs-lookup"><span data-stu-id="a9767-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="a9767-124">Teams PowerShell リリースノート</span><span class="sxs-lookup"><span data-stu-id="a9767-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="a9767-125">Microsoft Teams コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="a9767-125">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="a9767-126">Skype for Business コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="a9767-126">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="a9767-127">Microsoft Teams の管理者ロールを使用して Teams を管理する</span><span class="sxs-lookup"><span data-stu-id="a9767-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
