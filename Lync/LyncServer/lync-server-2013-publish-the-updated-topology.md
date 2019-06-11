---
title: 'Lync Server 2013: 更新したトポロジの公開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish the updated topology
ms:assetid: 59455dd1-6a9e-433f-a714-d3636c068100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204910(v=OCS.15)
ms:contentKeyID: 48184203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9f3be1443f98444712a66942417e1812181efe7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823890"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a><span data-ttu-id="813ab-102">Lync Server 2013 での更新したトポロジの公開</span><span class="sxs-lookup"><span data-stu-id="813ab-102">Publish the updated topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="813ab-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="813ab-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="813ab-104">トポロジビルダーでトポロジを更新した後は、常設チャットサーバーを構成して使用する前に、トポロジを中央管理ストアに発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="813ab-104">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Persistent Chat Server.</span></span> <span data-ttu-id="813ab-105">このデータの読み取り専用コピーはトポロジ内のすべてのサーバーにレプリケートされ、すべてのサーバーは、トポロジおよび他の構成の変更と同期された状態で維持されます。</span><span class="sxs-lookup"><span data-stu-id="813ab-105">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-an-updated-topology"></a><span data-ttu-id="813ab-106">更新されたトポロジを公開するには</span><span class="sxs-lookup"><span data-stu-id="813ab-106">To publish an updated topology</span></span>

<span data-ttu-id="813ab-107">トポロジを公開する前に、常設チャットサーバー用のデータベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="813ab-107">Before you publish your topology, install the databases for Persistent Chat Server.</span></span> <span data-ttu-id="813ab-108">[**アクション**]、[**データベースのインストール**] の順に選択して、トポロジビルダーを使用してデータベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="813ab-108">Use Topology Builder to install databases by selecting **Action** and **Install Database**.</span></span>

1.  <span data-ttu-id="813ab-109">Lync Server 2013 を実行しているか、Lync Server 管理ツールがインストールされているコンピューターの場合は、**ドメイン管理**者グループと**RTCUniversalServerAdmins**グループの両方のメンバーであるアカウントを使用してログオンします。フルコントロールがあります。常設チャットサーバーファイルストアで使用するアクセス許可 (読み取り、書き込み、変更) (Topology Builder では、必要な随意アクセス制御リスト (Dacl))、または同等のユーザー権限を持つアカウントを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="813ab-109">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of both the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file store to be used for the Persistent Chat Server file store (so that Topology Builder can configure the required discretionary access control lists (DACLs)), or an account with equivalent user rights.</span></span>

2.  <span data-ttu-id="813ab-110">トポロジビルダーを起動します。</span><span class="sxs-lookup"><span data-stu-id="813ab-110">Start Topology Builder.</span></span> <span data-ttu-id="813ab-111">[**既存の展開からトポロジをダウンロード**] を選択するか、**ローカルファイル**をローカルで保存した場合は、[トポロジを開く] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="813ab-111">Select **Download Topology from existing deployment**, or **Open Topology from a local file** if you saved it locally.</span></span>

3.  <span data-ttu-id="813ab-112">コンソールツリーで、[ **Lync Server 2013**] を右クリックし、[**トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="813ab-112">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="813ab-113">[**トポロジの公開**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="813ab-113">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="813ab-114">[**公開ウィザードの完了**] ページで、トポロジが正常に公開されたことを確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="813ab-114">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="813ab-115">トポロジを公開した後は、コンテンツをアーカイブする前に、常設チャットサーバーのサポートを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="813ab-115">After publishing the topology, you must configure support for Persistent Chat Server before any content can be archived.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

