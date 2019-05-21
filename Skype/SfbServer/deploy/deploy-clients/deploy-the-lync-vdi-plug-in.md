---
title: Lync VDI プラグインを Skype for Business Server と共に展開する
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: このトピックでは、リモート仮想デスクトップに接続しているときに Skype for Business を使用するための展開手順について説明します。
ms.openlocfilehash: a3955ac3634dbf52b47b70482772e7302876bf1e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288755"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a><span data-ttu-id="e5d93-103">Lync VDI プラグインを Skype for Business Server と共に展開する</span><span class="sxs-lookup"><span data-stu-id="e5d93-103">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>
 
<span data-ttu-id="e5d93-104">このトピックでは、リモート仮想デスクトップに接続しているときに Skype for Business を使用するための展開手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="e5d93-104">This topic discusses deployment procedures for using Skype for Business while connecting to a remote virtual desktop.</span></span> <span data-ttu-id="e5d93-105">計画の考慮事項は、 [VDI 環境での Skype For business の計画](../../plan-your-deployment/clients-and-devices/vdi-environments.md)に含まれています。</span><span class="sxs-lookup"><span data-stu-id="e5d93-105">Planning considerations are at [Plan for Skype for Business in VDI environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md).</span></span>
  
<span data-ttu-id="e5d93-106">仮想デスクトップ インフラストラクチャ (VDI) 環境は、非常に高度なセキュリティとコンプライアンスが求められる組織で使用します。</span><span class="sxs-lookup"><span data-stu-id="e5d93-106">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="e5d93-107">ユーザーは、仮想デスクトップのクライアントを使用して、ローカルの Windows コンピューターで作業します。</span><span class="sxs-lookup"><span data-stu-id="e5d93-107">Their users are on local Windows computers and using clients on a virtual desktop.</span></span> <span data-ttu-id="e5d93-108">Skype for Business を接続に使用すると、追加の VDI プラグインソフトウェアが必要になります。</span><span class="sxs-lookup"><span data-stu-id="e5d93-108">Using Skype for Business on a connection like that requires additional VDI plug-in software.</span></span>
  
<span data-ttu-id="e5d93-109">VDI プラグインコンポーネントには2つのソリューションがあります。1つは Microsoft が提供しており、もう1つは Citrix によって提供されています。</span><span class="sxs-lookup"><span data-stu-id="e5d93-109">There are two solutions available for the VDI plug-in component - one offered by Microsoft and one offered by Citrix.</span></span> <span data-ttu-id="e5d93-110">Microsoft は、新しい展開で新しい HDX リアルタイム最適化パックソリューションを使用することをお勧めしますが、そのライフサイクルの残りの部分については、引き続き元の Lync VDI プラグインをサポートします。</span><span class="sxs-lookup"><span data-stu-id="e5d93-110">Microsoft recommends using the new HDX RealTime Optimization Pack solution in new deployments but will continue to support the original Lync VDI Plug-in for the remainder of its lifecycle.</span></span> 
  
<span data-ttu-id="e5d93-111">このトピックでは、Microsoft Lync VDI プラグインの展開について詳しく説明します。これは、Windows 7、Windows 8、または Windows Server 2008 でのみサポートされ、Lync 2013 または Skype for Business クライアントでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e5d93-111">This topic provides details on deploying the Microsoft Lync VDI plug-in, which is only supported on Windows 7 and Windows 8 or Windows Server 2008, and only supports Lync 2013 or Skype for Business clients.</span></span> <span data-ttu-id="e5d93-112">このプラグインを更新する予定はありませんが、Skype for Business 用の[CITRIX HDX リアルタイム最適化パック](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT)は必要に応じて更新されます。</span><span class="sxs-lookup"><span data-stu-id="e5d93-112">There are no plans to update this plugin, but the [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business will be updated as needed.</span></span>
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a><span data-ttu-id="e5d93-113">Lync VDI プラグイン向けに環境を準備する</span><span class="sxs-lookup"><span data-stu-id="e5d93-113">Prepare your environment for the Lync VDI plug-in</span></span>
<span data-ttu-id="e5d93-114"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="e5d93-114"></span></span>

1. <span data-ttu-id="e5d93-115">Skype for Business Server で、Lync VDI プラグインのすべてのユーザーに対して EnableMediaRedirection が TRUE に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e5d93-115">In Skype for Business Server, ensure that EnableMediaRedirection is set to TRUE for all Lync VDI plug-in users.</span></span> <span data-ttu-id="e5d93-116">詳細については、「[新しい-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps)コマンドレット」および「 [csclientpolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)コマンドレット」のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5d93-116">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet.</span></span>
    
2. <span data-ttu-id="e5d93-117">データセンターサーバーで、すべての仮想デスクトップに Skype for Business クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e5d93-117">On the data center server, install the Skype for Business client on all virtual desktops.</span></span>
    
3. <span data-ttu-id="e5d93-118">ローカルコンピューターで、Lync VDI プラグインをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e5d93-118">On the local computers, install the Lync VDI plug-in.</span></span>
    
    <span data-ttu-id="e5d93-119">ここで、ヘッドセットや Web カメラなどのデバイスをローカル コンピューターに接続します。</span><span class="sxs-lookup"><span data-stu-id="e5d93-119">Users should now connect a device like a headset or webcam to their local computer.</span></span>
    
## <a name="configure-remote-desktop-connection-settings"></a><span data-ttu-id="e5d93-120">リモート デスクトップ接続の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="e5d93-120">Configure Remote Desktop Connection settings</span></span>
<span data-ttu-id="e5d93-121"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="e5d93-121"></span></span>

<span data-ttu-id="e5d93-122">Lync VDI プラグインのリモートデスクトップ接続を準備するには、ローカルコンピューターで次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e5d93-122">To prepare Remote Desktop Connection for the Lync VDI plug-in, follow these steps on the local computer:</span></span>
  
1. <span data-ttu-id="e5d93-123">ローカルコンピューターで Windows 8 を実行している場合は、この手順をスキップしてください。</span><span class="sxs-lookup"><span data-stu-id="e5d93-123">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="e5d93-124">ローカルコンピューターで Windows 7 SP1 を実行している場合は、最新の Windows 8 バージョンの[リモートデスクトップサービスクライアント](https://go.microsoft.com/fwlink/p/?LinkId=268032)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="e5d93-124">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the [Remote Desktop Services client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span>
    
2. <span data-ttu-id="e5d93-125">[**スタート**]、[**リモート デスクトップ接続**] の順にクリックして、リモート デスクトップ サービス クライアントを起動します。</span><span class="sxs-lookup"><span data-stu-id="e5d93-125">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>
    
3. <span data-ttu-id="e5d93-126">[**オプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5d93-126">Click **Options**.</span></span>
    
4. <span data-ttu-id="e5d93-127">[**ローカル リソース**] タブをクリックします。[**リモート オーディオ**] の下にある [**設定**] をクリックし、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e5d93-127">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
   - <span data-ttu-id="e5d93-128">[**リモート オーディオ再生**] で [**このコンピューターで再生**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5d93-128">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
   - <span data-ttu-id="e5d93-129">[**リモート オーディオ録音**] で [**録音しない**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5d93-129">Under **Remote audio recording**, select **Do not record**.</span></span>
    
   - <span data-ttu-id="e5d93-130">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5d93-130">Click **OK**.</span></span>
    
5. <span data-ttu-id="e5d93-131">[**エクスペリエンス**] タブをクリックします。[**パフォーマンス**] で [**ビットマップのキャッシュを保持**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="e5d93-131">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>
    
6. <span data-ttu-id="e5d93-132">[**全般**] タブをクリックします。[**コンピューター**] に仮想マシンの名前を入力し、[**接続**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5d93-132">Click the **General** tab. In **Computer**, type the name of the virtual desktop, and then click **Connect**.</span></span> 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a><span data-ttu-id="e5d93-133">仮想デスクトップにサインインして、Skype for Business を使用します。</span><span class="sxs-lookup"><span data-stu-id="e5d93-133">Sign in and use Skype for Business on the virtual desktop</span></span>
<span data-ttu-id="e5d93-134"><a name="SfB_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="e5d93-134"></span></span>

<span data-ttu-id="e5d93-135">Lync VDI プラグインを有効にすると、ユーザーは仮想デスクトップで Skype for Business にサインインするときに次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e5d93-135">After the Lync VDI plug-in is enabled, the user follows these steps when signing in to Skype for Business on the virtual desktop.</span></span>
  
1. <span data-ttu-id="e5d93-136">ユーザーは、仮想デスクトップで実行されている Skype for Business クライアントに自分の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e5d93-136">The user types his or her credentials in to the Skype for Business client running on the virtual desktop.</span></span>
    
2. <span data-ttu-id="e5d93-137">Skype for Business が Lync VDI プラグインを検出した後、Skype for Business は資格情報を再入力するようにユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="e5d93-137">After Skype for Business detects the Lync VDI plug-in, Skype for Business prompts the user to re-enter the credentials.</span></span> <span data-ttu-id="e5d93-138">このダイアログボックスでは、ユーザーが [**パスワードを保存**する] チェックボックスをオンにして、以降のサインインで資格情報を入力する必要がないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e5d93-138">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>
    
3. <span data-ttu-id="e5d93-139">Skype for Business は、Lync VDI プラグインとのペアリングを開始します。</span><span class="sxs-lookup"><span data-stu-id="e5d93-139">Skype for Business begins pairing with the Lync VDI plug-in.</span></span> <span data-ttu-id="e5d93-140">この場合、クライアントは、Skype for Business のステータスバーに2つのアイコンを表示します。</span><span class="sxs-lookup"><span data-stu-id="e5d93-140">While that happens, the client displays two icons in the Skype for Business status bar.</span></span> <span data-ttu-id="e5d93-141">左下のアイコンは、オーディオデバイスが利用できないことを示し、右下の点滅するアイコンは、VDI ペアリングが進行中であることを示します。</span><span class="sxs-lookup"><span data-stu-id="e5d93-141">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that VDI pairing is in progress: a.</span></span> <span data-ttu-id="e5d93-142">VDI ペアリングが成功すると、そのアイコンが、通話に使用するオーディオデバイスと VDI ペアリング成功: b を示すように変更されます。</span><span class="sxs-lookup"><span data-stu-id="e5d93-142">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success: b.</span></span> <span data-ttu-id="e5d93-143">ユーザーは、ローカルコンピューターに接続されている Skype for Business 互換デバイスで自分のプレゼンスを確認できるようになりました。また、通常通りに通話を発信して応答することができます。</span><span class="sxs-lookup"><span data-stu-id="e5d93-143">The user can now see his or her presence on Skype for Business compatible devices that are connected to the local computer, and place and answer calls as usual.</span></span>
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a><span data-ttu-id="e5d93-144">Lync VDI プラグインのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="e5d93-144">Troubleshoot the Lync VDI plug-in</span></span>
<span data-ttu-id="e5d93-145"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="e5d93-145"></span></span>

<span data-ttu-id="e5d93-146">Lync VDI プラグインのインストール後に問題が発生した場合は、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5d93-146">Refer to the following sections if you encounter issues after installing the Lync VDI plug-in.</span></span>
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a><span data-ttu-id="e5d93-147">Lync VDI プラグインのインストールに関する問題 </span><span class="sxs-lookup"><span data-stu-id="e5d93-147">Issues with installing the Lync VDI Plug-in</span></span>

<span data-ttu-id="e5d93-148">Lync VDI プラグインのインストールで問題が発生した場合は、次の点を確認してください。</span><span class="sxs-lookup"><span data-stu-id="e5d93-148">If there are issues with installing the Lync VDI plug-in, check the following:</span></span>
  
- <span data-ttu-id="e5d93-149">TEMP および TMP システム変数で指定したフォルダーに十分な容量がある。</span><span class="sxs-lookup"><span data-stu-id="e5d93-149">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>
    
- <span data-ttu-id="e5d93-150">書き込み保護がオフになっている。</span><span class="sxs-lookup"><span data-stu-id="e5d93-150">Ensure that write-protect is turned off.</span></span> <span data-ttu-id="e5d93-151">手順については、お使いのデバイスの製造元のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5d93-151">Refer to your device manufacturer's documentation for instructions.</span></span>
    
### <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="e5d93-152">ペアリングに関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="e5d93-152">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="e5d93-153">Lync VDI プラグインのペアリングに失敗した場合、右下のペアリングアイコンは、次のように赤い "X" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5d93-153">When Lync VDI plug-in pairing fails, the pairing icon in the lower right displays as a red "X" as shown:</span></span> 
  
<span data-ttu-id="e5d93-154">考えられる失敗の原因と、問題を修正するために行うことのできる対策を、以下に示します。</span><span class="sxs-lookup"><span data-stu-id="e5d93-154">The following are possible reasons for failures and the actions you can take to correct the problem.</span></span> 
  
- <span data-ttu-id="e5d93-155">**ユーザーがサインインの際に入力した資格情報が正しくない。**</span><span class="sxs-lookup"><span data-stu-id="e5d93-155">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="e5d93-156">ユーザーは、Skype for Business からサインアウトし、正しい資格情報を使用してもう一度サインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5d93-156">The user should sign out of Skype for Business and sign in again with the correct credentials.</span></span> <span data-ttu-id="e5d93-157">ペアリングのダイアログ ボックスが再表示され、ペアリングに成功したかどうかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5d93-157">The pairing dialog box will reappear and show whether pairing is successful.</span></span>
    
- <span data-ttu-id="e5d93-158">**リモート デスクトップ クライアントの別のインスタンスが実行している。**</span><span class="sxs-lookup"><span data-stu-id="e5d93-158">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="e5d93-159">Windows でリモートデスクトップ接続を使用している場合、ユーザーは次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5d93-159">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
1. <span data-ttu-id="e5d93-160">タスク マネージャーを起動します。**Alt+Ctrl+Del** キーを押し、[**タスク マネージャーの起動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5d93-160">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
2. <span data-ttu-id="e5d93-161">[**プロセス**] タブをクリックし、リスト内で **mstsc.exe** という名前のすべてのプロセスを見つけます。</span><span class="sxs-lookup"><span data-stu-id="e5d93-161">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
3. <span data-ttu-id="e5d93-162">各 **mstsc.exe** プロセスを強調表示し、[**プロセスの終了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5d93-162">Highlight each **mstsc.exe** process and then click **End Process**.</span></span> 
    
4. <span data-ttu-id="e5d93-163">新しいリモート デスクトップ セッションを起動して、もう一度接続してみます。</span><span class="sxs-lookup"><span data-stu-id="e5d93-163">Start a new remote desktop session and try connecting again.</span></span> 
    
- <span data-ttu-id="e5d93-164">**必要なファイルが適切にインストールされていない。**</span><span class="sxs-lookup"><span data-stu-id="e5d93-164">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="e5d93-165">プラグインをローカル コンピューターにインストールしたら、次のファイルが C:\Program Files\Microsoft Office\Office15 (または適切なドライブ文字) にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e5d93-165">After the plug-in is installed on the local computer, check to make sure that these files are present under C:\Program Files\Microsoft Office\Office15 (or the appropriate drive letter):</span></span>
    
  - <span data-ttu-id="e5d93-166">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="e5d93-166">LyncVdiPlugin.dll</span></span>
    
  - <span data-ttu-id="e5d93-167">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="e5d93-167">UcVdi.dll</span></span>
    
- <span data-ttu-id="e5d93-168">**Skype for Business クライアントはローカルコンピューターで実行されています。**</span><span class="sxs-lookup"><span data-stu-id="e5d93-168">**The Skype for Business client is running on the local computer.**</span></span>
    
    <span data-ttu-id="e5d93-169">Lync VDI プラグインを使用するには、ローカルコンピューターで Skype for Business クライアントを実行している必要があります。そうでないと、ペアリングは失敗します。</span><span class="sxs-lookup"><span data-stu-id="e5d93-169">To use the Lync VDI plug-in, a Skype for Business client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="e5d93-170">ベストプラクティスとして、ユーザーはローカルコンピューターに Skype for Business クライアントをインストールしないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5d93-170">As a best practice, the user should not install a Skype for Business client on the local computer.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e5d93-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5d93-171">See also</span></span>
<span data-ttu-id="e5d93-172"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="e5d93-172"></span></span>

[<span data-ttu-id="e5d93-173">Plan for Skype for Business in VDI environments</span><span class="sxs-lookup"><span data-stu-id="e5d93-173">Plan for Skype for Business in VDI environments</span></span>](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
