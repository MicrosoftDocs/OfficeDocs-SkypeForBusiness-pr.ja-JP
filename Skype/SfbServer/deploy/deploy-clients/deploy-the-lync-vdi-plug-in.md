---
title: Skype for Business Server 2015 での Lync VDI プラグインの展開
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: このトピックでは、Skype を使用してリモート仮想デスクトップへの接続中にビジネスの展開手順について説明します。
ms.openlocfilehash: a8f95903f3c06fd953b8d97ba829d4f23e8d72b6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server-2015"></a><span data-ttu-id="4dce4-103">Skype for Business Server 2015 での Lync VDI プラグインの展開</span><span class="sxs-lookup"><span data-stu-id="4dce4-103">Deploy the Lync VDI plug-in with Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4dce4-104">このトピックでは、Skype を使用してリモート仮想デスクトップへの接続中にビジネスの展開手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="4dce4-104">This topic discusses deployment procedures for using Skype for Business while connecting to a remote virtual desktop.</span></span> 
  
<span data-ttu-id="4dce4-105">仮想デスクトップ インフラストラクチャ (VDI) 環境は、非常に高度なセキュリティとコンプライアンスが求められる組織で使用します。</span><span class="sxs-lookup"><span data-stu-id="4dce4-105">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="4dce4-106">ユーザーは、仮想デスクトップのクライアントを使用して、ローカルの Windows コンピューターで作業します。</span><span class="sxs-lookup"><span data-stu-id="4dce4-106">Their users are on local Windows computers and using clients on a virtual desktop.</span></span> <span data-ttu-id="4dce4-107">使用して Skype ビジネスの接続のようなことには、VDI のプラグイン ソフトウェアを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dce4-107">Using Skype for Business on a connection like that requires additional VDI plug-in software.</span></span>
  
<span data-ttu-id="4dce4-108">ある 2 つのソリューションは、VDI のプラグイン コンポーネントでの使用可能ないずれかで提供されているマイクロソフトと Citrix が提供します。</span><span class="sxs-lookup"><span data-stu-id="4dce4-108">There are two solutions available for the VDI plug-in component - one offered by Microsoft and one offered by Citrix.</span></span> <span data-ttu-id="4dce4-109">マイクロソフトでは、新しい環境で新しい HDX リアルタイム最適化パック ソリューションを使用することをお勧めがライフ サイクルの残りの部分の元のプラグインの Lync VDI をサポートするために続行されます。</span><span class="sxs-lookup"><span data-stu-id="4dce4-109">Microsoft recommends using the new HDX RealTime Optimization Pack solution in new deployments but will continue to support the original Lync VDI Plug-in for the remainder of its lifecycle.</span></span> 
  
<span data-ttu-id="4dce4-110">このトピックは、Microsoft Lync VDI プラグインは、Windows 7 と Windows 8 または Windows Server 2008 でのみサポートされ、のみ Lync 2013 または Skype ビジネス 2015年のクライアントをサポートするを展開する方法の詳細を説明します。</span><span class="sxs-lookup"><span data-stu-id="4dce4-110">This topic provides details on deploying the Microsoft Lync VDI plug-in, which is only supported on Windows 7 and Windows 8 or Windows Server 2008, and only supports Lync 2013 or Skype for Business 2015 clients.</span></span> <span data-ttu-id="4dce4-111">このプラグインを更新する予定はありませんが、ビジネスの Skype の[Citrix HDX のリアルタイム最適化パック](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT)は必要に応じて更新されます。</span><span class="sxs-lookup"><span data-stu-id="4dce4-111">There are no plans to update this plugin, but the [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business will be updated as needed.</span></span>
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a><span data-ttu-id="4dce4-112">Lync VDI プラグイン向けに環境を準備する</span><span class="sxs-lookup"><span data-stu-id="4dce4-112">Prepare your environment for the Lync VDI plug-in</span></span>
<span data-ttu-id="4dce4-113"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="4dce4-113"></span></span>

1. <span data-ttu-id="4dce4-114">ビジネス サーバー 2015 の Skype での Lync VDI プラグインのすべてのユーザーの EnableMediaRedirection を TRUE に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4dce4-114">In Skype for Business Server 2015, ensure that EnableMediaRedirection is set to TRUE for all Lync VDI plug-in users.</span></span> <span data-ttu-id="4dce4-115">詳細については、[新規 CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps)コマンドレットと[セット CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dce4-115">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet.</span></span>
    
2. <span data-ttu-id="4dce4-116">データ センターのサーバーでは、ビジネス 2015年クライアントをすべての仮想デスクトップ上の Skype をインストールします。</span><span class="sxs-lookup"><span data-stu-id="4dce4-116">On the data center server, install the Skype for Business 2015 client on all virtual desktops.</span></span>
    
3. <span data-ttu-id="4dce4-117">ローカルのコンピューターでは、Lync VDI のプラグインをインストールします。</span><span class="sxs-lookup"><span data-stu-id="4dce4-117">On the local computers, install the Lync VDI plug-in.</span></span>
    
    <span data-ttu-id="4dce4-118">ここで、ヘッドセットや Web カメラなどのデバイスをローカル コンピューターに接続します。</span><span class="sxs-lookup"><span data-stu-id="4dce4-118">Users should now connect a device like a headset or webcam to their local computer.</span></span>
    
## <a name="configure-remote-desktop-connection-settings"></a><span data-ttu-id="4dce4-119">リモート デスクトップ接続の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="4dce4-119">Configure Remote Desktop Connection settings</span></span>
<span data-ttu-id="4dce4-120"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="4dce4-120"></span></span>

<span data-ttu-id="4dce4-121">プラグインの Lync VDI のリモート デスクトップ接続を準備するには、ローカル コンピューターでは以下の手順を実行。</span><span class="sxs-lookup"><span data-stu-id="4dce4-121">To prepare Remote Desktop Connection for the Lync VDI plug-in, follow these steps on the local computer:</span></span>
  
1. <span data-ttu-id="4dce4-122">ローカル コンピューターが Windows 8 を実行している場合は、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="4dce4-122">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="4dce4-123">ローカル コンピューターでは、SP1 を適用した Windows 7 を実行している場合、は、Windows 8 の最新バージョンの[リモート デスクトップ サービス クライアント](https://go.microsoft.com/fwlink/p/?LinkId=268032)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="4dce4-123">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the [Remote Desktop Services client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span>
    
2. <span data-ttu-id="4dce4-124">[**スタート**]、[**リモート デスクトップ接続**] の順にクリックして、リモート デスクトップ サービス クライアントを起動します。</span><span class="sxs-lookup"><span data-stu-id="4dce4-124">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>
    
3. <span data-ttu-id="4dce4-125">[**オプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dce4-125">Click **Options**.</span></span>
    
4. <span data-ttu-id="4dce4-126">[**ローカル リソース**] タブをクリックします。[**リモート オーディオ**] の下にある [**設定**] をクリックし、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4dce4-126">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
  - <span data-ttu-id="4dce4-127">[**リモート オーディオ再生**] で [**このコンピューターで再生**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4dce4-127">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
  - <span data-ttu-id="4dce4-128">[**リモート オーディオ録音**] で [**録音しない**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4dce4-128">Under **Remote audio recording**, select **Do not record**.</span></span>
    
  - <span data-ttu-id="4dce4-129">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dce4-129">Click **OK**.</span></span>
    
5. <span data-ttu-id="4dce4-130">[**エクスペリエンス**] タブをクリックします。[**パフォーマンス**] で [**ビットマップのキャッシュを保持**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="4dce4-130">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>
    
6. <span data-ttu-id="4dce4-131">[**全般**] タブをクリックします。[**コンピューター**] に仮想マシンの名前を入力し、[**接続**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dce4-131">Click the **General** tab. In **Computer**, type the name of the virtual desktop, and then click **Connect**.</span></span> 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a><span data-ttu-id="4dce4-132">仮想デスクトップにサインインして、Skype for Business を使用します。</span><span class="sxs-lookup"><span data-stu-id="4dce4-132">Sign in and use Skype for Business on the virtual desktop</span></span>
<span data-ttu-id="4dce4-133"><a name="SfB_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="4dce4-133"></span></span>

<span data-ttu-id="4dce4-134">Lync VDI のプラグインを有効にすると、ユーザーによって、仮想デスクトップ上でビジネス 2015年の Skype にサインインするときがこれらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="4dce4-134">After the Lync VDI plug-in is enabled, the user follows these steps when signing in to Skype for Business 2015 on the virtual desktop.</span></span>
  
1. <span data-ttu-id="4dce4-135">ユーザーは、自分の資格情報で仮想デスクトップで実行されているビジネス 2015年クライアントの Skype を入力します。</span><span class="sxs-lookup"><span data-stu-id="4dce4-135">The user types his or her credentials in to the Skype for Business 2015 client running on the virtual desktop.</span></span>
    
2. <span data-ttu-id="4dce4-136">ビジネス 2015年の Skype では、Lync VDI のプラグインが検出され後、Skype ビジネス 2015年の資格情報を再入力するように求めるプロンプトを表示します。</span><span class="sxs-lookup"><span data-stu-id="4dce4-136">After Skype for Business 2015 detects the Lync VDI plug-in, Skype for Business 2015 prompts the user to re-enter the credentials.</span></span> <span data-ttu-id="4dce4-137">このダイアログ ボックスで、ことをお勧めユーザーが**自分のパスワードを保存**] チェック ボックスを選択、必要はありませんそれ以降のサインイン時に資格情報を入力するようにします。</span><span class="sxs-lookup"><span data-stu-id="4dce4-137">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>
    
3. <span data-ttu-id="4dce4-138">ビジネス 2015年の Skype では、Lync VDI のプラグインとのペアリングを開始します。</span><span class="sxs-lookup"><span data-stu-id="4dce4-138">Skype for Business 2015 begins pairing with the Lync VDI plug-in.</span></span> <span data-ttu-id="4dce4-139">発生したときに、クライアントでは、ビジネス 2015年のステータス バーの Skype での 2 つのアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dce4-139">While that happens, the client displays two icons in the Skype for Business 2015 status bar.</span></span> <span data-ttu-id="4dce4-140">左下のアイコンは利用可能なオーディオ デバイスがないことを示し、右下の点滅するアイコンは VDI ペアリングが進行中であることを示します。</span><span class="sxs-lookup"><span data-stu-id="4dce4-140">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that VDI pairing is in progress:</span></span>
    4. <span data-ttu-id="4dce4-141">VDI ペアリングが成功すると、通話に使用されるオーディオ デバイスおよび VDI ペアリングが成功したことを示すアイコンに変わります。</span><span class="sxs-lookup"><span data-stu-id="4dce4-141">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success:</span></span>
    5. <span data-ttu-id="4dce4-142">ユーザーことができます今すぐ参照してください自分のプレゼンス Skype ビジネス 2015年の互換性のあるデバイスは、ローカルのコンピューターに接続し、通話に応答したりいつものようにするため。</span><span class="sxs-lookup"><span data-stu-id="4dce4-142">The user can now see his or her presence on Skype for Business 2015 compatible devices that are connected to the local computer, and place and answer calls as usual.</span></span>
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a><span data-ttu-id="4dce4-143">Lync VDI プラグインのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="4dce4-143">Troubleshoot the Lync VDI plug-in</span></span>
<span data-ttu-id="4dce4-144"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="4dce4-144"></span></span>

<span data-ttu-id="4dce4-145">Lync VDI プラグインのインストール後に問題が発生した場合は、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dce4-145">Refer to the following sections if you encounter issues after installing the Lync VDI plug-in.</span></span>
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a><span data-ttu-id="4dce4-146">Lync VDI プラグインのインストールに関する問題 </span><span class="sxs-lookup"><span data-stu-id="4dce4-146">Issues with installing the Lync VDI Plug-in</span></span>

<span data-ttu-id="4dce4-147">Lync VDI のプラグインをインストールすると問題がある場合は、以下を確認します。</span><span class="sxs-lookup"><span data-stu-id="4dce4-147">If there are issues with installing the Lync VDI plug-in, check the following:</span></span>
  
- <span data-ttu-id="4dce4-148">TEMP および TMP システム変数で指定したフォルダーに十分な容量がある。</span><span class="sxs-lookup"><span data-stu-id="4dce4-148">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>
    
- <span data-ttu-id="4dce4-149">書き込み保護がオフになっている。</span><span class="sxs-lookup"><span data-stu-id="4dce4-149">Ensure that write-protect is turned off.</span></span> <span data-ttu-id="4dce4-150">手順については、デバイスの製造元のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dce4-150">Refer to your device manufacturer's documentation for instructions.</span></span>
    
### <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="4dce4-151">ペアリングに関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="4dce4-151">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="4dce4-152">Lync VDI のプラグインのペアリングが失敗したとき、右下の表示で、赤い"X"として表示されているとのペアリングのアイコン。</span><span class="sxs-lookup"><span data-stu-id="4dce4-152">When Lync VDI plug-in pairing fails, the pairing icon in the lower right displays as a red "X" as shown:</span></span> 
  
<span data-ttu-id="4dce4-153">考えられる失敗の原因と、問題を修正するために行うことのできる対策を、以下に示します。</span><span class="sxs-lookup"><span data-stu-id="4dce4-153">The following are possible reasons for failures and the actions you can take to correct the problem.</span></span> 
  
- <span data-ttu-id="4dce4-154">**ユーザーがサインインの際に入力した資格情報が正しくない。**</span><span class="sxs-lookup"><span data-stu-id="4dce4-154">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="4dce4-155">ユーザーは、ビジネスの Skype からサインアウトして、正しい資格情報でサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dce4-155">The user should sign out of Skype for Business and sign in again with the correct credentials.</span></span> <span data-ttu-id="4dce4-156">ペアリングのダイアログ ボックスが再表示され、ペアリングに成功したかどうかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dce4-156">The pairing dialog box will reappear and show whether pairing is successful.</span></span>
    
- <span data-ttu-id="4dce4-157">**リモート デスクトップ クライアントの別のインスタンスが実行している。**</span><span class="sxs-lookup"><span data-stu-id="4dce4-157">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="4dce4-158">リモート デスクトップ接続を使用して、windows には、ユーザーが、次の操作にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dce4-158">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
1. <span data-ttu-id="4dce4-159">タスク マネージャーを起動します。**Alt+Ctrl+Del** キーを押し、[**タスク マネージャーの起動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dce4-159">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
2. <span data-ttu-id="4dce4-160">[**プロセス**] タブをクリックし、リスト内で **mstsc.exe** という名前のすべてのプロセスを見つけます。</span><span class="sxs-lookup"><span data-stu-id="4dce4-160">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
3. <span data-ttu-id="4dce4-161">各 **mstsc.exe** プロセスを強調表示し、[**プロセスの終了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4dce4-161">Highlight each **mstsc.exe** process and then click **End Process**.</span></span> 
    
4. <span data-ttu-id="4dce4-162">新しいリモート デスクトップ セッションを起動して、もう一度接続してみます。</span><span class="sxs-lookup"><span data-stu-id="4dce4-162">Start a new remote desktop session and try connecting again.</span></span> 
    
- <span data-ttu-id="4dce4-163">**必要なファイルが適切にインストールされていない。**</span><span class="sxs-lookup"><span data-stu-id="4dce4-163">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="4dce4-164">プラグインをローカル コンピューターにインストールしたら、次のファイルが C:\Program Files\Microsoft Office\Office15 (または適切なドライブ文字) にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4dce4-164">After the plug-in is installed on the local computer, check to make sure that these files are present under C:\Program Files\Microsoft Office\Office15 (or the appropriate drive letter):</span></span>
    
  - <span data-ttu-id="4dce4-165">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="4dce4-165">LyncVdiPlugin.dll</span></span>
    
  - <span data-ttu-id="4dce4-166">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="4dce4-166">UcVdi.dll</span></span>
    
- <span data-ttu-id="4dce4-167">**ビジネス 2015年クライアントの Skype は、ローカル コンピューターで行われています。**</span><span class="sxs-lookup"><span data-stu-id="4dce4-167">**The Skype for Business 2015 client is running on the local computer.**</span></span>
    
    <span data-ttu-id="4dce4-168">使用して Lync VDI のプラグインでは、ローカル コンピューター上、Skype ビジネス 2015年のクライアントを実行しないでください、それ以外の場合の組み合わせは失敗します。</span><span class="sxs-lookup"><span data-stu-id="4dce4-168">To use the Lync VDI plug-in, a Skype for Business 2015 client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="4dce4-169">ベスト プラクティスとして、ユーザーは、ローカル コンピューター上、Skype ビジネス 2015年のクライアントをインストールしないでください。</span><span class="sxs-lookup"><span data-stu-id="4dce4-169">As a best practice, the user should not install a Skype for Business 2015 client on the local computer.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4dce4-170">この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。</span><span class="sxs-lookup"><span data-stu-id="4dce4-170">See also</span></span>
<span data-ttu-id="4dce4-171"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="4dce4-171"></span></span>

#### 

[<span data-ttu-id="4dce4-172">VDI 環境でのビジネス用の Skype の計画</span><span class="sxs-lookup"><span data-stu-id="4dce4-172">Plan for Skype for Business in VDI environments</span></span>](../../plan-your-deployment/clients-and-devices/vdi-environments.md)

