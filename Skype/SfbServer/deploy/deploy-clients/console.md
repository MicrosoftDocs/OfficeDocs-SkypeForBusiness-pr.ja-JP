---
title: Skype Room Systems バージョン 2 コンソールを構成する
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: この記事では、Skype Room Systems バージョン 2 コンソール デバイスとその周辺機器の設定方法を説明します。
ms.openlocfilehash: 6ca029fa7f5560dfdfebd789938d9b53ff2e9abc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-a-skype-room-systems-v2-console"></a><span data-ttu-id="e1cd8-103">Skype Room Systems バージョン 2 コンソールを構成する</span><span class="sxs-lookup"><span data-stu-id="e1cd8-103">Configure a Skype Room Systems v2 console</span></span>
 
<span data-ttu-id="e1cd8-104">この記事では、Skype Room Systems バージョン 2 コンソール デバイスとその周辺機器の設定方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-104">This article describes how to set up the Skype Room Systems v2 console device and its peripherals.</span></span>
  
<span data-ttu-id="e1cd8-105">ビジネスおよび Exchange アカウントに必要な Skype が既に作成して[Skype ルーム システムの配置のバージョン 2](room-systems-v2.md)で説明したようにテストする場合のみ、この手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-105">You should only perform these steps if the necessary Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> <span data-ttu-id="e1cd8-106">ハードウェアとソフトウェアの[Skype ルーム システム v2 の要件](../../plan-your-deployment/clients-and-devices/requirements.md)」に記載する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-106">You will need the hardware and software described in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span> <span data-ttu-id="e1cd8-107">このトピックには次のセクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="e1cd8-108">インストール イメージを準備する</span><span class="sxs-lookup"><span data-stu-id="e1cd8-108">Prepare the installation image</span></span>](console.md#Prep_Image)
    
- [<span data-ttu-id="e1cd8-109">タブレット デバイスにプライベート CA 証明書をインストールします。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-109">Install a private CA certificate on the tablet device</span></span>](console.md#Certs)
    
- [<span data-ttu-id="e1cd8-110">Windows 10 と Skype ルーム システム v2 のコンソール アプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-110">Install Windows 10 and the Skype Room Systems v2 console app </span></span>](console.md#Reimage)
   
- [<span data-ttu-id="e1cd8-111">コンソールの初期設定</span><span class="sxs-lookup"><span data-stu-id="e1cd8-111">Initial set up of the Console </span></span>](console.md#Initial)
    
- [<span data-ttu-id="e1cd8-112">Skype ルーム システム v2 の展開のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="e1cd8-112">Skype Room Systems v2 Deployment Checklist</span></span>](console.md#Checklist)
    
> [!NOTE]
> <span data-ttu-id="e1cd8-113">Skype ルーム システム v2 は、ビジネス環境をデバイスのアカウントが正しく設定されて[Skype ルーム システムの配置のバージョン 2](room-systems-v2.md)で説明したように正しく構成されている Skype でのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-113">Skype Room Systems v2 will only work in a properly configured Skype for Business environment where the device accounts are set up correctly as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> 
  
## <a name="prepare-the-installation-image"></a><span data-ttu-id="e1cd8-114">インストール イメージを準備する</span><span class="sxs-lookup"><span data-stu-id="e1cd8-114">Prepare the installation image</span></span>
<span data-ttu-id="e1cd8-115"><a name="Prep_Image"> </a></span><span class="sxs-lookup"><span data-stu-id="e1cd8-115"></span></span>

<span data-ttu-id="e1cd8-116">Surface Pro 4 または Surface Pro の Skype ルーム システム v2 のアプリケーションをインストールするには、FAT32 ディスクとしてフォーマットされたメモリの 32 GB 以上の USB ストレージ デバイスが必要です。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-116">Installing the Skype Room Systems v2 app on a Surface Pro 4 or Surface Pro requires a USB storage device with at least 32GB of memory formatted as a FAT32 disk.</span></span> <span data-ttu-id="e1cd8-117">存在しないはずの他のデバイス上のファイルは、USB 記憶装置上の既存のファイルはすべて失われます。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-117">There should be no other files on the device, any existing files on the USB storage will be lost.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e1cd8-118">次の手順に従ってコンソール イメージを作成しないと、予期しない動作が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-118">Failure to create your console image according to these instructions will likely result in unexpected behavior.</span></span> <span data-ttu-id="e1cd8-119">Skype ルーム システム v2 のイメージの作成については、Windows 10 企業記念日の更新プログラム (バージョン 1607) がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-119">Windows 10 Enterprise Anniversary Update (Version 1607) is no longer supported for Skype Room Systems v2 image creation.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e1cd8-120">Windows 10 企業記念日を更新、Windows ストアを使用して Skype ルーム システム v2 更新 3 への移動で既存の Skype ルーム システム v2 機能しますが、次のように、新規インストールを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-120">An existing Skype Room Systems v2 with Windows 10 Enterprise Anniversary Update moving to Skype Room Systems v2 update 3 by way of the Windows Store will work, but a new installation should be done as described below.</span></span> 
  
1. <span data-ttu-id="e1cd8-121">[MSU](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-121">Download the [MSU for KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu).</span></span>
2. <span data-ttu-id="e1cd8-122">[CreateSrsMedia.ps1 スクリプト](https://go.microsoft.com/fwlink/?linkid=867842)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-122">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
3. <span data-ttu-id="e1cd8-123">MSU を KB4056892 の CreateSrsMedia.ps1 スクリプトと同じディレクトリに配置します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-123">Place the MSU for KB4056892 in the same directory as the CreateSrsMedia.ps1 script.</span></span>
4. <span data-ttu-id="e1cd8-124">10 の Windows コンピューターで管理者特権のプロンプトから CreateSrsMedia.ps1 スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-124">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>


<span data-ttu-id="e1cd8-125">Skype ルーム システム v2 の USB セットアップ ディスクを作成するスクリプトの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-125">Follow the script's instructions to create a Skype Room Systems v2 USB setup disk.</span></span> <span data-ttu-id="e1cd8-126">完了したら、USB ディスクをコンピューターから削除し、 [Windows の 10 をインストール](console.md#Reimage)して Skype ルーム システム v2 のコンソール アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-126">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Skype Room Systems v2 console app ](console.md#Reimage).</span></span>
    
## <a name="install-windows-10-and-the-skype-room-systems-v2-console-app"></a><span data-ttu-id="e1cd8-127">Windows 10 と Skype Room Systems バージョン 2 コンソール アプリをインストールする </span><span class="sxs-lookup"><span data-stu-id="e1cd8-127">Install Windows 10 and the Skype Room Systems v2 console app</span></span>
<span data-ttu-id="e1cd8-128"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="e1cd8-128"></span></span>

<span data-ttu-id="e1cd8-129">次に、作成したイメージを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-129">You now need to apply the image you've created.</span></span> <span data-ttu-id="e1cd8-130">タブレットは、アプライアンスとして実行され、Skype ルーム システム v2 アプリケーションのみを実行するのには既定のユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-130">The tablet will run as an appliance and the default user will be set to only run the Skype Room Systems v2 app.</span></span> 
  
1. <span data-ttu-id="e1cd8-131">タブレットを電源に接続します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-131">The tablet should be connected to a power source.</span></span> <span data-ttu-id="e1cd8-132">完全に電源オフの状態から開始します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-132">Start from a completely powered-off state.</span></span> <span data-ttu-id="e1cd8-133">必要に応じて、タブレットの電源が切れるまで、電源ボタンを押したままにします。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-133">If necessary, press and keep pressing the Power button until the tablet switches off.</span></span>
    
2. <span data-ttu-id="e1cd8-134">USB セットアップ ディスクをタブレットに取り付けます。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-134">Plug your USB Setup disk into the tablet.</span></span>
    
3. <span data-ttu-id="e1cd8-135">タブレットのボリューム ダウン (-) ボタンを押したままにします。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-135">Press and continue to hold the volume down (-) button on the tablet.</span></span> 
    
4. <span data-ttu-id="e1cd8-136">タブレットの電源ボタンを押して、離します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-136">Press and release the power button on the tablet.</span></span>
    
5. <span data-ttu-id="e1cd8-137">Windows セットアップが起動したら、ボリューム ダウン (-) ボタンを離します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-137">Once Windows setup is booted, release the volume down (-) button.</span></span>
    
6. <span data-ttu-id="e1cd8-138">Skype ルーム システム v2 デバイス起動すると、最初の動作によって異なります AutoUnattend.xml ファイルのどのバージョンの Sysprep.exe を使用 ([インストール イメージの準備](console.md#Prep_Image)の手順 7 を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-138">When the Skype Room Systems v2 device starts for the first time, its behavior will depend on which version of Sysprep.exe is used in the AutoUnattend.xml file (see step 7 of [Prepare the installation image](console.md#Prep_Image)):</span></span>
    
   - <span data-ttu-id="e1cd8-p107">コマンドの /shutdown バージョンを有効にした場合、システムはインストールを続行し、最終的にシャットダウンします。シャットダウン後に、Windows PE を含む外部メディアにブートし、DISM を使用して、言語パックのインストール、イメージの適用、マシンからの参照イメージのキャプチャ、またはその他の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-p107">If the /shutdown version of the command was enabled, the system will proceed with installation and eventually shut down. Once it is shut down, you may boot to external media containing Windows PE and use DISM to install language packs, apply images, capture your reference image from the machine, or perform other actions.</span></span>
    
   - <span data-ttu-id="e1cd8-141">コマンドの /reboot バージョンを有効にした場合、システムはインストールを続行し、ロケール設定を選択するようにユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-141">If the /reboot version of the command was enabled, the system will proceed with installation, and eventually ask the user to select their locale settings.</span></span> <span data-ttu-id="e1cd8-142">このオプションを選択後、Skype ルーム システムのバージョン 2 のデバイスの最初の起動時に起動します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-142">After making this selection, the Skype Room Systems v2 device will boot into its initial startup process.</span></span> <span data-ttu-id="e1cd8-143">「[コンソールの初期設定](console.md#Initial)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-143">See [Initial set up of the Console ](console.md#Initial)</span></span>
    
<span data-ttu-id="e1cd8-144">システムをシャット ダウンまたは再起動した後に、USB セットアップ ディスクを安全に取り外すことができます。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-144">After the system has shut down or rebooted, it is safe to remove the USB Setup Disk.</span></span> <span data-ttu-id="e1cd8-145">この段階で、タブレットをドックに設置し、お使いの会議室に必要な周辺機器を接続できます。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-145">At this point, you can place the tablet in the dock and attach the peripherals needed for your meeting room.</span></span> <span data-ttu-id="e1cd8-146">製造元の指示を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-146">Refer to the manufacturer instructions.</span></span>
  
 
### <a name="selecting-a-language-in-creators-update"></a><span data-ttu-id="e1cd8-147">Creators Update での言語の選択</span><span class="sxs-lookup"><span data-stu-id="e1cd8-147">Selecting a language in Creator's Update</span></span>

<span data-ttu-id="e1cd8-148">作成者の更新では、暗黙の言語の選択が必要な実際のアプリケーションの言語を使用してユーザーを提供しないシナリオで ApplyCurrentRegionAndLanguage.ps1 スクリプトを使用する必要があります (など、フランス語で発生するようにアプリケーションが欲しいが、次の英語で)。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-148">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e1cd8-149">次の操作指示は、Windows Creators Update を使用して作成されたデバイスに対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-149">The following instructions work only for devices created using Windows Creator's Update.</span></span> <span data-ttu-id="e1cd8-150">新しいプロビジョニング システムに対して適切に再イメージングされていないレガシー/販売中のシステムは、これらの操作指示を利用できませんが、手動での介入を必要とする最初の問題からは損害を受けます (Anniversary Edition では、セットアップの一部としてアプリの言語を明示的に選ぶことができます)。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-150">Legacy/in-market systems that have not been re-imaged properly to the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span> 
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="e1cd8-151">必要な言語を適用するには</span><span class="sxs-lookup"><span data-stu-id="e1cd8-151">To apply your desired language</span></span>

1. <span data-ttu-id="e1cd8-152">管理モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-152">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="e1cd8-153">[スタート] メニューを選択します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-153">Select the Start menu.</span></span>
    
3. <span data-ttu-id="e1cd8-154">ギア アイコンを選択して [**設定**] アプリを起動します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-154">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="e1cd8-155">選択**時間&amp;言語**です。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-155">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="e1cd8-156">選択**地域&amp;言語**です。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-156">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="e1cd8-157">[**言語の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-157">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="e1cd8-158">追加する言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-158">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="e1cd8-159">[言語] ボックスの一覧に追加した言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-159">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="e1cd8-160">[**既定に設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-160">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="e1cd8-161">削除する言語については、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-161">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="e1cd8-162">a.</span><span class="sxs-lookup"><span data-stu-id="e1cd8-162">a.</span></span> <span data-ttu-id="e1cd8-163">削除する言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-163">Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="e1cd8-164">b.</span><span class="sxs-lookup"><span data-stu-id="e1cd8-164">b.</span></span> <span data-ttu-id="e1cd8-165">[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-165">Select **Remove**.</span></span>
    
11. <span data-ttu-id="e1cd8-166">管理者特権でコマンド プロンプトを開始します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-166">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="e1cd8-167">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-167">Run the following command:</span></span> 
    
    <span data-ttu-id="e1cd8-168">powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1</span><span class="sxs-lookup"><span data-stu-id="e1cd8-168">powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1</span></span>
    
13. <span data-ttu-id="e1cd8-169">システムを再起動します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-169">Restart the system.</span></span>
    
<span data-ttu-id="e1cd8-170">Skype ルーム システムのバージョン 2 のデバイスに、目的の言語が適用されます。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-170">Your desired language is now applied to the Skype Room Systems v2 device.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="e1cd8-171">コンソールの初期設定 </span><span class="sxs-lookup"><span data-stu-id="e1cd8-171">Initial set up of the Console</span></span>
<span data-ttu-id="e1cd8-172"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="e1cd8-172"></span></span>

<span data-ttu-id="e1cd8-173">Windows をインストールすると、Skype ルーム システム v2 アプリケーションが次回起動したとき、または、/reboot オプションが選択された場合の初期のセットアップ プロセスに移動します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-173">After Windows is installed, the Skype Room Systems v2 app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="e1cd8-p113">[ユーザー アカウント] 画面が表示されます。デバイスで使用するルーム アカウントの Skype サインイン アドレス (ユーザー@ドメイン形式) を入力します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-p113">The User Account screen appears. Enter the Skype sign-in address (in user@domain format) of the room account to be used with the device.</span></span>
    
2. <span data-ttu-id="e1cd8-176">ルーム アカウントのパスワードを入力し、確認のためにもう一度入力します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-176">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="e1cd8-177">"ドメインの構成] の下で、Skype のビジネス サーバーの FQDN を設定します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-177">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="e1cd8-178">ビジネスの SIP ドメインの Skype ユーザーの Exchange ドメインと異なる場合は、このフィールドに、Exchange ドメインを入力します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-178">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="e1cd8-179">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-179">Click **Next**.</span></span>
    
5. <span data-ttu-id="e1cd8-180">[機能] 画面で指定されたデバイスを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-180">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="e1cd8-181">既定では、自動画面共有はオンで、会議名の非表示はオフになっています。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-181">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="e1cd8-182">選択対象のデバイスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-182">The devices to select are:</span></span>
    
   - <span data-ttu-id="e1cd8-183">会議用のマイク: 会議室で使用する既定のマイク。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-183">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="e1cd8-184">会議用のスピーカー: 会議で使用する既定のスピーカー。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-184">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="e1cd8-185">既定のスピーカー: HDMI インジェストからのオーディオ用に使用されるスピーカー。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-185">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
    <span data-ttu-id="e1cd8-p116">それぞれの項目に、選択できるドロップダウン メニューのオプションがあります。各デバイスについて選択を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-p116">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="e1cd8-188">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-188">Click **Finish**.</span></span>
    
<span data-ttu-id="e1cd8-189">アプリケーションはビジネス サーバー 2015 の上で入力した資格情報を持つ Skype にサインインします。 すぐに開始する必要がありでこれらの同じ資格情報を使用して Exchange の予定表の同期を開始する必要がありますも。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-189">The app should immediately start signing in to Skype for Business Server 2015 with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="e1cd8-190">アプリケーションの使用方法の詳細については、 [Skype ルーム システム バージョン 2 のヘルプ](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-190">For details on using the app, refer to the [Skype Room Systems version 2 help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e1cd8-191">Skype ルーム システム v2 では、認定されたコンソールのハードウェア (logitech (ロジクール) SmartDock) の存在に依存しています。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-191">Skype Room Systems v2 relies on the presence of certified console hardware (the Logitech SmartDock).</span></span> <span data-ttu-id="e1cd8-192">Surface Pro 4 または Surface Pro に読み込まれている Skype ルーム システム v2 のアプリケーションが含まれている正常に作成されたイメージはコンソールのハードウェアが検出された場合を除き、過去の初期セットアップ手順は起動しません。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-192">Even a correctly created image containing the Skype Room Systems v2 app loaded on a Surface Pro 4 or Surface Pro will not boot past the initial setup procedure unless the console hardware is detected.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e1cd8-193">英語以外の一部の言語のユーザーは、記号がタッチ キーボードでサポートされない場合に、コンソールに接続した物理的なキーボードが初期設定において必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-193">Some non-English language users may need a physical keyboard connected to the Console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span> 
  
### <a name="install-a-private-ca-certificate-on-the-tablet-device"></a><span data-ttu-id="e1cd8-194">タブレット デバイスにプライベート CA 証明書をインストールする</span><span class="sxs-lookup"><span data-stu-id="e1cd8-194">Install a private CA certificate on the tablet device</span></span>
<span data-ttu-id="e1cd8-195"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="e1cd8-195"></span></span>

<span data-ttu-id="e1cd8-196">Skype ルーム システムのバージョン 2 のデバイスは、ビジネスおよび Exchange のサーバーに接続するため、Skype で使用する証明書を信頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-196">The Skype Room Systems v2 device needs to trust the certificates used by the Skype for Business and Exchange servers it connects to.</span></span> <span data-ttu-id="e1cd8-197">O365 の場合、これらのサーバーはパブリックの証明機関を使用し、これらは Windows 10 で自動的に信頼されるため、この処理は自動的に行われます。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-197">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="e1cd8-198">証明機関がプライベートの場合は Active Directory および Windows の証明機関と設置型展開の 2 とおりの方法で Skype ルーム システム v2 デバイスに証明書を追加できます。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-198">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Skype Room Systems v2 device in a couple of ways:</span></span>
  
- <span data-ttu-id="e1cd8-199">証明機関が Active Directory に対して公開されていることを前提とした場合 (通常の展開オプション)、デバイスを Active Directory に参加させると、必要な証明書は自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-199">You can join the device to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="e1cd8-p120">イメージング処理の後に証明書を手動でインストールすることができます。この操作を行う前に、[コンソールの初期設定](console.md#Initial)を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-p120">You can install the certificate manually after the imaging process. Before you do this, you must complete [Initial set up of the Console ](console.md#Initial).</span></span> 
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="e1cd8-202">証明書を手動でインストールするには </span><span class="sxs-lookup"><span data-stu-id="e1cd8-202">To manually install the certificate</span></span>

1. <span data-ttu-id="e1cd8-203">CA 証明書をお使いのコンピューターにダウンロードして、C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer に保存します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-203">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="e1cd8-204">管理者モードでサーフェスの 4 を配置する ([管理者モードとデバイスの管理](../../manage/skype-room-systems-v2/skype-room-systems-v2.md#AdminMode)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-204">Place the Surface 4 in admin mode (see [Admin mode and device management](../../manage/skype-room-systems-v2/skype-room-systems-v2.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="e1cd8-205">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-205">Run the following command:</span></span>
    
  ```
  certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
  ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="e1cd8-206">Active Directory のドメインに参加します (オプション)</span><span class="sxs-lookup"><span data-stu-id="e1cd8-206">Join an Active Directory Domain (Optional)</span></span>
<span data-ttu-id="e1cd8-207"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="e1cd8-207"></span></span>

<span data-ttu-id="e1cd8-208">Skype ルーム システム v2 のデバイスは、ドメインに参加できます。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-208">You can join Skype Room Systems v2 devices to your domain.</span></span> <span data-ttu-id="e1cd8-209">Skype ルーム システム v2 のデバイスは、多くのワークステーションのポリシーは Skype ルーム システム v2 と互換性がないため PC ワークステーションから別の OU に配置してください。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-209">Skype Room Systems v2 devices should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Skype Room Systems v2.</span></span> <span data-ttu-id="e1cd8-210">一般的な例は、パスワードの強制ポリシー Skype ルーム システム v2 が自動的に起動できなくなります。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-210">A common example are password enforcement policies that will prevent Skype Room Systems v2 from starting up automatically.</span></span> <span data-ttu-id="e1cd8-211">GPO の設定の管理方法については、 [Skype ルームの管理のシステムのバージョン 2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-211">For information about the management of GPO settings, please refer to [Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span></span> 
  
### <a name="to-join-skype-room-system-v2-to-a-domain"></a><span data-ttu-id="e1cd8-212">Skype Room System バージョン 2 をドメインに参加させるには</span><span class="sxs-lookup"><span data-stu-id="e1cd8-212">To join Skype Room System v2 to a domain</span></span>

1. <span data-ttu-id="e1cd8-213">では、管理コンソールに記号 ([管理者モードとデバイスの管理](../../manage/skype-room-systems-v2/skype-room-systems-v2.md#AdminMode)を参照してください) を考慮します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-213">Sign into the console from the admin account (see [Admin mode and device management](../../manage/skype-room-systems-v2/skype-room-systems-v2.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="e1cd8-214">管理者特権で Powershell コマンド プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-214">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="e1cd8-215">Powershell に次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-215">Enter the following command in Powershell:</span></span>
    
  ```
  Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
  ```

<span data-ttu-id="e1cd8-216">たとえば、完全修飾ドメイン redmond.corp.microsoft.com は、「Skype ルーム システム v2」で、Skype ルーム システム v2 のデバイスが必要な場合は、リソース OU の子 OU の場合は、コマンドになります。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-216">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Skype Room Systems v2 devices to be in a "Skype Room Systems v2" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Skype_Room_System,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="e1cd8-217">ドメインに参加させるときに、コンピューターの名前を変更したい場合は、コンピューターの新しい名前の後に、新しい名前のフラグを使用します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-217">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="skype-room-systems-v2-deployment-checklist"></a><span data-ttu-id="e1cd8-218">Skype Room System バージョン 2 の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="e1cd8-218">Skype Room Systems v2 Deployment Checklist</span></span>
<span data-ttu-id="e1cd8-219"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="e1cd8-219"></span></span>

<span data-ttu-id="e1cd8-220">コンソール デバイスとそのすべての周辺機器が完全に構成されていることを最終確認するときは、以下のチェックリストを使用します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-220">Use the following checklist while doing a final verification that the console device and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="e1cd8-221">**アプリケーションの設定**</span><span class="sxs-lookup"><span data-stu-id="e1cd8-221">**Application Settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e1cd8-222">☐</span><span class="sxs-lookup"><span data-stu-id="e1cd8-222">☐</span></span>  <br/> |<span data-ttu-id="e1cd8-223">ルーム アカウント名と電話番号 (PSTN が有効な場合) が、コンソール画面の右上に正しく表示される</span><span class="sxs-lookup"><span data-stu-id="e1cd8-223">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="e1cd8-224">☐</span><span class="sxs-lookup"><span data-stu-id="e1cd8-224">☐</span></span>  <br/> |<span data-ttu-id="e1cd8-225">Windows コンピューター名が正しく設定されている (リモート管理に役立つ)</span><span class="sxs-lookup"><span data-stu-id="e1cd8-225">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="e1cd8-226">☐</span><span class="sxs-lookup"><span data-stu-id="e1cd8-226">☐</span></span>  <br/> |<span data-ttu-id="e1cd8-227">管理者アカウントのパスワードが設定されており、確認済みである</span><span class="sxs-lookup"><span data-stu-id="e1cd8-227">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="e1cd8-228">☐</span><span class="sxs-lookup"><span data-stu-id="e1cd8-228">☐</span></span>  <br/> |<span data-ttu-id="e1cd8-229">Surface Pro 4 または Surface Pro のすべてのシステム アップデートが適用済みである</span><span class="sxs-lookup"><span data-stu-id="e1cd8-229">All Surface Pro 4 or Surface Pro System Updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="e1cd8-230">**オーディオ/ビデオ周辺機器**</span><span class="sxs-lookup"><span data-stu-id="e1cd8-230">**Audio/Video Peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e1cd8-231">☐</span><span class="sxs-lookup"><span data-stu-id="e1cd8-231">☐</span></span>  <br/> |<span data-ttu-id="e1cd8-232">カメラ周辺機器のファームウェアのバージョンが正しい (該当する場合)</span><span class="sxs-lookup"><span data-stu-id="e1cd8-232">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="e1cd8-233">☐</span><span class="sxs-lookup"><span data-stu-id="e1cd8-233">☐</span></span>  <br/> |<span data-ttu-id="e1cd8-234">カメラの機能と、最適な位置を指定しました。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-234">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="e1cd8-235">☐</span><span class="sxs-lookup"><span data-stu-id="e1cd8-235">☐</span></span>  <br/> |<span data-ttu-id="e1cd8-236">既定の再生デバイスと既定の再生通信デバイスの設定が、目的のオーディオ周辺機器に設定されている</span><span class="sxs-lookup"><span data-stu-id="e1cd8-236">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="e1cd8-237">☐</span><span class="sxs-lookup"><span data-stu-id="e1cd8-237">☐</span></span>  <br/> |<span data-ttu-id="e1cd8-238">既定の録音通信デバイスの設定が目的のオーディオ周辺機器に設定されている</span><span class="sxs-lookup"><span data-stu-id="e1cd8-238">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="e1cd8-239">☐</span><span class="sxs-lookup"><span data-stu-id="e1cd8-239">☐</span></span>  <br/> |<span data-ttu-id="e1cd8-240">オーディオ周辺機器のファームウェアのバージョンが正しい (該当する場合)</span><span class="sxs-lookup"><span data-stu-id="e1cd8-240">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="e1cd8-241">☐</span><span class="sxs-lookup"><span data-stu-id="e1cd8-241">☐</span></span>  <br/> |<span data-ttu-id="e1cd8-242">オーディオ入力デバイスが機能し、適切に配置されている</span><span class="sxs-lookup"><span data-stu-id="e1cd8-242">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="e1cd8-243">☐</span><span class="sxs-lookup"><span data-stu-id="e1cd8-243">☐</span></span>  <br/> |<span data-ttu-id="e1cd8-244">オーディオ出力デバイスが機能し、適切に配置されている</span><span class="sxs-lookup"><span data-stu-id="e1cd8-244">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="e1cd8-245">**ドッキング ステーション**</span><span class="sxs-lookup"><span data-stu-id="e1cd8-245">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e1cd8-246">☐</span><span class="sxs-lookup"><span data-stu-id="e1cd8-246">☐</span></span>  <br/> |<span data-ttu-id="e1cd8-247">ケーブルが保護されており、圧迫されていない</span><span class="sxs-lookup"><span data-stu-id="e1cd8-247">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="e1cd8-248">☐</span><span class="sxs-lookup"><span data-stu-id="e1cd8-248">☐</span></span>  <br/> |<span data-ttu-id="e1cd8-249">HDMI を介したオーディオ インジェストが機能している</span><span class="sxs-lookup"><span data-stu-id="e1cd8-249">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="e1cd8-250">☐</span><span class="sxs-lookup"><span data-stu-id="e1cd8-250">☐</span></span>  <br/> |<span data-ttu-id="e1cd8-251">HDMI を介したビデオ インジェストが機能している</span><span class="sxs-lookup"><span data-stu-id="e1cd8-251">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="e1cd8-252">☐</span><span class="sxs-lookup"><span data-stu-id="e1cd8-252">☐</span></span>  <br/> |<span data-ttu-id="e1cd8-253">ドックは自由に回転することができる</span><span class="sxs-lookup"><span data-stu-id="e1cd8-253">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="e1cd8-254">☐</span><span class="sxs-lookup"><span data-stu-id="e1cd8-254">☐</span></span>  <br/> |<span data-ttu-id="e1cd8-255">表示の明るさが環境に適している</span><span class="sxs-lookup"><span data-stu-id="e1cd8-255">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="e1cd8-256">この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-256">See also</span></span>
<span data-ttu-id="e1cd8-257"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="e1cd8-257"></span></span>

#### 

[<span data-ttu-id="e1cd8-258">Skype ルームの計画システム v2</span><span class="sxs-lookup"><span data-stu-id="e1cd8-258">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="e1cd8-259">Skype の部屋を配置するシステム v2</span><span class="sxs-lookup"><span data-stu-id="e1cd8-259">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="e1cd8-260">Skype ルーム システム v2 のコンソールを構成します。</span><span class="sxs-lookup"><span data-stu-id="e1cd8-260">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="e1cd8-261">Skype ルームの管理システム v2</span><span class="sxs-lookup"><span data-stu-id="e1cd8-261">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

