---
title: 信頼されたサーバー認証を使用する監視ノードの構成
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
ms.openlocfilehash: 3ba69980f97e901703f51f71729c661821e70e61
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a><span data-ttu-id="d27eb-102">Lync Server 2013 の監視ノードを構成して、信頼されたサーバー認証を使用する</span><span class="sxs-lookup"><span data-stu-id="d27eb-102">Configuring a watcher node in Lync Server 2013 to use Trusted Server authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d27eb-103">_**トピックの最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="d27eb-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="d27eb-104">監視ノード コンピューターが境界ネットワーク内にある場合、信頼済みサーバー認証によって 1 つの証明書を管理するだけでよくなるので、管理負荷が大幅に軽減されます。膨大な数のユーザー アカウント パスワードを管理する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d27eb-104">If your watcher node computer lies inside the perimeter network, using Trusted Server authentication can greatly reduce administration taxes to maintaining a single certificate rather than numerous user account passwords.</span></span>

<span data-ttu-id="d27eb-p101">信頼済みサーバー認証を構成するには、最初のステップとして、まず監視ノード コンピューターをホストする信頼済みアプリケーション プールを作成します。信頼済みアプリケーション プールが作成されたら、その監視ノードで、信頼済みアプリケーションとして実行されるように代理トランザクションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d27eb-p101">The first step in configuring Trusted Server authentication is to create a trusted application pool to host the watcher node computer. After the trusted application pool has been created, you must then configure synthetic transactions on that watcher node to run as a trusted application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="d27eb-107">信頼されたアプリケーションとは、Lync Server 2013 の一部として実行される信頼できる状態が与えられているアプリケーションですが、これは製品の組み込みパーツではありません。</span><span class="sxs-lookup"><span data-stu-id="d27eb-107">A trusted application is an application that is given trusted status to run as part of Lync Server 2013, but that is not a built-in part of the product.</span></span> <span data-ttu-id="d27eb-108">信頼済みステータスのアプリケーションは、実行のたびに認証でチャレンジされることはありません。</span><span class="sxs-lookup"><span data-stu-id="d27eb-108">Trusted status means that the application will not be challenged for authentication each time it runs.</span></span>



</div>

<span data-ttu-id="d27eb-109">信頼されたアプリケーションプールを作成するには、Lync Server 2013 管理シェルを開き、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d27eb-109">To create a trusted application pool, open the Lync Server 2013 Management Shell and run a command similar to this:</span></span>

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> <span data-ttu-id="d27eb-110">上記のコマンドで使用されたパラメーターの詳細については、Lync Server 管理シェルプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d27eb-110">For details about the parameters used in the preceding command, type the following at the Lync Server Management Shell prompt:</span></span><BR><span data-ttu-id="d27eb-111">Get-Help New-CsTrustedApplicationPool -Full | more</span><span class="sxs-lookup"><span data-stu-id="d27eb-111">Get-Help New-CsTrustedApplicationPool -Full | more</span></span>



</div>

<span data-ttu-id="d27eb-112">信頼済みアプリケーション プールの作成後、代理トランザクションが信頼済みアプリケーションアプリケーションとして実行されるように監視ノード コンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="d27eb-112">After creating the trusted application pool, configure the watcher node computer to run synthetic transactions as a trusted application.</span></span> <span data-ttu-id="d27eb-113">これを行うには、**New-CsTrustedApplication** コマンドレットと、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d27eb-113">This is done by using the **New-CsTrustedApplication** cmdlet and a command similar to this:</span></span>

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

<span data-ttu-id="d27eb-114">上記のコマンドが完了し、信頼済みアプリケーションが作成されたら、Enable-CsTopology を実行して変更を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d27eb-114">When the preceding command completes and the trusted application has been created, run Enable-CsTopology to make sure that the changes take effect:</span></span>

    Enable-CsTopology

<span data-ttu-id="d27eb-115">Enable-CsTopology の実行後は、コンピューターを再起動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d27eb-115">After running Enable-CsTopology, we recommend that you restart the computer.</span></span>

<span data-ttu-id="d27eb-116">新しい信頼済みアプリケーションが作成されたことを確認するには、Lync Server 管理シェルプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d27eb-116">To verify that the new trusted application has been created, type the following at the Lync Server Management Shell prompt:</span></span>

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a><span data-ttu-id="d27eb-117">監視ノードで既定の証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="d27eb-117">Configuring a Default Certificate on the Watcher Node</span></span>

<span data-ttu-id="d27eb-118">各監視ノードには、Lync Server 展開ウィザードを使用して、既定の証明書が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d27eb-118">Each watcher node must have a Default certificate assigned by using the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="d27eb-119">**既定の証明書を割り当てるには**</span><span class="sxs-lookup"><span data-stu-id="d27eb-119">**To assign a Default certificate**</span></span>

1.  <span data-ttu-id="d27eb-120">[**スタート**]、[**すべてのプログラム**]、[ **Lync Server**]、[ **lync server 展開ウィザード**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d27eb-120">Click **Start**, click **All Programs**, click **Lync Server**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="d27eb-121">Lync Server 展開ウィザードで、[ **Lync Server システムのインストールまたは更新**] をクリックし、[**要求]、[インストール]、または [証明書の割り当て**] の [**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d27eb-121">In the Lync Server Deployment Wizard, click **Install or Update Lync Server System** and then click **Run** under the heading **Request, Install, or Assign Certificate**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="d27eb-122">[<STRONG>実行</STRONG>] ボタンをが無効になっている場合は、[<STRONG>ローカル構成ストアのインストール</STRONG>] で [<STRONG>実行</STRONG>] を最初にクリックしなければならないことがあります。</span><span class="sxs-lookup"><span data-stu-id="d27eb-122">If the <STRONG>Run</STRONG> button is disabled, you may need to first click <STRONG>Run</STRONG> under <STRONG>Install Local Configuration Store</STRONG>.</span></span>

    
    </div>

3.  <span data-ttu-id="d27eb-123">次のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d27eb-123">Do one of the following:</span></span>
    
      - <span data-ttu-id="d27eb-p104">既定の証明書として使用できる証明書が既にある場合は、証明書ウィザードで [**既定**] をクリックし、[**割り当て**] をクリックします。証明書の割り当てウィザードの手順に従って、証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d27eb-p104">If you already have a certificate that can be used as the Default certificate, click **Default** in the Certificate wizard and then click **Assign**. Follow the steps in the Certificate Assignment wizard to assign that certificate.</span></span>
    
      - <span data-ttu-id="d27eb-p105">既定の証明書として使用する証明書を要求する必要がある場合は、[**要求**] をクリックし、証明書要求ウィザードの手順に従ってその証明書を要求します。Web サーバー証明書の既定値を使用すると、既定の証明書として割り当てることができる証明書を取得できます。</span><span class="sxs-lookup"><span data-stu-id="d27eb-p105">If you need to request a certificate for use the Default certificate, click **Request** and then follow the steps in the Certificate Request wizard to request that certificate. If you use the default values for the Web Server certificate, you get a certificate that you can assign as the Default certificate.</span></span>

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a><span data-ttu-id="d27eb-128">監視ノードをインストールおよび構成する</span><span class="sxs-lookup"><span data-stu-id="d27eb-128">Installing and Configuring a Watcher Node</span></span>

<span data-ttu-id="d27eb-129">監視ノードコンピューターを再起動し、証明書を構成したら、Watchernode.msi ファイルを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d27eb-129">After you have restarted the watcher node computer and configured a certificate, you need to run the file Watchernode.msi.</span></span> <span data-ttu-id="d27eb-130">(Operations Manager エージェントファイルと Lync Server 2013 コアコンポーネントの両方がインストールされているコンピューターで Watchernode.msi を実行する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="d27eb-130">(You must run Watchernode.msi on a computer where both the Operations Manager agent files and the Lync Server 2013 core components are installed.)</span></span>

<span data-ttu-id="d27eb-131">**監視ノードをインストールおよび構成するには**</span><span class="sxs-lookup"><span data-stu-id="d27eb-131">**To install and configure a watcher node**</span></span>

1.  <span data-ttu-id="d27eb-132">[**スタート**]、[**すべてのプログラム**]、[ **Lync server**]、[ **lync server 管理シェル**] の順にクリックして、Lync server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d27eb-132">Open the Lync Server Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server**, and then clicking **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d27eb-133">Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します (Watchernode.msi のコピーへの実際のパスを指定します)。</span><span class="sxs-lookup"><span data-stu-id="d27eb-133">In the Lync Server Management Shell, type the following command and then press ENTER (specify the actual path to your copy of Watchernode.msi):</span></span>
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="d27eb-p107">コマンド ウィンドウから Watchernode.msi を実行することもできます。コマンド ウィンドウを開くには、[<STRONG>スタート</STRONG>] をクリックし、[<STRONG>コマンド プロンプト</STRONG>] を右クリックして、[<STRONG>管理者として実行</STRONG>] をクリックします。コマンド ウィンドウが開いたら、上記と同じコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="d27eb-p107">You can also run Watchernode.msi from a command window. To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>. When the command window opens, type the same preceding command.</span></span>

    
    </div>

<span data-ttu-id="d27eb-p108">上記のコマンドの名前/値ペア Authentication=TrustedServer は大文字と小文字が区別されるので、ここで示すとおりに正確に入力する必要があります。次のコマンドは、大文字と小文字が正しく使用されていないので失敗します。</span><span class="sxs-lookup"><span data-stu-id="d27eb-p108">Note that the name/value pair in the preceding command Authentication=TrustedServer is case-sensitive. You must type it exactly as shown. The following command fails because it does not use the correct letter casing:</span></span>

<span data-ttu-id="d27eb-140">C:\\Tools\\watchernode.msi authentication = trustedserver</span><span class="sxs-lookup"><span data-stu-id="d27eb-140">C:\\Tools\\Watchernode.msi authentication=trustedserver</span></span>

<span data-ttu-id="d27eb-p109">TrustedServer モードは、境界ネットワーク内のコンピューターでのみ使用できます。監視ノードが TrustedServer モードで実行されている場合は、管理者が、コンピューター上のテスト ユーザー パスワードを管理する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d27eb-p109">You can use TrustedServer mode only with computers that are located within the perimeter network. When a watcher node is running in TrustedServer mode, administrators do not have to maintain test user passwords on the computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

