---
title: Skype Room Systems バージョン 2 コンソールを構成する
ms.author: jambirk
author: jambirk
ms.reviewer: Travis-Snoozy
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: Strat_SB_Admin
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: この資料では、Skype ルーム システム v2 のコンソールとその周辺機器を設定する方法について説明します。
ms.openlocfilehash: 162aaaed5472fefc3c23cc11800b166ed4b26bc2
ms.sourcegitcommit: 788e3526ff973454f3904c33d867691a2fae814f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "28326717"
---
# <a name="configure-a-skype-room-systems-v2-console"></a><span data-ttu-id="e58ef-103">Skype Room Systems バージョン 2 コンソールを構成する</span><span class="sxs-lookup"><span data-stu-id="e58ef-103">Configure a Skype Room Systems v2 console</span></span>
 
<span data-ttu-id="e58ef-104">この資料では、Skype ルーム システム v2 のコンソールとその周辺機器を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-104">This article describes how to set up the Skype Room Systems v2 console and its peripherals.</span></span>
  
<span data-ttu-id="e58ef-105">ビジネスおよび Exchange アカウントに必要な Skype が既に作成して[Skype ルーム システムの配置のバージョン 2](room-systems-v2.md)で説明したようにテストする場合のみ、この手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e58ef-105">You should only perform these steps if the necessary Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> <span data-ttu-id="e58ef-106">ハードウェアとソフトウェアの[Skype ルーム システム v2 の要件](../../plan-your-deployment/clients-and-devices/requirements.md)」に記載する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e58ef-106">You will need the hardware and software described in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span> <span data-ttu-id="e58ef-107">このトピックには次のセクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e58ef-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="e58ef-108">インストール メディアを準備します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-108">Prepare the installation media</span></span>](console.md#Prep_Media)
    
- [<span data-ttu-id="e58ef-109">コンソールにプライベート CA 証明書をインストールします。</span><span class="sxs-lookup"><span data-stu-id="e58ef-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
    
- [<span data-ttu-id="e58ef-110">Windows 10 と Skype Room Systems バージョン 2 コンソール アプリをインストールする</span><span class="sxs-lookup"><span data-stu-id="e58ef-110">Install Windows 10 and the Skype Room Systems v2 console app</span></span>](console.md#Reimage)
   
- [<span data-ttu-id="e58ef-111">コンソールの初期設定</span><span class="sxs-lookup"><span data-stu-id="e58ef-111">Initial set up of the console</span></span>](console.md#Initial)
    
- [<span data-ttu-id="e58ef-112">Skype ルーム システム v2 の展開のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="e58ef-112">Skype Room Systems v2 deployment checklist</span></span>](console.md#Checklist)
    
> [!NOTE]
> <span data-ttu-id="e58ef-113">Skype ルーム システム v2 は、ビジネス環境をデバイスのアカウントが正しく設定されて[Skype ルーム システムの配置のバージョン 2](room-systems-v2.md)で説明したように正しく構成されている Skype でのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-113">Skype Room Systems v2 will only work in a properly configured Skype for Business environment where the device accounts are set up correctly as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="e58ef-114">インストール メディアを準備します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-114">Prepare the installation media</span></span>
<span data-ttu-id="e58ef-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="e58ef-115"></span></span>

<span data-ttu-id="e58ef-116">Skype ルーム システム v2 のコンソール アプリケーションをインストールするには、32 GB 以上の容量を持つ USB ストレージ デバイスが必要です。</span><span class="sxs-lookup"><span data-stu-id="e58ef-116">Installing the Skype Room Systems v2 console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="e58ef-117">存在しないはずのデバイス上のファイルUSB 記憶装置上の既存のファイルはすべて失われます。</span><span class="sxs-lookup"><span data-stu-id="e58ef-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e58ef-118">予期しない動作になる可能性があります、次の手順に従って、Skype ルーム システム v2 のインストール メディアを作成するに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="e58ef-118">Failure to create your Skype Room Systems v2 installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="e58ef-119">以下の手順は、新しい Skype ルーム システム v2 のデバイスのイメージにインストール メディアを作成するためです。</span><span class="sxs-lookup"><span data-stu-id="e58ef-119">The process below is for creating installation media to image new Skype Room System v2 devices.</span></span> <span data-ttu-id="e58ef-120">既存のデバイスでは、既定では、自動的に更新 Windows を更新し、Windows ストアから。</span><span class="sxs-lookup"><span data-stu-id="e58ef-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>
  
1. <span data-ttu-id="e58ef-121">[CreateSrsMedia.ps1 スクリプト](https://go.microsoft.com/fwlink/?linkid=867842)をダウンロードします。 </span><span class="sxs-lookup"><span data-stu-id="e58ef-121">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="e58ef-122">Windows 10 マシン上で管理者特権でのプロンプトから CreateSrsMedia.ps1 スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-122">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="e58ef-123">Skype ルーム システム v2 の USB セットアップ ディスクを作成するスクリプトの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="e58ef-123">Follow the script's instructions to create a Skype Room Systems v2 USB setup disk.</span></span>

> [!CAUTION]
> <span data-ttu-id="e58ef-124">メディアからの作成スクリプトを実行するフォルダーの名前にスペースを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="e58ef-124">The name of the folder that you run the media creation script from can not contain a space.</span></span> <span data-ttu-id="e58ef-125">フォルダー名にスペースがある場合、スクリプトは失敗します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-125">If there is a space in to folder name, the script will fail.</span></span>

<span data-ttu-id="e58ef-126">完了したら、USB ディスクをコンピューターから削除し、 [Windows の 10 をインストール](console.md#Reimage)して Skype ルーム システム v2 のコンソール アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="e58ef-126">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Skype Room Systems v2 console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-skype-room-systems-v2-console-app"></a><span data-ttu-id="e58ef-127">Windows 10 と Skype Room Systems バージョン 2 コンソール アプリをインストールする</span><span class="sxs-lookup"><span data-stu-id="e58ef-127">Install Windows 10 and the Skype Room Systems v2 console app</span></span>
<span data-ttu-id="e58ef-128"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="e58ef-128"></span></span>

<span data-ttu-id="e58ef-129">作成したセットアップ メディアを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e58ef-129">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="e58ef-130">アプライアンスとターゲット ・ デバイスが実行され、既定のユーザーは、Skype ルーム システム v2 のコンソール アプリケーションを実行するだけに設定されます。</span><span class="sxs-lookup"><span data-stu-id="e58ef-130">The target device will run as an appliance and the default user will be set to only run the Skype Room Systems v2 console app.</span></span>

1. <span data-ttu-id="e58ef-131">ドッキング ステーション (例えば、Surface Pro) でターゲット ・ デバイスをインストールする場合は、ドッキング ステーションから取り外します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-131">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="e58ef-132">ターゲット ・ デバイスがネットワークに接続されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-132">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="e58ef-133">ターゲット ・ デバイスが AC 電源に接続されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-133">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="e58ef-134">USB セットアップ ディスクをターゲット ・ デバイスに差し込みます。</span><span class="sxs-lookup"><span data-stu-id="e58ef-134">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="e58ef-135">USB セットアップ ディスクから起動します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-135">Boot to the USB setup disk.</span></span> <span data-ttu-id="e58ef-136">製造元の指示を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e58ef-136">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="e58ef-137">場合は、ターゲット ・ デバイスは、Surface Pro は、USB のセットアップ ディスクから起動するのには次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-137">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    1. <span data-ttu-id="e58ef-138">キーを押し、ボリューム ダウン (-) ボタンを押したままです。</span><span class="sxs-lookup"><span data-stu-id="e58ef-138">Press and continue to hold the volume down (-) button.</span></span>

    2. <span data-ttu-id="e58ef-139">キーを押し、電源ボタンを離します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-139">Press and release the power button.</span></span>

    3. <span data-ttu-id="e58ef-140">Windows セットアップが起動したら、ボリューム ダウン (-) ボタンを離します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-140">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="e58ef-141">インストールが完了したら、システムがシャット ダウンします。</span><span class="sxs-lookup"><span data-stu-id="e58ef-141">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="e58ef-142">システムがシャット ダウンした後、USB のセットアップ ディスクを削除すると安全です。</span><span class="sxs-lookup"><span data-stu-id="e58ef-142">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="e58ef-143">この時点で、(ドッキング ベースの製品を使用する) 場合は、そのドッキング ステーションにターゲット ・ デバイスを配置、会議室に必要な周辺機器を接続してネットワークに接続できます。</span><span class="sxs-lookup"><span data-stu-id="e58ef-143">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="e58ef-144">製造元の指示を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e58ef-144">Refer to the manufacturer instructions.</span></span>
  
### <a name="selecting-a-language"></a><span data-ttu-id="e58ef-145">言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-145">Selecting a language</span></span> 

<span data-ttu-id="e58ef-146">作成者の更新では、暗黙の言語の選択が必要な実際のアプリケーションの言語を使用してユーザーを提供しないシナリオで ApplyCurrentRegionAndLanguage.ps1 スクリプトを使用する必要があります (フランス語、考案するコンソール アプリケーションをするなどが、それは、次の英語で)。</span><span class="sxs-lookup"><span data-stu-id="e58ef-146">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e58ef-147">次の手順は、作成者の Windows 更新プログラムを使用して作成されたコンソールに対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-147">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="e58ef-148">新しいプロビジョニング システムでメディアを使用して設定されていないレガシ/市場でのシステムは、これらの手順を使用することはできませんが、この手動による介入を必要とする最初の問題からは低くもする必要があります (記念日のエディションを選択できます、アプリケーションの言語設定の一部として明示的に)。</span><span class="sxs-lookup"><span data-stu-id="e58ef-148">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="e58ef-149">必要な言語を適用するには</span><span class="sxs-lookup"><span data-stu-id="e58ef-149">To apply your desired language</span></span>

1. <span data-ttu-id="e58ef-150">管理モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="e58ef-150">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="e58ef-151">[スタート] メニューを選択します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-151">Select the Start menu.</span></span>
    
3. <span data-ttu-id="e58ef-152">ギア アイコンを選択して [**設定**] アプリを起動します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-152">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="e58ef-153">選択**時間&amp;言語**です。</span><span class="sxs-lookup"><span data-stu-id="e58ef-153">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="e58ef-154">選択**地域&amp;言語**です。</span><span class="sxs-lookup"><span data-stu-id="e58ef-154">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="e58ef-155">[**言語の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-155">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="e58ef-156">追加する言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-156">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="e58ef-157">[言語] ボックスの一覧に追加した言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-157">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="e58ef-158">[**既定に設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-158">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="e58ef-159">削除する言語については、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e58ef-159">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="e58ef-p109">a. 削除する言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-p109">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="e58ef-p110">b. [**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-p110">b. Select **Remove**.</span></span>
    
11. <span data-ttu-id="e58ef-164">管理者特権でコマンド プロンプトを開始します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-164">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="e58ef-165">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-165">Run the following command:</span></span> 
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="e58ef-166">システムを再起動します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-166">Restart the system.</span></span>
    
<span data-ttu-id="e58ef-167">Skype ルーム システム v2 のコンソールに、目的の言語が適用されます。</span><span class="sxs-lookup"><span data-stu-id="e58ef-167">Your desired language is now applied to the Skype Room Systems v2 console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="e58ef-168">コンソールの初期設定</span><span class="sxs-lookup"><span data-stu-id="e58ef-168">Initial set up of the console</span></span>
<span data-ttu-id="e58ef-169"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="e58ef-169"></span></span>

<span data-ttu-id="e58ef-170">Windows をインストールすると、Skype ルーム システム v2 のコンソール アプリケーションが次回起動したとき、または、/reboot オプションが選択された場合の初期のセットアップ プロセスに移動します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-170">After Windows is installed, the Skype Room Systems v2 console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="e58ef-171">[ユーザー アカウント] 画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e58ef-171">The User Account screen appears.</span></span> <span data-ttu-id="e58ef-172">Skype サインインのアドレスを入力 (user@domain 形式) で、コンソールで使用する部屋のアカウントです。</span><span class="sxs-lookup"><span data-stu-id="e58ef-172">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="e58ef-173">ルーム アカウントのパスワードを入力し、確認のためにもう一度入力します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-173">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="e58ef-174">"ドメインの構成] の下で、Skype のビジネス サーバーの FQDN を設定します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-174">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="e58ef-175">ビジネスの SIP ドメインの Skype ユーザーの Exchange ドメインと異なる場合は、このフィールドに、Exchange ドメインを入力します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-175">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="e58ef-176">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e58ef-176">Click **Next**.</span></span>
    
5. <span data-ttu-id="e58ef-177">[機能] 画面で指定されたデバイスを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e58ef-177">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="e58ef-178">既定では、自動画面共有はオンで、会議名の非表示はオフになっています。</span><span class="sxs-lookup"><span data-stu-id="e58ef-178">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="e58ef-179">選択対象のデバイスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e58ef-179">The devices to select are:</span></span>
    
   - <span data-ttu-id="e58ef-180">会議用のマイク: 会議室で使用する既定のマイク。</span><span class="sxs-lookup"><span data-stu-id="e58ef-180">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="e58ef-181">会議用のスピーカー: 会議で使用する既定のスピーカー。</span><span class="sxs-lookup"><span data-stu-id="e58ef-181">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="e58ef-182">既定のスピーカー: HDMI インジェストからのオーディオ用に使用されるスピーカー。</span><span class="sxs-lookup"><span data-stu-id="e58ef-182">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="e58ef-p114">それぞれの項目に、選択できるドロップダウン メニューのオプションがあります。各デバイスについて選択を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e58ef-p114">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="e58ef-185">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e58ef-185">Click **Finish**.</span></span>
    
<span data-ttu-id="e58ef-186">Skype ルーム システム v2 のコンソール アプリケーションは、ビジネス サーバー、上で入力した資格情報を持つ Skype にサインインします。 すぐに開始する必要がありで同じ資格情報を使用して Exchange の予定表の同期を開始する必要がありますも。</span><span class="sxs-lookup"><span data-stu-id="e58ef-186">The Skype Room Systems v2 console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="e58ef-187">コンソール アプリケーションの使用方法の詳細については、 [Skype ルーム システム バージョン 2 のヘルプ](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e58ef-187">For details on using the console app, refer to the [Skype Room Systems version 2 help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e58ef-188">Skype ルーム システム v2 では、認定されたコンソールのハードウェアの存在に依存しています。</span><span class="sxs-lookup"><span data-stu-id="e58ef-188">Skype Room Systems v2 relies on the presence of certified console hardware.</span></span> <span data-ttu-id="e58ef-189">Skype ルーム システム v2 のコンソール アプリケーションが含まれている正常に作成されたイメージはコンソールのハードウェアが検出された場合を除き、過去の最初のセットアップ手順は起動しません。</span><span class="sxs-lookup"><span data-stu-id="e58ef-189">Even a correctly created image containing the Skype Room Systems v2 console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="e58ef-190">Surface Pro ベースのソリューションでは、Surface Pro が必要に接続するこのチェックに合格するのには、付属のドッキング ハードウェア。</span><span class="sxs-lookup"><span data-stu-id="e58ef-190">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e58ef-191">英語以外の言語の一部のユーザーは、タッチ キーボードでは、シンボルはサポートされていない、初期セットアップ時にコンソールに接続されている物理的なキーボードを必要があります。</span><span class="sxs-lookup"><span data-stu-id="e58ef-191">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="e58ef-192">コンソールにプライベート CA 証明書をインストールします。</span><span class="sxs-lookup"><span data-stu-id="e58ef-192">Install a private CA certificate on the console</span></span>
<span data-ttu-id="e58ef-193"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="e58ef-193"></span></span>

<span data-ttu-id="e58ef-194">Skype ルーム システム v2 のコンソールでは、ビジネスおよび Exchange のサーバーに接続するため、Skype で使用する証明書を信頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e58ef-194">The Skype Room Systems v2 console needs to trust the certificates used by the Skype for Business and Exchange servers it connects to.</span></span> <span data-ttu-id="e58ef-195">O365 の場合、これらのサーバーはパブリックの証明機関を使用し、これらは Windows 10 で自動的に信頼されるため、この処理は自動的に行われます。</span><span class="sxs-lookup"><span data-stu-id="e58ef-195">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="e58ef-196">証明機関がプライベートの場合は Active Directory および Windows の証明機関と設置型展開の 2 とおりの方法で Skype ルーム システム v2 のコンソールに証明書を追加できます。</span><span class="sxs-lookup"><span data-stu-id="e58ef-196">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Skype Room Systems v2 console in a couple of ways:</span></span>
  
- <span data-ttu-id="e58ef-197">コンソールを Active Directory に参加させることができ、証明機関を指定する必要な証明書が Active Directory (通常の展開オプション) を発行するが自動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-197">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="e58ef-198">イメージング処理の後に証明書を手動でインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="e58ef-198">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="e58ef-199">これを行う前に[初期がコンソールの設定](console.md#Initial)を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e58ef-199">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="e58ef-200">証明書を手動でインストールするには </span><span class="sxs-lookup"><span data-stu-id="e58ef-200">To manually install the certificate</span></span>

1. <span data-ttu-id="e58ef-201">CA 証明書をお使いのコンピューターにダウンロードして、C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer に保存します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-201">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="e58ef-202">管理者モードでコンソールを配置する ([管理者モードとデバイスの管理](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="e58ef-202">Place the console in admin mode (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="e58ef-203">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-203">Run the following command:</span></span>
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="e58ef-204">(省略可能) Active Directory のドメインに参加します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-204">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="e58ef-205"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="e58ef-205"></span></span>

<span data-ttu-id="e58ef-206">Skype ルーム システム v2 のコンソールは、ドメインに参加できます。</span><span class="sxs-lookup"><span data-stu-id="e58ef-206">You can join Skype Room Systems v2 consoles to your domain.</span></span> <span data-ttu-id="e58ef-207">Skype ルーム システム v2 のコンソールは、多くのワークステーションのポリシーは Skype ルーム システム v2 と互換性がないため PC ワークステーションから別の OU に配置してください。</span><span class="sxs-lookup"><span data-stu-id="e58ef-207">Skype Room Systems v2 consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Skype Room Systems v2.</span></span> <span data-ttu-id="e58ef-208">一般的な例は、パスワードの強制ポリシー Skype ルーム システム v2 が自動的に起動できなくなります。</span><span class="sxs-lookup"><span data-stu-id="e58ef-208">A common example are password enforcement policies that will prevent Skype Room Systems v2 from starting up automatically.</span></span> <span data-ttu-id="e58ef-209">GPO 設定の管理の詳細については、「[Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e58ef-209">For information about the management of GPO settings, please refer to [Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span></span>
  
### <a name="to-join-skype-room-system-v2-to-a-domain"></a><span data-ttu-id="e58ef-210">Skype Room System バージョン 2 をドメインに参加させるには</span><span class="sxs-lookup"><span data-stu-id="e58ef-210">To join Skype Room System v2 to a domain</span></span>

1. <span data-ttu-id="e58ef-211">では、管理コンソールに記号 ([管理者モードとデバイスの管理](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)を参照してください) を考慮します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-211">Sign into the console from the admin account (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="e58ef-212">管理者特権で Powershell コマンド プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-212">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="e58ef-213">Powershell に次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-213">Enter the following command in Powershell:</span></span>
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="e58ef-214">たとえば、完全修飾ドメイン redmond.corp.microsoft.com は、「Skype ルーム システム v2」で、Skype ルーム システム v2 のコンソールが必要な場合は、リソース OU の子 OU の場合は、コマンドになります。</span><span class="sxs-lookup"><span data-stu-id="e58ef-214">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Skype Room Systems v2 consoles to be in a "Skype Room Systems v2" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Skype_Room_System,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="e58ef-215">ドメインに参加させるときに、コンピューターの名前を変更したい場合は、コンピューターの新しい名前の後に、新しい名前のフラグを使用します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-215">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="skype-room-systems-v2-deployment-checklist"></a><span data-ttu-id="e58ef-216">Skype ルーム システム v2 の展開のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="e58ef-216">Skype Room Systems v2 deployment checklist</span></span>
<span data-ttu-id="e58ef-217"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="e58ef-217"></span></span>

<span data-ttu-id="e58ef-218">コンソールとそのすべての周辺機器が完全に構成されている最終的な検証を行う際に、次のチェックリストを使用します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-218">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="e58ef-219">**アプリケーションの設定**</span><span class="sxs-lookup"><span data-stu-id="e58ef-219">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e58ef-220">☐</span><span class="sxs-lookup"><span data-stu-id="e58ef-220">☐</span></span>  <br/> |<span data-ttu-id="e58ef-221">ルーム アカウント名と電話番号 (PSTN が有効な場合) が、コンソール画面の右上に正しく表示される</span><span class="sxs-lookup"><span data-stu-id="e58ef-221">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="e58ef-222">☐</span><span class="sxs-lookup"><span data-stu-id="e58ef-222">☐</span></span>  <br/> |<span data-ttu-id="e58ef-223">Windows コンピューター名が正しく設定されている (リモート管理に役立つ)</span><span class="sxs-lookup"><span data-stu-id="e58ef-223">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="e58ef-224">☐</span><span class="sxs-lookup"><span data-stu-id="e58ef-224">☐</span></span>  <br/> |<span data-ttu-id="e58ef-225">管理者アカウントのパスワードが設定されており、確認済みである</span><span class="sxs-lookup"><span data-stu-id="e58ef-225">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="e58ef-226">☐</span><span class="sxs-lookup"><span data-stu-id="e58ef-226">☐</span></span>  <br/> |<span data-ttu-id="e58ef-227">すべてのファームウェア更新プログラムが適用されています。</span><span class="sxs-lookup"><span data-stu-id="e58ef-227">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="e58ef-228">**オーディオ/ビデオ周辺機器**</span><span class="sxs-lookup"><span data-stu-id="e58ef-228">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e58ef-229">☐</span><span class="sxs-lookup"><span data-stu-id="e58ef-229">☐</span></span>  <br/> |<span data-ttu-id="e58ef-230">カメラ周辺機器のファームウェアのバージョンが正しい (該当する場合)</span><span class="sxs-lookup"><span data-stu-id="e58ef-230">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="e58ef-231">☐</span><span class="sxs-lookup"><span data-stu-id="e58ef-231">☐</span></span>  <br/> |<span data-ttu-id="e58ef-232">カメラの機能と、最適な位置を指定しました。</span><span class="sxs-lookup"><span data-stu-id="e58ef-232">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="e58ef-233">☐</span><span class="sxs-lookup"><span data-stu-id="e58ef-233">☐</span></span>  <br/> |<span data-ttu-id="e58ef-234">既定の再生デバイスと既定の再生通信デバイスの設定が、目的のオーディオ周辺機器に設定されている</span><span class="sxs-lookup"><span data-stu-id="e58ef-234">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="e58ef-235">☐</span><span class="sxs-lookup"><span data-stu-id="e58ef-235">☐</span></span>  <br/> |<span data-ttu-id="e58ef-236">既定の録音通信デバイスの設定が目的のオーディオ周辺機器に設定されている</span><span class="sxs-lookup"><span data-stu-id="e58ef-236">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="e58ef-237">☐</span><span class="sxs-lookup"><span data-stu-id="e58ef-237">☐</span></span>  <br/> |<span data-ttu-id="e58ef-238">オーディオ周辺機器のファームウェアのバージョンが正しい (該当する場合)</span><span class="sxs-lookup"><span data-stu-id="e58ef-238">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="e58ef-239">☐</span><span class="sxs-lookup"><span data-stu-id="e58ef-239">☐</span></span>  <br/> |<span data-ttu-id="e58ef-240">オーディオ入力デバイスが機能し、適切に配置されている</span><span class="sxs-lookup"><span data-stu-id="e58ef-240">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="e58ef-241">☐</span><span class="sxs-lookup"><span data-stu-id="e58ef-241">☐</span></span>  <br/> |<span data-ttu-id="e58ef-242">オーディオ出力デバイスが機能し、適切に配置されている</span><span class="sxs-lookup"><span data-stu-id="e58ef-242">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="e58ef-243">**ドック**</span><span class="sxs-lookup"><span data-stu-id="e58ef-243">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e58ef-244">☐</span><span class="sxs-lookup"><span data-stu-id="e58ef-244">☐</span></span>  <br/> |<span data-ttu-id="e58ef-245">ケーブルが保護されており、圧迫されていない</span><span class="sxs-lookup"><span data-stu-id="e58ef-245">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="e58ef-246">☐</span><span class="sxs-lookup"><span data-stu-id="e58ef-246">☐</span></span>  <br/> |<span data-ttu-id="e58ef-247">HDMI を介したオーディオ インジェストが機能している</span><span class="sxs-lookup"><span data-stu-id="e58ef-247">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="e58ef-248">☐</span><span class="sxs-lookup"><span data-stu-id="e58ef-248">☐</span></span>  <br/> |<span data-ttu-id="e58ef-249">HDMI を介したビデオ インジェストが機能している</span><span class="sxs-lookup"><span data-stu-id="e58ef-249">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="e58ef-250">☐</span><span class="sxs-lookup"><span data-stu-id="e58ef-250">☐</span></span>  <br/> |<span data-ttu-id="e58ef-251">ドックは自由に回転することができる</span><span class="sxs-lookup"><span data-stu-id="e58ef-251">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="e58ef-252">☐</span><span class="sxs-lookup"><span data-stu-id="e58ef-252">☐</span></span>  <br/> |<span data-ttu-id="e58ef-253">表示の明るさが環境に適している</span><span class="sxs-lookup"><span data-stu-id="e58ef-253">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="e58ef-254">この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。</span><span class="sxs-lookup"><span data-stu-id="e58ef-254">See also</span></span>
<span data-ttu-id="e58ef-255"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="e58ef-255"></span></span>

[<span data-ttu-id="e58ef-256">Plan for Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="e58ef-256">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="e58ef-257">Skype Room System バージョン 2 を展開する</span><span class="sxs-lookup"><span data-stu-id="e58ef-257">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="e58ef-258">Skype Room Systems バージョン 2 コンソールを構成する</span><span class="sxs-lookup"><span data-stu-id="e58ef-258">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="e58ef-259">Skype Room Systems バージョン 2 を管理する</span><span class="sxs-lookup"><span data-stu-id="e58ef-259">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)