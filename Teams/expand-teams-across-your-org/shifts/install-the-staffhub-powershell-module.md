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
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 122a704df184619591f121f088162a045733cf4b
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992132"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="2eb6f-103">Microsoft StaffHub PowerShell モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="2eb6f-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2eb6f-104">2019 年 12 月 31 日より、Microsoft StaffHub が廃止されます。</span><span class="sxs-lookup"><span data-stu-id="2eb6f-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="2eb6f-105">Microsoft では、StaffHub の機能を Microsoft Teams に組み込む作業に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="2eb6f-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="2eb6f-106">現在、Teams にはシフト アプリのスケジュール管理機能が含まれています。今後、他の機能もロールアウトされる予定です。</span><span class="sxs-lookup"><span data-stu-id="2eb6f-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="2eb6f-107">StaffHub は、2019 年 12 月 31 日以降すべてのユーザーがご利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="2eb6f-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="2eb6f-108">ユーザーが StaffHub を開くと、Teams をダウンロードするように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2eb6f-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="2eb6f-109">詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2eb6f-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="2eb6f-110">この記事の手順を使用して、Microsoft StaffHub PowerShell モジュールをインストールして接続します。</span><span class="sxs-lookup"><span data-stu-id="2eb6f-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="2eb6f-111">これは[、StaffHub teams を teams に移動](move-staffhub-teams-to-shifts-in-teams.md)するために必要です。</span><span class="sxs-lookup"><span data-stu-id="2eb6f-111">You'll need this to [move your StaffHub teams to Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="2eb6f-112">Microsoft StaffHub PowerShell モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="2eb6f-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="2eb6f-113">[StaffHub PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftStaffHub)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="2eb6f-113">Download the [StaffHub PowerShell module](https://www.powershellgallery.com/packages/MicrosoftStaffHub).</span></span>
2. <span data-ttu-id="2eb6f-114">Windows PowerShell 3.0 以降を管理者として開きます。これを行うには、[**スタート**] をクリックし、「 **windows powershell**」と入力して、[ **windows powershell**] を右クリックし、[**管理者として実行**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2eb6f-114">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="2eb6f-115">最新バージョンの Windows PowerShell を取得するには、「 [Windows powershell をインストール](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2eb6f-115">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span>
3. <span data-ttu-id="2eb6f-116">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2eb6f-116">Run the following:</span></span>

    ```PowerShell
    $ENV:PSModulePath
    ```
4. <span data-ttu-id="2eb6f-117">出力のフォルダーパスを確認し、次の手順に進む前に、パス内のすべてのフォルダーがコンピューターに存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="2eb6f-117">Check the folder path in the output and make sure that all folders in the path exist on your computer before you go to the next step.</span></span> <span data-ttu-id="2eb6f-118">フォルダーがない場合は、フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2eb6f-118">If folders are missing, create them.</span></span>
5. <span data-ttu-id="2eb6f-119">StaffHub PowerShell モジュールのインストールを許可するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="2eb6f-119">Run the following to allow for installation of the StaffHub PowerShell module:</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
6. <span data-ttu-id="2eb6f-120">次を実行します&lt;。&gt;ここで、path は手順3からの出力のパスです。</span><span class="sxs-lookup"><span data-stu-id="2eb6f-120">Run the following, where &lt;path&gt; is the path in the output from step 3.</span></span> <span data-ttu-id="2eb6f-121">たとえば、パスが C:\Users\User1\Documents\WindowsPowerShell\Modules. のように表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="2eb6f-121">For example, the path might look like C:\Users\User1\Documents\WindowsPowerShell\Modules.</span></span>

    <span data-ttu-id="2eb6f-122">各コマンドは別々に実行してください。</span><span class="sxs-lookup"><span data-stu-id="2eb6f-122">Be sure to run each command separately.</span></span>

    ```PowerShell
    Install-Module -Name PackageManagement -Force  -AllowClobber
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    ```
7. <span data-ttu-id="2eb6f-123">Windows PowerShell を終了します。</span><span class="sxs-lookup"><span data-stu-id="2eb6f-123">Exit Windows PowerShell.</span></span>
8. <span data-ttu-id="2eb6f-124">Windows PowerShell 3.0 以降をグローバル管理者として開き、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2eb6f-124">Open Windows PowerShell 3.0 or later as a global admin, and then run the following:</span></span>

    ```PowerShell
    Install-Module -Name MicrosoftStaffHub
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="2eb6f-125">Microsoft StaffHub PowerShell モジュールに接続する</span><span class="sxs-lookup"><span data-stu-id="2eb6f-125">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="2eb6f-126">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2eb6f-126">Run the following:</span></span>

    ```PowerShell
    Connect-StaffHub
    ```

2. <span data-ttu-id="2eb6f-127">メッセージが表示されたら、グローバル管理者としてログインします。</span><span class="sxs-lookup"><span data-stu-id="2eb6f-127">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2eb6f-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="2eb6f-128">Related topics</span></span>

- [<span data-ttu-id="2eb6f-129">Microsoft StaffHub PowerShell リファレンス</span><span class="sxs-lookup"><span data-stu-id="2eb6f-129">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="2eb6f-130">Microsoft StaffHub のチームを Teams の Shifts に移動する</span><span class="sxs-lookup"><span data-stu-id="2eb6f-130">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
