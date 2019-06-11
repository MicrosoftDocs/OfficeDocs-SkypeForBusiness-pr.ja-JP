---
title: 'Lync Server 2013: Lync Server のサーバー コンポーネントのインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install Lync Server server components
ms:assetid: 186aed6e-7adf-4a92-9f2e-f9a4de5ff202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398239(v=OCS.15)
ms:contentKeyID: 48183528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 895047715bfa632970adbabb20311d8c68182499
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-server-components-for-lync-server-2013"></a><span data-ttu-id="407d4-102">Lync Server 2013 のサーバー コンポーネントのインストール</span><span class="sxs-lookup"><span data-stu-id="407d4-102">Install server components for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="407d4-103">_**最終更新日:** 2014-05-05_</span><span class="sxs-lookup"><span data-stu-id="407d4-103">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="407d4-104">以下の手順を実行する前に、ローカル管理者と、Active Directory の RTCUniversalReadOnlyAdmins グループのメンバーの両方のドメインユーザーアカウントでサーバーにログオンしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="407d4-104">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmins group in Active Directory.</span></span>

<span data-ttu-id="407d4-105">Lync Server 展開ウィザードを使って、各 Lync server の役割に必要なコンポーネントをインストールし、サーバーをアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="407d4-105">The Lync Server Deployment Wizard is used to install the needed components for each Lync server role and to activate the server.</span></span> <span data-ttu-id="407d4-106">この記事では、Lync インフラストラクチャに Standard Edition サーバーまたはフロントエンドサーバーを展開する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="407d4-106">This article walks you through the steps of deploying a Standard Edition server or a Front End Server in your Lync infrastructure.</span></span>

<div>

## <a name="to-install-lync-server-components"></a><span data-ttu-id="407d4-107">Lync Server コンポーネントをインストールするには</span><span class="sxs-lookup"><span data-stu-id="407d4-107">To install Lync Server components</span></span>

1.  <span data-ttu-id="407d4-108">Lync Server 展開ウィザードが実行されていない場合は、Lync をインストールするサーバーで起動します。</span><span class="sxs-lookup"><span data-stu-id="407d4-108">If the Lync Server Deployment Wizard isn’t running, start it on the server you want to install Lync onto.</span></span>

2.  <span data-ttu-id="407d4-109">[ **Lync Server System のインストールまたは更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="407d4-109">Click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="407d4-110">展開ウィザードで、[**手順 1: ローカル構成ストアをインストール**する] が緑のチェックマークであることを確認します。つまり、このサーバーには、ストアのローカルコピーが正常にインストールされていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="407d4-110">In the Deployment Wizard, confirm that **Step 1: Install Local Configuration Store** has a green check mark, which means that this server has a local copy of the store installed successfully.</span></span> <span data-ttu-id="407d4-111">オンになっていない場合は、サーバーにローカル構成ストアをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="407d4-111">If it’s not checked, you need to install the Local Configuration store on the server.</span></span> <span data-ttu-id="407d4-112">「 [Lync Server 2013 でローカル構成ストアをインストールする」](lync-server-2013-install-the-local-configuration-store.md)の手順に従って、ここに戻ります。</span><span class="sxs-lookup"><span data-stu-id="407d4-112">Follow the steps at [Install the Local Configuration store in Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) and then come back here.</span></span>

4.  <span data-ttu-id="407d4-113">サーバーに Lync Server 2013 コンポーネントをインストールする準備ができたら、「**手順 2: Lync Server コンポーネントをセットアップまたは削除**する」の横にある [**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="407d4-113">When you’re ready to install the Lync Server 2013 components on your server, click **Run** next to **Step 2: Setup or Remove Lync Server Components**.</span></span>

5.  <span data-ttu-id="407d4-114">[ **Lync Server コンポーネントのセットアップ**] ページで、[**次**へ] をクリックして、公開したトポロジで定義されたコンポーネントをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="407d4-114">On the **Set Up Lync Server Components** page, click **Next** to set up components as defined in your published topology.</span></span>

6.  <span data-ttu-id="407d4-115">[**コマンドの実行**] ページには、セットアップが行われるときのコマンドとインストール情報の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="407d4-115">The **Executing Commands** page will display a summary of commands and installation information as the set up takes place.</span></span> <span data-ttu-id="407d4-116">終了したら、表示するログをリストから選び、[**ログの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="407d4-116">When it’s done, you can use the list to select a log to view, and then click **View Log**.</span></span>

7.  <span data-ttu-id="407d4-117">Lync Server 2013 コンポーネントのセットアップが完了し、必要に応じてログを確認したら、[**完了**] をクリックして、インストールの手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="407d4-117">When Lync Server 2013 components setup is done, and you’ve reviewed the logs as needed, click **Finish** to complete this step in the installation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="407d4-118">サーバーを再起動するように求めるメッセージが表示された場合 (インストールする必要がある場合に発生する場合があります) は、そのようなことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="407d4-118">If you’re prompted to restart the server (which might happen if Windows Desktop Experience needed to be installed), definitely do that.</span></span> <span data-ttu-id="407d4-119">コンピューターがバックアップされて実行されている場合は、上記の手順3を実行してから、上記の手順をもう一度実行する必要があります (基本的に、展開ウィザードで手順2を実行します)。</span><span class="sxs-lookup"><span data-stu-id="407d4-119">When the computer is back up and running, you need to do these steps over again, starting from step three listed above (basically run Step 2 in the Deployment Wizard one more time).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

