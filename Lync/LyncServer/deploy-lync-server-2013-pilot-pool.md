---
title: Lync Server 2013 パイロットプールの展開
description: Lync Server 2013 パイロットプールを展開します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205144(v=OCS.15)
ms:contentKeyID: 48185028
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a599cee1719f773ebbf3cf5a71405aa9b7259261
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550793"
---
# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="7ec93-103">Lync Server 2013 パイロットプールの展開</span><span class="sxs-lookup"><span data-stu-id="7ec93-103">Deploy Lync Server 2013 pilot pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ec93-104">_**トピックの最終更新日:** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="7ec93-104">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="7ec93-105">Lync Server 2013 への移行に必要な最初の手順の1つは、パイロットプールを展開することです。</span><span class="sxs-lookup"><span data-stu-id="7ec93-105">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="7ec93-106">パイロットプールは、lync server 2013 と Lync Server 2010 の展開との共存をテストする場所です。</span><span class="sxs-lookup"><span data-stu-id="7ec93-106">The pilot pool is where you test coexistence of Lync Server 2013 with your Lync Server 2010 deployment.</span></span> <span data-ttu-id="7ec93-107">共存は、すべてのユーザーとプールを Lync Server 2013 に移動するまで、一時的な状態になります。</span><span class="sxs-lookup"><span data-stu-id="7ec93-107">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="7ec93-108">パイロット プールを展開するときには、新しいフロントエンド プールの定義ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="7ec93-108">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="7ec93-109">Lync server 2010 プールにある、Lync Server 2013 パイロットプールと同じ機能とワークロードを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ec93-109">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Lync Server 2010 pool.</span></span> <span data-ttu-id="7ec93-110">アーカイブサーバー、監視サーバー、または System Center Operations Manager を使用して Lync Server 2010 環境をアーカイブまたは監視する場合に、移行を通じてアーカイブまたは監視を続行するには、これらの機能をパイロット環境に展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ec93-110">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Lync Server 2010 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="7ec93-111">Lync Server 2010 環境をアーカイブまたは監視するために展開したバージョンは、Lync Server 2013 環境のデータをキャプチャしません。</span><span class="sxs-lookup"><span data-stu-id="7ec93-111">The version you deployed to archive or monitor your Lync Server 2010 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7ec93-112">次の手順では、パイロット プール全体の展開プロセスの中で検討する必要がある機能と設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="7ec93-112">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="7ec93-113">このセクションで説明するのは、パイロット プールの展開の際に考慮が必要となる主なポイントのみです。</span><span class="sxs-lookup"><span data-stu-id="7ec93-113">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="7ec93-114">詳細な手順については、「 <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> 展開ガイドの展開ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec93-114">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="7ec93-115">**Lync Server 2013 パイロットプールを展開するには**</span><span class="sxs-lookup"><span data-stu-id="7ec93-115">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="7ec93-116">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="7ec93-116">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="7ec93-117">[ **Lync Server 2013** **Enterprise Edition フロントエンドプール**] に到達するまでツリーを展開します。</span><span class="sxs-lookup"><span data-stu-id="7ec93-117">Expand the tree until you reach **Lync Server 2013** **Enterprise Edition Front End pools**.</span></span>

3.  <span data-ttu-id="7ec93-118">[**Enterprise Edition フロントエンド プール**] を右クリックし、[**新しいフロントエンド プール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ec93-118">Right click **Enterprise Edition Front End pools**, and select **New Front End Pool**.</span></span>
    
    <span data-ttu-id="7ec93-119">![トポロジビルダーのサーバープールの選択サブメニュー](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "トポロジビルダーのサーバープールの選択サブメニュー")</span><span class="sxs-lookup"><span data-stu-id="7ec93-119">![Topology Builder Server pool selection submenu](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Topology Builder Server pool selection submenu")</span></span>

4.  <span data-ttu-id="7ec93-120">プールの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="7ec93-120">Enter the pool FQDN.</span></span> <span data-ttu-id="7ec93-121">パイロットプールを定義するときは、Enterprise Edition フロントエンドプールまたは Standard Edition サーバーを展開することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7ec93-121">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="7ec93-122">Lync Server 2013 では、パイロットプールの機能が従来のプールに展開されたものと一致している必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7ec93-122">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="7ec93-123">パイロット プールに対して定義するプールまたはサーバーの完全修飾ドメイン名 (FQDN) は一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ec93-123">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="7ec93-124">現在展開されている Lync Server 2010 プールの名前、または現在展開されている他のすべてのサーバーの名前と一致させることはできません。</span><span class="sxs-lookup"><span data-stu-id="7ec93-124">It cannot match the name of the currently deployed Lync Server 2010 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="7ec93-125">![新しいフロントエンドプールの定義ウィザード FQDN ページ](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "新しいフロントエンドプールの定義ウィザード FQDN ページ")</span><span class="sxs-lookup"><span data-stu-id="7ec93-125">![Define New Front End Pool Wizard FQDN page](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Define New Front End Pool Wizard FQDN page")</span></span>

5.  <span data-ttu-id="7ec93-126">**[機能の選択]** ページで、このフロント エンド プールで必要な機能のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="7ec93-126">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="7ec93-127">たとえば、インスタントメッセージング (IM) とプレゼンス機能のみを展開する場合は、[会議] チェックボックスをオンにしてマルチパーティ IM を許可しますが、ダイヤルイン (PSTN) 会議、エンタープライズ Voip、または通話受付管理の各チェックボックスは、音声、ビデオ、および共同作業の会議機能を表すものであるため、選択しません。</span><span class="sxs-lookup"><span data-stu-id="7ec93-127">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="7ec93-128">機能の選択の詳細については、「展開」のドキュメントの「 [Define and configure a Front End pool Or Standard Edition server In Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec93-128">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="7ec93-129">![フロントエンドプールの [機能の選択] ページ](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "フロントエンドプールの [機能の選択] ページ")</span><span class="sxs-lookup"><span data-stu-id="7ec93-129">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

6.  <span data-ttu-id="7ec93-130">[併置された **サーバーの役割の選択** ] ページで、仲介サーバーを Lync server 2013 に併置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7ec93-130">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="7ec93-131">従来のトポロジを Lync Server 2013 とマージする場合は、最初に Lync Server 2010 仲介サーバーを併置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ec93-131">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Lync Server 2010 Mediation Server.</span></span> <span data-ttu-id="7ec93-132">トポロジをマージし、Lync Server 2013 仲介サーバーを構成した後で、展開プロセスで仲介サーバーの役割を Lync Server 2013 に移動するときに、併置された仲介サーバーを保持するか、スタンドアロンサーバーに変更するかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="7ec93-132">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="7ec93-133">![フロントエンドプール [併置されたサーバーの役割の選択] ページ](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "フロントエンドプール [併置されたサーバーの役割の選択] ページ")</span><span class="sxs-lookup"><span data-stu-id="7ec93-133">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

7.  <span data-ttu-id="7ec93-p108">パイロット プールの展開時は、[**サーバーの役割とこのフロントエンド プールの関連付け**] ページで、[**このフロントエンド プールのメディア コンポーネントで使用されるエッジ プールを有効にする**] オプションを選択しないでください。これは、移行のフェーズが進んだ段階で有効にしてオンラインにする機能です。現時点ではこの設定はオフのままにしてください。</span><span class="sxs-lookup"><span data-stu-id="7ec93-p108">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option. This is a feature you will enable and bring online in a later phase of migration. Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="7ec93-137">![サーバーの役割をフロントエンドプールページと関連付ける](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "サーバーの役割をフロントエンドプールページと関連付ける")</span><span class="sxs-lookup"><span data-stu-id="7ec93-137">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

8.  <span data-ttu-id="7ec93-138">[**Office Web Apps Server の選択**] ページで [**新規作成**] をクリックし、アプリケーション サーバーの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="7ec93-138">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="7ec93-139">![新しい Office Web Apps サーバーの FQDN プロパティを定義する](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "新しい Office Web Apps サーバーの FQDN プロパティを定義する")</span><span class="sxs-lookup"><span data-stu-id="7ec93-139">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

9.  <span data-ttu-id="7ec93-140">[ **アーカイブ Sql server ストアの定義** ] ページで、lync Server のアーカイブと監視の両方のために sql server ストアを定義するときに、以前に lync server 2013 用に作成した sql server インスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ec93-140">On the **Define the Archiving SQL Server store** page, when defining the SQL Server store for both Lync Server Archiving and Monitoring, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="7ec93-141">![アーカイブ SQL Server ストアの定義ページ](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "アーカイブ SQL Server ストアの定義ページ")</span><span class="sxs-lookup"><span data-stu-id="7ec93-141">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

10. <span data-ttu-id="7ec93-142">トポロジを公開するために、[**Lync Server**] ノードを右クリックし、[**トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7ec93-142">To publish your topology, right-click the **Lync Server** node, and then click **Publish Topology**.</span></span>
    
    <span data-ttu-id="7ec93-143">![トポロジビルダー構成済みトポロジを表示する](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "トポロジビルダー構成済みトポロジを表示する")</span><span class="sxs-lookup"><span data-stu-id="7ec93-143">![Topology Builder displaying a configured topology](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Topology Builder displaying a configured topology")</span></span>

11. <span data-ttu-id="7ec93-144">公開プロセスが完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7ec93-144">When the publish process has completed, click **Finish**.</span></span>

<span data-ttu-id="7ec93-145">構成ストアのローカルコピーをインストールし、必要なサービスを開始するには、「展開」のドキュメントの「 [Setting Up Front End Servers And Front end プール For Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec93-145">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>

