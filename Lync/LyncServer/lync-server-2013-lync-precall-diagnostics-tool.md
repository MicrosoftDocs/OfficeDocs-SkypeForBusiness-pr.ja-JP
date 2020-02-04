---
title: 'Lync Server 2013: Lync PreCall ツール'
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
ms.openlocfilehash: 004d3b30dc2c2886eb7a2d8977f1da062277cc92
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742337"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a><span data-ttu-id="7d44d-102">Lync の PreCall のすべての診断ツール (Lync Server 2013)</span><span class="sxs-lookup"><span data-stu-id="7d44d-102">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d44d-103">_**最終更新日:** 2016-11-04_</span><span class="sxs-lookup"><span data-stu-id="7d44d-103">_**Topic Last Modified:** 2016-11-04_</span></span>

<span data-ttu-id="7d44d-104">Lync PreCall Diagnostics ツール (PCD) はクライアントベースのアプリケーションであり、ネットワークの現在の状態が、今後のエンタープライズ音声通話での音声品質にどのように影響するかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="7d44d-104">The Lync PreCall Diagnostics Tool (PCD) is a client-based application that allows you to see how the current state of your network might impact the audio quality in an upcoming Enterprise Voice call.</span></span>

<span data-ttu-id="7d44d-105">PCD は、ネットワークの最後のホップが脆弱である可能性が高い場合 (たとえば、公共の WiFi ネットワークまたはホームユーザーのノート pc など) に最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7d44d-105">PCD is most useful in situations where the last hop of a network is likely to be the weakest (for example, with laptops on a public WiFi network or home users).</span></span> <span data-ttu-id="7d44d-106">PCD は、ネットワークのこの最終区間を走査する小さなパケットストリームを作成します。</span><span class="sxs-lookup"><span data-stu-id="7d44d-106">PCD creates a small packet stream that traverses this final leg of the network.</span></span> <span data-ttu-id="7d44d-107">このツールは、パケットストリームを分析して、この区間でのジッターと損失が通話品質にどのように影響するかを予測し、レポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="7d44d-107">The tool then analyzes the packet stream to estimate how the jitter and loss along this leg might impact call quality, and then provides a report.</span></span> <span data-ttu-id="7d44d-108">PCD は、通話が行われているときでも、クライアントで継続的に実行できます。</span><span class="sxs-lookup"><span data-stu-id="7d44d-108">You can run PCD continuously on the client, even while calls are being placed.</span></span> <span data-ttu-id="7d44d-109">パケットストリームは、帯域幅に大きな影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="7d44d-109">The packet stream does not have a significant effect on bandwidth.</span></span>

<span data-ttu-id="7d44d-110">**PCD バージョン1.1 の最新のリリースには、次の機能強化が含まれています。**</span><span class="sxs-lookup"><span data-stu-id="7d44d-110">**The latest release of the PCD, version 1.1, includes the following enhancements:**</span></span>

  - <span data-ttu-id="7d44d-111">長いパスワードをサポートし、最大127文字まで使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="7d44d-111">Support for longer passwords, which can now be up to 127 characters</span></span>

  - <span data-ttu-id="7d44d-112">認証サインインの問題に関する追加診断</span><span class="sxs-lookup"><span data-stu-id="7d44d-112">Additional diagnostics for authentication sign-in issues</span></span>

  - <span data-ttu-id="7d44d-113">Lync ハイブリッド展開のサポートが向上</span><span class="sxs-lookup"><span data-stu-id="7d44d-113">Better support for Lync hybrid deployments</span></span>

  - <span data-ttu-id="7d44d-114">資格情報ピッカーの更新</span><span class="sxs-lookup"><span data-stu-id="7d44d-114">Updates to credential picker</span></span>

  - <span data-ttu-id="7d44d-115">安定性の向上</span><span class="sxs-lookup"><span data-stu-id="7d44d-115">Stability improvements</span></span>

<span data-ttu-id="7d44d-116">ご意見をお寄せいただき、ありがとうございます。</span><span class="sxs-lookup"><span data-stu-id="7d44d-116">We appreciate any feedback.</span></span> <span data-ttu-id="7d44d-117">すべてのサポート質問または問題を[PCD のフィードバック](mailto:pcdfb@microsoft.com)エイリアスに<pcdfb@microsoft.com>送信してください。</span><span class="sxs-lookup"><span data-stu-id="7d44d-117">Please send all support questions or issues to the [PCD Feedback](mailto:pcdfb@microsoft.com) alias at <pcdfb@microsoft.com>.</span></span>

<span data-ttu-id="7d44d-118">このトピックには次のセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="7d44d-118">This topic includes the following sections:</span></span>

  - <span data-ttu-id="7d44d-119">Lync PCD のバージョン</span><span class="sxs-lookup"><span data-stu-id="7d44d-119">Lync PCD Versions</span></span>

  - <span data-ttu-id="7d44d-120">Lync PCD システム要件</span><span class="sxs-lookup"><span data-stu-id="7d44d-120">Lync PCD System Requirements</span></span>

  - <span data-ttu-id="7d44d-121">Lync PCD の機能</span><span class="sxs-lookup"><span data-stu-id="7d44d-121">Lync PCD Features</span></span>

  - <span data-ttu-id="7d44d-122">Lync PCD を実行する</span><span class="sxs-lookup"><span data-stu-id="7d44d-122">Running Lync PCD</span></span>

  - <span data-ttu-id="7d44d-123">Lync PCD をアンインストールする</span><span class="sxs-lookup"><span data-stu-id="7d44d-123">Uninstalling Lync PCD</span></span>

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a><span data-ttu-id="7d44d-124">Lync PCD のバージョン</span><span class="sxs-lookup"><span data-stu-id="7d44d-124">Lync PCD Versions</span></span>

<span data-ttu-id="7d44d-125">このトピックでは、無料でダウンロードできるツールの次のバージョンについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7d44d-125">This topic describes the following versions of the tool, available for free download:</span></span>

  - <span data-ttu-id="7d44d-126">Windows デスクトップアプリ ([http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914))</span><span class="sxs-lookup"><span data-stu-id="7d44d-126">Windows Desktop App ([http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914))</span></span>

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a><span data-ttu-id="7d44d-127">Lync PCD システム要件</span><span class="sxs-lookup"><span data-stu-id="7d44d-127">Lync PCD System Requirements</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7d44d-128">PCD をご利用になるには、ユニファイドコミュニケーション Web API (UCWA) をインストールして、Lync Server の展開でモバイルクライアントをサポートするように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d44d-128">PCD requires that Unified Communications Web API (UCWA) be installed and configured to support mobile clients in the Lync Server deployment.</span></span> <span data-ttu-id="7d44d-129">UCWA は Lync Server と共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="7d44d-129">UCWA is installed with Lync Server.</span></span>



</div>

<div>

## <a name="windows-desktop-app-requirements"></a><span data-ttu-id="7d44d-130">Windows デスクトップアプリの要件</span><span class="sxs-lookup"><span data-stu-id="7d44d-130">Windows Desktop App Requirements</span></span>

  - <span data-ttu-id="7d44d-131">Windows 7 または Windows 8 オペレーティングシステムの任意のエディション</span><span class="sxs-lookup"><span data-stu-id="7d44d-131">Any edition of the Windows 7 or Windows 8 operating system</span></span>

  - <span data-ttu-id="7d44d-132">Microsoft .NET Framework 4.5 は、で入手できます。[http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)</span><span class="sxs-lookup"><span data-stu-id="7d44d-132">Microsoft .NET Framework 4.5 available at [http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)</span></span>

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a><span data-ttu-id="7d44d-133">Lync PCD の機能</span><span class="sxs-lookup"><span data-stu-id="7d44d-133">Lync PCD Features</span></span>

<span data-ttu-id="7d44d-134">Lync PCD には、次の機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7d44d-134">Lync PCD includes the following features:</span></span>

  - <span data-ttu-id="7d44d-135">既定ではオンデマンドで実行する (2 分バースト)</span><span class="sxs-lookup"><span data-stu-id="7d44d-135">Run in default On Demand (2 minute bursts)</span></span>

  - <span data-ttu-id="7d44d-136">Always On (スナップビューで最大24時間) モードで実行する</span><span class="sxs-lookup"><span data-stu-id="7d44d-136">Run in Always On (up to 24 hours in snapped view) mode</span></span>

  - <span data-ttu-id="7d44d-137">テストの実行の履歴ビュー</span><span class="sxs-lookup"><span data-stu-id="7d44d-137">Historical view of your test runs</span></span>

  - <span data-ttu-id="7d44d-138">サインインエラーの診断 (Windows 8 向け Lync PCD)</span><span class="sxs-lookup"><span data-stu-id="7d44d-138">Diagnose sign-in failures (Lync PCD for Windows 8 only)</span></span>

<span data-ttu-id="7d44d-139">![Lync PCD 機能のサインインの進行状況を示すスクリーンショット](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD 機能のサインインの進行状況を示すスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="7d44d-139">![Lync PCD features Sign in progress screen shot](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD features Sign in progress screen shot")</span></span>

  - <span data-ttu-id="7d44d-140">ネットワークメトリックのグラフィカル表示–ネットワーク MOS、パケット損失、および全画面表示とスナップビューでの着信のジッター。</span><span class="sxs-lookup"><span data-stu-id="7d44d-140">Graphical view of network metrics – Network MOS, Packet Loss and Interarrival Jitter in full screen and snapped view.</span></span>

<span data-ttu-id="7d44d-141">**全画面表示**</span><span class="sxs-lookup"><span data-stu-id="7d44d-141">**Full screen view**</span></span>

<span data-ttu-id="7d44d-142">![PreCall 診断ツールのテスト結果のグラフ](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall 診断ツールのテスト結果のグラフ")</span><span class="sxs-lookup"><span data-stu-id="7d44d-142">![PreCall Diagnostic Tool test result graphs](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall Diagnostic Tool test result graphs")</span></span>

<span data-ttu-id="7d44d-143">**スナップビュー**</span><span class="sxs-lookup"><span data-stu-id="7d44d-143">**Snapped view**</span></span>

<span data-ttu-id="7d44d-144">![PreCall 診断ツール、使用状況テストの結果](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall 診断ツール、使用状況テストの結果")</span><span class="sxs-lookup"><span data-stu-id="7d44d-144">![PreCall Diagnostic Tool Utilization test results](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall Diagnostic Tool Utilization test results")</span></span>

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a><span data-ttu-id="7d44d-145">Lync PCD を実行する</span><span class="sxs-lookup"><span data-stu-id="7d44d-145">Running Lync PCD</span></span>

<div>

## <a name="running-windows-desktop-app"></a><span data-ttu-id="7d44d-146">Windows デスクトップアプリを実行している場合</span><span class="sxs-lookup"><span data-stu-id="7d44d-146">Running Windows Desktop App</span></span>

1.  <span data-ttu-id="7d44d-147">Windows 7 システムで PCD を開始するには、[**スタート**] メニューから [**すべての診断**を事前に実行] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7d44d-147">To start the PCD on a Windows 7 system, select **PreCall Diagnostics** from the **Start** menu.</span></span>
    
    <span data-ttu-id="7d44d-148">Windows 8 システムで PCD を開始するには、スタート画面でアイコンを選ぶか、"すべての診断" を検索します。</span><span class="sxs-lookup"><span data-stu-id="7d44d-148">To start the PCD on a Windows 8 system, select the icon on your Start screen, or search for “PreCall Diagnostics.”</span></span>
    
    <span data-ttu-id="7d44d-149">![PreCall 診断ツール アイコン](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall 診断ツール アイコン")</span><span class="sxs-lookup"><span data-stu-id="7d44d-149">![PreCall Diagnostic tool icon](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall Diagnostic tool icon")</span></span>

2.  <span data-ttu-id="7d44d-150">ツールが起動したら、資格情報を提供するための推奨される方法を選択し、[**すべての診断ツールのオプション**] ダイアログボックスでネットワークの動作モードを選択して、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7d44d-150">When the tool starts, select your preferred method of providing credentials and select the network operating mode in the **PreCall Diagnostics Tool Options** dialog box, then select **OK**:</span></span>

3.  <span data-ttu-id="7d44d-151">[**テストの開始**] ボタンを選択して診断の実行を開始します。</span><span class="sxs-lookup"><span data-stu-id="7d44d-151">Select the **Start Test** button to start running diagnostics.</span></span>
    
    <span data-ttu-id="7d44d-152">[**ネットワーク資格情報を使用**する] オプションを選択した場合、テストは直ちに開始されます。</span><span class="sxs-lookup"><span data-stu-id="7d44d-152">If you selected the **Use network credentials** option, the test begins immediately.</span></span>
    
    <span data-ttu-id="7d44d-153">[**資格情報を入力**する] オプションを選んだ場合は、[ **Windows セキュリティ**] ダイアログボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="7d44d-153">If you selected the **Let me enter my credentials** option, the **Windows Security** dialog box opens.</span></span> <span data-ttu-id="7d44d-154">資格情報を入力すると、テストが開始されます。</span><span class="sxs-lookup"><span data-stu-id="7d44d-154">After you enter your credentials, the test starts.</span></span>

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a><span data-ttu-id="7d44d-155">Lync PCD をアンインストールする</span><span class="sxs-lookup"><span data-stu-id="7d44d-155">Uninstalling Lync PCD</span></span>

<span data-ttu-id="7d44d-156">Lync PCD を削除するには、使用しているオペレーティングシステムの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="7d44d-156">To remove Lync PCD, follow the procedure for your operating system:</span></span>

  - <span data-ttu-id="7d44d-157">Windows 7 システムでは、**コントロールパネル**を開き、[**プログラムと機能**] を選択して、[ **Lync 2013 precall Diagnostics**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="7d44d-157">On a Windows 7 system, open the **Control Panel**, select **Programs and Features**, and double-click **Lync 2013 PreCall Diagnostics**.</span></span>

  - <span data-ttu-id="7d44d-158">Windows 8 システムでは、PCD タイルを右クリックして、スタート画面の下部にあるアプリバーから [**アンインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7d44d-158">On a Windows 8 system, right-click on the PCD tile and click **Uninstall** from the app bar at the bottom of the start screen.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

