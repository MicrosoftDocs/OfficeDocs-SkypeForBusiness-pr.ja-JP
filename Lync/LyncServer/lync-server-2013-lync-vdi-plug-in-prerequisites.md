---
title: 'Lync Server 2013: Lync VDI プラグインの前提条件'
description: 'Lync Server 2013: Lync VDI プラグインの前提条件。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync VDI plug-in prerequisites
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205304(v=OCS.15)
ms:contentKeyID: 48185552
ms.date: 03/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4389f776747426d07442e29418ab97e9609de7ee
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566543"
---
# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a><span data-ttu-id="51662-103">Lync Server 2013 での lync VDI プラグインの前提条件</span><span class="sxs-lookup"><span data-stu-id="51662-103">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51662-104">_**トピックの最終更新日:** 2017-03-07_</span><span class="sxs-lookup"><span data-stu-id="51662-104">_**Topic Last Modified:** 2017-03-07_</span></span>

<span data-ttu-id="51662-105">仮想デスクトップインフラストラクチャ (VDI) 環境では、仮想マシンとユーザーのローカルコンピューターが、このセクションで説明する要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="51662-105">In a virtual desktop infrastructure (VDI) environment, the virtual machines and the user’s local computer must meet the requirements outlined in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="51662-p101">仮想化環境のインストール方法および展開方法の詳細については、仮想化ソリューション プロバイダーに問い合わせてください。Hyper-V およびリモート デスクトップ サービスに基づいた仮想化環境の展開については、Microsoft TechNet ライブラリの次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51662-p101">Refer to your virtualization solution provider for details about how to install and deploy the virtualized environment. For information about deploying a virtualized environment based on Hyper-V and Remote Desktop Services, see the following articles in the Microsoft TechNet Library:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="51662-108">Hyper-v <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span><span class="sxs-lookup"><span data-stu-id="51662-108">Hyper-V at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span></span></P>
> <LI>
> <P><span data-ttu-id="51662-109">Windows Server &nbsp; 2008 R2 のリモートデスクトップ &nbsp; サービス <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span><span class="sxs-lookup"><span data-stu-id="51662-109">Remote Desktop Services in Windows Server&nbsp;2008&nbsp;R2 at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="51662-110">データ センターのコンピューターで実行されている仮想マシンに対する要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="51662-110">The following are requirements for the virtual machines running on the data center computer:</span></span>

  - <span data-ttu-id="51662-111">仮想マシンは、最新のサービスパックを使用して Windows 10、windows 8.1、Windows 8、Windows 7、または Windows Server 2008 R2 で構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51662-111">Virtual machines must be configured with Windows 10, Windows 8.1, Windows 8, Windows 7, or Windows Server 2008 R2 with the latest service packs.</span></span>

<span data-ttu-id="51662-112">ユーザーとユーザーのローカルコンピューターの要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="51662-112">The following are requirements for the user and the user’s local computer:</span></span>

  - <span data-ttu-id="51662-113">ユーザーは、Lync Server 2013 に所属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="51662-113">The user must be homed on Lync Server 2013.</span></span>

  - <span data-ttu-id="51662-114">ローカルコンピューターでは、Windows Embedded Standard 7 SP1、windows 7 SP1、windows 8、Windows 8.1 が埋め込まれているか、または Windows 8.1 (埋め込まれていない) を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="51662-114">The local computer must be running Windows Embedded Standard 7 with SP1, Windows 7 with SP1, Windows 8, Windows 8.1 Embedded, or Windows 8.1 (not embedded).</span></span>

  - <span data-ttu-id="51662-115">リモートデスクトップサービスを使用している場合、Lync VDI プラグインのビット数 (つまり、アプリケーションが32ビットであるか、または64ビットであるか) は、ローカルコンピューターのオペレーティングシステムのビット数と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="51662-115">If you are using Remote Desktop Services, the Lync VDI plug-in bitness (that is, whether the application is 32-bit or 64-bit) must match the local computer’s operating system bitness.</span></span> <span data-ttu-id="51662-116">ローカル コンピューターと仮想マシンのオペレーティング システムのビット数が一致する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="51662-116">The bitness of the operating system on the local computer and the operating system on the virtual machine do not need to match.</span></span> <span data-ttu-id="51662-117">別の仮想化ソリューションまたは仮想化プラットフォームを使用している場合は、ビット数の要件については、仮想化ソリューション プロバイダーのガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="51662-117">If you are using another virtualization solution or platform, refer to guidance from your virtualization solution provider about bitness requirements.</span></span>

  - <span data-ttu-id="51662-118">ローカル コンピューターは、最新バージョンのリモート デスクトップ クライアントを実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="51662-118">The local computer must be running the latest version of the remote desktop client.</span></span> <span data-ttu-id="51662-119">マイクロソフトからリモート デスクトップ サービス クライアントの最新更新プログラムをインストールするか、仮想化ソリューション プロバイダーから最新のリモート デスクトップ クライアント ソフトウェアをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="51662-119">Install the latest updates of Remote Desktop Services client from Microsoft or the latest remote desktop client software from your virtualization solution provider.</span></span> <span data-ttu-id="51662-120">最新のリモートデスクトップサービスの更新については、「」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032) 。</span><span class="sxs-lookup"><span data-stu-id="51662-120">For the latest Remote Desktop Services updates, see [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

  - <span data-ttu-id="51662-121">ローカル コンピューター上のリモート デスクトップ クライアントの設定は、オーディオがローカル コンピューターで再生され、リモート録音が無効となるように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51662-121">On the local computer, the remote desktop client settings must be configured so that audio plays on the local computer and remote recording is disabled.</span></span> <span data-ttu-id="51662-122">Windows でこれらの設定をリモートデスクトップ接続用に構成するには、次のセクション「リモートデスクトップ接続の設定を構成するには」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51662-122">To configure these settings for Remote Desktop Connection in Windows, see the next section, "To configure Remote Desktop Connection settings."</span></span>

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a><span data-ttu-id="51662-123">リモート デスクトップ接続の設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="51662-123">To configure Remote Desktop Connection settings</span></span>

<span data-ttu-id="51662-124">Windows で Lync VDI プラグインのリモートデスクトップ接続を準備するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="51662-124">To prepare Remote Desktop Connection in Windows for the Lync VDI plug-in, follow these steps.</span></span>

1.  <span data-ttu-id="51662-125">ローカルコンピューターで Windows 8 を実行している場合は、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="51662-125">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="51662-126">ローカルコンピューターで Windows 7 SP1 を実行している場合は、最新の Windows 8 バージョンのリモートデスクトップサービスクライアントをインストールし [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032) ます。</span><span class="sxs-lookup"><span data-stu-id="51662-126">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the Remote Desktop Services client, available at [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

2.  <span data-ttu-id="51662-127">[**スタート**]、[**リモート デスクトップ接続**] の順にクリックして、リモート デスクトップ サービス クライアントを起動します。</span><span class="sxs-lookup"><span data-stu-id="51662-127">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>

3.  <span data-ttu-id="51662-128">[**オプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51662-128">Click **Options**.</span></span>

4.  <span data-ttu-id="51662-129">[**ローカル リソース**] タブをクリックします。[**リモート オーディオ**] の下にある [**設定**] をクリックし、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="51662-129">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
      - <span data-ttu-id="51662-130">[**リモート オーディオ再生**] の下の [**このコンピュータで再生**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="51662-130">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
      - <span data-ttu-id="51662-131">[**リモート オーディオ録音**] の下の [**録音しない**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="51662-131">Under **Remote audio recording**, select **Do not record**.</span></span>
    
      - <span data-ttu-id="51662-132">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51662-132">Click **OK**.</span></span>

5.  <span data-ttu-id="51662-133">[**エクスペリエンス**] タブをクリックします。[**パフォーマンス**] の下にある [**ビットマップのキャッシュを保持**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="51662-133">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>

6.  <span data-ttu-id="51662-134">[**全般**] タブをクリックします。[**コンピューター**] で仮想マシンの名前を入力し、[**接続**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51662-134">Click the **General** tab. In **Computer**, type the name of the virtual machine, and then click **Connect**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

