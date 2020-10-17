---
title: 'Lync Server 2013: Lync PreCall Diagnostics Tool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync PreCall Diagnostics Tool
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn451255(v=OCS.15)
ms:contentKeyID: 56708404
ms.date: 11/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19051eb183dc12f091de0d90ebb707bc6cee8fc5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525154"
---
# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a><span data-ttu-id="e131f-102">Lync PreCall Diagnostics Tool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e131f-102">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e131f-103">_**トピックの最終更新日:** 2016-11-04_</span><span class="sxs-lookup"><span data-stu-id="e131f-103">_**Topic Last Modified:** 2016-11-04_</span></span>

<span data-ttu-id="e131f-104">Lync PreCall Diagnostics Tool (PCD) はクライアントベースのアプリケーションで、これにより、ネットワークの現在の状態が今後のエンタープライズ Voip 通話の音声品質にどのように影響するかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e131f-104">The Lync PreCall Diagnostics Tool (PCD) is a client-based application that allows you to see how the current state of your network might impact the audio quality in an upcoming Enterprise Voice call.</span></span>

<span data-ttu-id="e131f-105">PCD は、ネットワークの最後のホップが脆弱になる可能性がある状況 (たとえば、公共の WiFi ネットワークやホームユーザーのラップトップを使用している場合) に最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e131f-105">PCD is most useful in situations where the last hop of a network is likely to be the weakest (for example, with laptops on a public WiFi network or home users).</span></span> <span data-ttu-id="e131f-106">PCD は、ネットワークの最終区間を通過する小さなパケットストリームを作成します。</span><span class="sxs-lookup"><span data-stu-id="e131f-106">PCD creates a small packet stream that traverses this final leg of the network.</span></span> <span data-ttu-id="e131f-107">次に、このツールは、パケットストリームを分析して、このレッグによるジッターと損失が通話品質にどのように影響するかを予測し、レポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="e131f-107">The tool then analyzes the packet stream to estimate how the jitter and loss along this leg might impact call quality, and then provides a report.</span></span> <span data-ttu-id="e131f-108">通話が配置されている場合でも、PCD をクライアント上で継続的に実行することができます。</span><span class="sxs-lookup"><span data-stu-id="e131f-108">You can run PCD continuously on the client, even while calls are being placed.</span></span> <span data-ttu-id="e131f-109">パケットストリームは、帯域幅に大きな影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="e131f-109">The packet stream does not have a significant effect on bandwidth.</span></span>

<span data-ttu-id="e131f-110">**PCD バージョン1.1 の最新リリースには、次の機能拡張が含まれています。**</span><span class="sxs-lookup"><span data-stu-id="e131f-110">**The latest release of the PCD, version 1.1, includes the following enhancements:**</span></span>

  - <span data-ttu-id="e131f-111">長いパスワードのサポート。これで、最大127文字にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e131f-111">Support for longer passwords, which can now be up to 127 characters</span></span>

  - <span data-ttu-id="e131f-112">認証サインインの問題に関するその他の診断</span><span class="sxs-lookup"><span data-stu-id="e131f-112">Additional diagnostics for authentication sign-in issues</span></span>

  - <span data-ttu-id="e131f-113">Lync ハイブリッド展開のサポートの向上</span><span class="sxs-lookup"><span data-stu-id="e131f-113">Better support for Lync hybrid deployments</span></span>

  - <span data-ttu-id="e131f-114">資格情報選択の更新</span><span class="sxs-lookup"><span data-stu-id="e131f-114">Updates to credential picker</span></span>

  - <span data-ttu-id="e131f-115">安定性の向上</span><span class="sxs-lookup"><span data-stu-id="e131f-115">Stability improvements</span></span>

<span data-ttu-id="e131f-116">フィードバックは歓迎します。</span><span class="sxs-lookup"><span data-stu-id="e131f-116">We appreciate any feedback.</span></span> <span data-ttu-id="e131f-117">すべてのサポートの質問または問題を [PCD フィードバック](mailto:pcdfb@microsoft.com) エイリアスに送信してください <pcdfb@microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="e131f-117">Please send all support questions or issues to the [PCD Feedback](mailto:pcdfb@microsoft.com) alias at <pcdfb@microsoft.com>.</span></span>

<span data-ttu-id="e131f-118">このトピックには、以下のセクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e131f-118">This topic includes the following sections:</span></span>

  - <span data-ttu-id="e131f-119">Lync PCD のバージョン</span><span class="sxs-lookup"><span data-stu-id="e131f-119">Lync PCD Versions</span></span>

  - <span data-ttu-id="e131f-120">Lync PCD のシステム要件</span><span class="sxs-lookup"><span data-stu-id="e131f-120">Lync PCD System Requirements</span></span>

  - <span data-ttu-id="e131f-121">Lync PCD の機能</span><span class="sxs-lookup"><span data-stu-id="e131f-121">Lync PCD Features</span></span>

  - <span data-ttu-id="e131f-122">Lync PCD を実行する</span><span class="sxs-lookup"><span data-stu-id="e131f-122">Running Lync PCD</span></span>

  - <span data-ttu-id="e131f-123">Lync PCD のアンインストール</span><span class="sxs-lookup"><span data-stu-id="e131f-123">Uninstalling Lync PCD</span></span>

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a><span data-ttu-id="e131f-124">Lync PCD のバージョン</span><span class="sxs-lookup"><span data-stu-id="e131f-124">Lync PCD Versions</span></span>

<span data-ttu-id="e131f-125">このトピックでは、無料でダウンロードできる、次のバージョンのツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e131f-125">This topic describes the following versions of the tool, available for free download:</span></span>

  - <span data-ttu-id="e131f-126">Windows デスクトップアプリ ( [https://go.microsoft.com/fwlink/?LinkId=327914](https://go.microsoft.com/fwlink/p/?linkid=327914) )</span><span class="sxs-lookup"><span data-stu-id="e131f-126">Windows Desktop App ([https://go.microsoft.com/fwlink/?LinkId=327914](https://go.microsoft.com/fwlink/p/?linkid=327914))</span></span>

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a><span data-ttu-id="e131f-127">Lync PCD のシステム要件</span><span class="sxs-lookup"><span data-stu-id="e131f-127">Lync PCD System Requirements</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e131f-128">PCD では、Lync Server 展開のモバイルクライアントをサポートするように統合コミュニケーション Web API (UCWA) がインストールおよび構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e131f-128">PCD requires that Unified Communications Web API (UCWA) be installed and configured to support mobile clients in the Lync Server deployment.</span></span> <span data-ttu-id="e131f-129">UCWA は Lync Server と共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e131f-129">UCWA is installed with Lync Server.</span></span>



</div>

<div>

## <a name="windows-desktop-app-requirements"></a><span data-ttu-id="e131f-130">Windows デスクトップアプリの要件</span><span class="sxs-lookup"><span data-stu-id="e131f-130">Windows Desktop App Requirements</span></span>

  - <span data-ttu-id="e131f-131">Windows 7 または Windows 8 オペレーティングシステムのすべてのエディション</span><span class="sxs-lookup"><span data-stu-id="e131f-131">Any edition of the Windows 7 or Windows 8 operating system</span></span>

  - <span data-ttu-id="e131f-132">Microsoft .NET Framework 4.5 で利用可能 [https://go.microsoft.com/fwlink/?LinkId=327790](https://go.microsoft.com/fwlink/p/?linkid=327790)</span><span class="sxs-lookup"><span data-stu-id="e131f-132">Microsoft .NET Framework 4.5 available at [https://go.microsoft.com/fwlink/?LinkId=327790](https://go.microsoft.com/fwlink/p/?linkid=327790)</span></span>

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a><span data-ttu-id="e131f-133">Lync PCD の機能</span><span class="sxs-lookup"><span data-stu-id="e131f-133">Lync PCD Features</span></span>

<span data-ttu-id="e131f-134">Lync PCD には、次の機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e131f-134">Lync PCD includes the following features:</span></span>

  - <span data-ttu-id="e131f-135">必要に応じて既定で実行する (2 分のバースト)</span><span class="sxs-lookup"><span data-stu-id="e131f-135">Run in default On Demand (2 minute bursts)</span></span>

  - <span data-ttu-id="e131f-136">Always On で実行 (スナップビューで最大24時間) モード</span><span class="sxs-lookup"><span data-stu-id="e131f-136">Run in Always On (up to 24 hours in snapped view) mode</span></span>

  - <span data-ttu-id="e131f-137">テストの実行の履歴ビュー</span><span class="sxs-lookup"><span data-stu-id="e131f-137">Historical view of your test runs</span></span>

  - <span data-ttu-id="e131f-138">サインインの失敗を診断する (Lync PCD for Windows 8 のみ)</span><span class="sxs-lookup"><span data-stu-id="e131f-138">Diagnose sign-in failures (Lync PCD for Windows 8 only)</span></span>

<span data-ttu-id="e131f-139">![Lync PCD の機能サインインの進行状況を示すスクリーンショット](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD の機能サインインの進行状況を示すスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="e131f-139">![Lync PCD features Sign in progress screen shot](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD features Sign in progress screen shot")</span></span>

  - <span data-ttu-id="e131f-140">ネットワーク指標のグラフィカルな表示–ネットワーク MOS、パケット損失、および全画面表示およびスナップビューでの着荷のジッター。</span><span class="sxs-lookup"><span data-stu-id="e131f-140">Graphical view of network metrics – Network MOS, Packet Loss and Interarrival Jitter in full screen and snapped view.</span></span>

<span data-ttu-id="e131f-141">**全画面表示**</span><span class="sxs-lookup"><span data-stu-id="e131f-141">**Full screen view**</span></span>

<span data-ttu-id="e131f-142">![PreCall 診断ツールのテスト結果グラフ](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall 診断ツールのテスト結果グラフ")</span><span class="sxs-lookup"><span data-stu-id="e131f-142">![PreCall Diagnostic Tool test result graphs](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall Diagnostic Tool test result graphs")</span></span>

<span data-ttu-id="e131f-143">**スナップビュー**</span><span class="sxs-lookup"><span data-stu-id="e131f-143">**Snapped view**</span></span>

<span data-ttu-id="e131f-144">![PreCall 診断ツールの使用テスト結果](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall 診断ツールの使用テスト結果")</span><span class="sxs-lookup"><span data-stu-id="e131f-144">![PreCall Diagnostic Tool Utilization test results](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall Diagnostic Tool Utilization test results")</span></span>

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a><span data-ttu-id="e131f-145">Lync PCD を実行する</span><span class="sxs-lookup"><span data-stu-id="e131f-145">Running Lync PCD</span></span>

<div>

## <a name="running-windows-desktop-app"></a><span data-ttu-id="e131f-146">Windows デスクトップアプリを実行する</span><span class="sxs-lookup"><span data-stu-id="e131f-146">Running Windows Desktop App</span></span>

1.  <span data-ttu-id="e131f-147">Windows 7 システム上で PCD を開始するには、[**スタート**] メニューから [ **precall Diagnostics** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e131f-147">To start the PCD on a Windows 7 system, select **PreCall Diagnostics** from the **Start** menu.</span></span>
    
    <span data-ttu-id="e131f-148">Windows 8 システム上で PCD を開始するには、スタート画面でアイコンを選択するか、または "PreCall Diagnostics" を検索します。</span><span class="sxs-lookup"><span data-stu-id="e131f-148">To start the PCD on a Windows 8 system, select the icon on your Start screen, or search for “PreCall Diagnostics.”</span></span>
    
    <span data-ttu-id="e131f-149">![PreCall 診断ツールアイコン](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall 診断ツールアイコン")</span><span class="sxs-lookup"><span data-stu-id="e131f-149">![PreCall Diagnostic tool icon](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall Diagnostic tool icon")</span></span>

2.  <span data-ttu-id="e131f-150">ツールが起動したら、資格情報を提供するために推奨される方法を選択し、[ **すべての診断ツールオプション** ] ダイアログボックスでネットワーク動作モードを選択して、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e131f-150">When the tool starts, select your preferred method of providing credentials and select the network operating mode in the **PreCall Diagnostics Tool Options** dialog box, then select **OK**:</span></span>

3.  <span data-ttu-id="e131f-151">[ **テストの開始** ] ボタンを選択して、診断の実行を開始します。</span><span class="sxs-lookup"><span data-stu-id="e131f-151">Select the **Start Test** button to start running diagnostics.</span></span>
    
    <span data-ttu-id="e131f-152">[ **ネットワーク資格情報を使用** する] オプションを選択した場合、テストはすぐに開始されます。</span><span class="sxs-lookup"><span data-stu-id="e131f-152">If you selected the **Use network credentials** option, the test begins immediately.</span></span>
    
    <span data-ttu-id="e131f-153">**[資格情報を入力**する] オプションを選択した場合は、[ **Windows セキュリティ**] ダイアログボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="e131f-153">If you selected the **Let me enter my credentials** option, the **Windows Security** dialog box opens.</span></span> <span data-ttu-id="e131f-154">資格情報を入力すると、テストが開始されます。</span><span class="sxs-lookup"><span data-stu-id="e131f-154">After you enter your credentials, the test starts.</span></span>

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a><span data-ttu-id="e131f-155">Lync PCD のアンインストール</span><span class="sxs-lookup"><span data-stu-id="e131f-155">Uninstalling Lync PCD</span></span>

<span data-ttu-id="e131f-156">Lync PCD を削除するには、オペレーティングシステムの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e131f-156">To remove Lync PCD, follow the procedure for your operating system:</span></span>

  - <span data-ttu-id="e131f-157">Windows 7 システムで、[ **コントロールパネル**] を開き、[ **プログラムと機能**] を選択して、[ **Lync 2013 precall Diagnostics**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="e131f-157">On a Windows 7 system, open the **Control Panel**, select **Programs and Features**, and double-click **Lync 2013 PreCall Diagnostics**.</span></span>

  - <span data-ttu-id="e131f-158">Windows 8 システムで、PCD タイルを右クリックし、スタート画面の下部にあるアプリバーから [ **アンインストール** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e131f-158">On a Windows 8 system, right-click on the PCD tile and click **Uninstall** from the app bar at the bottom of the start screen.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

