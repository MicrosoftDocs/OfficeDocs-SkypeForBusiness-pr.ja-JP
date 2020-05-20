---
title: プレリリース版の Teams PowerShell モジュールをインストールする
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: brandber
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: PowerShell テストギャラリーからプレリリース版の Teams PowerShell モジュールをインストールするには、次の手順を実行します。
ms.openlocfilehash: 1d85fac2ee6a1c8565f8482f7208a2f5ae33db60
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321770"
---
# <a name="install-the-pre-release-version-of-the-teams-powershell-module"></a><span data-ttu-id="96868-103">プレリリース版の Teams PowerShell モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="96868-103">Install the pre-release version of the Teams PowerShell module</span></span>

<span data-ttu-id="96868-104">この記事では、 [Powershell テストギャラリー](https://www.poshtestgallery.com/packages/MicrosoftTeams/)から最新のプレリリース版の Teams PowerShell モジュールをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="96868-104">This article describes how to install the latest pre-release version of the Teams PowerShell module from the [PowerShell Test Gallery](https://www.poshtestgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="96868-105">Teams の機能を管理するためのコマンドレットは、一般的なバージョンのモジュールでサポートされておらず、プレリリース版でのみ使用できるシナリオでは、プレリリース版の Teams PowerShell モジュールが必要です。</span><span class="sxs-lookup"><span data-stu-id="96868-105">You'll need the pre-release version of the Teams PowerShell module in scenarios where cmdlets for managing a Teams feature aren't supported in the Generally Available version of the module and are only available in the pre-release version.</span></span>

<span data-ttu-id="96868-106">次の手順を使用して、PowerShell テストギャラリーから最新のプレリリース版の Teams PowerShell モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="96868-106">Use these steps to install the latest pre-release version of the Teams PowerShell module from the PowerShell Test Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="96868-107">PowerShell テストギャラリーから、[パブリック Powershell ギャラリー](https://www.powershellgallery.com/packages/MicrosoftTeams/)のバージョンのモジュールと共に Teams powershell モジュールをインストールしないでください。</span><span class="sxs-lookup"><span data-stu-id="96868-107">Don't install the Teams PowerShell module from the PowerShell Test Gallery side-by-side with a version of the module from the [public PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="96868-108">次の手順に従って、最初にパブリック PowerShell ギャラリーから Teams PowerShell モジュールをアンインストールしてから、PowerShell テストギャラリーから最新バージョンのモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="96868-108">Follow these steps to first uninstall the Teams PowerShell module from the public PowerShell Gallery, and then install the latest version of the module from the PowerShell Test Gallery.</span></span>

1. <span data-ttu-id="96868-109">既存のすべての PowerShell セッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="96868-109">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="96868-110">Windows PowerShell モジュールの新しいインスタンスを開始します。</span><span class="sxs-lookup"><span data-stu-id="96868-110">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="96868-111">パブリック PowerShell ギャラリーから Teams PowerShell モジュールをアンインストールするには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="96868-111">Run the following to uninstall the Teams PowerShell module from the public PowerShell Gallery:</span></span>

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. <span data-ttu-id="96868-112">既存のすべての PowerShell セッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="96868-112">Close all existing PowerShell sessions.</span></span>
5. <span data-ttu-id="96868-113">もう一度 Windows PowerShell モジュールを起動し、次の操作を実行して、PowerShell テストギャラリーを信頼できるソースとして登録します。</span><span class="sxs-lookup"><span data-stu-id="96868-113">Start the Windows PowerShell module again, and then run the following to register the PowerShell Test Gallery as a trusted source:</span></span>

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. <span data-ttu-id="96868-114">次の操作を実行して、PowerShell テストギャラリーから最新の Teams PowerShell モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="96868-114">Run the following to install the latest Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. <span data-ttu-id="96868-115">次の操作を実行して、PowerShell テストギャラリーの最新バージョンの Teams PowerShell モジュールが正常にインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="96868-115">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="96868-116">PowerShell テストギャラリーから最新バージョンの Teams PowerShell モジュールに更新する</span><span class="sxs-lookup"><span data-stu-id="96868-116">Update to the latest version of the Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="96868-117">PowerShell テストギャラリーから既に Teams PowerShell モジュールをインストールしている場合は、次の手順を使用して最新バージョンに更新します。</span><span class="sxs-lookup"><span data-stu-id="96868-117">If you already installed the Teams PowerShell module from the PowerShell Test Gallery, use the following steps to update to the latest version.</span></span>

1. <span data-ttu-id="96868-118">既存のすべての PowerShell セッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="96868-118">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="96868-119">Windows PowerShell モジュールの新しいインスタンスを開始します。</span><span class="sxs-lookup"><span data-stu-id="96868-119">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="96868-120">次の操作を実行して、PowerShell テストギャラリーから現在インストールされている Teams PowerShell モジュールのバージョンを更新します。</span><span class="sxs-lookup"><span data-stu-id="96868-120">Run the following to update the currently installed version of the Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. <span data-ttu-id="96868-121">次の操作を実行して、PowerShell テストギャラリーの最新バージョンの Teams PowerShell モジュールが正常にインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="96868-121">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a><span data-ttu-id="96868-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="96868-122">Related topics</span></span>

- [<span data-ttu-id="96868-123">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="96868-123">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
