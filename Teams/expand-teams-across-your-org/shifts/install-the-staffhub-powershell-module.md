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
ms.openlocfilehash: 9ce0d1acec923d09591e8f81b3f500ee9a910f5c
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464667"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="d8ee2-103">Microsoft StaffHub PowerShell モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="d8ee2-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8ee2-104">2019 年 10 月 1 日より、Microsoft StaffHub が廃止されます。</span><span class="sxs-lookup"><span data-stu-id="d8ee2-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="d8ee2-105">Microsoft Teams で StaffHub 機能を構築しています。</span><span class="sxs-lookup"><span data-stu-id="d8ee2-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="d8ee2-106">現在、チームには、スケジュール管理のためのシフトアプリが含まれており、その他の機能も時間の経過と共にロールアウトされます。</span><span class="sxs-lookup"><span data-stu-id="d8ee2-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="d8ee2-107">2019年10月1日の StaffHub はすべてのユーザーに対して機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="d8ee2-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="d8ee2-108">StaffHub を開こうとしたユーザーには、チームをダウンロードするように指示するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8ee2-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="d8ee2-109">詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8ee2-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="d8ee2-110">この記事の手順を使用して、Microsoft StaffHub PowerShell モジュールをインストールして接続します。</span><span class="sxs-lookup"><span data-stu-id="d8ee2-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="d8ee2-111">これは、PowerShell を使用して StaffHub を管理し、StaffHub teams を Microsoft Teams に移動するために必要となります。</span><span class="sxs-lookup"><span data-stu-id="d8ee2-111">You'll need this to manage StaffHub by using PowerShell and to move your StaffHub teams to Microsoft Teams.</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="d8ee2-112">Microsoft StaffHub PowerShell モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="d8ee2-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="d8ee2-113">Windows PowerShell 3.0 以降を管理者として開きます。これを行うには、[**スタート**] をクリックし、「 **windows powershell**」と入力して、[ **windows powershell**] を右クリックし、[**管理者として実行**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d8ee2-113">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="d8ee2-114">最新バージョンの Windows PowerShell を取得するには、「 [Windows powershell をインストール](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8ee2-114">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span> 
2. <span data-ttu-id="d8ee2-115">次の操作を実行して、現在の安定したバージョンの StaffHub PowerShell モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d8ee2-115">Run the following to install the current stable version of the StaffHub PowerShell module:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub
    ```
    
    <span data-ttu-id="d8ee2-116">このコマンドは、最新バージョンをインストールする必要がある場合にのみ実行できます。これは、現在の安定バージョンよりも不安定な可能性があります。`Install-Module -Name MicrosoftStaffHub -AllowPrerelease`</span><span class="sxs-lookup"><span data-stu-id="d8ee2-116">You can run this command only if you need to install the latest version, which may have more instabilities than the current stable version: `Install-Module -Name MicrosoftStaffHub -AllowPrerelease`</span></span>

     > [!NOTE]
     > <span data-ttu-id="d8ee2-117">不安定な状態で、最新バージョンのインストール中にエラーが発生した場合は、次の操作を実行できます。`Install-Module PowershellGet -Force`</span><span class="sxs-lookup"><span data-stu-id="d8ee2-117">If you receive an error during the installation of the latest version with more instabilities, you can run: `Install-Module PowershellGet -Force`</span></span>

3. <span data-ttu-id="d8ee2-118">警告メッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="d8ee2-118">You may see the warning message:</span></span>

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

<span data-ttu-id="d8ee2-119">を`Y`入力し`Enter`て、をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8ee2-119">Type `Y` and click `Enter`.</span></span>
 
4. <span data-ttu-id="d8ee2-120">Windows PowerShell を終了します。</span><span class="sxs-lookup"><span data-stu-id="d8ee2-120">Exit Windows PowerShell.</span></span>

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="d8ee2-121">Microsoft StaffHub PowerShell モジュールに接続する</span><span class="sxs-lookup"><span data-stu-id="d8ee2-121">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="d8ee2-122">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d8ee2-122">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="d8ee2-123">メッセージが表示されたら、グローバル管理者としてログインします。</span><span class="sxs-lookup"><span data-stu-id="d8ee2-123">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d8ee2-124">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d8ee2-124">Related topics</span></span>

- [<span data-ttu-id="d8ee2-125">Microsoft StaffHub PowerShell リファレンス</span><span class="sxs-lookup"><span data-stu-id="d8ee2-125">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="d8ee2-126">Microsoft StaffHub のチームを Teams の Shifts に移動する</span><span class="sxs-lookup"><span data-stu-id="d8ee2-126">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
