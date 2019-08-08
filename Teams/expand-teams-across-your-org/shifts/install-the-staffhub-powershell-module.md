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
description: Microsoft StaffHub PowerShell モジュールをインストールして接続する方法について説明します。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 179276a049a30f1d049521cc3b4db326b988667c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36246181"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="cf709-103">Microsoft StaffHub PowerShell モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="cf709-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf709-104">2019 年 10 月 1 日より、Microsoft StaffHub が廃止されます。</span><span class="sxs-lookup"><span data-stu-id="cf709-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="cf709-105">Microsoft Teams で StaffHub 機能を構築しています。</span><span class="sxs-lookup"><span data-stu-id="cf709-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="cf709-106">現在、チームには、スケジュール管理のためのシフトアプリが含まれており、その他の機能も時間の経過と共にロールアウトされます。</span><span class="sxs-lookup"><span data-stu-id="cf709-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="cf709-107">2019年10月1日の StaffHub はすべてのユーザーに対して機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="cf709-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="cf709-108">StaffHub を開こうとしたユーザーには、チームをダウンロードするように指示するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf709-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="cf709-109">詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf709-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="cf709-110">この記事の手順を使用して、Microsoft StaffHub PowerShell モジュールをインストールして接続します。</span><span class="sxs-lookup"><span data-stu-id="cf709-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="cf709-111">これは、PowerShell を使用して StaffHub を管理し、StaffHub teams を Microsoft Teams に移動するために必要となります。</span><span class="sxs-lookup"><span data-stu-id="cf709-111">You'll need this to manage StaffHub by using PowerShell and to move your StaffHub teams to Microsoft Teams.</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="cf709-112">Microsoft StaffHub PowerShell モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="cf709-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="cf709-113">[StaffHub PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="cf709-113">Download the [StaffHub PowerShell module](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span></span> 
2. <span data-ttu-id="cf709-114">Windows PowerShell 3.0 以降を管理者として開きます。これを行うには、[**スタート**] をクリックし、「 **windows powershell**」と入力して、[ **windows powershell**] を右クリックし、[**管理者として実行**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cf709-114">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="cf709-115">最新バージョンの Windows PowerShell を取得するには、「 [Windows powershell をインストール](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf709-115">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span> 
3. <span data-ttu-id="cf709-116">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cf709-116">Run the following:</span></span>

    ```
    $ENV:PSModulePath
    ```
    

4. <span data-ttu-id="cf709-117">出力のフォルダーパスを確認し、次の手順に進む前に、パス内のすべてのフォルダーがコンピューターに存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="cf709-117">Check the folder path in the output and make sure that all folders in the path exist on your computer before you go to the next step.</span></span> <span data-ttu-id="cf709-118">フォルダーがない場合は、フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="cf709-118">If folders are missing, create them.</span></span>
5. <span data-ttu-id="cf709-119">StaffHub PowerShell モジュールのインストールを許可するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="cf709-119">Run the following to allow for installation of the StaffHub PowerShell module:</span></span>

    ```
    Set-ExecutionPolicy RemoteSigned
    ```

6. <span data-ttu-id="cf709-120">次を実行します&lt;。&gt;ここで、path は手順2の出力のパスです。</span><span class="sxs-lookup"><span data-stu-id="cf709-120">Run the following, where &lt;path&gt; is the path in the output from step 2.</span></span> <span data-ttu-id="cf709-121">たとえば、パスが C:\Users\User1\Documents\WindowsPowerShell\Modules. のように表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="cf709-121">For example, the path might look like C:\Users\User1\Documents\WindowsPowerShell\Modules.</span></span>

    <span data-ttu-id="cf709-122">各コマンドは別々に実行してください。</span><span class="sxs-lookup"><span data-stu-id="cf709-122">Be sure to run each command separately.</span></span>

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PackageManagement -Force  -AllowClobber
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.5-alpha -AllowPrerelease
    ```
7. <span data-ttu-id="cf709-123">Windows PowerShell を終了します。</span><span class="sxs-lookup"><span data-stu-id="cf709-123">Exit Windows PowerShell.</span></span>
8. <span data-ttu-id="cf709-124">Windows PowerShell 3.0 以降をグローバル管理者として開き、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="cf709-124">Open Windows PowerShell 3.0 or later as a global admin, and then run the following:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.5-alpha -AllowPrerelease
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="cf709-125">Microsoft StaffHub PowerShell モジュールに接続する</span><span class="sxs-lookup"><span data-stu-id="cf709-125">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="cf709-126">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cf709-126">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="cf709-127">メッセージが表示されたら、グローバル管理者としてログインします。</span><span class="sxs-lookup"><span data-stu-id="cf709-127">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cf709-128">関連トピック</span><span class="sxs-lookup"><span data-stu-id="cf709-128">Related topics</span></span>

- [<span data-ttu-id="cf709-129">Microsoft StaffHub PowerShell リファレンス</span><span class="sxs-lookup"><span data-stu-id="cf709-129">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="cf709-130">Microsoft StaffHub のチームを Teams の Shifts に移動する</span><span class="sxs-lookup"><span data-stu-id="cf709-130">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
