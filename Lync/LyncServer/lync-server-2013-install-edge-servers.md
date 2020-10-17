---
title: 'Lync Server 2013: エッジサーバーのインストール'
description: 'Lync Server 2013: エッジサーバーをインストールします。'
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
ms.openlocfilehash: e699a7f41b0ee554bc85fb2d9a72a2d9a42870cb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559583"
---
# <a name="install-edge-servers-for-lync-server-2013"></a><span data-ttu-id="91c53-103">Lync Server 2013 のエッジサーバーのインストール</span><span class="sxs-lookup"><span data-stu-id="91c53-103">Install Edge Servers for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91c53-104">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="91c53-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="91c53-105">[Lync server 展開ウィザード] を使用して、エッジサーバーに Lync Server 2013 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="91c53-105">You install Lync Server 2013 on Edge Servers by using Lync Server Deployment Wizard.</span></span> <span data-ttu-id="91c53-106">各エッジ サーバーで展開ウィザードを実行することにより、エッジ サーバーのセットアップに必要なタスクの大部分を完了できます。</span><span class="sxs-lookup"><span data-stu-id="91c53-106">By running the Deployment Wizard on each Edge Server, you can complete most of the tasks required to set up the Edge Server.</span></span> <span data-ttu-id="91c53-107">エッジサーバーに Lync Server 2013 を展開するには、既にトポロジビルダーを実行している必要があります。これにより、エッジサーバートポロジを定義して発行し、エッジサーバーから使用可能なメディアにエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="91c53-107">In order to deploy Lync Server 2013 on an Edge Server, you must have already run Topology Builder to define and publish your Edge Server topology, and exported it to media that is available from the Edge Server.</span></span> <span data-ttu-id="91c53-108">詳細については、「 [Lync server 2013 の外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md) 」および「 [lync server 2013 トポロジをエクスポートして、エッジインストール用の外部メディアにコピーする](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91c53-108">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<span data-ttu-id="91c53-109">展開ウィザードを使用して各エッジサーバーをインストールし、必要な証明書をインストールして割り当て、必要なサービスを開始するには、「 [Lync server 2013 2013 での外部ユーザーアクセスのサポートの構成](lync-server-2013-configuring-support-for-external-user-access.md)」に記載されている情報を[Verifying your edge deployment in Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md)使用して設定を完了します。この情報を使用して、セットアップを検証します (サーバーとクライアントの</span><span class="sxs-lookup"><span data-stu-id="91c53-109">After using the Deployment Wizard to install each Edge Server, install and assign the required certificates, and start the required services, you can complete the setup by using the information in [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) to enable and configure external user access and the information in [Verifying your edge deployment in Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md) to validate the setup, including server and client connectivity.</span></span>

<div>

## <a name="to-install-an-edge-server"></a><span data-ttu-id="91c53-110">エッジ サーバーをインストールするには</span><span class="sxs-lookup"><span data-stu-id="91c53-110">To install an Edge Server</span></span>

1.  <span data-ttu-id="91c53-111">Administrators グループのメンバーとして、または同等の権限およびアクセス権を有するアカウントとして、エッジ サーバーをインストールするコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="91c53-111">Log on to the computer on which you want to install your Edge Server as a member of the local Administrators group or an account with equivalent user rights and permissions.</span></span>

2.  <span data-ttu-id="91c53-112">トポロジビルダーを使用して作成したトポロジ構成ファイルがエッジサーバーで使用できることを確認します (たとえば、トポロジ構成ファイルをコピーした USB ドライブにアクセスするか、またはファイルをコピーしたネットワーク共有へのアクセスを確認します)。</span><span class="sxs-lookup"><span data-stu-id="91c53-112">Ensure that the topology configuration file you created using Topology Builder, and then exported and copied to external media, is available on the Edge Server (for example, access to the USB drive onto which you copied the topology configuration file, or verify access to the network share where you copied the file).</span></span>

3.  <span data-ttu-id="91c53-113">展開ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="91c53-113">Start the Deployment Wizard.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="91c53-p102">Microsoft Visual C++ (再頒布可能) をインストール必要があるというメッセージが表示されたら、[<STRONG>はい</STRONG>] をクリックします。 次のダイアログ ボックスで、既定の [<STRONG>インストール先</STRONG>] をそのまま使用するか、または [<STRONG>参照</STRONG>] をクリックして別のロケーションを選択し、[<STRONG>インストール</STRONG>] をクリックします。 次のダイアログ ボックスで、[<STRONG>使用許諾契約書に同意します</STRONG>] チェック ボックスをオンにし、[<STRONG>OK</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="91c53-p102">If you get a message saying that you need to install Microsoft Visual C++ Redistributable, click <STRONG>Yes</STRONG>. In the next dialog box, you can accept the default <STRONG>Installation Location</STRONG> or click the <STRONG>Browse</STRONG> to select an alternate location, and then click <STRONG>Install</STRONG>. In the next dialog box, select the <STRONG>I accept the terms in the license agreement</STRONG> check box, and then click <STRONG>OK</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="91c53-117">展開ウィザードで、[**Lync Server システムのインストールまたは更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="91c53-117">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="91c53-118">ウィザードが展開状態を判別した後、[**手順 1: ローカル構成ストアのインストール**] で [**実行**] をクリックし、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="91c53-118">After the wizard determines the deployment state, for **Step 1. Install Local Configuration Store**, click **Run** and then do the following:</span></span>
    
      - <span data-ttu-id="91c53-119">[**中央管理ストアのローカル レプリカの構成**] ダイアログ ボックスで、[**ファイルからインポートする (エッジ サーバーで推奨)**] をクリックします。エクスポートしたトポロジ構成ファイルのロケーションに進み、.zip ファイルを選択し、[**開く**] をクリックします。そして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="91c53-119">In the **Configure Local Replica of Central Management Store** dialog box, click **Import from a file (Recommended for Edge Servers)**, go to the location of the exported topology configuration file, select the .zip file, click **Open**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="91c53-120">展開ウィザードが構成ファイルから構成情報を読み取り、ローカル コンピューターへ XML 構成ファイルを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="91c53-120">The Deployment Wizard reads the configuration information from the configuration file and writes the XML configuration file to the local computer.</span></span>
    
      - <span data-ttu-id="91c53-121">[**コマンドの実行**] プロセスが完了した後、[**終了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="91c53-121">After the **Executing Commands** process is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="91c53-122">展開ウィザードで、[ **ステップ 2: Lync Server コンポーネントのセットアップまたは削除** ] をクリックして、ローカルコンピューターに格納されている XML 構成ファイルに指定されている lync server 2013 エッジコンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="91c53-122">In the Deployment Wizard, click **Step 2: SetUp or Remove Lync Server Components** to install the Lync Server 2013 edge components specified in the XML configuration file that is stored on the local computer.</span></span>

7.  <span data-ttu-id="91c53-123">インストールが完了したら、「 [Set Up Edge certificates For Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) 」の情報を使用して、サービスを開始する前に必要な証明書をインストールして割り当てます。</span><span class="sxs-lookup"><span data-stu-id="91c53-123">After completing the installation, use the information in [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) to install and assign the required certificates before you start services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

