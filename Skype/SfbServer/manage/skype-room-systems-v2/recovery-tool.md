---
title: Skype ルーム システム v2 の回復ツールを使用します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: この資料では、Skype ルーム システム v2 は、サポートされている状態にする最新のシステムを使用する回復ツールを使用する方法について説明します。
ms.openlocfilehash: cd8e05be686cef1df44f364c515a6116edf06209
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2018
ms.locfileid: "19504979"
---
# <a name="use-the-skype-room-systems-v2-recovery-tool"></a><span data-ttu-id="d1f6a-103">Skype ルーム システム v2 の回復ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-103">Use the Skype Room Systems v2 recovery tool</span></span>
 
<span data-ttu-id="d1f6a-104">この資料では、Skype ルーム システム v2 は、サポートされている状態にする最新のシステムを使用する回復ツールを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-104">This article discusses how to use the recovery tool for Skype Room Systems v2, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="d1f6a-105">Skype ルーム システム v2 のコンソールに「最新のシステム構成」のエラーが表示されて、このツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-105">You would use this tool when the Skype Room Systems v2 console shows a "system config out of date" error.</span></span>
  

<span data-ttu-id="d1f6a-106"><a name="Prerequisites"> </a></span><span class="sxs-lookup"><span data-stu-id="d1f6a-106"></span></span>  
## <a name="prerequisites"></a><span data-ttu-id="d1f6a-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="d1f6a-107">Prerequisites</span></span>

<span data-ttu-id="d1f6a-108">最新[Skype ルーム システム v2 のインストール パッケージ](https://go.microsoft.com/fwlink/?linkid=851168)をダウンロードし、USB メモリ スティックまたはネットワーク共有 Skype ルーム システムのバージョン 2 のデバイスにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-108">Download the latest [Skype Room Systems v2 installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Skype Room Systems v2 device.</span></span>

<span data-ttu-id="d1f6a-109">[KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)をインストールする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-109">You may also need to install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span>

<span data-ttu-id="d1f6a-110"><a name="Windows-ver"> </a></span><span class="sxs-lookup"><span data-stu-id="d1f6a-110"></span></span>
## <a name="verify-windows-version"></a><span data-ttu-id="d1f6a-111">Windows のバージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-111">Verify Windows Version</span></span> 

1. <span data-ttu-id="d1f6a-112">管理者アカウントへのログイン**の設定 > Windows の設定 > 管理者へのサインイン**Skype ルーム システム v2 デバイスから。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-112">Login to an admin account by going to **Settings> Windows Setting> Admin Sign In** from the Skype Room Systems v2 device.</span></span> <span data-ttu-id="d1f6a-113">このオプションでは、ログイン画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-113">This option brings you to the login screen.</span></span>
2. <span data-ttu-id="d1f6a-114">既定の管理者、管理者用のアカウントにサインイン中のアカウント`admin`パスワードを使用して`sfb`。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-114">Sign into an admin account, the default admin account being `admin` with the password `sfb`.</span></span>
3. <span data-ttu-id="d1f6a-115">[スタート] メニューをクリックして`winver.exe`をクリックして、[検索] ボックスに \**コマンドの実行*結果をします。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-115">Click on the start menu and type `winver.exe` into the search box and click \**Run Command* on the result.</span></span>
4. <span data-ttu-id="d1f6a-116">情報ウィンドウの 2 番目の行で 'バージョン' の後の番号を書き留めます。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-116">Make note of the number after 'Version' on the second line of the info pane.</span></span>

>[!NOTE]
><span data-ttu-id="d1f6a-117">1607 またはそれ以前に、新しいバージョンがある場合次の手順に進む前に<a href="#Windows-up">回復する前に更新プログラムの Windows</a>の手順の<a href="#Perform">リカバリを実行する</a>手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-117">If the Version shown is 1607 or earlier, follow the steps in the <a href="#Windows-up">Update Windows before recovery</a> steps before proceding to the <a href="#Perform">Perform a recovery</a> steps.</span></span> <span data-ttu-id="d1f6a-118">表示されるバージョンが 1607 よりも大きい場合は、手順をのみ<a href="#Perform">実行するリカバリ</a>です。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-118">If the Version shown is greater than 1607, follow only the steps in <a href="#Perform">Perform a recovery</a>.</span></span>

<span data-ttu-id="d1f6a-119"><a name="Windows-up"> </a></span><span class="sxs-lookup"><span data-stu-id="d1f6a-119"></span></span>
## <a name="update-windows-before-recovery-if-needed"></a><span data-ttu-id="d1f6a-120">(必要な場合)、回復する前に Windows を更新します。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-120">Update Windows before recovery (if needed)</span></span>

1. <span data-ttu-id="d1f6a-121">Admin ユーザーとしてログインしたまま、中には、管理者として Powershell プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-121">While still logged in as an admin user, launch an elevated Powershell prompt.</span></span>
2. <span data-ttu-id="d1f6a-122">コマンドを実行して`Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-122">Run the command `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span></span>
3. <span data-ttu-id="d1f6a-123">Windows Update を実行し、Windows 1709 用の更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-123">Run Windows Update and install the update for Windows 1709.</span></span>
4. <span data-ttu-id="d1f6a-124">1709 を更新した後、完全な記号は管理者アカウントにバックアップし、 [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-124">After the update to 1709 is complete sign back into admin account and install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span> <span data-ttu-id="d1f6a-125">リンクから更新プログラムを実行することがありますまたは Windows Update を使用します。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-125">The update may be done from the link or using Windows Update.</span></span>
5. <span data-ttu-id="d1f6a-126">省略可能な手順としては、Windows Update からの追加の更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-126">As an optional step, install any additional updates available from Windows Update.</span></span>

<span data-ttu-id="d1f6a-127"><a name="Perform"> </a></span><span class="sxs-lookup"><span data-stu-id="d1f6a-127"></span></span>
## <a name="perform-a-recovery"></a><span data-ttu-id="d1f6a-128">リカバリを実行します。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-128">Perform a recovery</span></span>

1. <span data-ttu-id="d1f6a-129">Skype ルーム システム v2 デバイスの管理者アカウントにサインインし、管理者特権でコマンド プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-129">Sign in to the admin account on your Skype Room Systems v2 device, and launch an elevated command prompt.</span></span>
2. <span data-ttu-id="d1f6a-130">Skype ルーム システム v2 デバイスからできることを確認するにアクセスするのには、 `RecoveryTool.ps1` 、Skype ルーム システム v2 のインストール パッケージから抽出されたファイルに含まれるファイルです。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-130">Verify from the Skype Room Systems v2 device that you are able to access the `RecoveryTool.ps1` file, which is included in the files extracted from the Skype Room Systems v2 installation package.</span></span> <span data-ttu-id="d1f6a-131">必須コンポーネントを準備する際に使用する USB ドライブ、ネットワーク共有上のキットをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-131">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3. <span data-ttu-id="d1f6a-132">Powershell.exe コマンドを実行して`-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-132">Run the Powershell.exe command `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4. <span data-ttu-id="d1f6a-133">スクリプトのオプションを選択してメッセージが表示されたら`1:"Repair System"`。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-133">When prompted by the script select option `1:"Repair System"`.</span></span>
5. <span data-ttu-id="d1f6a-134">完了すると、Skype ルーム システム v2 のデバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-134">Upon completion, reboot the Skype Room Systems v2 device.</span></span> <span data-ttu-id="d1f6a-135">もの完全に回復した 2 回目、もう一度自動的に再起動されます。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-135">It will reboot again automatically and come up fully recovered the second time.</span></span>



<span data-ttu-id="d1f6a-136"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="d1f6a-136"></span></span>  
## <a name="see-also"></a><span data-ttu-id="d1f6a-137">この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。</span><span class="sxs-lookup"><span data-stu-id="d1f6a-137">See also</span></span>
 
[<span data-ttu-id="d1f6a-138">Skype ルーム システムのバージョン 2 のヘルプ</span><span class="sxs-lookup"><span data-stu-id="d1f6a-138">Skype Room Systems version 2 help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="d1f6a-139">Skype Room Systems バージョン 2 を管理する</span><span class="sxs-lookup"><span data-stu-id="d1f6a-139">Manage Skype Room Systems v2</span></span>](skype-room-systems-v2.md)