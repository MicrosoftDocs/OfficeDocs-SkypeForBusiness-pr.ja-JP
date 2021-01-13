---
title: Skype for Business Server を使用した Lync VDI プラグインの展開
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: このトピックでは、リモート仮想デスクトップへの接続中に Skype for Business を使用するための展開手順について説明します。
ms.openlocfilehash: f7ff99045c861c4435675d9e9e86deaedd499c10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805937"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a><span data-ttu-id="ceb3a-103">Skype for Business Server を使用した Lync VDI プラグインの展開</span><span class="sxs-lookup"><span data-stu-id="ceb3a-103">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>
 
<span data-ttu-id="ceb3a-104">このトピックでは、リモート仮想デスクトップへの接続中に Skype for Business を使用するための展開手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-104">This topic discusses deployment procedures for using Skype for Business while connecting to a remote virtual desktop.</span></span> <span data-ttu-id="ceb3a-105">計画に関する考慮事項については [、VDI 環境での Skype for Business の計画に関する説明を参照してください](../../plan-your-deployment/clients-and-devices/vdi-environments.md)。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-105">Planning considerations are at [Plan for Skype for Business in VDI environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md).</span></span>
  
<span data-ttu-id="ceb3a-106">仮想デスクトップ インフラストラクチャ (VDI) 環境は、セキュリティとコンプライアンスの問題が特に重要である一部の組織で使用されています。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-106">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="ceb3a-107">ユーザーは、ローカル Windows コンピューター上にいて、仮想デスクトップ上のクライアントを使用しています。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-107">Their users are on local Windows computers and using clients on a virtual desktop.</span></span> <span data-ttu-id="ceb3a-108">このような接続で Skype for Business を使用するには、追加の VDI プラグイン ソフトウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-108">Using Skype for Business on a connection like that requires additional VDI plug-in software.</span></span>
  
<span data-ttu-id="ceb3a-109">VDI プラグイン コンポーネントには、Microsoft が提供するソリューションと Citrix が提供するソリューションの 2 つがあります。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-109">There are two solutions available for the VDI plug-in component - one offered by Microsoft and one offered by Citrix.</span></span> <span data-ttu-id="ceb3a-110">Microsoft では、新しい展開で新しい HDX RealTime Optimization Pack ソリューションの使用をお勧めしますが、ライフサイクルの残りの部分では元の Lync VDI プラグインを引き続きサポートします。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-110">Microsoft recommends using the new HDX RealTime Optimization Pack solution in new deployments but will continue to support the original Lync VDI Plug-in for the remainder of its lifecycle.</span></span> 
  
<span data-ttu-id="ceb3a-111">このトピックでは、Windows 7 および Windows 8 または Windows Server 2008 でのみサポートされ、Lync 2013 または Skype for Business クライアントのみをサポートする Microsoft Lync VDI プラグインの展開に関する詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-111">This topic provides details on deploying the Microsoft Lync VDI plug-in, which is only supported on Windows 7 and Windows 8 or Windows Server 2008, and only supports Lync 2013 or Skype for Business clients.</span></span> <span data-ttu-id="ceb3a-112">このプラグインを更新する予定はありません。 [ただし、Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business は必要に応じて更新されます。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-112">There are no plans to update this plugin, but the [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business will be updated as needed.</span></span>
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a><span data-ttu-id="ceb3a-113">Lync VDI プラグインの環境を準備する</span><span class="sxs-lookup"><span data-stu-id="ceb3a-113">Prepare your environment for the Lync VDI plug-in</span></span>
<span data-ttu-id="ceb3a-114"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="ceb3a-114"><a name="Prepare_vdi"> </a></span></span>

1. <span data-ttu-id="ceb3a-115">Skype for Business Server で、すべての Lync VDI プラグイン ユーザーに対して EnableMediaRedirection が TRUE に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-115">In Skype for Business Server, ensure that EnableMediaRedirection is set to TRUE for all Lync VDI plug-in users.</span></span> <span data-ttu-id="ceb3a-116">詳細については [、New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) コマンドレットと [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-116">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet.</span></span>
    
2. <span data-ttu-id="ceb3a-117">データ センター サーバーで、すべての仮想デスクトップに Skype for Business クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-117">On the data center server, install the Skype for Business client on all virtual desktops.</span></span>
    
3. <span data-ttu-id="ceb3a-118">ローカル コンピューターに、Lync VDI プラグインをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-118">On the local computers, install the Lync VDI plug-in.</span></span>
    
    <span data-ttu-id="ceb3a-119">ユーザーは、ヘッドセットや Web カメラのようなデバイスをローカル コンピューターに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-119">Users should now connect a device like a headset or webcam to their local computer.</span></span>
    
## <a name="configure-remote-desktop-connection-settings"></a><span data-ttu-id="ceb3a-120">リモート デスクトップ接続の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="ceb3a-120">Configure Remote Desktop Connection settings</span></span>
<span data-ttu-id="ceb3a-121"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="ceb3a-121"><a name="Prepare_vdi"> </a></span></span>

<span data-ttu-id="ceb3a-122">Lync VDI プラグインのリモート デスクトップ接続を準備するには、ローカル コンピューターで次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-122">To prepare Remote Desktop Connection for the Lync VDI plug-in, follow these steps on the local computer:</span></span>
  
1. <span data-ttu-id="ceb3a-123">ローカル コンピューターがローカル コンピューターを実行しているWindows 8、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-123">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="ceb3a-124">ローカル コンピューターで Windows 7 SP1 を実行している場合は、リモート デスクトップ Windows 8 クライアントの最新バージョン [をインストールします](https://go.microsoft.com/fwlink/p/?LinkId=268032)。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-124">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the [Remote Desktop Services client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span>
    
2. <span data-ttu-id="ceb3a-125">[**スタート**]、[**リモート デスクトップ接続**] の順にクリックして、リモート デスクトップ サービス クライアントを起動します。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-125">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>
    
3. <span data-ttu-id="ceb3a-126">[**オプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-126">Click **Options**.</span></span>
    
4. <span data-ttu-id="ceb3a-127">[**ローカル リソース**] タブをクリックします。[**リモート オーディオ**] の下にある [**設定**] をクリックし、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-127">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
   - <span data-ttu-id="ceb3a-128">[**リモート オーディオ再生**] の下の [**このコンピュータで再生**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-128">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
   - <span data-ttu-id="ceb3a-129">[**リモート オーディオ録音**] の下の [**録音しない**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-129">Under **Remote audio recording**, select **Do not record**.</span></span>
    
   - <span data-ttu-id="ceb3a-130">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-130">Click **OK**.</span></span>
    
5. <span data-ttu-id="ceb3a-131">[**エクスペリエンス**] タブをクリックします。[**パフォーマンス**] の下にある [**ビットマップのキャッシュを保持**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-131">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>
    
6. <span data-ttu-id="ceb3a-132">[全般] **タブをクリック** します。コンピューター **で**、仮想デスクトップの名前を入力し、[接続] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-132">Click the **General** tab. In **Computer**, type the name of the virtual desktop, and then click **Connect**.</span></span> 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a><span data-ttu-id="ceb3a-133">仮想デスクトップでサインインして Skype for Business を使用する</span><span class="sxs-lookup"><span data-stu-id="ceb3a-133">Sign in and use Skype for Business on the virtual desktop</span></span>
<span data-ttu-id="ceb3a-134"><a name="SfB_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="ceb3a-134"><a name="SfB_signin"> </a></span></span>

<span data-ttu-id="ceb3a-135">Lync VDI プラグインを有効にした後、ユーザーは仮想デスクトップで Skype for Business にサインインするときに次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-135">After the Lync VDI plug-in is enabled, the user follows these steps when signing in to Skype for Business on the virtual desktop.</span></span>
  
1. <span data-ttu-id="ceb3a-136">ユーザーは、仮想デスクトップで実行されている Skype for Business クライアントに自分の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-136">The user types his or her credentials in to the Skype for Business client running on the virtual desktop.</span></span>
    
2. <span data-ttu-id="ceb3a-137">Skype for Business が Lync VDI プラグインを検出すると、Skype for Business はユーザーに資格情報の再入力を求めるメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-137">After Skype for Business detects the Lync VDI plug-in, Skype for Business prompts the user to re-enter the credentials.</span></span> <span data-ttu-id="ceb3a-138">このダイアログ ボックスでは、ユーザーが後でサインインする際に資格情報を入力する必要が生じないので、[パスワードを保存する] チェック ボックスをオンにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-138">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>
    
3. <span data-ttu-id="ceb3a-139">Skype for Business は、Lync VDI プラグインとのペアリングを開始します。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-139">Skype for Business begins pairing with the Lync VDI plug-in.</span></span> <span data-ttu-id="ceb3a-140">この場合、クライアントは Skype for Business ステータス バーに 2 つのアイコンを表示します。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-140">While that happens, the client displays two icons in the Skype for Business status bar.</span></span> <span data-ttu-id="ceb3a-141">左下のアイコンは、オーディオ デバイスが使用できない状態を示し、右下の点滅するアイコンは VDI ペアリングが進行中を示します。a.</span><span class="sxs-lookup"><span data-stu-id="ceb3a-141">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that VDI pairing is in progress: a.</span></span> <span data-ttu-id="ceb3a-142">VDI ペアリングが成功すると、アイコンが変更され、呼び出しに使用されるオーディオ デバイスと VDI ペアリングの成功を示します。b.</span><span class="sxs-lookup"><span data-stu-id="ceb3a-142">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success: b.</span></span> <span data-ttu-id="ceb3a-143">これで、ユーザーは、ローカル コンピューターに接続されている Skype for Business 互換デバイスで自分のプレゼンスを確認し、通常どおり通話を行って応答できます。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-143">The user can now see his or her presence on Skype for Business compatible devices that are connected to the local computer, and place and answer calls as usual.</span></span>
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a><span data-ttu-id="ceb3a-144">Lync VDI プラグインのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ceb3a-144">Troubleshoot the Lync VDI plug-in</span></span>
<span data-ttu-id="ceb3a-145"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="ceb3a-145"><a name="tshoot_VDI"> </a></span></span>

<span data-ttu-id="ceb3a-146">Lync VDI プラグインのインストール後に問題が発生した場合は、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-146">Refer to the following sections if you encounter issues after installing the Lync VDI plug-in.</span></span>
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a><span data-ttu-id="ceb3a-147">Lync VDI プラグインのインストールに関する問題</span><span class="sxs-lookup"><span data-stu-id="ceb3a-147">Issues with installing the Lync VDI Plug-in</span></span>

<span data-ttu-id="ceb3a-148">Lync VDI プラグインのインストールに問題がある場合は、次のチェック を行います。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-148">If there are issues with installing the Lync VDI plug-in, check the following:</span></span>
  
- <span data-ttu-id="ceb3a-149">TEMP および TMP システム変数で指定したフォルダーに十分な容量がある。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-149">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>
    
- <span data-ttu-id="ceb3a-150">書き込み保護がオフになっている。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-150">Ensure that write-protect is turned off.</span></span> <span data-ttu-id="ceb3a-151">手順については、デバイスの製造元のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-151">Refer to your device manufacturer's documentation for instructions.</span></span>
    
### <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="ceb3a-152">ペアリングに関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ceb3a-152">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="ceb3a-153">Lync VDI プラグインのペアリングが失敗すると、右下のペアリング アイコンは次のように赤い "X" で表示されます。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-153">When Lync VDI plug-in pairing fails, the pairing icon in the lower right displays as a red "X" as shown:</span></span> 
  
<span data-ttu-id="ceb3a-154">エラーの考えられる原因と、問題を修正するために実行できる操作を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-154">The following are possible reasons for failures and the actions you can take to correct the problem.</span></span> 
  
- <span data-ttu-id="ceb3a-155">**ユーザーがサインインの際に入力した資格情報が正しくない。**</span><span class="sxs-lookup"><span data-stu-id="ceb3a-155">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="ceb3a-156">ユーザーは Skype for Business からサインアウトし、正しい資格情報でもう一度サインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-156">The user should sign out of Skype for Business and sign in again with the correct credentials.</span></span> <span data-ttu-id="ceb3a-157">ペアリングのダイアログ ボックスが再表示され、ペアリングに成功したかどうかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-157">The pairing dialog box will reappear and show whether pairing is successful.</span></span>
    
- <span data-ttu-id="ceb3a-158">**リモート デスクトップ クライアントの別のインスタンスが実行している。**</span><span class="sxs-lookup"><span data-stu-id="ceb3a-158">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="ceb3a-159">Windows でリモート デスクトップ接続を使用している場合、ユーザーは次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-159">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
1. <span data-ttu-id="ceb3a-160">タスク マネージャーを起動します。**Alt+Ctrl+Del** キーを押し、[**タスク マネージャーの起動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-160">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
2. <span data-ttu-id="ceb3a-161">[**プロセス**] タブをクリックし、リスト内で **mstsc.exe** という名前のすべてのプロセスを見つけます。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-161">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
3. <span data-ttu-id="ceb3a-162">各 **mstsc.exe** プロセスを強調表示し、[**プロセスの終了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-162">Highlight each **mstsc.exe** process and then click **End Process**.</span></span> 
    
4. <span data-ttu-id="ceb3a-163">新しいリモート デスクトップ セッションを起動して、再び接続を試みます。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-163">Start a new remote desktop session and try connecting again.</span></span> 
    
- <span data-ttu-id="ceb3a-164">**必要なファイルが適切にインストールされていない。**</span><span class="sxs-lookup"><span data-stu-id="ceb3a-164">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="ceb3a-165">プラグインがローカル コンピューターにインストールされた後、これらのファイルが C:\Program Files\Microsoft Office\Office15 (または適切なドライブ文字) の下に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-165">After the plug-in is installed on the local computer, check to make sure that these files are present under C:\Program Files\Microsoft Office\Office15 (or the appropriate drive letter):</span></span>
    
  - <span data-ttu-id="ceb3a-166">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="ceb3a-166">LyncVdiPlugin.dll</span></span>
    
  - <span data-ttu-id="ceb3a-167">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="ceb3a-167">UcVdi.dll</span></span>
    
- <span data-ttu-id="ceb3a-168">**Skype for Business クライアントがローカル コンピューターで実行されている。**</span><span class="sxs-lookup"><span data-stu-id="ceb3a-168">**The Skype for Business client is running on the local computer.**</span></span>
    
    <span data-ttu-id="ceb3a-169">Lync VDI プラグインを使用するには、Skype for Business クライアントがローカル コンピューターで実行されていない必要があります。実行しないと、ペアリングが失敗します。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-169">To use the Lync VDI plug-in, a Skype for Business client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="ceb3a-170">ベスト プラクティスとして、ユーザーはローカル コンピューターに Skype for Business クライアントをインストールしなけずにしてください。</span><span class="sxs-lookup"><span data-stu-id="ceb3a-170">As a best practice, the user should not install a Skype for Business client on the local computer.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ceb3a-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="ceb3a-171">See also</span></span>
<span data-ttu-id="ceb3a-172"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="ceb3a-172"><a name="tshoot_VDI"> </a></span></span>

[<span data-ttu-id="ceb3a-173">VDI 環境での Skype for Business の計画</span><span class="sxs-lookup"><span data-stu-id="ceb3a-173">Plan for Skype for Business in VDI environments</span></span>](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
