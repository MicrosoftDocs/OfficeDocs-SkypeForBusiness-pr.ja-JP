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
ms.openlocfilehash: ef80290e6b8a1ce4de834a000148d60b2c5ef89d
ms.sourcegitcommit: 7d5dd650480ca2e55c24ce30408a5058067f6932
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "37775076"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="a9f4a-103">Microsoft StaffHub PowerShell モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="a9f4a-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a9f4a-104">2019年12月31日有効な場合、Microsoft StaffHub は廃止されます。</span><span class="sxs-lookup"><span data-stu-id="a9f4a-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="a9f4a-105">Microsoft Teams で StaffHub 機能を構築しています。</span><span class="sxs-lookup"><span data-stu-id="a9f4a-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="a9f4a-106">現在、チームには、スケジュール管理のためのシフトアプリが含まれており、その他の機能も時間の経過と共にロールアウトされます。</span><span class="sxs-lookup"><span data-stu-id="a9f4a-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="a9f4a-107">StaffHub は、2019年12月31日にすべてのユーザーに対して機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="a9f4a-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="a9f4a-108">StaffHub を開こうとしたユーザーには、チームをダウンロードするように指示するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9f4a-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="a9f4a-109">詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9f4a-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="a9f4a-110">この記事の手順を使用して、Microsoft StaffHub PowerShell モジュールをインストールして接続します。</span><span class="sxs-lookup"><span data-stu-id="a9f4a-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="a9f4a-111">これは[、StaffHub teams を teams に移動](move-staffhub-teams-to-shifts-in-teams.md)するために必要です。</span><span class="sxs-lookup"><span data-stu-id="a9f4a-111">You'll need this to [move your StaffHub teams to Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="a9f4a-112">Microsoft StaffHub PowerShell モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="a9f4a-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="a9f4a-113">[StaffHub PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftStaffHub)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="a9f4a-113">Download the [StaffHub PowerShell module](https://www.powershellgallery.com/packages/MicrosoftStaffHub).</span></span>
2. <span data-ttu-id="a9f4a-114">Windows PowerShell 3.0 以降を管理者として開きます。これを行うには、[**スタート**] をクリックし、「 **windows powershell**」と入力して、[ **windows powershell**] を右クリックし、[**管理者として実行**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a9f4a-114">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="a9f4a-115">最新バージョンの Windows PowerShell を取得するには、「 [Windows powershell をインストール](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9f4a-115">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span>
3. <span data-ttu-id="a9f4a-116">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a9f4a-116">Run the following:</span></span>

    ```
    $ENV:PSModulePath
    ```
4. <span data-ttu-id="a9f4a-117">出力のフォルダーパスを確認し、次の手順に進む前に、パス内のすべてのフォルダーがコンピューターに存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="a9f4a-117">Check the folder path in the output and make sure that all folders in the path exist on your computer before you go to the next step.</span></span> <span data-ttu-id="a9f4a-118">フォルダーがない場合は、フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a9f4a-118">If folders are missing, create them.</span></span>
5. <span data-ttu-id="a9f4a-119">StaffHub PowerShell モジュールのインストールを許可するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a9f4a-119">Run the following to allow for installation of the StaffHub PowerShell module:</span></span>

    ```
    Set-ExecutionPolicy RemoteSigned
    ```
6. <span data-ttu-id="a9f4a-120">次を実行します&lt;。&gt;ここで、path は手順3からの出力のパスです。</span><span class="sxs-lookup"><span data-stu-id="a9f4a-120">Run the following, where &lt;path&gt; is the path in the output from step 3.</span></span> <span data-ttu-id="a9f4a-121">たとえば、パスが C:\Users\User1\Documents\WindowsPowerShell\Modules. のように表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="a9f4a-121">For example, the path might look like C:\Users\User1\Documents\WindowsPowerShell\Modules.</span></span>

    <span data-ttu-id="a9f4a-122">各コマンドは別々に実行してください。</span><span class="sxs-lookup"><span data-stu-id="a9f4a-122">Be sure to run each command separately.</span></span>

    ```
    Install-Module -Name PackageManagement -Force  -AllowClobber
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    ```
7. <span data-ttu-id="a9f4a-123">Windows PowerShell を終了します。</span><span class="sxs-lookup"><span data-stu-id="a9f4a-123">Exit Windows PowerShell.</span></span>
8. <span data-ttu-id="a9f4a-124">Windows PowerShell 3.0 以降をグローバル管理者として開き、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a9f4a-124">Open Windows PowerShell 3.0 or later as a global admin, and then run the following:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub

## Connect to the Microsoft StaffHub PowerShell module

1. Run the following:

    ```
    <span data-ttu-id="a9f4a-125">Connect-StaffHub</span><span class="sxs-lookup"><span data-stu-id="a9f4a-125">Connect-StaffHub</span></span>
    ```

2. When you're prompted, log in as a global admin.

## Related topics

- [Microsoft StaffHub PowerShell reference](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
- [Move your Microsoft StaffHub teams to Shifts in Teams](move-staffhub-teams-to-shifts-in-teams.md)
