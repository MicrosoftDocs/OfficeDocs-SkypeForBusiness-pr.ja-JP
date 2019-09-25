---
title: StaffHub PowerShell モジュールをインストールする
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft StaffHub PowerShell モジュールのプレリリース版をインストールして接続する方法について説明します。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80f8f586d8a2a41d0d716e0821eb1f6d8d4bcbee
ms.sourcegitcommit: 6ba9eeb81b7d55ffc319d6d6658d0ecac83c2159
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "37142036"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="cd1f9-103">Microsoft StaffHub PowerShell モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="cd1f9-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd1f9-104">2019 年 10 月 1 日より、Microsoft StaffHub が廃止されます。</span><span class="sxs-lookup"><span data-stu-id="cd1f9-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="cd1f9-105">Microsoft Teams で StaffHub 機能を構築しています。</span><span class="sxs-lookup"><span data-stu-id="cd1f9-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="cd1f9-106">現在、チームには、スケジュール管理のためのシフトアプリが含まれており、その他の機能も時間の経過と共にロールアウトされます。</span><span class="sxs-lookup"><span data-stu-id="cd1f9-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="cd1f9-107">2019年10月1日の StaffHub はすべてのユーザーに対して機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="cd1f9-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="cd1f9-108">StaffHub を開こうとしたユーザーには、チームをダウンロードするように指示するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd1f9-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="cd1f9-109">詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd1f9-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="cd1f9-110">この記事の手順に従って、プレリリース版の Microsoft StaffHub PowerShell モジュールをインストールして接続します。</span><span class="sxs-lookup"><span data-stu-id="cd1f9-110">Use the steps in this article to install and connect to the prerelease version of the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="cd1f9-111">これは[、StaffHub teams を teams に移動](move-staffhub-teams-to-shifts-in-teams.md)するために必要です。</span><span class="sxs-lookup"><span data-stu-id="cd1f9-111">You'll need this to [move your StaffHub teams to Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span>

## <a name="install-the-prerelease-version-of-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="cd1f9-112">プレリリース版の Microsoft StaffHub PowerShell モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="cd1f9-112">Install the prerelease version of the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="cd1f9-113">Windows PowerShell 3.0 以降を管理者として開きます。これを行うには、[**スタート**] をクリックし、「 **windows powershell**」と入力して、[ **windows powershell**] を右クリックし、[**管理者として実行**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd1f9-113">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="cd1f9-114">最新バージョンの Windows PowerShell を取得するには、「 [Windows powershell をインストール](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd1f9-114">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span> 
2. <span data-ttu-id="cd1f9-115">次の操作を実行して、プレリリース版の StaffHub PowerShell モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="cd1f9-115">Run the following to install the prerelease version of the StaffHub PowerShell module:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub -AllowPrerelease
    ```
3. <span data-ttu-id="cd1f9-116">警告メッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="cd1f9-116">You may see the warning message:</span></span>

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

    <span data-ttu-id="cd1f9-117">「 `Y`」と入力し`Enter`て、をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd1f9-117">Type `Y`, and then click `Enter`.</span></span>
 
4. <span data-ttu-id="cd1f9-118">Windows PowerShell を終了します。</span><span class="sxs-lookup"><span data-stu-id="cd1f9-118">Exit Windows PowerShell.</span></span>

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="cd1f9-119">Microsoft StaffHub PowerShell モジュールに接続する</span><span class="sxs-lookup"><span data-stu-id="cd1f9-119">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="cd1f9-120">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cd1f9-120">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="cd1f9-121">メッセージが表示されたら、グローバル管理者としてログインします。</span><span class="sxs-lookup"><span data-stu-id="cd1f9-121">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cd1f9-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="cd1f9-122">Related topics</span></span>

- [<span data-ttu-id="cd1f9-123">Microsoft StaffHub PowerShell リファレンス</span><span class="sxs-lookup"><span data-stu-id="cd1f9-123">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="cd1f9-124">Microsoft StaffHub のチームを Teams の Shifts に移動する</span><span class="sxs-lookup"><span data-stu-id="cd1f9-124">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
