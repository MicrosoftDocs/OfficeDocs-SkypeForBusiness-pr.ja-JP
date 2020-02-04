---
title: 'Lync Server 2013: エッジ サーバーのインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Edge Servers
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398230(v=OCS.15)
ms:contentKeyID: 48183503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22d1961a158ead735ae63d20bb2bd233d6ed5958
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-edge-servers-for-lync-server-2013"></a><span data-ttu-id="ffe30-102">Lync Server 2013 のエッジ サーバーのインストール</span><span class="sxs-lookup"><span data-stu-id="ffe30-102">Install Edge Servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffe30-103">_**最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="ffe30-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="ffe30-104">Lync Server 2013 は、Lync Server 展開ウィザードを使って、エッジサーバーにインストールします。</span><span class="sxs-lookup"><span data-stu-id="ffe30-104">You install Lync Server 2013 on Edge Servers by using Lync Server Deployment Wizard.</span></span> <span data-ttu-id="ffe30-105">各エッジサーバーで展開ウィザードを実行することで、エッジサーバーのセットアップに必要なほとんどのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ffe30-105">By running the Deployment Wizard on each Edge Server, you can complete most of the tasks required to set up the Edge Server.</span></span> <span data-ttu-id="ffe30-106">エッジサーバーに Lync Server 2013 を展開するには、既にトポロジビルダーを実行して、エッジサーバートポロジを定義および公開し、エッジサーバーから入手できるメディアにエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffe30-106">In order to deploy Lync Server 2013 on an Edge Server, you must have already run Topology Builder to define and publish your Edge Server topology, and exported it to media that is available from the Edge Server.</span></span> <span data-ttu-id="ffe30-107">詳細については、「 [Lync server 2013 の外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」および「 [lync server 2013 トポロジをエクスポートして、edge インストール用の外部メディアにコピーする](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffe30-107">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<span data-ttu-id="ffe30-108">展開ウィザードを使用して各エッジサーバーをインストールし、必要な証明書をインストールして割り当て、必要なサービスを開始するには、「 [Lync server 2013 で外部ユーザーアクセスのサポートを構成](lync-server-2013-configuring-support-for-external-user-access.md)する」の情報を使用して、外部ユーザーのアクセスを有効にして構成すると共に、 [lync server 2013 で](lync-server-2013-verifying-your-edge-deployment.md)の microsoft Edge の展開を確認し</span><span class="sxs-lookup"><span data-stu-id="ffe30-108">After using the Deployment Wizard to install each Edge Server, install and assign the required certificates, and start the required services, you can complete the setup by using the information in [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) to enable and configure external user access and the information in [Verifying your edge deployment in Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md) to validate the setup, including server and client connectivity.</span></span>

<div>

## <a name="to-install-an-edge-server"></a><span data-ttu-id="ffe30-109">エッジサーバーをインストールするには</span><span class="sxs-lookup"><span data-stu-id="ffe30-109">To install an Edge Server</span></span>

1.  <span data-ttu-id="ffe30-110">エッジサーバーをローカルの管理者グループのメンバーまたは同等のユーザー権限とアクセス許可を持つアカウントとしてインストールするコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ffe30-110">Log on to the computer on which you want to install your Edge Server as a member of the local Administrators group or an account with equivalent user rights and permissions.</span></span>

2.  <span data-ttu-id="ffe30-111">トポロジビルダーを使用して作成したトポロジ構成ファイルと、外部メディアにエクスポートしてコピーしたものは、Edge サーバーで利用できます (たとえば、トポロジ構成ファイルをコピーした USB ドライブにアクセスするか、確認してください)。ファイルをコピーしたネットワーク共有にアクセスします)。</span><span class="sxs-lookup"><span data-stu-id="ffe30-111">Ensure that the topology configuration file you created using Topology Builder, and then exported and copied to external media, is available on the Edge Server (for example, access to the USB drive onto which you copied the topology configuration file, or verify access to the network share where you copied the file).</span></span>

3.  <span data-ttu-id="ffe30-112">展開ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="ffe30-112">Start the Deployment Wizard.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ffe30-113">Microsoft Visual C++ 再頒布可能パッケージをインストールする必要があるというメッセージが表示されたら、[<STRONG>はい</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffe30-113">If you get a message saying that you need to install Microsoft Visual C++ Redistributable, click <STRONG>Yes</STRONG>.</span></span> <span data-ttu-id="ffe30-114">次のダイアログボックスでは、既定の<STRONG>インストール場所</STRONG>をそのまま使用するか、[<STRONG>参照</STRONG>] をクリックして別の場所を選択し、[<STRONG>インストール</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffe30-114">In the next dialog box, you can accept the default <STRONG>Installation Location</STRONG> or click the <STRONG>Browse</STRONG> to select an alternate location, and then click <STRONG>Install</STRONG>.</span></span> <span data-ttu-id="ffe30-115">次のダイアログボックスで、[<STRONG>使用許諾契約書の条項に同意</STRONG>します] チェックボックスをオンにし、[ <STRONG>OK</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffe30-115">In the next dialog box, select the <STRONG>I accept the terms in the license agreement</STRONG> check box, and then click <STRONG>OK</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="ffe30-116">展開ウィザードで、[ **Lync Server System のインストールまたは更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffe30-116">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="ffe30-117">ウィザードによって、手順1の展開状態が決定された後 **。ローカル構成ストアをインストール**し、[**実行**] をクリックして、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ffe30-117">After the wizard determines the deployment state, for **Step 1. Install Local Configuration Store**, click **Run** and then do the following:</span></span>
    
      - <span data-ttu-id="ffe30-118">[**全体管理ストアのローカルレプリカの構成**] ダイアログボックスで、[**ファイルからのインポート (Edge サーバーに推奨)**] をクリックし、エクスポートされたトポロジ構成ファイルの場所に移動して、.zip ファイルを選択し、[**開く**] をクリックして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffe30-118">In the **Configure Local Replica of Central Management Store** dialog box, click **Import from a file (Recommended for Edge Servers)**, go to the location of the exported topology configuration file, select the .zip file, click **Open**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="ffe30-119">展開ウィザードは、構成ファイルから構成情報を読み取り、その XML 構成ファイルをローカルコンピューターに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="ffe30-119">The Deployment Wizard reads the configuration information from the configuration file and writes the XML configuration file to the local computer.</span></span>
    
      - <span data-ttu-id="ffe30-120">[**コマンドの実行**] プロセスが完了した後、[**終了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffe30-120">After the **Executing Commands** process is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="ffe30-121">展開ウィザードで、[**手順 2: Lync サーバーコンポーネントをセットアップまたは削除**する] をクリックして、ローカルコンピューターに保存されている XML 構成ファイルで指定されている lync server 2013 edge コンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ffe30-121">In the Deployment Wizard, click **Step 2: SetUp or Remove Lync Server Components** to install the Lync Server 2013 edge components specified in the XML configuration file that is stored on the local computer.</span></span>

7.  <span data-ttu-id="ffe30-122">インストールが完了したら、サービスを開始する前に、 [Lync Server 2013 の Edge 証明書のセットアップ](lync-server-2013-set-up-edge-certificates.md)に関する情報を使用して、必要な証明書をインストールして割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ffe30-122">After completing the installation, use the information in [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) to install and assign the required certificates before you start services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

