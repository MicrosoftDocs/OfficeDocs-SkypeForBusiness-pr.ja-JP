---
title: Microsoft Teams Rooms のコンソールを構成する
ms.author: dstrome
author: dstrome
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
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: この記事では、Microsoft Teams Rooms のコンソールとその周辺機器の設定および構成方法を説明します。
ms.openlocfilehash: 7a36ed93f370c0aeb302da246b223732383719fb
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662062"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a><span data-ttu-id="568db-103">Microsoft Teams Rooms のコンソールを構成する</span><span class="sxs-lookup"><span data-stu-id="568db-103">Configure a Microsoft Teams Rooms console</span></span>

<span data-ttu-id="568db-104">この記事では、Microsoft Teams Rooms のコンソールとその周辺機器の設定方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="568db-104">This article describes how to set up the Microsoft Teams Rooms console and its peripherals.</span></span>
  
<span data-ttu-id="568db-105">これらの手順は、「[デプロイの概要](rooms-deploy.md)」で説明されているように、必要な Microsoft Teams アカウントや Skype for Business のアカウントと Exchange アカウントが既に作成されている場合にのみ実行してください。</span><span class="sxs-lookup"><span data-stu-id="568db-105">You should only perform these steps if the necessary Microsoft Teams or Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Microsoft Teams Rooms](rooms-deploy.md).</span></span> <span data-ttu-id="568db-106">「[Microsoft Teams Rooms の要件](requirements.md)」で説明されているハードウェアとソフトウェアが必要になります。</span><span class="sxs-lookup"><span data-stu-id="568db-106">You will need the hardware and software described in [Microsoft Teams Rooms requirements](requirements.md).</span></span> <span data-ttu-id="568db-107">このトピックには次のセクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="568db-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="568db-108">インストール メディアを準備する</span><span class="sxs-lookup"><span data-stu-id="568db-108">Prepare the installation media</span></span>](console.md#Prep_Media)
- [<span data-ttu-id="568db-109">コンソールにプライベート CA 証明書をインストールする</span><span class="sxs-lookup"><span data-stu-id="568db-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
- [<span data-ttu-id="568db-110">Windows 10 と Microsoft Teams Rooms のコンソール アプリをインストールする</span><span class="sxs-lookup"><span data-stu-id="568db-110">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>](console.md#Reimage)
- [<span data-ttu-id="568db-111">コンソールの初期設定</span><span class="sxs-lookup"><span data-stu-id="568db-111">Initial set up of the console</span></span>](console.md#Initial)
- [<span data-ttu-id="568db-112">Microsoft Teams Rooms のデプロイ チェックリスト</span><span class="sxs-lookup"><span data-stu-id="568db-112">Microsoft Teams Rooms deployment checklist</span></span>](console.md#Checklist)

> [!NOTE]
> <span data-ttu-id="568db-113">Microsoft Teams Rooms は、「[デプロイの概要](rooms-deploy.md)」で説明されているとおりにデバイス アカウントが正しく設定されている、適切に構成された Microsoft Teams 環境または Skype for Business 環境でのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="568db-113">Microsoft Teams Rooms will only work in a properly configured Microsoft Teams or Skype for Business environment where the device accounts are set up correctly as described in [Deploy Microsoft Teams Rooms](rooms-deploy.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="568db-114">インストール メディアを準備する</span><span class="sxs-lookup"><span data-stu-id="568db-114">Prepare the installation media</span></span>
<span data-ttu-id="568db-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="568db-115"><a name="Prep_Media"> </a></span></span>

<span data-ttu-id="568db-116">Microsoft Teams Rooms のコンソール アプリをインストールするには、少なくとも 32GB の容量がある USB 記憶装置が必要です。</span><span class="sxs-lookup"><span data-stu-id="568db-116">Installing the Microsoft Teams Rooms console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="568db-117">このデバイスには他のファイルが存在しないようにする必要があります。この USB ストレージ上の既存のファイルはすべて失われます。</span><span class="sxs-lookup"><span data-stu-id="568db-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="568db-118">記載されている説明に従って Microsoft Teams Rooms のインストール メディアを作成しないと、予期しない動作が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="568db-118">Failure to create your Microsoft Teams Rooms installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="568db-119">次の手順で、新しい Microsoft Teams Rooms デバイスのイメージを作成するためにインストール メディアを作成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="568db-119">The process below is for creating installation media to image new Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="568db-120">既定では、既存のデバイスは Windows Update および Windows ストアから自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="568db-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="568db-121">Microsoft Teams Rooms のインストール メディアを作成するために使用する Windows 10 コンピューターは、ターゲット インストール メディアと同じか、それ以降のバージョンの Windows で動作している必要があります。</span><span class="sxs-lookup"><span data-stu-id="568db-121">The Windows 10 machine used to create the Microsoft Teams Rooms installation media must be on the same or later version of Windows as the target installation media.</span></span>
  
1. <span data-ttu-id="568db-122">[CreateSrsMedia.ps1 スクリプト](https://go.microsoft.com/fwlink/?linkid=867842)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="568db-122">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="568db-123">Windows 10 コンピューターの管理者特権でのプロンプトから CreateSrsMedia.ps1 スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="568db-123">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="568db-124">スクリプトの指示に従って、Microsoft Teams Rooms USB セットアップ ディスクを作成します。</span><span class="sxs-lookup"><span data-stu-id="568db-124">Follow the script's instructions to create a Microsoft Teams Rooms USB setup disk.</span></span>


> [!TIP]
> <span data-ttu-id="568db-125">CreateSrsMedia.ps1 が起動されるたびに、画面出力にはそのセッションのログ ファイル名かトランスクリプト名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="568db-125">Each time the CreateSrsMedia.ps1 script starts, the screen output will include the name of a log file or transcript for the session.</span></span> <span data-ttu-id="568db-126">スクリプトの実行で問題が発生した場合は、サポートを要求するときに、そのトランスクリプトのコピーを使用できるようにしておいてください。</span><span class="sxs-lookup"><span data-stu-id="568db-126">If there are issues with running the script, make sure to have a copy of that transcript available when requesting support.</span></span> 

<span data-ttu-id="568db-127">CreateSrsMedia.ps1 スクリプトを実行すると、次のタスクが自動化されます。</span><span class="sxs-lookup"><span data-stu-id="568db-127">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="568db-128">Microsoft Teams Rooms 用の最新の MSI インストーラーをダウンロードする。</span><span class="sxs-lookup"><span data-stu-id="568db-128">Download the latest MSI installer for Microsoft Teams Rooms.</span></span>
2. <span data-ttu-id="568db-129">ユーザーが提供する必要のある Windows のビルドを判別する。</span><span class="sxs-lookup"><span data-stu-id="568db-129">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="568db-130">最新のリリース版は、Microsoft Teams Rooms デバイスで使用するためのテストやサポートがなされていない場合があります。</span><span class="sxs-lookup"><span data-stu-id="568db-130">The most recently released versions may or may not be tested and supported for use with Microsoft Teams Rooms devices.</span></span>
3. <span data-ttu-id="568db-131">必要なサポート コンポーネントをダウンロードする。</span><span class="sxs-lookup"><span data-stu-id="568db-131">Download necessary supporting components.</span></span>
4. <span data-ttu-id="568db-132">必要なコンポーネントをインストール メディアにアセンブルする。</span><span class="sxs-lookup"><span data-stu-id="568db-132">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="568db-133">特定のバージョンの Windows 10 が必要です。このバージョンはボリューム ライセンスのお客様のみが利用できます。</span><span class="sxs-lookup"><span data-stu-id="568db-133">A specific version of Windows 10 is required, and this version is only available to volume licensing customers.</span></span>  <span data-ttu-id="568db-134">[ボリューム ライセンス サービス センター](https://www.microsoft.com/Licensing/servicecenter/)からコピーを入手できます。</span><span class="sxs-lookup"><span data-stu-id="568db-134">You can get a copy from the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).</span></span>

<span data-ttu-id="568db-135">完了したら、コンピューターから USB ディスクを削除し、「[Windows 10 と Microsoft Teams Roomsのコンソール アプリをインストールする](console.md#Reimage)」に進みます。</span><span class="sxs-lookup"><span data-stu-id="568db-135">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Microsoft Teams Rooms console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a><span data-ttu-id="568db-136">Windows 10 と Microsoft Teams Rooms コンソール アプリをインストールする</span><span class="sxs-lookup"><span data-stu-id="568db-136">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>
<span data-ttu-id="568db-137"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="568db-137"><a name="Reimage"> </a></span></span>

<span data-ttu-id="568db-138">ここで、作成したセットアップ メディアを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="568db-138">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="568db-139">ターゲット デバイスは、アプライアンスとして実行されます。既定のユーザーは Microsoft Teams Rooms コンソール アプリのみを実行するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="568db-139">The target device will run as an appliance and the default user will be set to only run the Microsoft Teams Rooms console app.</span></span>

1. <span data-ttu-id="568db-140">ターゲット デバイスがドック (Surface Pro など) にインストールされている場合は、ドックとの接続を解除します。</span><span class="sxs-lookup"><span data-stu-id="568db-140">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="568db-141">ターゲット デバイスがネットワークに接続されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="568db-141">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="568db-142">ターゲット デバイスが AC 電源に接続されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="568db-142">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="568db-143">USB セットアップ ディスクをターゲット デバイスに差し込みます。</span><span class="sxs-lookup"><span data-stu-id="568db-143">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="568db-144">USB セットアップ ディスクにブートします。</span><span class="sxs-lookup"><span data-stu-id="568db-144">Boot to the USB setup disk.</span></span> <span data-ttu-id="568db-145">製造元の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="568db-145">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="568db-146">ターゲット デバイスが Surface Pro の場合は、次の手順を使用して USB セットアップ ディスクにブートします。</span><span class="sxs-lookup"><span data-stu-id="568db-146">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="568db-147">a.</span><span class="sxs-lookup"><span data-stu-id="568db-147">a.</span></span> <span data-ttu-id="568db-148">ボリューム ダウン (-) ボタンを押したままにします。</span><span class="sxs-lookup"><span data-stu-id="568db-148">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="568db-149">b.</span><span class="sxs-lookup"><span data-stu-id="568db-149">b.</span></span> <span data-ttu-id="568db-150">電源ボタンを押して、離します。</span><span class="sxs-lookup"><span data-stu-id="568db-150">Press and release the power button.</span></span>

    <span data-ttu-id="568db-151">c.</span><span class="sxs-lookup"><span data-stu-id="568db-151">c.</span></span> <span data-ttu-id="568db-152">Windows セットアップが起動したら、ボリューム ダウン (-) ボタンを離します。</span><span class="sxs-lookup"><span data-stu-id="568db-152">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="568db-153">インストールが完了すると、システムがシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="568db-153">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="568db-154">システムがシャット ダウンしたら、USB セットアップ ディスクを安全に取り外すことができます。</span><span class="sxs-lookup"><span data-stu-id="568db-154">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="568db-155">これで、ターゲット デバイスをドックに設置して (ドックベースの製品を使用している場合)、会議室に必要な周辺機器を取り付け、ネットワークに接続することができます。</span><span class="sxs-lookup"><span data-stu-id="568db-155">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="568db-156">製造元の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="568db-156">Refer to the manufacturer instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="568db-157">Microsoft Teams Rooms のソフトウェア更新プログラムは、ビジネス向け Microsoft Store から自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="568db-157">Software updates for Microsoft Teams Rooms are automatically downloaded from the Microsoft Store for Business.</span></span> <span data-ttu-id="568db-158">会議室コンソールがストアにアクセスして自己更新できるかどうかを確認するには、「[ビジネスおよび教育機関向け Microsoft Store の前提条件](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="568db-158">See [Prerequisites for Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) to verify that the room console will be able to access the store and self-update.</span></span>  

### <a name="selecting-a-language"></a><span data-ttu-id="568db-159">言語の選択</span><span class="sxs-lookup"><span data-stu-id="568db-159">Selecting a language</span></span> 

<span data-ttu-id="568db-160">Creators Update では、暗黙的に言語を選択するとアプリケーションの言語がユーザーが希望する言語に設定されない場合 (フランス語でコンソール アプリを表示したいのに英語で表示される場合など)、ApplyCurrentRegionAndLanguage.ps1 スクリプトを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="568db-160">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="568db-161">次の手順は、Windows Creators Update を使用して作成されたコンソールにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="568db-161">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="568db-162">新しいプロビジョニング システムを使用するメディアを使用してセットアップされていないレガシ システムや現行のシステムでは次の手順は使用できません。ただし、この手動操作が必要となる最初の問題の影響を受けないようにする必要もあります (Anniversary Edition では、セットアップの一部としてアプリの言語を明示的に選択できます)。</span><span class="sxs-lookup"><span data-stu-id="568db-162">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="568db-163">必要な言語を適用するには</span><span class="sxs-lookup"><span data-stu-id="568db-163">To apply your desired language</span></span>

1. <span data-ttu-id="568db-164">管理モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="568db-164">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="568db-165">[スタート] メニューを選択します。</span><span class="sxs-lookup"><span data-stu-id="568db-165">Select the Start menu.</span></span>
    
3. <span data-ttu-id="568db-166">ギア アイコンを選択して [**設定**] アプリを起動します。</span><span class="sxs-lookup"><span data-stu-id="568db-166">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="568db-167">**[時刻 &amp; 言語]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="568db-167">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="568db-168">**[地域 &amp; 言語]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="568db-168">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="568db-169">[**言語の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="568db-169">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="568db-170">追加する言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="568db-170">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="568db-171">[言語] 一覧に追加した言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="568db-171">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="568db-172">[**既定に設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="568db-172">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="568db-173">削除する言語については、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="568db-173">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="568db-p115">a. 削除する言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="568db-p115">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="568db-p116">b. [**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="568db-p116">b. Select **Remove**.</span></span>
    
11. <span data-ttu-id="568db-178">管理者特権でコマンド プロンプトを開始します。</span><span class="sxs-lookup"><span data-stu-id="568db-178">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="568db-179">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="568db-179">Run the following command:</span></span> 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="568db-180">システムを再起動します。</span><span class="sxs-lookup"><span data-stu-id="568db-180">Restart the system.</span></span>
    
<span data-ttu-id="568db-181">これで、目的の言語が Microsoft Teams Rooms のコンソールに適用されます。</span><span class="sxs-lookup"><span data-stu-id="568db-181">Your desired language is now applied to the Microsoft Teams Rooms console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="568db-182">コンソールの初期設定</span><span class="sxs-lookup"><span data-stu-id="568db-182">Initial set up of the console</span></span>
<span data-ttu-id="568db-183"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="568db-183"><a name="Initial"> </a></span></span>

<span data-ttu-id="568db-184">Windows をインストールすると、次回 Microsoft Teams Rooms のコンソール アプリを起動するか、/reboot オプションが選択されていた場合、アプリの初期設定プロセスが実行されます。</span><span class="sxs-lookup"><span data-stu-id="568db-184">After Windows is installed, the Microsoft Teams Rooms console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="568db-185">[ユーザー アカウント] 画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="568db-185">The User Account screen appears.</span></span> <span data-ttu-id="568db-186">コンソールで使用される会議室アカウントの Skype サインイン アドレス ("ユーザー@ドメイン" 形式) を入力します。</span><span class="sxs-lookup"><span data-stu-id="568db-186">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="568db-187">会議室アカウントのパスワードを入力し、確認のためにもう一度入力します。</span><span class="sxs-lookup"><span data-stu-id="568db-187">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="568db-188">[Configure Domain](ドメインの設定) で、Skype for Business Server の FQDN を設定します。</span><span class="sxs-lookup"><span data-stu-id="568db-188">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="568db-189">Skype for Business SIP ドメインがユーザーの Exchange ドメインと異なる場合は、このフィールドに Exchange ドメインを入力します。</span><span class="sxs-lookup"><span data-stu-id="568db-189">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="568db-190">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="568db-190">Click **Next**.</span></span>
    
5. <span data-ttu-id="568db-191">[機能] 画面に表示されたデバイスを選択して、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="568db-191">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="568db-192">既定では、自動画面共有はオンで、会議名の非表示はオフになっています。</span><span class="sxs-lookup"><span data-stu-id="568db-192">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="568db-193">選択対象のデバイスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="568db-193">The devices to select are:</span></span>
    
   - <span data-ttu-id="568db-194">会議用のマイク: 会議室で使用する既定のマイク。</span><span class="sxs-lookup"><span data-stu-id="568db-194">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="568db-195">会議用のスピーカー: 会議で使用する既定のスピーカー。</span><span class="sxs-lookup"><span data-stu-id="568db-195">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="568db-196">既定のスピーカー: HDMI インジェストからのオーディオ用に使用されるスピーカー。</span><span class="sxs-lookup"><span data-stu-id="568db-196">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="568db-p120">それぞれの項目に、選択できるドロップダウン メニューのオプションがあります。各デバイスについて選択を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="568db-p120">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="568db-199">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="568db-199">Click **Finish**.</span></span>
    
<span data-ttu-id="568db-200">Microsoft Teams Rooms のコンソール アプリは、先ほど入力した資格情報を使用して Skype for Business Server へのサインインを直ちに開始し、同じ資格情報を使用して Exchange との予定表の同期も開始します。</span><span class="sxs-lookup"><span data-stu-id="568db-200">The Microsoft Teams Rooms console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="568db-201">コンソール アプリの使用方法の詳細については、「[Microsoft Teams Rooms のヘルプ](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="568db-201">For details on using the console app, refer to the [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="568db-202">Microsoft Teams Rooms には、認定されたコンソール ハードウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="568db-202">Microsoft Teams Rooms relies on the presence of certified console hardware.</span></span> <span data-ttu-id="568db-203">Microsoft Teams Rooms のコンソール アプリを含むイメージが正しく作成されていても、コンソール ハードウェアが検出されない限り、そのイメージは初期設定手順の後に起動しません。</span><span class="sxs-lookup"><span data-stu-id="568db-203">Even a correctly created image containing the Microsoft Teams Rooms console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="568db-204">Surface Pro ベースのソリューションの場合、このチェックが成功するには、Surface Pro と付属するドック ハードウェアが接続されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="568db-204">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="568db-205">ユーザーが英語以外の言語を使用する場合、タッチ キーボードでは記号がサポートされておらず、初期設定の際に物理キーボードをコンソールに接続することが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="568db-205">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="568db-206">コンソールにプライベート CA 証明書をインストールする</span><span class="sxs-lookup"><span data-stu-id="568db-206">Install a private CA certificate on the console</span></span>
<span data-ttu-id="568db-207"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="568db-207"><a name="Certs"> </a></span></span>

<span data-ttu-id="568db-208">Microsoft Teams Rooms のコンソールは、接続先のサーバーで使用されている証明書を信頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="568db-208">The Microsoft Teams Rooms console needs to trust the certificates used by the servers it connects to.</span></span> <span data-ttu-id="568db-209">O365 の場合、これらのサーバーでは公的証明機関が使用され、Windows 10 によって自動的に信頼されるため、この処理は自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="568db-209">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="568db-210">Active Directory や Windows 証明機関を使用したオンプレミス デプロイなど、民間の証明機関を使用する場合は、Microsoft Teams Rooms のコンソールに次の 2 つの方法で証明書を追加できます。</span><span class="sxs-lookup"><span data-stu-id="568db-210">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Microsoft Teams Rooms console in a couple of ways:</span></span>
  
- <span data-ttu-id="568db-211">証明機関が Active Directory に対して公開されている場合 (通常のデプロイ オプション)、コンソールを Active Directory に参加させると、必要な証明書は自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="568db-211">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="568db-212">イメージング プロセスの後で、証明書を手動でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="568db-212">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="568db-213">この操作を行う前に、[コンソールの初期設定](console.md#Initial)を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="568db-213">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="568db-214">証明書を手動でインストールするには </span><span class="sxs-lookup"><span data-stu-id="568db-214">To manually install the certificate</span></span>

1. <span data-ttu-id="568db-215">CA 証明書をお使いのコンピューターにダウンロードして、C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer に保存します。</span><span class="sxs-lookup"><span data-stu-id="568db-215">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="568db-216">コンソールを管理者モードにします (「[管理者モードとデバイス管理](rooms-operations.md#AdminMode)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="568db-216">Place the console in admin mode (see [Admin mode and device management](rooms-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="568db-217">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="568db-217">Run the following command:</span></span>
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="568db-218">Active Directory ドメインに参加する (オプション)</span><span class="sxs-lookup"><span data-stu-id="568db-218">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="568db-219"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="568db-219"><a name="Certs"> </a></span></span>

<span data-ttu-id="568db-220">Microsoft Teams Rooms のコンソールをドメインに参加させることができます。</span><span class="sxs-lookup"><span data-stu-id="568db-220">You can join Microsoft Teams Rooms consoles to your domain.</span></span> <span data-ttu-id="568db-221">Microsoft Teams Rooms のコンソールは、使用する PC ワークステーションとは別の OU に配置する必要があります。これは、多くのワークステーション ポリシーは Microsoft Teams Roomsと互換性がないためです。</span><span class="sxs-lookup"><span data-stu-id="568db-221">Microsoft Teams Rooms consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Microsoft Teams Rooms.</span></span> <span data-ttu-id="568db-222">たとえば、パスワードの強制ポリシーが設定されていると、Microsoft Teams Rooms は自動的に起動しなくなります。</span><span class="sxs-lookup"><span data-stu-id="568db-222">A common example are password enforcement policies that will prevent Microsoft Teams Rooms from starting up automatically.</span></span> <span data-ttu-id="568db-223">GPO 設定の管理の詳細については、「[Microsoft Teams Rooms の管理](rooms-operations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="568db-223">For information about the management of GPO settings, please refer to [Manage Microsoft Teams Rooms](rooms-operations.md).</span></span>
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a><span data-ttu-id="568db-224">Microsoft Teams Rooms をドメインに参加させるには</span><span class="sxs-lookup"><span data-stu-id="568db-224">To join Microsoft Teams Rooms to a domain</span></span>

1. <span data-ttu-id="568db-225">管理者アカウントからコンソールにサインインします (「[管理者モードとデバイス管理](rooms-operations.md#AdminMode)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="568db-225">Sign into the console from the admin account (see [Admin mode and device management](rooms-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="568db-226">管理者特権で Powershell コマンド プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="568db-226">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="568db-227">Powershell に次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="568db-227">Enter the following command in Powershell:</span></span>
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="568db-228">たとえば、完全修飾ドメインが redmond.corp.microsoft.com で、Microsoft Teams Rooms のコンソールを "Resources" OU の子である "Microsoft Teams Rooms" OU に配置する場合、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="568db-228">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Microsoft Teams Rooms consoles to be in a "Microsoft Teams Rooms" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="568db-229">ドメインに参加させるときにコンピューターの名前を変更する場合は、-NewName フラグを使用し、その後にコンピューターの新しい名前を続けます。</span><span class="sxs-lookup"><span data-stu-id="568db-229">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a><span data-ttu-id="568db-230">Microsoft Teams Rooms のデプロイ チェックリスト</span><span class="sxs-lookup"><span data-stu-id="568db-230">Microsoft Teams Rooms deployment checklist</span></span>
<span data-ttu-id="568db-231"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="568db-231"><a name="Checklist"> </a></span></span>

<span data-ttu-id="568db-232">コンソールとそのすべての周辺機器が完全に構成されていることを最終確認するときは、以下のチェックリストを使用します。</span><span class="sxs-lookup"><span data-stu-id="568db-232">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="568db-233">**アプリケーションの設定**</span><span class="sxs-lookup"><span data-stu-id="568db-233">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="568db-234">☐</span><span class="sxs-lookup"><span data-stu-id="568db-234">☐</span></span>  <br/> |<span data-ttu-id="568db-235">ルーム アカウント名と電話番号 (PSTN が有効な場合) が、コンソール画面の右上に正しく表示される</span><span class="sxs-lookup"><span data-stu-id="568db-235">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="568db-236">☐</span><span class="sxs-lookup"><span data-stu-id="568db-236">☐</span></span>  <br/> |<span data-ttu-id="568db-237">Windows コンピューター名が正しく設定されている (リモート管理に役立つ)</span><span class="sxs-lookup"><span data-stu-id="568db-237">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="568db-238">☐</span><span class="sxs-lookup"><span data-stu-id="568db-238">☐</span></span>  <br/> |<span data-ttu-id="568db-239">管理者アカウントのパスワードが設定されており、確認済みである</span><span class="sxs-lookup"><span data-stu-id="568db-239">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="568db-240">☐</span><span class="sxs-lookup"><span data-stu-id="568db-240">☐</span></span>  <br/> |<span data-ttu-id="568db-241">すべてのファームウェア更新プログラムが適用されている</span><span class="sxs-lookup"><span data-stu-id="568db-241">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="568db-242">**オーディオ/ビデオ周辺機器**</span><span class="sxs-lookup"><span data-stu-id="568db-242">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="568db-243">☐</span><span class="sxs-lookup"><span data-stu-id="568db-243">☐</span></span>  <br/> |<span data-ttu-id="568db-244">カメラ周辺機器のファームウェアのバージョンが正しい (該当する場合)</span><span class="sxs-lookup"><span data-stu-id="568db-244">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="568db-245">☐</span><span class="sxs-lookup"><span data-stu-id="568db-245">☐</span></span>  <br/> |<span data-ttu-id="568db-246">カメラが機能し、適切に配置されている</span><span class="sxs-lookup"><span data-stu-id="568db-246">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="568db-247">☐</span><span class="sxs-lookup"><span data-stu-id="568db-247">☐</span></span>  <br/> |<span data-ttu-id="568db-248">既定の再生デバイスと既定の再生通信デバイスの設定が、目的のオーディオ周辺機器に設定されている</span><span class="sxs-lookup"><span data-stu-id="568db-248">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="568db-249">☐</span><span class="sxs-lookup"><span data-stu-id="568db-249">☐</span></span>  <br/> |<span data-ttu-id="568db-250">既定の録音通信デバイスの設定が目的のオーディオ周辺機器に設定されている</span><span class="sxs-lookup"><span data-stu-id="568db-250">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="568db-251">☐</span><span class="sxs-lookup"><span data-stu-id="568db-251">☐</span></span>  <br/> |<span data-ttu-id="568db-252">オーディオ周辺機器のファームウェアのバージョンが正しい (該当する場合)</span><span class="sxs-lookup"><span data-stu-id="568db-252">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="568db-253">☐</span><span class="sxs-lookup"><span data-stu-id="568db-253">☐</span></span>  <br/> |<span data-ttu-id="568db-254">オーディオ入力デバイスが機能し、適切に配置されている</span><span class="sxs-lookup"><span data-stu-id="568db-254">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="568db-255">☐</span><span class="sxs-lookup"><span data-stu-id="568db-255">☐</span></span>  <br/> |<span data-ttu-id="568db-256">オーディオ出力デバイスが機能し、適切に配置されている</span><span class="sxs-lookup"><span data-stu-id="568db-256">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="568db-257">**ドック**</span><span class="sxs-lookup"><span data-stu-id="568db-257">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="568db-258">☐</span><span class="sxs-lookup"><span data-stu-id="568db-258">☐</span></span>  <br/> |<span data-ttu-id="568db-259">ケーブルが保護されており、圧迫されていない</span><span class="sxs-lookup"><span data-stu-id="568db-259">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="568db-260">☐</span><span class="sxs-lookup"><span data-stu-id="568db-260">☐</span></span>  <br/> |<span data-ttu-id="568db-261">HDMI を介したオーディオ インジェストが機能している</span><span class="sxs-lookup"><span data-stu-id="568db-261">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="568db-262">☐</span><span class="sxs-lookup"><span data-stu-id="568db-262">☐</span></span>  <br/> |<span data-ttu-id="568db-263">HDMI を介したビデオ インジェストが機能している</span><span class="sxs-lookup"><span data-stu-id="568db-263">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="568db-264">☐</span><span class="sxs-lookup"><span data-stu-id="568db-264">☐</span></span>  <br/> |<span data-ttu-id="568db-265">ドックは自由に回転することができる</span><span class="sxs-lookup"><span data-stu-id="568db-265">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="568db-266">☐</span><span class="sxs-lookup"><span data-stu-id="568db-266">☐</span></span>  <br/> |<span data-ttu-id="568db-267">表示の明るさが環境に適している</span><span class="sxs-lookup"><span data-stu-id="568db-267">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="568db-268">関連項目</span><span class="sxs-lookup"><span data-stu-id="568db-268">See also</span></span>
<span data-ttu-id="568db-269"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="568db-269"><a name="Checklist"> </a></span></span>

[<span data-ttu-id="568db-270">Microsoft Teams Rooms を計画する</span><span class="sxs-lookup"><span data-stu-id="568db-270">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="568db-271">Microsoft Teams Rooms をデプロイする</span><span class="sxs-lookup"><span data-stu-id="568db-271">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="568db-272">Microsoft Teams Rooms コンソールを構成する</span><span class="sxs-lookup"><span data-stu-id="568db-272">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="568db-273">Microsoft Teams Rooms を管理する</span><span class="sxs-lookup"><span data-stu-id="568db-273">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
