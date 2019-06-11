---
title: 'Lync Server 2013: Lync VDI プラグインの前提条件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync VDI plug-in prerequisites
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205304(v=OCS.15)
ms:contentKeyID: 48185552
ms.date: 03/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae32480e5a3dbfbdfc22c4dbde59c62383c9587f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a><span data-ttu-id="84361-102">Lync Server 2013 の Lync VDI プラグインの前提条件</span><span class="sxs-lookup"><span data-stu-id="84361-102">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84361-103">_**最終更新日:** 2017-03-07_</span><span class="sxs-lookup"><span data-stu-id="84361-103">_**Topic Last Modified:** 2017-03-07_</span></span>

<span data-ttu-id="84361-104">仮想デスクトップインフラストラクチャ (VDI) 環境では、仮想マシンとユーザーのローカルコンピューターがこのセクションで示されている要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="84361-104">In a virtual desktop infrastructure (VDI) environment, the virtual machines and the user’s local computer must meet the requirements outlined in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="84361-105">仮想化された環境をインストールして展開する方法の詳細については、仮想化ソリューションプロバイダーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="84361-105">Refer to your virtualization solution provider for details about how to install and deploy the virtualized environment.</span></span> <span data-ttu-id="84361-106">Hyper-v とリモートデスクトップサービスに基づいて仮想環境を展開する方法については、Microsoft TechNet ライブラリの次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84361-106">For information about deploying a virtualized environment based on Hyper-V and Remote Desktop Services, see the following articles in the Microsoft TechNet Library:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="84361-107">Hyper-v<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span><span class="sxs-lookup"><span data-stu-id="84361-107">Hyper-V at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span></span></P>
> <LI>
> <P><span data-ttu-id="84361-108">Windows Server&nbsp;2008&nbsp;R2 のリモートデスクトップサービス (at)<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span><span class="sxs-lookup"><span data-stu-id="84361-108">Remote Desktop Services in Windows Server&nbsp;2008&nbsp;R2 at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="84361-109">データセンターコンピューターで実行されている仮想マシンの要件を次に示します。</span><span class="sxs-lookup"><span data-stu-id="84361-109">The following are requirements for the virtual machines running on the data center computer:</span></span>

  - <span data-ttu-id="84361-110">仮想マシンは、最新の service pack を使用して、Windows 10、Windows 8.1、Windows 8、windows 7、または Windows Server 2008 R2 で構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84361-110">Virtual machines must be configured with Windows 10, Windows 8.1, Windows 8, Windows 7, or Windows Server 2008 R2 with the latest service packs.</span></span>

<span data-ttu-id="84361-111">ユーザーとユーザーのローカルコンピューターの要件を次に示します。</span><span class="sxs-lookup"><span data-stu-id="84361-111">The following are requirements for the user and the user’s local computer:</span></span>

  - <span data-ttu-id="84361-112">ユーザーは、Lync Server 2013 上に置かれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="84361-112">The user must be homed on Lync Server 2013.</span></span>

  - <span data-ttu-id="84361-113">ローカルコンピューターでは、SP1、Windows 7 SP1、Windows 8、windows 8.1 Embedded、または Windows 8.1 (埋め込み以外) で Windows Embedded 標準7を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="84361-113">The local computer must be running Windows Embedded Standard 7 with SP1, Windows 7 with SP1, Windows 8, Windows 8.1 Embedded, or Windows 8.1 (not embedded).</span></span>

  - <span data-ttu-id="84361-114">リモートデスクトップサービスを使用している場合は、Lync VDI プラグインビット (つまり、32ビットと64ビットのどちらであるか) がローカルコンピューターのオペレーティングシステムのビットと一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="84361-114">If you are using Remote Desktop Services, the Lync VDI plug-in bitness (that is, whether the application is 32-bit or 64-bit) must match the local computer’s operating system bitness.</span></span> <span data-ttu-id="84361-115">ローカルコンピューター上のオペレーティングシステムと仮想マシン上のオペレーティングシステムのビットが一致している必要はありません。</span><span class="sxs-lookup"><span data-stu-id="84361-115">The bitness of the operating system on the local computer and the operating system on the virtual machine do not need to match.</span></span> <span data-ttu-id="84361-116">別の仮想化ソリューションまたはプラットフォームを使用している場合は、「ビット要件について仮想化ソリューションプロバイダーからのガイダンス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84361-116">If you are using another virtualization solution or platform, refer to guidance from your virtualization solution provider about bitness requirements.</span></span>

  - <span data-ttu-id="84361-117">ローカルコンピューターで、最新バージョンのリモートデスクトップクライアントが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="84361-117">The local computer must be running the latest version of the remote desktop client.</span></span> <span data-ttu-id="84361-118">Microsoft からリモート デスクトップ サービス クライアントの最新更新プログラムをインストールするか、仮想化ソリューション プロバイダーから最新のリモート デスクトップ クライアント ソフトウェアをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="84361-118">Install the latest updates of Remote Desktop Services client from Microsoft or the latest remote desktop client software from your virtualization solution provider.</span></span> <span data-ttu-id="84361-119">最新のリモートデスクトップサービスの更新につい[https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)ては、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84361-119">For the latest Remote Desktop Services updates, see [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

  - <span data-ttu-id="84361-120">ローカル コンピューター上のリモート デスクトップ クライアントの設定は、オーディオがローカル コンピューターで再生され、リモート レコーディングが無効となるように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84361-120">On the local computer, the remote desktop client settings must be configured so that audio plays on the local computer and remote recording is disabled.</span></span> <span data-ttu-id="84361-121">Windows でリモートデスクトップ接続のこれらの設定を構成するには、次のセクション「リモートデスクトップ接続設定を構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84361-121">To configure these settings for Remote Desktop Connection in Windows, see the next section, "To configure Remote Desktop Connection settings."</span></span>

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a><span data-ttu-id="84361-122">リモートデスクトップ接続設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="84361-122">To configure Remote Desktop Connection settings</span></span>

<span data-ttu-id="84361-123">Windows で Lync VDI プラグインのリモートデスクトップ接続を準備するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="84361-123">To prepare Remote Desktop Connection in Windows for the Lync VDI plug-in, follow these steps.</span></span>

1.  <span data-ttu-id="84361-124">ローカルコンピューターで Windows 8 を実行している場合は、この手順をスキップしてください。</span><span class="sxs-lookup"><span data-stu-id="84361-124">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="84361-125">ローカルコンピューターで Windows 7 SP1 を実行している場合は、最新の Windows 8 バージョンのリモートデスクトップサービスクライアントをインストール[https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)します。</span><span class="sxs-lookup"><span data-stu-id="84361-125">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the Remote Desktop Services client, available at [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

2.  <span data-ttu-id="84361-126">[**スタート**]、[**リモート デスクトップ接続**] の順にクリックして、リモート デスクトップ サービス クライアントを起動します。</span><span class="sxs-lookup"><span data-stu-id="84361-126">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>

3.  <span data-ttu-id="84361-127">[**オプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84361-127">Click **Options**.</span></span>

4.  <span data-ttu-id="84361-128">[**ローカル リソース**] タブをクリックします。[**リモート オーディオ**] の下にある [**設定**] をクリックし、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="84361-128">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
      - <span data-ttu-id="84361-129">[**リモート オーディオ再生**] で [**このコンピューターで再生**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="84361-129">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
      - <span data-ttu-id="84361-130">[**リモート オーディオ録音**] で [**録音しない**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="84361-130">Under **Remote audio recording**, select **Do not record**.</span></span>
    
      - <span data-ttu-id="84361-131">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84361-131">Click **OK**.</span></span>

5.  <span data-ttu-id="84361-132">[**エクスペリエンス**] タブをクリックします。[**パフォーマンス**] で [**ビットマップのキャッシュを保持**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="84361-132">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>

6.  <span data-ttu-id="84361-133">[**全般**] タブをクリックします。[**コンピューター**] で、仮想マシンの名前を入力し、[**接続**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84361-133">Click the **General** tab. In **Computer**, type the name of the virtual machine, and then click **Connect**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

