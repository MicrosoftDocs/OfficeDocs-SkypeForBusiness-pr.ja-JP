---
title: 'Lync Server 2013: Standard Edition サーバー データベースのインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5cad6f67dbf1bfff1ee16dbd7455b02d904aac0d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-standard-edition-server-database-for-lync-server-2013"></a><span data-ttu-id="3d4bc-102">Lync Server 2013 の Standard Edition サーバー データベースのインストール</span><span class="sxs-lookup"><span data-stu-id="3d4bc-102">Install Standard Edition server database for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d4bc-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="3d4bc-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="3d4bc-104">インフラストラクチャ内で、標準エディションのサーバーをインフラストラクチャ内の唯一のサーバーとして設定します。これは、**展開ウィザード**で最初のサーバーを設定することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="3d4bc-104">Setting up a Standard Edition server as the only server in your infrastructure that homes users differs from other server installations in that there is a selection in the **Deployment Wizard** specifically for setting up the initial server.</span></span>

<div>

## <a name="to-install-a-standard-edition-server"></a><span data-ttu-id="3d4bc-105">Standard Edition サーバーをインストールするには</span><span class="sxs-lookup"><span data-stu-id="3d4bc-105">To install a Standard Edition server</span></span>

1.  <span data-ttu-id="3d4bc-106">Standard Edition server をインストールしようとしているサーバーに、ローカル管理者または同等のドメインとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="3d4bc-106">Log on to the server where you are going to install Standard Edition server as a local administrator or a domain equivalent.</span></span>

2.  <span data-ttu-id="3d4bc-107">Active Directory ドメインサービスの準備ができていない場合は、最初にこれらの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3d4bc-107">If you have not prepared Active Directory Domain Services, then first perform those procedures.</span></span> <span data-ttu-id="3d4bc-108">詳細については、「 [Lync Server 2013 用の Active Directory ドメインサービスの準備](lync-server-2013-preparing-active-directory-domain-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d4bc-108">For details, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

3.  <span data-ttu-id="3d4bc-109">Lync Server 展開ウィザードで、[**最初の Standard Edition サーバーの準備**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d4bc-109">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="3d4bc-110">[**単一標準エディションサーバーの準備**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d4bc-110">On the **Prepare single Standard Edition Server** page, click **Next**.</span></span>

5.  <span data-ttu-id="3d4bc-111">[**コマンドの実行**] ページで、SQL Server 2012 Express が中央管理ストアとしてインストールされています。</span><span class="sxs-lookup"><span data-stu-id="3d4bc-111">On the **Executing Commands** page, the SQL Server 2012 Express is installed as the Central Management store.</span></span> <span data-ttu-id="3d4bc-112">必要なファイアウォールルールが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3d4bc-112">Necessary firewall rules are created.</span></span> <span data-ttu-id="3d4bc-113">データベースと必須ソフトウェアのインストールが完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d4bc-113">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3d4bc-114">最初のインストールでは、コマンド出力の概要画面に表示される更新プログラムがないと、時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3d4bc-114">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="3d4bc-115">これは、SQL Server Express がインストールされているためです。</span><span class="sxs-lookup"><span data-stu-id="3d4bc-115">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="3d4bc-116">データベースのインストールを監視する必要がある場合は、タスクマネージャーを使用してセットアップを監視します。</span><span class="sxs-lookup"><span data-stu-id="3d4bc-116">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

6.  <span data-ttu-id="3d4bc-117">[Lync Server 展開ウィザード] ページで、[管理ツール] をまだインストールしていない場合は、[**トポロジビルダーのインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d4bc-117">On the Lync Server Deployment Wizard page, click **Install Topology Builder** if you have not previously installed the administrative tools.</span></span> <span data-ttu-id="3d4bc-118">詳細については、「 [Lync Server 2013 管理ツールをインストール](lync-server-2013-install-lync-server-administrative-tools.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d4bc-118">For details, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

7.  <span data-ttu-id="3d4bc-119">[Active Directory の準備] の横に緑色のチェックマークが表示されていることを確認します。 "最初の Standard Edition サーバーの準備" と "トポロジビルダーのインストール" を確認してください。</span><span class="sxs-lookup"><span data-stu-id="3d4bc-119">Confirm that there are green check marks next to “Prepare Active Directory,” “Prepare first Standard Edition server,” and “Install Topology Builder.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

