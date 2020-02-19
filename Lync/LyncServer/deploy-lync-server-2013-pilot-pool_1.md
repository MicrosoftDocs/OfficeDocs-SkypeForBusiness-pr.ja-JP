---
title: Lync Server 2013 パイロットプールの展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: 19c27053-8b21-401f-ad91-75c2dd355e91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204718(v=OCS.15)
ms:contentKeyID: 48183539
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95ce311b5b7c47343c3ec72bf63a7d1b96cf9839
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="d1b34-102">Lync Server 2013 パイロットプールの展開</span><span class="sxs-lookup"><span data-stu-id="d1b34-102">Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1b34-103">_**トピックの最終更新日:** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="d1b34-103">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="d1b34-104">Lync Server 2013 への移行に必要な最初の手順の1つは、パイロットプールを展開することです。</span><span class="sxs-lookup"><span data-stu-id="d1b34-104">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="d1b34-105">パイロットプールは、Office Communications Server 2007 R2 展開と Lync Server 2013 の共存をテストする場所です。</span><span class="sxs-lookup"><span data-stu-id="d1b34-105">The pilot pool is where you test coexistence of Lync Server 2013 with your Office Communications Server 2007 R2 deployment.</span></span> <span data-ttu-id="d1b34-106">共存は、すべてのユーザーとプールを Lync Server 2013 に移動するまで、一時的な状態になります。</span><span class="sxs-lookup"><span data-stu-id="d1b34-106">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="d1b34-107">パイロット プールを展開するときには、新しいフロントエンド プールの定義ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="d1b34-107">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="d1b34-108">Office Communications Server 2007 R2 プールにある Lync Server 2013 パイロットプールに、同じ機能とワークロードを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1b34-108">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="d1b34-109">アーカイブサーバー、監視サーバー、または System Center Operations Manager を使用して Office Communications Server 2007 R2 環境のアーカイブまたは監視を行っていて、移行を通じてアーカイブまたは監視を続行する必要がある場合は、また、これらの機能をパイロット環境に展開します。</span><span class="sxs-lookup"><span data-stu-id="d1b34-109">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Office Communications Server 2007 R2 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="d1b34-110">Office Communications Server 2007 R2 環境をアーカイブまたは監視するために展開したバージョンでは、Lync Server 2013 環境のデータはキャプチャされません。</span><span class="sxs-lookup"><span data-stu-id="d1b34-110">The version you deployed to archive or monitor your Office Communications Server 2007 R2 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d1b34-111">次の手順では、パイロット プール全体の展開プロセスの中で検討する必要がある機能と設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1b34-111">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="d1b34-112">このセクションで説明するのは、パイロット プールの展開の際に考慮が必要となる主なポイントのみです。</span><span class="sxs-lookup"><span data-stu-id="d1b34-112">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="d1b34-113">詳細な手順については、「 <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A>展開ガイドの展開ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1b34-113">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="d1b34-114">**Lync Server 2013 パイロットプールを展開するには**</span><span class="sxs-lookup"><span data-stu-id="d1b34-114">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="d1b34-115">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="d1b34-115">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="d1b34-116">トポロジ ビルダーを開き、トポロジの新規作成を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1b34-116">Open Topology Builder and choose to create a new topology.</span></span>

3.  <span data-ttu-id="d1b34-117">プライマリ SIP ドメインを入力します。</span><span class="sxs-lookup"><span data-stu-id="d1b34-117">Enter the primary SIP domain.</span></span>
    
    <span data-ttu-id="d1b34-118">![新しいトポロジの作成、プライマリドメインページの定義](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "新しいトポロジの作成、プライマリドメインページの定義")</span><span class="sxs-lookup"><span data-stu-id="d1b34-118">![Create New Topology, Define primary domain page](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Create New Topology, Define primary domain page")</span></span>

4.  <span data-ttu-id="d1b34-119">**新しいフロントエンド プールの定義**ウィザードに達するまで、ウィザードの入力を続けます。</span><span class="sxs-lookup"><span data-stu-id="d1b34-119">Continue completing the wizard until you reach the **Define the New Front End pool** wizard.</span></span> <span data-ttu-id="d1b34-120">[次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1b34-120">Click Next.</span></span>

5.  <span data-ttu-id="d1b34-121">プールの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="d1b34-121">Enter the pool FQDN.</span></span> <span data-ttu-id="d1b34-122">パイロットプールを定義するときは、Enterprise Edition フロントエンドプールまたは Standard Edition サーバーを展開することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d1b34-122">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="d1b34-123">Lync Server 2013 では、パイロットプールの機能が従来のプールに展開されたものと一致している必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d1b34-123">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d1b34-124">パイロット プールに対して定義するプールまたはサーバーの完全修飾ドメイン名 (FQDN) は一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1b34-124">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="d1b34-125">現在展開されている Office Communications Server 2007 R2 プールの名前、または現在展開されている他のすべてのサーバーの名前と一致させることはできません。</span><span class="sxs-lookup"><span data-stu-id="d1b34-125">It cannot match the name of the currently deployed Office Communications Server 2007 R2 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="d1b34-126">![フロントエンドプールの FQDN ページを定義する](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "フロントエンドプールの FQDN ページを定義する")</span><span class="sxs-lookup"><span data-stu-id="d1b34-126">![Define the Front End pool FQDN page](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Define the Front End pool FQDN page")</span></span>

6.  <span data-ttu-id="d1b34-127">プールに追加されるコンピューターを定義します。</span><span class="sxs-lookup"><span data-stu-id="d1b34-127">Define the computer that will be added to the pool.</span></span>
    
    <span data-ttu-id="d1b34-128">![[新しいフロントエンドプールの定義] ダイアログ](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "[新しいフロントエンドプールの定義] ダイアログ")</span><span class="sxs-lookup"><span data-stu-id="d1b34-128">![Define New Front End Pool dialog](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Define New Front End Pool dialog")</span></span>

7.  <span data-ttu-id="d1b34-129">**[機能の選択]** ページで、このフロント エンド プールで必要な機能のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d1b34-129">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="d1b34-130">たとえば、インスタントメッセージング (IM) とプレゼンス機能のみを展開する場合は、[会議] チェックボックスをオンにしてマルチパーティ IM を許可しますが、ダイヤルイン (PSTN) 会議、エンタープライズ Voip、または通話受付管理のチェックボックスは選択しません。音声、ビデオ、および共同作業の会議機能を表すからです。</span><span class="sxs-lookup"><span data-stu-id="d1b34-130">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="d1b34-131">機能の選択の詳細については、「展開」のドキュメントの「 [Define and configure a Front End pool Or Standard Edition server In Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1b34-131">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="d1b34-132">![フロントエンドプールの [機能の選択] ページ](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "フロントエンドプールの [機能の選択] ページ")</span><span class="sxs-lookup"><span data-stu-id="d1b34-132">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

8.  <span data-ttu-id="d1b34-133">[併置された**サーバーの役割の選択**] ページで、仲介サーバーを Lync server 2013 に併置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d1b34-133">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="d1b34-134">従来のトポロジを Lync Server 2013 とマージする場合は、最初に Office Communications Server 2007 R2 仲介サーバーを併置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1b34-134">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Office Communications Server 2007 R2 Mediation Server.</span></span> <span data-ttu-id="d1b34-135">トポロジをマージし、Lync Server 2013 仲介サーバーを構成した後で、仲介サーバーの役割を後で Lync Server 2013 に移動するときに、併置された仲介サーバーを保持するか、スタンドアロンサーバーに変更するかを決定できます。手順.</span><span class="sxs-lookup"><span data-stu-id="d1b34-135">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="d1b34-136">![フロントエンドプール [併置されたサーバーの役割の選択] ページ](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "フロントエンドプール [併置されたサーバーの役割の選択] ページ")</span><span class="sxs-lookup"><span data-stu-id="d1b34-136">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

9.  <span data-ttu-id="d1b34-p109">パイロット プールの展開時は、[**サーバーの役割とこのフロントエンド プールの関連付け**] ページで、[**このフロントエンド プールのメディア コンポーネントで使用されるエッジ プールを有効にする**] オプションを選択しないでください。これは、移行のフェーズが進んだ段階で有効にしてオンラインにする機能です。現時点ではこの設定はオフのままにしてください。</span><span class="sxs-lookup"><span data-stu-id="d1b34-p109">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option. This is a feature you will enable and bring online in a later phase of migration. Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="d1b34-140">![サーバーの役割をフロントエンドプールページと関連付ける](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "サーバーの役割をフロントエンドプールページと関連付ける")</span><span class="sxs-lookup"><span data-stu-id="d1b34-140">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

10. <span data-ttu-id="d1b34-141">[**Office Web Apps Server の選択**] ページで [**新規作成**] をクリックし、アプリケーション サーバーの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="d1b34-141">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="d1b34-142">![新しい Office Web Apps サーバーの FQDN プロパティを定義する](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "新しい Office Web Apps サーバーの FQDN プロパティを定義する")</span><span class="sxs-lookup"><span data-stu-id="d1b34-142">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

11. <span data-ttu-id="d1b34-143">[**アーカイブ SQL Server ストアの定義**] ページで、以前に Lync Server 2013 用に作成した sql server インスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="d1b34-143">On the **Define the Archiving SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="d1b34-144">![アーカイブ SQL Server ストアの定義ページ](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "アーカイブ SQL Server ストアの定義ページ")</span><span class="sxs-lookup"><span data-stu-id="d1b34-144">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

12. <span data-ttu-id="d1b34-145">[**監視 SQL server ストアの定義**] ページで、以前に Lync Server 2013 用に作成した sql server インスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="d1b34-145">On the **Define the Monitoring SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span> <span data-ttu-id="d1b34-146">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1b34-146">Click **Finish**.</span></span>

13. <span data-ttu-id="d1b34-p111">トポロジ ビルダーの最上位ノードで、[**Lync Server**] を右クリックし、[**プロパティの編集**] をクリックします。[**簡易 URL**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1b34-p111">From the top node of Topology Builder, right click **Lync Server** and click **Edit Properties.** Click **Simple URLs**.</span></span>

14. <span data-ttu-id="d1b34-149">[**管理アクセス URL**] を更新します。</span><span class="sxs-lookup"><span data-stu-id="d1b34-149">Update the **Administrative access URL**.</span></span>
    
    <span data-ttu-id="d1b34-150">![[プロパティの編集]、[簡易 Url] ページ](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "[プロパティの編集]、[簡易 Url] ページ")</span><span class="sxs-lookup"><span data-stu-id="d1b34-150">![Edit Properties, Simple URLs page](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Edit Properties, Simple URLs page")</span></span>
    
    <span data-ttu-id="d1b34-151">簡易 Url の詳細については、「展開」のドキュメントの「 [Edit or configure Simple urls In Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1b34-151">For additional information on Simple URLs, see the topic [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

15. <span data-ttu-id="d1b34-152">[**プロパティの編集**] で、[**中央管理サーバー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1b34-152">From the **Edit Properties**, click **Central Management Server**.</span></span>

16. <span data-ttu-id="d1b34-153">ドロップダウンリストから、[Lync Server 2013] プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="d1b34-153">From the drop-down list, select the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="d1b34-154">![[プロパティの編集]、[中央管理サーバー] ページ](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "[プロパティの編集]、[中央管理サーバー] ページ")</span><span class="sxs-lookup"><span data-stu-id="d1b34-154">![Edit Properties, Central Management Server page](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Edit Properties, Central Management Server page")</span></span>

17. <span data-ttu-id="d1b34-155">[OK] をクリックして、[**プロパティの編集**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d1b34-155">Click OK to close **the Edit Properties** page.</span></span>

18. <span data-ttu-id="d1b34-156">[**アクション**] メニューの [**トポロジの公開**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1b34-156">From the **Action** menu, select **Publish Topology**.</span></span>

19. <span data-ttu-id="d1b34-157">公開プロセスが完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1b34-157">When the publish process has completed, click **Finish**.</span></span>

20. <span data-ttu-id="d1b34-158">Lync Server 2013 展開ウィザードに戻り、[ **Lync Server システムのインストールまたは更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1b34-158">Returning to the Lync Server 2013 Deployment Wizard, click **Install or Update Lync Server System**.</span></span>
    
    <span data-ttu-id="d1b34-159">![Lync Server 2013 展開ウィザード](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013 展開ウィザード")</span><span class="sxs-lookup"><span data-stu-id="d1b34-159">![Lync Server 2013 Deployment Wizard](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013 Deployment Wizard")</span></span>

<span data-ttu-id="d1b34-160">構成ストアのローカルコピーをインストールし、必要なサービスを開始するには、「展開」のドキュメントの「 [Setting Up Front End Servers And Front end プール For Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1b34-160">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>

