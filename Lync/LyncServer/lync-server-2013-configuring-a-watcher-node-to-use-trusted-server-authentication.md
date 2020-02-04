---
title: 信頼されたサーバー認証を使用するためのウォッチャーノードの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7279e18c73ecca9340f57d40794a3e9eb2dd160b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741227"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a><span data-ttu-id="ee695-102">Lync Server 2013 で監視ノードを構成して、信頼されたサーバー認証を使用する</span><span class="sxs-lookup"><span data-stu-id="ee695-102">Configuring a watcher node in Lync Server 2013 to use Trusted Server authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee695-103">_**最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="ee695-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="ee695-104">ウォッチャーノードコンピューターが境界ネットワーク内にある場合、信頼されたサーバー認証を使用すると、多数のユーザーアカウントパスワードではなく1つの証明書を管理するために管理税が大幅に減少する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ee695-104">If your watcher node computer lies inside the perimeter network, using Trusted Server authentication can greatly reduce administration taxes to maintaining a single certificate rather than numerous user account passwords.</span></span>

<span data-ttu-id="ee695-105">信頼されたサーバー認証を構成するための最初の手順は、監視ノードコンピューターをホストする信頼されたアプリケーションプールを作成することです。</span><span class="sxs-lookup"><span data-stu-id="ee695-105">The first step in configuring Trusted Server authentication is to create a trusted application pool to host the watcher node computer.</span></span> <span data-ttu-id="ee695-106">信頼されたアプリケーションプールを作成した後で、そのウォッチャーノードの代理トランザクションを、信頼されたアプリケーションとして実行されるように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee695-106">After the trusted application pool has been created, you must then configure synthetic transactions on that watcher node to run as a trusted application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="ee695-107">信頼されたアプリケーションとは、Lync Server 2013 の一部として実行される信頼された状態を提供するアプリケーションですが、製品の組み込みの部分ではありません。</span><span class="sxs-lookup"><span data-stu-id="ee695-107">A trusted application is an application that is given trusted status to run as part of Lync Server 2013, but that is not a built-in part of the product.</span></span> <span data-ttu-id="ee695-108">Trusted status means that the application will not be challenged for authentication each time it runs.</span><span class="sxs-lookup"><span data-stu-id="ee695-108">Trusted status means that the application will not be challenged for authentication each time it runs.</span></span>



</div>

<span data-ttu-id="ee695-109">信頼されたアプリケーションプールを作成するには、Lync Server 2013 管理シェルを開き、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ee695-109">To create a trusted application pool, open the Lync Server 2013 Management Shell and run a command similar to this:</span></span>

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> <span data-ttu-id="ee695-110">上記のコマンドで使用されるパラメーターの詳細については、「Lync Server 管理シェルのプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ee695-110">For details about the parameters used in the preceding command, type the following at the Lync Server Management Shell prompt:</span></span><BR><span data-ttu-id="ee695-111">CsTrustedApplicationPool---------------------もっとその</span><span class="sxs-lookup"><span data-stu-id="ee695-111">Get-Help New-CsTrustedApplicationPool -Full | more</span></span>



</div>

<span data-ttu-id="ee695-112">信頼されたアプリケーションプールを作成したら、信頼されたアプリケーションとして代理トランザクションを実行するようにウォッチャーノードのコンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="ee695-112">After creating the trusted application pool, configure the watcher node computer to run synthetic transactions as a trusted application.</span></span> <span data-ttu-id="ee695-113">これを行うには、 **CsTrustedApplication**コマンドレットと次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ee695-113">This is done by using the **New-CsTrustedApplication** cmdlet and a command similar to this:</span></span>

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

<span data-ttu-id="ee695-114">上記のコマンドが完了し、信頼されたアプリケーションが作成されたら、Enable-CsTopology ツールを実行して、変更が反映されるようにします。</span><span class="sxs-lookup"><span data-stu-id="ee695-114">When the preceding command completes and the trusted application has been created, run Enable-CsTopology to make sure that the changes take effect:</span></span>

    Enable-CsTopology

<span data-ttu-id="ee695-115">Enable-CsTopology ツールを実行した後、コンピューターを再起動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ee695-115">After running Enable-CsTopology, we recommend that you restart the computer.</span></span>

<span data-ttu-id="ee695-116">新しい信頼済みアプリケーションが作成されたことを確認するには、Lync Server 管理シェルのプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ee695-116">To verify that the new trusted application has been created, type the following at the Lync Server Management Shell prompt:</span></span>

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a><span data-ttu-id="ee695-117">ウォッチャーノードでの既定の証明書の構成</span><span class="sxs-lookup"><span data-stu-id="ee695-117">Configuring a Default Certificate on the Watcher Node</span></span>

<span data-ttu-id="ee695-118">各ウォッチャーノードには、Lync Server 展開ウィザードを使用して、既定の証明書を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee695-118">Each watcher node must have a Default certificate assigned by using the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="ee695-119">**既定の証明書を割り当てるには**</span><span class="sxs-lookup"><span data-stu-id="ee695-119">**To assign a Default certificate**</span></span>

1.  <span data-ttu-id="ee695-120">[**スタート**] をクリックし、[**すべてのプログラム**] をクリックし、[ **lync server**] をクリックして、[ **lync server Deployment Wizard**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee695-120">Click **Start**, click **All Programs**, click **Lync Server**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="ee695-121">Lync Server 展開ウィザードで、[ **Lync Server System をインストールまたは更新**する] をクリックし、[**要求]、[インストール]、または [証明書の割り当て**] の [**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee695-121">In the Lync Server Deployment Wizard, click **Install or Update Lync Server System** and then click **Run** under the heading **Request, Install, or Assign Certificate**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="ee695-122">[<STRONG>実行</STRONG>] ボタンが無効になっている場合は、最初に [<STRONG>ローカル構成ストアのインストール</STRONG>] の [<STRONG>実行</STRONG>] をクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee695-122">If the <STRONG>Run</STRONG> button is disabled, you may need to first click <STRONG>Run</STRONG> under <STRONG>Install Local Configuration Store</STRONG>.</span></span>

    
    </div>

3.  <span data-ttu-id="ee695-123">次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="ee695-123">Do one of the following:</span></span>
    
      - <span data-ttu-id="ee695-124">既定の証明書として使用できる証明書が既にある場合は、証明書ウィザードで [**既定**] をクリックし、[**割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee695-124">If you already have a certificate that can be used as the Default certificate, click **Default** in the Certificate wizard and then click **Assign**.</span></span> <span data-ttu-id="ee695-125">証明書の割り当てウィザードの手順に従って、証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ee695-125">Follow the steps in the Certificate Assignment wizard to assign that certificate.</span></span>
    
      - <span data-ttu-id="ee695-126">既定の証明書を使用するために証明書を要求する必要がある場合は、[**要求**] をクリックし、証明書の要求ウィザードの手順に従って証明書を要求します。</span><span class="sxs-lookup"><span data-stu-id="ee695-126">If you need to request a certificate for use the Default certificate, click **Request** and then follow the steps in the Certificate Request wizard to request that certificate.</span></span> <span data-ttu-id="ee695-127">Web サーバー証明書の既定値を使用すると、既定の証明書として割り当てることができる証明書を取得できます。</span><span class="sxs-lookup"><span data-stu-id="ee695-127">If you use the default values for the Web Server certificate, you get a certificate that you can assign as the Default certificate.</span></span>

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a><span data-ttu-id="ee695-128">ウォッチャーノードのインストールと構成</span><span class="sxs-lookup"><span data-stu-id="ee695-128">Installing and Configuring a Watcher Node</span></span>

<span data-ttu-id="ee695-129">ウォッチャーノードのコンピューターを再起動して証明書を構成したら、Watchernode ファイルを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee695-129">After you have restarted the watcher node computer and configured a certificate, you need to run the file Watchernode.msi.</span></span> <span data-ttu-id="ee695-130">(Operations Manager エージェントファイルと Lync Server 2013 コアコンポーネントの両方がインストールされているコンピューターで Watchernode を実行する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="ee695-130">(You must run Watchernode.msi on a computer where both the Operations Manager agent files and the Lync Server 2013 core components are installed.)</span></span>

<span data-ttu-id="ee695-131">**ウォッチャーノードをインストールして構成するには**</span><span class="sxs-lookup"><span data-stu-id="ee695-131">**To install and configure a watcher node**</span></span>

1.  <span data-ttu-id="ee695-132">[**スタート**] をクリックし、[**すべてのプログラム**]、[ **Lync Server**]、[ **lync server 管理シェル**] の順にクリックして、lync server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ee695-132">Open the Lync Server Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server**, and then clicking **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ee695-133">Lync Server 管理シェルで、次のコマンドを入力し、enter キーを押します (Watchernode のコピーの実際のパスを指定します)。</span><span class="sxs-lookup"><span data-stu-id="ee695-133">In the Lync Server Management Shell, type the following command and then press ENTER (specify the actual path to your copy of Watchernode.msi):</span></span>
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="ee695-134">コマンドウィンドウから Watchernode を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="ee695-134">You can also run Watchernode.msi from a command window.</span></span> <span data-ttu-id="ee695-135">コマンド ウィンドウを開くには、[<STRONG>スタート</STRONG>] メニューをクリックし、[<STRONG>コマンド プロンプト</STRONG>] を右クリックして、[<STRONG>管理者として実行</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee695-135">To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>.</span></span> <span data-ttu-id="ee695-136">コマンドウィンドウが開いたら、上記と同じコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="ee695-136">When the command window opens, type the same preceding command.</span></span>

    
    </div>

<span data-ttu-id="ee695-137">上のコマンド Authentication = TrustedServer では、名前/値のペアは大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ee695-137">Note that the name/value pair in the preceding command Authentication=TrustedServer is case-sensitive.</span></span> <span data-ttu-id="ee695-138">示されているとおりに入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee695-138">You must type it exactly as shown.</span></span> <span data-ttu-id="ee695-139">次のコマンドは、正しい文字の大文字と小文字を区別しないために失敗します。</span><span class="sxs-lookup"><span data-stu-id="ee695-139">The following command fails because it does not use the correct letter casing:</span></span>

<span data-ttu-id="ee695-140">C:\\ツール\\Watchernode 認証 = trustedserver</span><span class="sxs-lookup"><span data-stu-id="ee695-140">C:\\Tools\\Watchernode.msi authentication=trustedserver</span></span>

<span data-ttu-id="ee695-141">TrustedServer モードは、境界ネットワーク内に配置されているコンピューターでのみ使うことができます。</span><span class="sxs-lookup"><span data-stu-id="ee695-141">You can use TrustedServer mode only with computers that are located within the perimeter network.</span></span> <span data-ttu-id="ee695-142">Watcher ノードが TrustedServer モードで実行されている場合、管理者は、コンピューター上のテストユーザーパスワードを管理する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ee695-142">When a watcher node is running in TrustedServer mode, administrators do not have to maintain test user passwords on the computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

