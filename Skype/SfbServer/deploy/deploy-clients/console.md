---
title: マイクロソフト チームの会議室のコンソールを構成します。
ms.author: jambirk
author: jambirk
ms.reviewer: Travis-Snoozy
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: この資料では、マイクロソフト チームの会議室のコンソールとその周辺機器を設定する方法について説明します。
ms.openlocfilehash: 9027057314d405788e81d4d27f9ce4e5d5649a48
ms.sourcegitcommit: a505869a3cc2fe6fe4ee18bcbe99bf980aa91a86
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "31520156"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a><span data-ttu-id="f18fe-103">マイクロソフト チームの会議室のコンソールを構成します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-103">Configure a Microsoft Teams Rooms console</span></span>

<span data-ttu-id="f18fe-104">この資料では、マイクロソフト チームの会議室のコンソールとその周辺機器を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-104">This article describes how to set up the Microsoft Teams Rooms console and its peripherals.</span></span>
  
<span data-ttu-id="f18fe-105">ビジネスおよび Exchange アカウントに必要な Skype が既に作成して[Microsoft チームの部屋の配置](room-systems-v2.md)で説明したようにテストする場合のみ、この手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f18fe-105">You should only perform these steps if the necessary Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Microsoft Teams Rooms](room-systems-v2.md).</span></span> <span data-ttu-id="f18fe-106">ハードウェアとソフトウェアが[マイクロソフト チームの会議室の要件](../../plan-your-deployment/clients-and-devices/requirements.md)」に記載する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f18fe-106">You will need the hardware and software described in [Microsoft Teams Rooms requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span> <span data-ttu-id="f18fe-107">このトピックには次のセクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f18fe-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="f18fe-108">インストール メディアを準備します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-108">Prepare the installation media</span></span>](console.md#Prep_Media)
- [<span data-ttu-id="f18fe-109">コンソールにプライベート CA 証明書をインストールします。</span><span class="sxs-lookup"><span data-stu-id="f18fe-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
- [<span data-ttu-id="f18fe-110">10 の Windows とマイクロソフトのチームの会議室のコンソール アプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f18fe-110">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>](console.md#Reimage)
- [<span data-ttu-id="f18fe-111">コンソールの初期設定</span><span class="sxs-lookup"><span data-stu-id="f18fe-111">Initial set up of the console</span></span>](console.md#Initial)
- [<span data-ttu-id="f18fe-112">マイクロソフト チームの会議室の展開のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="f18fe-112">Microsoft Teams Rooms deployment checklist</span></span>](console.md#Checklist)

> [!NOTE]
> <span data-ttu-id="f18fe-113">マイクロソフト チームの会議室は、ビジネス環境をデバイスのアカウントが正しく設定されて[マイクロソフト チーム ルームの展開](room-systems-v2.md)で説明したように正しく構成されている Skype でのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-113">Microsoft Teams Rooms will only work in a properly configured Skype for Business environment where the device accounts are set up correctly as described in [Deploy Microsoft Teams Rooms](room-systems-v2.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="f18fe-114">インストール メディアを準備します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-114">Prepare the installation media</span></span>
<span data-ttu-id="f18fe-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="f18fe-115"></span></span>

<span data-ttu-id="f18fe-116">マイクロソフト チームの会議室のコンソール アプリケーションをインストールするには、32 GB 以上の容量を持つ USB ストレージ デバイスが必要です。</span><span class="sxs-lookup"><span data-stu-id="f18fe-116">Installing the Microsoft Teams Rooms console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="f18fe-117">存在しないはずのデバイス上のファイルUSB 記憶装置上の既存のファイルはすべて失われます。</span><span class="sxs-lookup"><span data-stu-id="f18fe-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f18fe-118">予期しない動作になる可能性があります次の手順に従って、マイクロソフト チームの会議室のインストール メディアを作成するに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="f18fe-118">Failure to create your Microsoft Teams Rooms installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="f18fe-119">以下の手順は、イメージの新しいマイクロソフト チームの会議室のデバイスにインストール メディアを作成するためです。</span><span class="sxs-lookup"><span data-stu-id="f18fe-119">The process below is for creating installation media to image new Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="f18fe-120">既存のデバイスでは、既定では、自動的に更新 Windows を更新し、Windows ストアから。</span><span class="sxs-lookup"><span data-stu-id="f18fe-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>
  
1. <span data-ttu-id="f18fe-121">[CreateSrsMedia.ps1 スクリプト](https://go.microsoft.com/fwlink/?linkid=867842)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f18fe-121">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="f18fe-122">Windows 10 マシン上で管理者特権でのプロンプトから CreateSrsMedia.ps1 スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-122">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="f18fe-123">マイクロソフト チームの会議室の USB セットアップ ディスクを作成するスクリプトの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="f18fe-123">Follow the script's instructions to create a Microsoft Teams Rooms USB setup disk.</span></span>


> [!TIP]
> <span data-ttu-id="f18fe-124">CreateSrsMedia.ps1 スクリプトが起動するたびに画面の出力は、セッションのトラン スクリプトのログ ファイルの名前を含まれます。</span><span class="sxs-lookup"><span data-stu-id="f18fe-124">Each time the CreateSrsMedia.ps1 script starts, the screen output will include the name of a log file or transcript for the session.</span></span> <span data-ttu-id="f18fe-125">スクリプトを実行して問題がある場合は、サポートを要求するときのトラン スクリプトを利用可能なコピーを持つことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f18fe-125">If there are issues with running the script, make sure to have a copy of that transcript available when requesting support.</span></span> 

<span data-ttu-id="f18fe-126">CreateSrsMedia.ps1 スクリプトは、次のタスクを自動化します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-126">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="f18fe-127">マイクロソフト チームの会議室の最新の MSI インストーラーをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f18fe-127">Download the latest MSI installer for Microsoft Teams Rooms.</span></span>
2. <span data-ttu-id="f18fe-128">ユーザーを指定する必要があります Windows のビルドを決定します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-128">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="f18fe-129">最も最近リリースされたバージョン可能性がありますまたは可能性がありますいないテストしてマイクロソフト チームの会議室のデバイスでの使用をサポートしました。</span><span class="sxs-lookup"><span data-stu-id="f18fe-129">The most recently released versions may or may not be tested and supported for use with Microsoft Teams Rooms devices.</span></span>
3. <span data-ttu-id="f18fe-130">サポートするために必要なコンポーネントをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f18fe-130">Download necessary supporting components.</span></span>
4. <span data-ttu-id="f18fe-131">インストール メディアに必要なコンポーネントをアセンブルします。</span><span class="sxs-lookup"><span data-stu-id="f18fe-131">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="f18fe-132">Windows 10 の特定のバージョンが必要なと、このバージョンは、ボリューム ライセンスのお客様に利用可能なだけです。</span><span class="sxs-lookup"><span data-stu-id="f18fe-132">A specific version of Windows 10 is required, and this version is only available to volume licensing customers.</span></span>  <span data-ttu-id="f18fe-133">[ボリューム ライセンス サービス センター](https://www.microsoft.com/Licensing/servicecenter/)からコピーを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="f18fe-133">You can get a copy from the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).</span></span>

<span data-ttu-id="f18fe-134">完了したら、USB ディスクをコンピューターから削除し、[コンソール アプリケーションの Windows 10 をインストールし、マイクロソフト チームの部屋](console.md#Reimage)に進みます。</span><span class="sxs-lookup"><span data-stu-id="f18fe-134">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Microsoft Teams Rooms console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a><span data-ttu-id="f18fe-135">10 の Windows とマイクロソフトのチームの会議室のコンソール アプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f18fe-135">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>
<span data-ttu-id="f18fe-136"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="f18fe-136"></span></span>

<span data-ttu-id="f18fe-137">作成したセットアップ メディアを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f18fe-137">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="f18fe-138">アプライアンスとターゲット ・ デバイスが実行され、既定のユーザーは、マイクロソフト チームの会議室のコンソール アプリケーションを実行するだけに設定されます。</span><span class="sxs-lookup"><span data-stu-id="f18fe-138">The target device will run as an appliance and the default user will be set to only run the Microsoft Teams Rooms console app.</span></span>

1. <span data-ttu-id="f18fe-139">ドッキング ステーション (例えば、Surface Pro) でターゲット ・ デバイスをインストールする場合は、ドッキング ステーションから取り外します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-139">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="f18fe-140">ターゲット ・ デバイスがネットワークに接続されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-140">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="f18fe-141">ターゲット ・ デバイスが AC 電源に接続されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-141">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="f18fe-142">USB セットアップ ディスクをターゲット ・ デバイスに差し込みます。</span><span class="sxs-lookup"><span data-stu-id="f18fe-142">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="f18fe-143">USB セットアップ ディスクから起動します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-143">Boot to the USB setup disk.</span></span> <span data-ttu-id="f18fe-144">製造元の指示を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f18fe-144">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="f18fe-145">場合は、ターゲット ・ デバイスは、Surface Pro は、USB のセットアップ ディスクから起動するのには次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-145">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="f18fe-146">a.</span><span class="sxs-lookup"><span data-stu-id="f18fe-146">a.</span></span> <span data-ttu-id="f18fe-147">キーを押し、ボリューム ダウン (-) ボタンを押したままです。</span><span class="sxs-lookup"><span data-stu-id="f18fe-147">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="f18fe-148">b.</span><span class="sxs-lookup"><span data-stu-id="f18fe-148">b.</span></span> <span data-ttu-id="f18fe-149">キーを押し、電源ボタンを離します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-149">Press and release the power button.</span></span>

    <span data-ttu-id="f18fe-150">c.</span><span class="sxs-lookup"><span data-stu-id="f18fe-150">c.</span></span> <span data-ttu-id="f18fe-151">Windows セットアップが起動したら、ボリューム ダウン (-) ボタンを離します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-151">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="f18fe-152">インストールが完了したら、システムがシャット ダウンします。</span><span class="sxs-lookup"><span data-stu-id="f18fe-152">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="f18fe-153">システムがシャット ダウンした後、USB のセットアップ ディスクを削除すると安全です。</span><span class="sxs-lookup"><span data-stu-id="f18fe-153">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="f18fe-154">この時点で、(ドッキング ベースの製品を使用する) 場合は、そのドッキング ステーションにターゲット ・ デバイスを配置、会議室に必要な周辺機器を接続してネットワークに接続できます。</span><span class="sxs-lookup"><span data-stu-id="f18fe-154">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="f18fe-155">製造元の指示を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f18fe-155">Refer to the manufacturer instructions.</span></span>
  
### <a name="selecting-a-language"></a><span data-ttu-id="f18fe-156">言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-156">Selecting a language</span></span> 

<span data-ttu-id="f18fe-157">作成者の更新では、暗黙の言語の選択が必要な実際のアプリケーションの言語を使用してユーザーを提供しないシナリオで ApplyCurrentRegionAndLanguage.ps1 スクリプトを使用する必要があります (フランス語、考案するコンソール アプリケーションをするなどが、それは、次の英語で)。</span><span class="sxs-lookup"><span data-stu-id="f18fe-157">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f18fe-158">次の手順は、作成者の Windows 更新プログラムを使用して作成されたコンソールに対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-158">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="f18fe-159">新しいプロビジョニング システムでメディアを使用して設定されていないレガシ/市場でのシステムは、これらの手順を使用することはできませんが、この手動による介入を必要とする最初の問題からは低くもする必要があります (記念日のエディションを選択できます、アプリケーションの言語設定の一部として明示的に)。</span><span class="sxs-lookup"><span data-stu-id="f18fe-159">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="f18fe-160">必要な言語を適用するには</span><span class="sxs-lookup"><span data-stu-id="f18fe-160">To apply your desired language</span></span>

1. <span data-ttu-id="f18fe-161">管理モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="f18fe-161">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="f18fe-162">[スタート] メニューを選択します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-162">Select the Start menu.</span></span>
    
3. <span data-ttu-id="f18fe-163">ギア アイコンを選択して [**設定**] アプリを起動します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-163">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="f18fe-164">選択**時間&amp;言語**です。</span><span class="sxs-lookup"><span data-stu-id="f18fe-164">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="f18fe-165">選択**地域&amp;言語**です。</span><span class="sxs-lookup"><span data-stu-id="f18fe-165">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="f18fe-166">[**言語の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-166">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="f18fe-167">追加する言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-167">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="f18fe-168">[言語] ボックスの一覧に追加した言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-168">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="f18fe-169">[**既定に設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-169">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="f18fe-170">削除する言語については、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f18fe-170">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="f18fe-p114">a. 削除する言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-p114">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="f18fe-p115">b. [**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-p115">b. Select **Remove**.</span></span>
    
11. <span data-ttu-id="f18fe-175">管理者特権でコマンド プロンプトを開始します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-175">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="f18fe-176">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-176">Run the following command:</span></span> 
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="f18fe-177">システムを再起動します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-177">Restart the system.</span></span>
    
<span data-ttu-id="f18fe-178">マイクロソフト チームの会議室のコンソールに、目的の言語が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f18fe-178">Your desired language is now applied to the Microsoft Teams Rooms console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="f18fe-179">コンソールの初期設定</span><span class="sxs-lookup"><span data-stu-id="f18fe-179">Initial set up of the console</span></span>
<span data-ttu-id="f18fe-180"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="f18fe-180"></span></span>

<span data-ttu-id="f18fe-181">Windows がインストールされると、マイクロソフト チームの会議室のコンソール アプリケーションが次回起動したとき、または、/reboot オプションが選択された場合の初期のセットアップ プロセスに移動します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-181">After Windows is installed, the Microsoft Teams Rooms console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="f18fe-182">[ユーザー アカウント] 画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f18fe-182">The User Account screen appears.</span></span> <span data-ttu-id="f18fe-183">Skype サインインのアドレスを入力 (user@domain 形式) で、コンソールで使用する部屋のアカウントです。</span><span class="sxs-lookup"><span data-stu-id="f18fe-183">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="f18fe-184">ルーム アカウントのパスワードを入力し、確認のためにもう一度入力します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-184">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="f18fe-185">"ドメインの構成] の下で、Skype のビジネス サーバーの FQDN を設定します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-185">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="f18fe-186">ビジネスの SIP ドメインの Skype ユーザーの Exchange ドメインと異なる場合は、このフィールドに、Exchange ドメインを入力します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-186">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="f18fe-187">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f18fe-187">Click **Next**.</span></span>
    
5. <span data-ttu-id="f18fe-188">[機能] 画面で指定されたデバイスを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f18fe-188">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="f18fe-189">既定では、自動画面共有はオンで、会議名の非表示はオフになっています。</span><span class="sxs-lookup"><span data-stu-id="f18fe-189">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="f18fe-190">選択対象のデバイスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f18fe-190">The devices to select are:</span></span>
    
   - <span data-ttu-id="f18fe-191">会議用のマイク: 会議室で使用する既定のマイク。</span><span class="sxs-lookup"><span data-stu-id="f18fe-191">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="f18fe-192">会議用のスピーカー: 会議で使用する既定のスピーカー。</span><span class="sxs-lookup"><span data-stu-id="f18fe-192">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="f18fe-193">既定のスピーカー: HDMI インジェストからのオーディオ用に使用されるスピーカー。</span><span class="sxs-lookup"><span data-stu-id="f18fe-193">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="f18fe-p119">それぞれの項目に、選択できるドロップダウン メニューのオプションがあります。各デバイスについて選択を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f18fe-p119">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="f18fe-196">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f18fe-196">Click **Finish**.</span></span>
    
<span data-ttu-id="f18fe-197">マイクロソフト チームの会議室のコンソール アプリケーションは、ビジネス サーバー、上で入力した資格情報を持つ Skype にサインインします。 すぐに開始する必要がありで同じ資格情報を使用して Exchange の予定表の同期を開始する必要がありますも。</span><span class="sxs-lookup"><span data-stu-id="f18fe-197">The Microsoft Teams Rooms console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="f18fe-198">コンソール アプリケーションの使用方法の詳細については、[マイクロソフト チームの会議室のヘルプ](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f18fe-198">For details on using the console app, refer to the [Microsoft Teams Rooms help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f18fe-199">マイクロソフト チームの会議室では、認定されたコンソールのハードウェアの存在に依存しています。</span><span class="sxs-lookup"><span data-stu-id="f18fe-199">Microsoft Teams Rooms relies on the presence of certified console hardware.</span></span> <span data-ttu-id="f18fe-200">コンソール ハードウェアが検出された場合を除き、マイクロソフト チームの会議室のコンソール アプリケーションが含まれている正常に作成されたイメージは過去の初期セットアップ手順起動しません。</span><span class="sxs-lookup"><span data-stu-id="f18fe-200">Even a correctly created image containing the Microsoft Teams Rooms console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="f18fe-201">Surface Pro ベースのソリューションでは、Surface Pro が必要に接続するこのチェックに合格するのには、付属のドッキング ハードウェア。</span><span class="sxs-lookup"><span data-stu-id="f18fe-201">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f18fe-202">英語以外の言語の一部のユーザーは、タッチ キーボードでは、シンボルはサポートされていない、初期セットアップ時にコンソールに接続されている物理的なキーボードを必要があります。</span><span class="sxs-lookup"><span data-stu-id="f18fe-202">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="f18fe-203">コンソールにプライベート CA 証明書をインストールします。</span><span class="sxs-lookup"><span data-stu-id="f18fe-203">Install a private CA certificate on the console</span></span>
<span data-ttu-id="f18fe-204"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="f18fe-204"></span></span>

<span data-ttu-id="f18fe-205">マイクロソフト チームの会議室のコンソールでは、ビジネスおよび Exchange のサーバーに接続するため、Skype で使用する証明書を信頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f18fe-205">The Microsoft Teams Rooms console needs to trust the certificates used by the Skype for Business and Exchange servers it connects to.</span></span> <span data-ttu-id="f18fe-206">O365 の場合、これらのサーバーはパブリックの証明機関を使用し、これらは Windows 10 で自動的に信頼されるため、この処理は自動的に行われます。</span><span class="sxs-lookup"><span data-stu-id="f18fe-206">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="f18fe-207">証明機関がプライベートの場合は Active Directory および Windows の証明機関と設置型展開の方法のいくつかのマイクロソフト チームの会議室のコンソールに証明書を追加できます。</span><span class="sxs-lookup"><span data-stu-id="f18fe-207">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Microsoft Teams Rooms console in a couple of ways:</span></span>
  
- <span data-ttu-id="f18fe-208">コンソールを Active Directory に参加させることができ、証明機関を指定する必要な証明書が Active Directory (通常の展開オプション) を発行するが自動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-208">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="f18fe-209">イメージング処理の後に証明書を手動でインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="f18fe-209">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="f18fe-210">これを行う前に[初期がコンソールの設定](console.md#Initial)を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f18fe-210">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="f18fe-211">証明書を手動でインストールするには </span><span class="sxs-lookup"><span data-stu-id="f18fe-211">To manually install the certificate</span></span>

1. <span data-ttu-id="f18fe-212">CA 証明書をお使いのコンピューターにダウンロードして、C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer に保存します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-212">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="f18fe-213">管理者モードでコンソールを配置する ([管理者モードとデバイスの管理](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="f18fe-213">Place the console in admin mode (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="f18fe-214">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-214">Run the following command:</span></span>
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="f18fe-215">(省略可能) Active Directory のドメインに参加します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-215">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="f18fe-216"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="f18fe-216"></span></span>

<span data-ttu-id="f18fe-217">マイクロソフト チームの会議室のコンソールは、ドメインに参加できます。</span><span class="sxs-lookup"><span data-stu-id="f18fe-217">You can join Microsoft Teams Rooms consoles to your domain.</span></span> <span data-ttu-id="f18fe-218">マイクロソフト チームの会議室のコンソールは、多くのワークステーションのポリシーは、マイクロソフト チームの会議室では互換性がないため PC ワークステーションから別の OU に配置してください。</span><span class="sxs-lookup"><span data-stu-id="f18fe-218">Microsoft Teams Rooms consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Microsoft Teams Rooms.</span></span> <span data-ttu-id="f18fe-219">一般的な例は、パスワードの強制ポリシー マイクロソフト チームの会議室が自動的に起動できなくなります。</span><span class="sxs-lookup"><span data-stu-id="f18fe-219">A common example are password enforcement policies that will prevent Microsoft Teams Rooms from starting up automatically.</span></span> <span data-ttu-id="f18fe-220">GPO の設定の管理方法については、[マイクロソフト チームのルームの管理](../../manage/skype-room-systems-v2/room-systems-v2-operations.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f18fe-220">For information about the management of GPO settings, please refer to [Manage Microsoft Teams Rooms](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span></span>
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a><span data-ttu-id="f18fe-221">マイクロソフト チームの会議室をドメインに参加させる</span><span class="sxs-lookup"><span data-stu-id="f18fe-221">To join Microsoft Teams Rooms to a domain</span></span>

1. <span data-ttu-id="f18fe-222">では、管理コンソールに記号 ([管理者モードとデバイスの管理](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)を参照してください) を考慮します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-222">Sign into the console from the admin account (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="f18fe-223">管理者特権で Powershell コマンド プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-223">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="f18fe-224">Powershell に次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-224">Enter the following command in Powershell:</span></span>
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="f18fe-225">などの場合は、完全修飾のドメインは、redmond.corp.microsoft.com、「リソース」OU の子である「マイクロソフト チーム ルーム」OU に、マイクロソフト チームの会議室のコンソール、コマンドになります。</span><span class="sxs-lookup"><span data-stu-id="f18fe-225">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Microsoft Teams Rooms consoles to be in a "Microsoft Teams Rooms" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="f18fe-226">ドメインに参加させるときに、コンピューターの名前を変更したい場合は、コンピューターの新しい名前の後に、新しい名前のフラグを使用します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-226">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a><span data-ttu-id="f18fe-227">マイクロソフト チームの会議室の展開のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="f18fe-227">Microsoft Teams Rooms deployment checklist</span></span>
<span data-ttu-id="f18fe-228"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="f18fe-228"></span></span>

<span data-ttu-id="f18fe-229">コンソールとそのすべての周辺機器が完全に構成されている最終的な検証を行う際に、次のチェックリストを使用します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-229">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="f18fe-230">**アプリケーションの設定**</span><span class="sxs-lookup"><span data-stu-id="f18fe-230">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f18fe-231">☐</span><span class="sxs-lookup"><span data-stu-id="f18fe-231">☐</span></span>  <br/> |<span data-ttu-id="f18fe-232">ルーム アカウント名と電話番号 (PSTN が有効な場合) が、コンソール画面の右上に正しく表示される</span><span class="sxs-lookup"><span data-stu-id="f18fe-232">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="f18fe-233">☐</span><span class="sxs-lookup"><span data-stu-id="f18fe-233">☐</span></span>  <br/> |<span data-ttu-id="f18fe-234">Windows コンピューター名が正しく設定されている (リモート管理に役立つ)</span><span class="sxs-lookup"><span data-stu-id="f18fe-234">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="f18fe-235">☐</span><span class="sxs-lookup"><span data-stu-id="f18fe-235">☐</span></span>  <br/> |<span data-ttu-id="f18fe-236">管理者アカウントのパスワードが設定されており、確認済みである</span><span class="sxs-lookup"><span data-stu-id="f18fe-236">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="f18fe-237">☐</span><span class="sxs-lookup"><span data-stu-id="f18fe-237">☐</span></span>  <br/> |<span data-ttu-id="f18fe-238">すべてのファームウェア更新プログラムが適用されています。</span><span class="sxs-lookup"><span data-stu-id="f18fe-238">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="f18fe-239">**オーディオ/ビデオ周辺機器**</span><span class="sxs-lookup"><span data-stu-id="f18fe-239">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f18fe-240">☐</span><span class="sxs-lookup"><span data-stu-id="f18fe-240">☐</span></span>  <br/> |<span data-ttu-id="f18fe-241">カメラ周辺機器のファームウェアのバージョンが正しい (該当する場合)</span><span class="sxs-lookup"><span data-stu-id="f18fe-241">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="f18fe-242">☐</span><span class="sxs-lookup"><span data-stu-id="f18fe-242">☐</span></span>  <br/> |<span data-ttu-id="f18fe-243">カメラの機能と、最適な位置を指定しました。</span><span class="sxs-lookup"><span data-stu-id="f18fe-243">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="f18fe-244">☐</span><span class="sxs-lookup"><span data-stu-id="f18fe-244">☐</span></span>  <br/> |<span data-ttu-id="f18fe-245">既定の再生デバイスと既定の再生通信デバイスの設定が、目的のオーディオ周辺機器に設定されている</span><span class="sxs-lookup"><span data-stu-id="f18fe-245">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="f18fe-246">☐</span><span class="sxs-lookup"><span data-stu-id="f18fe-246">☐</span></span>  <br/> |<span data-ttu-id="f18fe-247">既定の録音通信デバイスの設定が目的のオーディオ周辺機器に設定されている</span><span class="sxs-lookup"><span data-stu-id="f18fe-247">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="f18fe-248">☐</span><span class="sxs-lookup"><span data-stu-id="f18fe-248">☐</span></span>  <br/> |<span data-ttu-id="f18fe-249">オーディオ周辺機器のファームウェアのバージョンが正しい (該当する場合)</span><span class="sxs-lookup"><span data-stu-id="f18fe-249">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="f18fe-250">☐</span><span class="sxs-lookup"><span data-stu-id="f18fe-250">☐</span></span>  <br/> |<span data-ttu-id="f18fe-251">オーディオ入力デバイスが機能し、適切に配置されている</span><span class="sxs-lookup"><span data-stu-id="f18fe-251">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="f18fe-252">☐</span><span class="sxs-lookup"><span data-stu-id="f18fe-252">☐</span></span>  <br/> |<span data-ttu-id="f18fe-253">オーディオ出力デバイスが機能し、適切に配置されている</span><span class="sxs-lookup"><span data-stu-id="f18fe-253">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="f18fe-254">**ドック**</span><span class="sxs-lookup"><span data-stu-id="f18fe-254">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f18fe-255">☐</span><span class="sxs-lookup"><span data-stu-id="f18fe-255">☐</span></span>  <br/> |<span data-ttu-id="f18fe-256">ケーブルが保護されており、圧迫されていない</span><span class="sxs-lookup"><span data-stu-id="f18fe-256">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="f18fe-257">☐</span><span class="sxs-lookup"><span data-stu-id="f18fe-257">☐</span></span>  <br/> |<span data-ttu-id="f18fe-258">HDMI を介したオーディオ インジェストが機能している</span><span class="sxs-lookup"><span data-stu-id="f18fe-258">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="f18fe-259">☐</span><span class="sxs-lookup"><span data-stu-id="f18fe-259">☐</span></span>  <br/> |<span data-ttu-id="f18fe-260">HDMI を介したビデオ インジェストが機能している</span><span class="sxs-lookup"><span data-stu-id="f18fe-260">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="f18fe-261">☐</span><span class="sxs-lookup"><span data-stu-id="f18fe-261">☐</span></span>  <br/> |<span data-ttu-id="f18fe-262">ドックは自由に回転することができる</span><span class="sxs-lookup"><span data-stu-id="f18fe-262">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="f18fe-263">☐</span><span class="sxs-lookup"><span data-stu-id="f18fe-263">☐</span></span>  <br/> |<span data-ttu-id="f18fe-264">表示の明るさが環境に適している</span><span class="sxs-lookup"><span data-stu-id="f18fe-264">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f18fe-265">関連項目</span><span class="sxs-lookup"><span data-stu-id="f18fe-265">See also</span></span>
<span data-ttu-id="f18fe-266"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="f18fe-266"></span></span>

[<span data-ttu-id="f18fe-267">マイクロソフト チームの会議室のプラン</span><span class="sxs-lookup"><span data-stu-id="f18fe-267">Plan for Microsoft Teams Rooms</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="f18fe-268">マイクロソフト チームの会議室を配置します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-268">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="f18fe-269">マイクロソフト チームの会議室のコンソールを構成します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-269">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="f18fe-270">マイクロソフト チームの会議室を管理します。</span><span class="sxs-lookup"><span data-stu-id="f18fe-270">Manage Microsoft Teams Rooms</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)
