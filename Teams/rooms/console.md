---
title: Microsoft Teams 室コンソールを構成する
ms.author: v-lanac
author: lanachin
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: この記事では、Microsoft Teams のルーム本体とその周辺機器を設定する方法について説明します。
ms.openlocfilehash: c91c570cd83cc07f1f15823623f2b02a2ebcddf4
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826095"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a><span data-ttu-id="78f48-103">Microsoft Teams 室コンソールを構成する</span><span class="sxs-lookup"><span data-stu-id="78f48-103">Configure a Microsoft Teams Rooms console</span></span>

<span data-ttu-id="78f48-104">この記事では、Microsoft Teams のルーム本体とその周辺機器を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="78f48-104">This article describes how to set up the Microsoft Teams Rooms console and its peripherals.</span></span>
  
<span data-ttu-id="78f48-105">以下の手順は、「 [Microsoft Teams ルームの展開](rooms-deploy.md)」の説明に従って、必要な Microsoft teams または Skype for Business および Exchange アカウントが既に作成およびテストされている場合にのみ実行してください。</span><span class="sxs-lookup"><span data-stu-id="78f48-105">You should only perform these steps if the necessary Microsoft Teams or Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Microsoft Teams Rooms](rooms-deploy.md).</span></span> <span data-ttu-id="78f48-106">[Microsoft Teams の会議室の要件](requirements.md)について説明されているハードウェアとソフトウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="78f48-106">You will need the hardware and software described in [Microsoft Teams Rooms requirements](requirements.md).</span></span> <span data-ttu-id="78f48-107">このトピックには次のセクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="78f48-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="78f48-108">インストールメディアを準備する</span><span class="sxs-lookup"><span data-stu-id="78f48-108">Prepare the installation media</span></span>](console.md#Prep_Media)
- [<span data-ttu-id="78f48-109">プライベート CA 証明書をコンソールにインストールする</span><span class="sxs-lookup"><span data-stu-id="78f48-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
- [<span data-ttu-id="78f48-110">Windows 10 と Microsoft Teams のルームコンソールアプリをインストールする</span><span class="sxs-lookup"><span data-stu-id="78f48-110">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>](console.md#Reimage)
- [<span data-ttu-id="78f48-111">本体の初期設定</span><span class="sxs-lookup"><span data-stu-id="78f48-111">Initial set up of the console</span></span>](console.md#Initial)
- [<span data-ttu-id="78f48-112">Microsoft Teams のルーム展開のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="78f48-112">Microsoft Teams Rooms deployment checklist</span></span>](console.md#Checklist)

> [!NOTE]
> <span data-ttu-id="78f48-113">Microsoft Teams のルームは、適切に構成された Microsoft Teams または Skype for Business 環境でのみ機能します。ここでは、「 [Microsoft Teams ルームを展開](rooms-deploy.md)する」の説明に従って、デバイスアカウントが正しく設定されています。</span><span class="sxs-lookup"><span data-stu-id="78f48-113">Microsoft Teams Rooms will only work in a properly configured Microsoft Teams or Skype for Business environment where the device accounts are set up correctly as described in [Deploy Microsoft Teams Rooms](rooms-deploy.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="78f48-114">インストールメディアを準備する</span><span class="sxs-lookup"><span data-stu-id="78f48-114">Prepare the installation media</span></span>
<span data-ttu-id="78f48-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="78f48-115"><a name="Prep_Media"> </a></span></span>

<span data-ttu-id="78f48-116">Microsoft Teams のルームコンソールアプリをインストールするには、少なくとも 32 GB の容量を備えた USB ストレージデバイスが必要です。</span><span class="sxs-lookup"><span data-stu-id="78f48-116">Installing the Microsoft Teams Rooms console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="78f48-117">デバイスにその他のファイルは存在しません。USB ストレージ上の既存のファイルは失われます。</span><span class="sxs-lookup"><span data-stu-id="78f48-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="78f48-118">この手順に従って Microsoft Teams ルームのインストールメディアを作成しても、予期しない動作が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="78f48-118">Failure to create your Microsoft Teams Rooms installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="78f48-119">次のプロセスは、新しい Microsoft Teams 室のデバイスにイメージを追加するインストールメディアを作成することです。</span><span class="sxs-lookup"><span data-stu-id="78f48-119">The process below is for creating installation media to image new Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="78f48-120">既定では、既存のデバイスは、Windows Update と Windows ストアから自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="78f48-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78f48-121">Microsoft Teams ルームの作成に使用される Windows 10 コンピューターは、ターゲットインストールメディアと同じバージョンまたはそれ以降のバージョンの Windows にインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="78f48-121">The Windows 10 machine used to create the Microsoft Teams Rooms installation media must be on the same or later version of Windows as the target installation media.</span></span>
  
1. <span data-ttu-id="78f48-122">メディアのロードスクリプトをダウンロードします[。](https://go.microsoft.com/fwlink/?linkid=867842)</span><span class="sxs-lookup"><span data-stu-id="78f48-122">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="78f48-123">Windows 10 マシン上で管理者特権でのプロンプトから CreateSrsMedia.ps1 スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="78f48-123">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="78f48-124">スクリプトの手順に従って、Microsoft Teams の会議セットアップディスクを作成します。</span><span class="sxs-lookup"><span data-stu-id="78f48-124">Follow the script's instructions to create a Microsoft Teams Rooms USB setup disk.</span></span>


> [!TIP]
> <span data-ttu-id="78f48-125">表示されるのは、"/ファイルの記録" というスクリプトが起動するたびに、画面出力には、そのセッションのログファイルまたはトランスクリプトの名前が含まれます。</span><span class="sxs-lookup"><span data-stu-id="78f48-125">Each time the CreateSrsMedia.ps1 script starts, the screen output will include the name of a log file or transcript for the session.</span></span> <span data-ttu-id="78f48-126">スクリプトの実行で問題が発生した場合は、サポートのリクエスト時にそのトランスクリプトのコピーが入手可能であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="78f48-126">If there are issues with running the script, make sure to have a copy of that transcript available when requesting support.</span></span> 

<span data-ttu-id="78f48-127">このスクリプトは、次のタスクを自動化します。</span><span class="sxs-lookup"><span data-stu-id="78f48-127">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="78f48-128">Microsoft Teams ルーム用の最新の MSI インストーラーをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="78f48-128">Download the latest MSI installer for Microsoft Teams Rooms.</span></span>
2. <span data-ttu-id="78f48-129">ユーザーが指定する必要がある Windows のビルドを確認します。</span><span class="sxs-lookup"><span data-stu-id="78f48-129">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="78f48-130">最新のリリース版は、Microsoft Teams 室のデバイスでの使用が、テストおよびサポートされていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="78f48-130">The most recently released versions may or may not be tested and supported for use with Microsoft Teams Rooms devices.</span></span>
3. <span data-ttu-id="78f48-131">必要なサポートコンポーネントをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="78f48-131">Download necessary supporting components.</span></span>
4. <span data-ttu-id="78f48-132">インストールメディアで必要なコンポーネントを組み立てます。</span><span class="sxs-lookup"><span data-stu-id="78f48-132">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="78f48-133">Windows 10 の特定のバージョンが必要です。このバージョンはボリュームライセンスのお客様のみが利用できます。</span><span class="sxs-lookup"><span data-stu-id="78f48-133">A specific version of Windows 10 is required, and this version is only available to volume licensing customers.</span></span>  <span data-ttu-id="78f48-134">[ボリュームライセンスサービスセンター](https://www.microsoft.com/Licensing/servicecenter/)からコピーを取得できます。</span><span class="sxs-lookup"><span data-stu-id="78f48-134">You can get a copy from the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).</span></span>

<span data-ttu-id="78f48-135">完了したら、コンピューターから USB ディスクを取り出して、「 [Windows 10 と Microsoft Teams のルームコンソールアプリをインストール](console.md#Reimage)する」に進みます。</span><span class="sxs-lookup"><span data-stu-id="78f48-135">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Microsoft Teams Rooms console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a><span data-ttu-id="78f48-136">Windows 10 と Microsoft Teams のルームコンソールアプリをインストールする</span><span class="sxs-lookup"><span data-stu-id="78f48-136">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>
<span data-ttu-id="78f48-137"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="78f48-137"><a name="Reimage"> </a></span></span>

<span data-ttu-id="78f48-138">作成したセットアップメディアを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78f48-138">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="78f48-139">ターゲットデバイスはアプライアンスとして実行され、既定のユーザーは Microsoft Teams 室コンソールアプリのみを実行するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="78f48-139">The target device will run as an appliance and the default user will be set to only run the Microsoft Teams Rooms console app.</span></span>

1. <span data-ttu-id="78f48-140">ターゲットデバイスが dock (Surface Pro など) に装着されている場合は、dock から接続を切断します。</span><span class="sxs-lookup"><span data-stu-id="78f48-140">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="78f48-141">ターゲットデバイスがネットワークに接続されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="78f48-141">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="78f48-142">ターゲットデバイスが AC 電源に接続されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="78f48-142">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="78f48-143">USB セットアップディスクをターゲットデバイスに接続します。</span><span class="sxs-lookup"><span data-stu-id="78f48-143">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="78f48-144">USB セットアップディスクを起動します。</span><span class="sxs-lookup"><span data-stu-id="78f48-144">Boot to the USB setup disk.</span></span> <span data-ttu-id="78f48-145">製造元の指示を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78f48-145">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="78f48-146">ターゲットデバイスが Surface Pro である場合は、次の手順を使用して USB セットアップディスクを起動します。</span><span class="sxs-lookup"><span data-stu-id="78f48-146">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="78f48-147">a.</span><span class="sxs-lookup"><span data-stu-id="78f48-147">a.</span></span> <span data-ttu-id="78f48-148">[音量を下げる] (-) ボタンを押し続けます。</span><span class="sxs-lookup"><span data-stu-id="78f48-148">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="78f48-149">b.</span><span class="sxs-lookup"><span data-stu-id="78f48-149">b.</span></span> <span data-ttu-id="78f48-150">電源ボタンを押してから離します。</span><span class="sxs-lookup"><span data-stu-id="78f48-150">Press and release the power button.</span></span>

    <span data-ttu-id="78f48-151">c.</span><span class="sxs-lookup"><span data-stu-id="78f48-151">c.</span></span> <span data-ttu-id="78f48-152">Windows セットアップが起動したら、ボリューム ダウン (-) ボタンを離します。</span><span class="sxs-lookup"><span data-stu-id="78f48-152">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="78f48-153">インストールが完了すると、システムはシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="78f48-153">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="78f48-154">システムがシャットダウンされたら、USB セットアップディスクを削除しても安全です。</span><span class="sxs-lookup"><span data-stu-id="78f48-154">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="78f48-155">この時点で、ドックにターゲットデバイスを配置し (dock ベースの製品を使用している場合)、会議室に必要な周辺機器を接続し、ネットワークに接続することができます。</span><span class="sxs-lookup"><span data-stu-id="78f48-155">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="78f48-156">製造元の指示を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78f48-156">Refer to the manufacturer instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="78f48-157">Microsoft Teams 会議室のソフトウェア更新プログラムは、一般法人向け Microsoft Store から自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="78f48-157">Software updates for Microsoft Teams Rooms are automatically downloaded from the Microsoft Store for Business.</span></span> <span data-ttu-id="78f48-158">会議室コンソールがストアにアクセスして自己更新を行うことができることを確認するには、「 [Microsoft Store For Business And エデュケーション用の前提条件](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78f48-158">See [Prerequisites for Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) to verify that the room console will be able to access the store and self-update.</span></span>  

### <a name="selecting-a-language"></a><span data-ttu-id="78f48-159">言語の選択</span><span class="sxs-lookup"><span data-stu-id="78f48-159">Selecting a language</span></span> 

<span data-ttu-id="78f48-160">Creator の更新では、暗黙的な言語の選択によって、ユーザーが実際のアプリケーション言語を使用していない場合 (たとえば、コンソールアプリをフランス語で起動する必要がある場合)、ApplyCurrentRegionAndLanguage. ps1 スクリプトを使用する必要があります。これは英語で提供されています)。</span><span class="sxs-lookup"><span data-stu-id="78f48-160">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="78f48-161">次の手順は、Windows Creator の更新プログラムを使用して作成されたコンソールでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="78f48-161">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="78f48-162">新しいプロビジョニングシステムでメディアを使用して設定していないレガシー/市場システムでは、これらの手順を使用することはできませんが、この手動介入が必要となる最初の問題には影響しません。また、セットアップの一環としてアプリの言語を明示的に選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="78f48-162">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="78f48-163">必要な言語を適用するには</span><span class="sxs-lookup"><span data-stu-id="78f48-163">To apply your desired language</span></span>

1. <span data-ttu-id="78f48-164">管理モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="78f48-164">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="78f48-165">[スタート] メニューを選択します。</span><span class="sxs-lookup"><span data-stu-id="78f48-165">Select the Start menu.</span></span>
    
3. <span data-ttu-id="78f48-166">ギア アイコンを選択して [**設定**] アプリを起動します。</span><span class="sxs-lookup"><span data-stu-id="78f48-166">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="78f48-167">[**時刻&amp;の言語**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="78f48-167">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="78f48-168">[**地域&amp;の言語**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="78f48-168">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="78f48-169">[**言語の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="78f48-169">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="78f48-170">追加する言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="78f48-170">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="78f48-171">[言語] リストに追加した言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="78f48-171">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="78f48-172">[**既定に設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="78f48-172">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="78f48-173">削除する言語については、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="78f48-173">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="78f48-p115">a. 削除する言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="78f48-p115">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="78f48-p116">b. [**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="78f48-p116">b. Select **Remove**.</span></span>
    
11. <span data-ttu-id="78f48-178">管理者特権でコマンド プロンプトを開始します。</span><span class="sxs-lookup"><span data-stu-id="78f48-178">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="78f48-179">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="78f48-179">Run the following command:</span></span> 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="78f48-180">システムを再起動します。</span><span class="sxs-lookup"><span data-stu-id="78f48-180">Restart the system.</span></span>
    
<span data-ttu-id="78f48-181">目的の言語が Microsoft Teams のルームコンソールに適用されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="78f48-181">Your desired language is now applied to the Microsoft Teams Rooms console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="78f48-182">本体の初期設定</span><span class="sxs-lookup"><span data-stu-id="78f48-182">Initial set up of the console</span></span>
<span data-ttu-id="78f48-183"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="78f48-183"><a name="Initial"> </a></span></span>

<span data-ttu-id="78f48-184">Windows をインストールした後、Microsoft Teams のルームコンソールアプリは、次に起動したとき、または/reboot オプションが選択されたときに、初期セットアッププロセスに進みます。</span><span class="sxs-lookup"><span data-stu-id="78f48-184">After Windows is installed, the Microsoft Teams Rooms console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="78f48-185">[ユーザー アカウント] 画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="78f48-185">The User Account screen appears.</span></span> <span data-ttu-id="78f48-186">コンソールで使用する会議室アカウントの Skype サインインアドレス (user@domain 形式) を入力します。</span><span class="sxs-lookup"><span data-stu-id="78f48-186">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="78f48-187">ルーム アカウントのパスワードを入力し、確認のためにもう一度入力します。</span><span class="sxs-lookup"><span data-stu-id="78f48-187">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="78f48-188">[ドメインの構成] で、Skype for Business Server の FQDN を設定します。</span><span class="sxs-lookup"><span data-stu-id="78f48-188">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="78f48-189">Skype for Business SIP ドメインがユーザーの Exchange ドメインと異なる場合は、このフィールドに Exchange ドメインを入力します。</span><span class="sxs-lookup"><span data-stu-id="78f48-189">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="78f48-190">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="78f48-190">Click **Next**.</span></span>
    
5. <span data-ttu-id="78f48-191">[機能] 画面で指示されたデバイスを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="78f48-191">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="78f48-192">既定では、自動画面共有はオンで、会議名の非表示はオフになっています。</span><span class="sxs-lookup"><span data-stu-id="78f48-192">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="78f48-193">選択対象のデバイスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="78f48-193">The devices to select are:</span></span>
    
   - <span data-ttu-id="78f48-194">会議用のマイク: 会議室で使用する既定のマイク。</span><span class="sxs-lookup"><span data-stu-id="78f48-194">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="78f48-195">会議用のスピーカー: 会議で使用する既定のスピーカー。</span><span class="sxs-lookup"><span data-stu-id="78f48-195">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="78f48-196">既定のスピーカー: HDMI インジェストからのオーディオ用に使用されるスピーカー。</span><span class="sxs-lookup"><span data-stu-id="78f48-196">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="78f48-p120">それぞれの項目に、選択できるドロップダウン メニューのオプションがあります。各デバイスについて選択を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="78f48-p120">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="78f48-199">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="78f48-199">Click **Finish**.</span></span>
    
<span data-ttu-id="78f48-200">Microsoft Teams のルームコンソールアプリは、上で入力された資格情報を使って Skype for Business Server へのサインインを開始し、同じ資格情報を使用して、予定表の Exchange との同期を開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78f48-200">The Microsoft Teams Rooms console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="78f48-201">コンソールアプリの使い方の詳細については、「 [Microsoft Teams ルームのヘルプ](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78f48-201">For details on using the console app, refer to the [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="78f48-202">Microsoft Teams のルームは、認定された本体のハードウェアの存在に依存します。</span><span class="sxs-lookup"><span data-stu-id="78f48-202">Microsoft Teams Rooms relies on the presence of certified console hardware.</span></span> <span data-ttu-id="78f48-203">Microsoft Teams のルームコンソールアプリが正しく作成された画像も、本体のハードウェアが検出されていない限り、初期セットアップ手順を実行しても起動しません。</span><span class="sxs-lookup"><span data-stu-id="78f48-203">Even a correctly created image containing the Microsoft Teams Rooms console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="78f48-204">Surface Pro ベースのソリューションの場合、このチェックに合格するには、Surface Pro が付随する dock ハードウェアに接続されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="78f48-204">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="78f48-205">一部の英語以外の言語ユーザーは、タッチキーボードで記号がサポートされていない場合は、最初のセットアップ中に本体に物理キーボードが接続されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="78f48-205">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="78f48-206">プライベート CA 証明書をコンソールにインストールする</span><span class="sxs-lookup"><span data-stu-id="78f48-206">Install a private CA certificate on the console</span></span>
<span data-ttu-id="78f48-207"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="78f48-207"><a name="Certs"> </a></span></span>

<span data-ttu-id="78f48-208">Microsoft Teams のルームコンソールは、接続先のサーバーで使用されている証明書を信頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78f48-208">The Microsoft Teams Rooms console needs to trust the certificates used by the servers it connects to.</span></span> <span data-ttu-id="78f48-209">O365 の場合、これらのサーバーはパブリックの証明機関を使用し、これらは Windows 10 で自動的に信頼されるため、この処理は自動的に行われます。</span><span class="sxs-lookup"><span data-stu-id="78f48-209">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="78f48-210">証明機関が非公開の場合 (Active Directory と Windows 証明機関を使ったオンプレミスの展開など)、次の2つの方法で、Microsoft Teams のルームコンソールに証明書を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="78f48-210">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Microsoft Teams Rooms console in a couple of ways:</span></span>
  
- <span data-ttu-id="78f48-211">コンソールを Active Directory に参加すると、証明機関が Active Directory に公開されている場合は、必要な証明書が自動的に追加されます (通常の展開オプション)。</span><span class="sxs-lookup"><span data-stu-id="78f48-211">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="78f48-212">イメージング処理の後に証明書を手動でインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="78f48-212">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="78f48-213">この操作を行う前に、[本体の初期設定](console.md#Initial)を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78f48-213">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="78f48-214">証明書を手動でインストールするには </span><span class="sxs-lookup"><span data-stu-id="78f48-214">To manually install the certificate</span></span>

1. <span data-ttu-id="78f48-215">CA 証明書をお使いのコンピューターにダウンロードして、C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer に保存します。</span><span class="sxs-lookup"><span data-stu-id="78f48-215">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="78f48-216">コンソールを管理モードで配置します (「[管理者モードとデバイス管理」を](rooms-operations.md#AdminMode)参照してください)。</span><span class="sxs-lookup"><span data-stu-id="78f48-216">Place the console in admin mode (see [Admin mode and device management](rooms-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="78f48-217">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="78f48-217">Run the following command:</span></span>
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="78f48-218">Active Directory ドメインに参加する (オプション)</span><span class="sxs-lookup"><span data-stu-id="78f48-218">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="78f48-219"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="78f48-219"><a name="Certs"> </a></span></span>

<span data-ttu-id="78f48-220">Microsoft Teams のルームコンソールをドメインに参加できます。</span><span class="sxs-lookup"><span data-stu-id="78f48-220">You can join Microsoft Teams Rooms consoles to your domain.</span></span> <span data-ttu-id="78f48-221">Microsoft Teams のルームコンソールは、多くのワークステーションポリシーが Microsoft Teams のルームと互換性がないため、PC ワークステーションとは別の OU に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78f48-221">Microsoft Teams Rooms consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Microsoft Teams Rooms.</span></span> <span data-ttu-id="78f48-222">一般的な例としては、Microsoft Teams のルームが自動的に起動しないようにするためのパスワード適用ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="78f48-222">A common example are password enforcement policies that will prevent Microsoft Teams Rooms from starting up automatically.</span></span> <span data-ttu-id="78f48-223">GPO 設定の管理については、「 [Microsoft Teams ルームを管理](rooms-operations.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78f48-223">For information about the management of GPO settings, please refer to [Manage Microsoft Teams Rooms](rooms-operations.md).</span></span>
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a><span data-ttu-id="78f48-224">Microsoft Teams のルームをドメインに参加するには</span><span class="sxs-lookup"><span data-stu-id="78f48-224">To join Microsoft Teams Rooms to a domain</span></span>

1. <span data-ttu-id="78f48-225">管理者アカウントから本体にサインインします (「[管理者モードとデバイス管理」を](rooms-operations.md#AdminMode)参照してください)。</span><span class="sxs-lookup"><span data-stu-id="78f48-225">Sign into the console from the admin account (see [Admin mode and device management](rooms-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="78f48-226">管理者特権で Powershell コマンド プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="78f48-226">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="78f48-227">Powershell に次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="78f48-227">Enter the following command in Powershell:</span></span>
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="78f48-228">たとえば、完全修飾ドメインが redmond.corp.microsoft.com で、Microsoft Teams のルームコンソールを "Resources" OU の子である "Microsoft Teams 室" OU に追加したい場合、コマンドは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="78f48-228">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Microsoft Teams Rooms consoles to be in a "Microsoft Teams Rooms" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="78f48-229">ドメインに参加するときにコンピューター名を変更するには、-NewName フラグの後にコンピューターの新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="78f48-229">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a><span data-ttu-id="78f48-230">Microsoft Teams のルーム展開のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="78f48-230">Microsoft Teams Rooms deployment checklist</span></span>
<span data-ttu-id="78f48-231"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="78f48-231"><a name="Checklist"> </a></span></span>

<span data-ttu-id="78f48-232">本体とそのすべての周辺機器が完全に設定されていることを確認するために、次のチェックリストを使用します。</span><span class="sxs-lookup"><span data-stu-id="78f48-232">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="78f48-233">**アプリケーションの設定**</span><span class="sxs-lookup"><span data-stu-id="78f48-233">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="78f48-234">☐</span><span class="sxs-lookup"><span data-stu-id="78f48-234">☐</span></span>  <br/> |<span data-ttu-id="78f48-235">ルーム アカウント名と電話番号 (PSTN が有効な場合) が、コンソール画面の右上に正しく表示される</span><span class="sxs-lookup"><span data-stu-id="78f48-235">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="78f48-236">☐</span><span class="sxs-lookup"><span data-stu-id="78f48-236">☐</span></span>  <br/> |<span data-ttu-id="78f48-237">Windows コンピューター名が正しく設定されている (リモート管理に役立つ)</span><span class="sxs-lookup"><span data-stu-id="78f48-237">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="78f48-238">☐</span><span class="sxs-lookup"><span data-stu-id="78f48-238">☐</span></span>  <br/> |<span data-ttu-id="78f48-239">管理者アカウントのパスワードが設定されており、確認済みである</span><span class="sxs-lookup"><span data-stu-id="78f48-239">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="78f48-240">☐</span><span class="sxs-lookup"><span data-stu-id="78f48-240">☐</span></span>  <br/> |<span data-ttu-id="78f48-241">すべてのファームウェア更新プログラムが適用されました</span><span class="sxs-lookup"><span data-stu-id="78f48-241">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="78f48-242">**オーディオ/ビデオ周辺機器**</span><span class="sxs-lookup"><span data-stu-id="78f48-242">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="78f48-243">☐</span><span class="sxs-lookup"><span data-stu-id="78f48-243">☐</span></span>  <br/> |<span data-ttu-id="78f48-244">カメラ周辺機器のファームウェアのバージョンが正しい (該当する場合)</span><span class="sxs-lookup"><span data-stu-id="78f48-244">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="78f48-245">☐</span><span class="sxs-lookup"><span data-stu-id="78f48-245">☐</span></span>  <br/> |<span data-ttu-id="78f48-246">カメラ機能と最適な配置</span><span class="sxs-lookup"><span data-stu-id="78f48-246">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="78f48-247">☐</span><span class="sxs-lookup"><span data-stu-id="78f48-247">☐</span></span>  <br/> |<span data-ttu-id="78f48-248">既定の再生デバイスと既定の再生通信デバイスの設定が、目的のオーディオ周辺機器に設定されている</span><span class="sxs-lookup"><span data-stu-id="78f48-248">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="78f48-249">☐</span><span class="sxs-lookup"><span data-stu-id="78f48-249">☐</span></span>  <br/> |<span data-ttu-id="78f48-250">既定の録音通信デバイスの設定が目的のオーディオ周辺機器に設定されている</span><span class="sxs-lookup"><span data-stu-id="78f48-250">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="78f48-251">☐</span><span class="sxs-lookup"><span data-stu-id="78f48-251">☐</span></span>  <br/> |<span data-ttu-id="78f48-252">オーディオ周辺機器のファームウェアのバージョンが正しい (該当する場合)</span><span class="sxs-lookup"><span data-stu-id="78f48-252">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="78f48-253">☐</span><span class="sxs-lookup"><span data-stu-id="78f48-253">☐</span></span>  <br/> |<span data-ttu-id="78f48-254">オーディオ入力デバイスが機能し、適切に配置されている</span><span class="sxs-lookup"><span data-stu-id="78f48-254">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="78f48-255">☐</span><span class="sxs-lookup"><span data-stu-id="78f48-255">☐</span></span>  <br/> |<span data-ttu-id="78f48-256">オーディオ出力デバイスが機能し、適切に配置されている</span><span class="sxs-lookup"><span data-stu-id="78f48-256">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="78f48-257">**ドック**</span><span class="sxs-lookup"><span data-stu-id="78f48-257">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="78f48-258">☐</span><span class="sxs-lookup"><span data-stu-id="78f48-258">☐</span></span>  <br/> |<span data-ttu-id="78f48-259">ケーブルが保護されており、圧迫されていない</span><span class="sxs-lookup"><span data-stu-id="78f48-259">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="78f48-260">☐</span><span class="sxs-lookup"><span data-stu-id="78f48-260">☐</span></span>  <br/> |<span data-ttu-id="78f48-261">HDMI を介したオーディオ インジェストが機能している</span><span class="sxs-lookup"><span data-stu-id="78f48-261">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="78f48-262">☐</span><span class="sxs-lookup"><span data-stu-id="78f48-262">☐</span></span>  <br/> |<span data-ttu-id="78f48-263">HDMI を介したビデオ インジェストが機能している</span><span class="sxs-lookup"><span data-stu-id="78f48-263">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="78f48-264">☐</span><span class="sxs-lookup"><span data-stu-id="78f48-264">☐</span></span>  <br/> |<span data-ttu-id="78f48-265">ドックは自由に回転することができる</span><span class="sxs-lookup"><span data-stu-id="78f48-265">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="78f48-266">☐</span><span class="sxs-lookup"><span data-stu-id="78f48-266">☐</span></span>  <br/> |<span data-ttu-id="78f48-267">表示の明るさが環境に適している</span><span class="sxs-lookup"><span data-stu-id="78f48-267">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="78f48-268">関連項目</span><span class="sxs-lookup"><span data-stu-id="78f48-268">See also</span></span>
<span data-ttu-id="78f48-269"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="78f48-269"><a name="Checklist"> </a></span></span>

[<span data-ttu-id="78f48-270">Microsoft Teams のルームを計画する</span><span class="sxs-lookup"><span data-stu-id="78f48-270">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="78f48-271">Microsoft Teams ルームの展開</span><span class="sxs-lookup"><span data-stu-id="78f48-271">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="78f48-272">Microsoft Teams 室コンソールを構成する</span><span class="sxs-lookup"><span data-stu-id="78f48-272">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="78f48-273">Microsoft Teams Rooms を管理する</span><span class="sxs-lookup"><span data-stu-id="78f48-273">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
