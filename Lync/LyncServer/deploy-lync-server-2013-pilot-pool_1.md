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
ms.openlocfilehash: 46e6d4bd34c20038e430323b0f78ccf4f918aa62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="842eb-102">Lync Server 2013 パイロットプールの展開</span><span class="sxs-lookup"><span data-stu-id="842eb-102">Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="842eb-103">_**最終更新日:** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="842eb-103">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="842eb-104">Lync Server 2013 への移行に必要な最初の手順の1つは、パイロットプールを展開することです。</span><span class="sxs-lookup"><span data-stu-id="842eb-104">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="842eb-105">パイロットプールは、Lync Server 2013 と Office Communications Server 2007 R2 の展開との共存をテストする場所です。</span><span class="sxs-lookup"><span data-stu-id="842eb-105">The pilot pool is where you test coexistence of Lync Server 2013 with your Office Communications Server 2007 R2 deployment.</span></span> <span data-ttu-id="842eb-106">[共存] は、すべてのユーザーとプールを Lync Server 2013 に移動するまで継続して使用できます。</span><span class="sxs-lookup"><span data-stu-id="842eb-106">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="842eb-107">パイロットプールを展開する場合は、[新しいフロントエンドプールの定義] ウィザードを使います。</span><span class="sxs-lookup"><span data-stu-id="842eb-107">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="842eb-108">Lync Server 2013 パイロットプールで、Office Communications Server 2007 R2 プールにあるものと同じ機能とワークロードを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="842eb-108">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="842eb-109">Office Communications Server 2007 R2 環境をアーカイブまたは監視するためにアーカイブサーバー、監視サーバー、または System Center Operations Manager を展開していて、移行を通じてアーカイブまたは監視を継続する場合は、パイロット環境でも、これらの機能が展開されます。</span><span class="sxs-lookup"><span data-stu-id="842eb-109">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Office Communications Server 2007 R2 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="842eb-110">Office Communications Server 2007 R2 環境をアーカイブまたは監視するために展開したバージョンでは、Lync Server 2013 環境のデータはキャプチャされません。</span><span class="sxs-lookup"><span data-stu-id="842eb-110">The version you deployed to archive or monitor your Office Communications Server 2007 R2 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="842eb-111">次の手順では、パイロットプールの全体的な展開プロセスの一部として考慮する必要がある機能と設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="842eb-111">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="842eb-112">このセクションでは、パイロットプールの展開の一部として考慮する必要がある重要なポイントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="842eb-112">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="842eb-113">詳細な手順については、「 <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A>展開ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="842eb-113">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="842eb-114">**Lync Server 2013 パイロットプールを展開するには**</span><span class="sxs-lookup"><span data-stu-id="842eb-114">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="842eb-115">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="842eb-115">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="842eb-116">トポロジビルダーを開き、新しいトポロジの作成を選択します。</span><span class="sxs-lookup"><span data-stu-id="842eb-116">Open Topology Builder and choose to create a new topology.</span></span>

3.  <span data-ttu-id="842eb-117">プライマリ SIP ドメインを入力します。</span><span class="sxs-lookup"><span data-stu-id="842eb-117">Enter the primary SIP domain.</span></span>
    
    <span data-ttu-id="842eb-118">![新しいトポロジを作成し、プライマリドメインページを定義する](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "新しいトポロジを作成し、プライマリドメインページを定義する")</span><span class="sxs-lookup"><span data-stu-id="842eb-118">![Create New Topology, Define primary domain page](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Create New Topology, Define primary domain page")</span></span>

4.  <span data-ttu-id="842eb-119">[**新しいフロントエンドプールの定義**] ウィザードが表示されるまで、ウィザードの手順を続行します。</span><span class="sxs-lookup"><span data-stu-id="842eb-119">Continue completing the wizard until you reach the **Define the New Front End pool** wizard.</span></span> <span data-ttu-id="842eb-120">[ 次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="842eb-120">Click Next.</span></span>

5.  <span data-ttu-id="842eb-121">プールの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="842eb-121">Enter the pool FQDN.</span></span> <span data-ttu-id="842eb-122">パイロットプールを定義する場合は、Enterprise Edition のフロントエンドプールまたは Standard Edition サーバーを展開することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="842eb-122">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="842eb-123">Lync Server 2013 では、パイロットプールの機能が、従来のプールに展開されたものと一致する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="842eb-123">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="842eb-124">パイロットプールに対して定義するプールまたはサーバーの完全修飾ドメイン名 (FQDN) は一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="842eb-124">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="842eb-125">現在展開されている Office Communications Server 2007 R2 プール、または現在展開されているその他のサーバーの名前と一致させることはできません。</span><span class="sxs-lookup"><span data-stu-id="842eb-125">It cannot match the name of the currently deployed Office Communications Server 2007 R2 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="842eb-126">![フロントエンドプールの FQDN ページを定義する](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "フロントエンドプールの FQDN ページを定義する")</span><span class="sxs-lookup"><span data-stu-id="842eb-126">![Define the Front End pool FQDN page](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Define the Front End pool FQDN page")</span></span>

6.  <span data-ttu-id="842eb-127">プールに追加されるコンピューターを定義します。</span><span class="sxs-lookup"><span data-stu-id="842eb-127">Define the computer that will be added to the pool.</span></span>
    
    <span data-ttu-id="842eb-128">![[新しいフロントエンドプールの定義] ダイアログ](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "[新しいフロントエンドプールの定義] ダイアログ")</span><span class="sxs-lookup"><span data-stu-id="842eb-128">![Define New Front End Pool dialog](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Define New Front End Pool dialog")</span></span>

7.  <span data-ttu-id="842eb-129">**[機能の選択**] ページで、このフロントエンドプールに必要な機能のチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="842eb-129">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="842eb-130">たとえば、インスタントメッセージング (IM) とプレゼンス機能のみを展開している場合、[会議] チェックボックスをオンにして、マルチパーティ IM を許可しますが、ダイヤルイン (PSTN) 会議、エンタープライズボイス、または通話受付制御のチェックボックスは選択しません。音声、ビデオ、および共同作業の会議機能を表します。</span><span class="sxs-lookup"><span data-stu-id="842eb-130">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="842eb-131">機能の選択の詳細については、展開ドキュメントの「 [Lync server 2013 でのフロントエンドプールまたは Standard Edition サーバーの定義と構成](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="842eb-131">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="842eb-132">![フロントエンドプールの [機能] ページ](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "フロントエンドプールの [機能] ページ")</span><span class="sxs-lookup"><span data-stu-id="842eb-132">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

8.  <span data-ttu-id="842eb-133">**[併置**されたサーバーの役割の選択] ページで、Lync server 2013 で仲介サーバーを検索することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="842eb-133">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="842eb-134">従来のトポロジを Lync Server 2013 と統合する場合は、最初に Office Communications Server 2007 R2 仲介サーバーを検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="842eb-134">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Office Communications Server 2007 R2 Mediation Server.</span></span> <span data-ttu-id="842eb-135">トポロジをマージして Lync Server 2013 仲介サーバーを構成した後、展開後に仲介サーバーの役割を Lync Server 2013 に移行するときに、併置された仲介サーバーを保持するか、スタンドアロンサーバーに変更するかを決定できます。プロセス.</span><span class="sxs-lookup"><span data-stu-id="842eb-135">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="842eb-136">![フロントエンドプール [併置したサーバーの役割] ページを選択する](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "フロントエンドプール [併置したサーバーの役割] ページを選択する")</span><span class="sxs-lookup"><span data-stu-id="842eb-136">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

9.  <span data-ttu-id="842eb-137">パイロットプールの展開中に、[**サーバーの役割をこのフロントエンドプールに関連付ける**] ページで、[**このフロントエンドプールのメディアコンポーネントで使用するエッジプールを有効**にする] オプションを選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="842eb-137">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option.</span></span> <span data-ttu-id="842eb-138">これは、移行の後のフェーズで有効にしてオンラインにする機能です。</span><span class="sxs-lookup"><span data-stu-id="842eb-138">This is a feature you will enable and bring online in a later phase of migration.</span></span> <span data-ttu-id="842eb-139">ここでは、この設定をオフのままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="842eb-139">Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="842eb-140">![サーバーの役割をフロントエンドプールページに関連付ける](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "サーバーの役割をフロントエンドプールページに関連付ける")</span><span class="sxs-lookup"><span data-stu-id="842eb-140">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

10. <span data-ttu-id="842eb-141">[ **Office Web Apps サーバーを選択**してください] ページで、[**新規**] をクリックし、アプリケーションサーバーの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="842eb-141">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="842eb-142">![新しい Office Web Apps サーバーの FQDN プロパティを定義する](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "新しい Office Web Apps サーバーの FQDN プロパティを定義する")</span><span class="sxs-lookup"><span data-stu-id="842eb-142">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

11. <span data-ttu-id="842eb-143">[**アーカイブ SQL Server ストアの定義**] ページで、以前に Lync Server 2013 用に作成した SQL server インスタンスを選びます。</span><span class="sxs-lookup"><span data-stu-id="842eb-143">On the **Define the Archiving SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="842eb-144">![アーカイブ SQL Server ストアの定義ページ](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "アーカイブ SQL Server ストアの定義ページ")</span><span class="sxs-lookup"><span data-stu-id="842eb-144">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

12. <span data-ttu-id="842eb-145">[ **MONITORING SQL server ストアの定義**] ページで、以前に Lync Server 2013 用に作成した sql server インスタンスを選びます。</span><span class="sxs-lookup"><span data-stu-id="842eb-145">On the **Define the Monitoring SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span> <span data-ttu-id="842eb-146">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="842eb-146">Click **Finish**.</span></span>

13. <span data-ttu-id="842eb-147">トポロジビルダーのトップノードで、[ **Lync Server** ] を右クリックし、[プロパティの編集] をクリックし**ます。**</span><span class="sxs-lookup"><span data-stu-id="842eb-147">From the top node of Topology Builder, right click **Lync Server** and click **Edit Properties.**</span></span> <span data-ttu-id="842eb-148">[ **Simple url**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="842eb-148">Click **Simple URLs**.</span></span>

14. <span data-ttu-id="842eb-149">**管理アクセスの URL**を更新します。</span><span class="sxs-lookup"><span data-stu-id="842eb-149">Update the **Administrative access URL**.</span></span>
    
    <span data-ttu-id="842eb-150">![[プロパティの編集] の [シンプルな Url] ページ](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "[プロパティの編集] の [シンプルな Url] ページ")</span><span class="sxs-lookup"><span data-stu-id="842eb-150">![Edit Properties, Simple URLs page](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Edit Properties, Simple URLs page")</span></span>
    
    <span data-ttu-id="842eb-151">単純な Url の詳細については、展開ドキュメントの「 [Lync Server 2013 での単純な url の編集または構成](lync-server-2013-edit-or-configure-simple-urls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="842eb-151">For additional information on Simple URLs, see the topic [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

15. <span data-ttu-id="842eb-152">[**プロパティの編集**] の [**サーバーの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="842eb-152">From the **Edit Properties**, click **Central Management Server**.</span></span>

16. <span data-ttu-id="842eb-153">ドロップダウンリストから、Lync Server 2013 プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="842eb-153">From the drop-down list, select the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="842eb-154">![[プロパティの中央管理] ページを編集する](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "[プロパティの中央管理] ページを編集する")</span><span class="sxs-lookup"><span data-stu-id="842eb-154">![Edit Properties, Central Management Server page](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Edit Properties, Central Management Server page")</span></span>

17. <span data-ttu-id="842eb-155">[OK] をクリックし**て、[プロパティの編集**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="842eb-155">Click OK to close **the Edit Properties** page.</span></span>

18. <span data-ttu-id="842eb-156">[**操作**] メニューの [**トポロジの公開**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="842eb-156">From the **Action** menu, select **Publish Topology**.</span></span>

19. <span data-ttu-id="842eb-157">発行プロセスが完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="842eb-157">When the publish process has completed, click **Finish**.</span></span>

20. <span data-ttu-id="842eb-158">Lync Server 2013 展開ウィザードに戻り、[ **Lync Server System のインストールまたは更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="842eb-158">Returning to the Lync Server 2013 Deployment Wizard, click **Install or Update Lync Server System**.</span></span>
    
    <span data-ttu-id="842eb-159">![Lync Server 2013 展開ウィザード](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013 展開ウィザード")</span><span class="sxs-lookup"><span data-stu-id="842eb-159">![Lync Server 2013 Deployment Wizard](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013 Deployment Wizard")</span></span>

<span data-ttu-id="842eb-160">構成ストアのローカルコピーをインストールし、必要なサービスを開始するには、「展開ドキュメントで[Lync Server 2013 用のフロントエンドサーバーとフロントエンドプールを設定](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="842eb-160">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>

