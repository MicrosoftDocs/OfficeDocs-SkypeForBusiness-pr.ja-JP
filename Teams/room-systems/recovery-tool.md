---
title: Microsoft Teams Rooms の回復ツールを使用する
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: davgroom
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
ms.collection: M365-voice
localization_priority: Normal
description: この記事では、Microsoft Teams 室の回復ツールの使用方法について説明します。この機能は、サポートされている状態にシステムを移行するために使用します。
ms.openlocfilehash: cbfb3ef1ec033389894b3b7479e454160dc77b1b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305485"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="d8818-103">Microsoft Teams Rooms の回復ツールを使用する</span><span class="sxs-lookup"><span data-stu-id="d8818-103">Use the Microsoft Teams Rooms recovery tool</span></span>
 
<span data-ttu-id="d8818-104">この記事では、Microsoft Teams 室の回復ツールの使用方法について説明します。この機能は、サポートされている状態にシステムを移行するために使用します。</span><span class="sxs-lookup"><span data-stu-id="d8818-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="d8818-105">このツールは、Microsoft Teams の [会議室] コンソールに "システム構成の終了" というエラーが表示されている場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="d8818-105">You would use this tool when the Microsoft Teams Rooms console shows a "system config out of date" error.</span></span>
  

<span data-ttu-id="d8818-106"><a name="Prerequisites"> </a></span><span class="sxs-lookup"><span data-stu-id="d8818-106"></span></span>  
## <a name="prerequisites"></a><span data-ttu-id="d8818-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="d8818-107">Prerequisites</span></span>

<span data-ttu-id="d8818-108">最新の[Microsoft Teams ルームインストールパッケージ](https://go.microsoft.com/fwlink/?linkid=851168)をダウンロードし、それを USB メモリスティックまたは Microsoft teams 室デバイスにアクセスできるネットワーク共有に抽出します。</span><span class="sxs-lookup"><span data-stu-id="d8818-108">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

<span data-ttu-id="d8818-109">また、 [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8818-109">You may also need to install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span>

<span data-ttu-id="d8818-110"><a name="Windows-ver"> </a></span><span class="sxs-lookup"><span data-stu-id="d8818-110"></span></span>
## <a name="verify-windows-version"></a><span data-ttu-id="d8818-111">Windows のバージョンを確認する</span><span class="sxs-lookup"><span data-stu-id="d8818-111">Verify Windows Version</span></span> 

1. <span data-ttu-id="d8818-112">Microsoft Teams 室のデバイスから**Settings> Windows Setting> admin のサインイン**にアクセスして、管理者アカウントにログインします。</span><span class="sxs-lookup"><span data-stu-id="d8818-112">Login to an admin account by going to **Settings> Windows Setting> Admin Sign In** from the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="d8818-113">このオプションでは、ログイン画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8818-113">This option brings you to the login screen.</span></span>
2. <span data-ttu-id="d8818-114">既定の管理者アカウントであるパスワード`admin` `sfb`を使って、管理者アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="d8818-114">Sign into an admin account, the default admin account being `admin` with the password `sfb`.</span></span>
3. <span data-ttu-id="d8818-115">[スタート] メニューをクリックし`winver.exe`て、検索ボックスに入力し、結果に対して [\**実行]* をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8818-115">Click on the start menu and type `winver.exe` into the search box and click \**Run Command* on the result.</span></span>
4. <span data-ttu-id="d8818-116">[情報] ウィンドウの2行目の [バージョン] の後の番号をメモしておきます。</span><span class="sxs-lookup"><span data-stu-id="d8818-116">Make note of the number after 'Version' on the second line of the info pane.</span></span>

>[!NOTE]
><span data-ttu-id="d8818-117">表示されているバージョンが1607以前の場合は、「回復<a href="#Windows-up">前に Windows を更新</a>する」の手順に従って、Proceding を<a href="#Perform">実行</a>してください。</span><span class="sxs-lookup"><span data-stu-id="d8818-117">If the Version shown is 1607 or earlier, follow the steps in the <a href="#Windows-up">Update Windows before recovery</a> steps before proceding to the <a href="#Perform">Perform a recovery</a> steps.</span></span> <span data-ttu-id="d8818-118">表示されているバージョンが1607よりも大きい場合は、「<a href="#Perform">回復を実行する</a>」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="d8818-118">If the Version shown is greater than 1607, follow only the steps in <a href="#Perform">Perform a recovery</a>.</span></span>

<span data-ttu-id="d8818-119"><a name="Windows-up"> </a></span><span class="sxs-lookup"><span data-stu-id="d8818-119"></span></span>
## <a name="update-windows-before-recovery-if-needed"></a><span data-ttu-id="d8818-120">回復前に Windows を更新する (必要な場合)</span><span class="sxs-lookup"><span data-stu-id="d8818-120">Update Windows before recovery (if needed)</span></span>

1. <span data-ttu-id="d8818-121">引き続き管理者ユーザーとしてログインしている場合は、管理者特権の Powershell プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="d8818-121">While still logged in as an admin user, launch an elevated Powershell prompt.</span></span>
2. <span data-ttu-id="d8818-122">コマンド`Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`を実行します。</span><span class="sxs-lookup"><span data-stu-id="d8818-122">Run the command `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span></span>
3. <span data-ttu-id="d8818-123">Windows Update を実行して、Windows 1709 用の更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d8818-123">Run Windows Update and install the update for Windows 1709.</span></span>
4. <span data-ttu-id="d8818-124">1709への更新が完了したら、管理者アカウントにサインインし直して、 [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="d8818-124">After the update to 1709 is complete sign back into admin account and install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span> <span data-ttu-id="d8818-125">更新は、リンクから、または Windows Update を使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d8818-125">The update may be done from the link or using Windows Update.</span></span>
5. <span data-ttu-id="d8818-126">オプションの手順として、Windows Update から入手できる追加の更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d8818-126">As an optional step, install any additional updates available from Windows Update.</span></span>

<span data-ttu-id="d8818-127"><a name="Perform"> </a></span><span class="sxs-lookup"><span data-stu-id="d8818-127"></span></span>
## <a name="perform-a-recovery"></a><span data-ttu-id="d8818-128">回復を実行する</span><span class="sxs-lookup"><span data-stu-id="d8818-128">Perform a recovery</span></span>

1. <span data-ttu-id="d8818-129">Microsoft Teams 室のデバイスで管理者アカウントにサインインして、管理者特権のコマンドプロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="d8818-129">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2. <span data-ttu-id="d8818-130">Microsoft teams 室のインストールパッケージから抽出されたファイルに含ま`RecoveryTool.ps1`れているファイルにアクセスできる、microsoft Teams のルームデバイスから確認します。</span><span class="sxs-lookup"><span data-stu-id="d8818-130">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1` file, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="d8818-131">キットは、前提条件を準備するときに使用したネットワーク共有または USB ドライブにあります。</span><span class="sxs-lookup"><span data-stu-id="d8818-131">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3. <span data-ttu-id="d8818-132">Powershell .exe コマンド`-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`を実行します。</span><span class="sxs-lookup"><span data-stu-id="d8818-132">Run the Powershell.exe command `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4. <span data-ttu-id="d8818-133">スクリプト選択オプション`1:"Repair System"`のプロンプトが表示された場合。</span><span class="sxs-lookup"><span data-stu-id="d8818-133">When prompted by the script select option `1:"Repair System"`.</span></span>
5. <span data-ttu-id="d8818-134">完了したら、Microsoft Teams 室のデバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="d8818-134">Upon completion, reboot the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="d8818-135">自動的に再起動され、2回目の回復が完了します。</span><span class="sxs-lookup"><span data-stu-id="d8818-135">It will reboot again automatically and come up fully recovered the second time.</span></span>



<span data-ttu-id="d8818-136"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="d8818-136"></span></span>  
## <a name="see-also"></a><span data-ttu-id="d8818-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8818-137">See also</span></span>
 
[<span data-ttu-id="d8818-138">Microsoft Teams Rooms ヘルプ</span><span class="sxs-lookup"><span data-stu-id="d8818-138">Microsoft Teams Rooms help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="d8818-139">Microsoft Teams Rooms を管理する</span><span class="sxs-lookup"><span data-stu-id="d8818-139">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
