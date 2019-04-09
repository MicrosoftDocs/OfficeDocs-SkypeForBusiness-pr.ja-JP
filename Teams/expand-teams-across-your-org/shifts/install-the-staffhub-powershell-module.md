---
title: StaffHub PowerShell モジュールをインストールします。
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 04/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: インストールし、マイクロソフトの StaffHub の PowerShell モジュールに接続する方法を説明します。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe419348d966d9ddfc5c16eee29d9a5005cd6db8
ms.sourcegitcommit: a505869a3cc2fe6fe4ee18bcbe99bf980aa91a86
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "31555135"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="01935-103">Microsoft StaffHub の PowerShell モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="01935-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01935-104">2019 年 10 月 1 日より、Microsoft StaffHub が廃止されます。</span><span class="sxs-lookup"><span data-stu-id="01935-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="01935-105">マイクロソフトのチームに StaffHub 機能が進められています。</span><span class="sxs-lookup"><span data-stu-id="01935-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="01935-106">今日では、チームには、スケジュール管理のためのシフトのアプリケーションが含まれていて、その他の機能が時間の経過と共に展開されます。</span><span class="sxs-lookup"><span data-stu-id="01935-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="01935-107">StaffHub は、2019 年 10 月 1 日ですべてのユーザーの作業を停止します。</span><span class="sxs-lookup"><span data-stu-id="01935-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="01935-108">StaffHub を開こうとするとすべての人がチームをダウンロードすることを指示するメッセージ表示されます。</span><span class="sxs-lookup"><span data-stu-id="01935-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="01935-109">詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01935-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="01935-110">インストールし、マイクロソフトの StaffHub の PowerShell モジュールへの接続をこの資料の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="01935-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="01935-111">この PowerShell を使用して StaffHub を管理して、マイクロソフトのチーム、StaffHub チームに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01935-111">You'll need this to manage StaffHub by using PowerShell and to move your StaffHub teams to Microsoft Teams.</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="01935-112">Microsoft StaffHub の PowerShell モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="01935-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="01935-113">[StaffHub PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="01935-113">Download the [StaffHub PowerShell module](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span></span> 
2. <span data-ttu-id="01935-114">3.0 以降は、管理者として、Windows PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="01935-114">Open Windows PowerShell 3.0 or later as an administrator.</span></span> <span data-ttu-id="01935-115">これを行うには、[**スタート**] ボタン、 **Windows PowerShell**を入力、 **Windows PowerShell**を右クリックし [**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="01935-115">To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="01935-116">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="01935-116">Run the following:</span></span>

    ```
    $ENV:PSModulePath
    ```

4. <span data-ttu-id="01935-117">出力フォルダーのパスを確認し、次の手順に進む前に、コンピューター上のパスのすべてのフォルダーが存在するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="01935-117">Check the folder path in the output and make sure that all folders in the path exist on your computer before you go to the next step.</span></span> <span data-ttu-id="01935-118">フォルダーが存在しない場合は、それらを作成します。</span><span class="sxs-lookup"><span data-stu-id="01935-118">If folders are missing, create them.</span></span>
5. <span data-ttu-id="01935-119">、次を実行、&lt;パス&gt;は、手順 2 からの出力のパス。</span><span class="sxs-lookup"><span data-stu-id="01935-119">Run the following, where &lt;path&gt; is the path in the output from step 2.</span></span> <span data-ttu-id="01935-120">たとえば、パスは、C:\Users\User1\Documents\WindowsPowerShell\Modules のようになります。</span><span class="sxs-lookup"><span data-stu-id="01935-120">For example, the path might look like C:\Users\User1\Documents\WindowsPowerShell\Modules.</span></span>

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.2
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.2
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="01935-121">Microsoft StaffHub PowerShell モジュールへの接続します。</span><span class="sxs-lookup"><span data-stu-id="01935-121">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="01935-122">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="01935-122">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="01935-123">グローバル管理者としてメッセージが表示されたら、ログします。</span><span class="sxs-lookup"><span data-stu-id="01935-123">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="01935-124">関連トピック</span><span class="sxs-lookup"><span data-stu-id="01935-124">Related topics</span></span>

- [<span data-ttu-id="01935-125">Microsoft StaffHub PowerShell 参照</span><span class="sxs-lookup"><span data-stu-id="01935-125">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="01935-126">Microsoft StaffHubのチームを、TeamsのShiftsに移動します</span><span class="sxs-lookup"><span data-stu-id="01935-126">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
