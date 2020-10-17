---
title: 'Lync Server 2013: Lync Server 管理ツールを開く'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Open Lync Server administrative tools
ms:assetid: 8c58de94-9e0a-4368-9e14-9afcaa1142d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195741(v=OCS.15)
ms:contentKeyID: 48184778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c3b8ae0dd21221700101d1c94e1a72a4e987de5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531764"
---
# <a name="open-lync-server-2013-administrative-tools"></a><span data-ttu-id="4b78f-102">Lync Server 2013 管理ツールを開く</span><span class="sxs-lookup"><span data-stu-id="4b78f-102">Open Lync Server 2013 administrative tools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b78f-103">_**トピックの最終更新日:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="4b78f-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="4b78f-104">このトピックの手順を使用して、Lync Server 2013 トポロジの展開、構成、またはトラブルシューティングを行うための管理ツールを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="4b78f-104">You can use the procedures in this topic to open administrative tools to deploy, configure, or troubleshoot your Lync Server 2013 topology.</span></span>

  - <span data-ttu-id="4b78f-105">展開ウィザード</span><span class="sxs-lookup"><span data-stu-id="4b78f-105">Deployment Wizard</span></span>

  - <span data-ttu-id="4b78f-106">トポロジ ビルダー</span><span class="sxs-lookup"><span data-stu-id="4b78f-106">Topology Builder</span></span>

  - <span data-ttu-id="4b78f-107">Lync Server コントロール パネル</span><span class="sxs-lookup"><span data-stu-id="4b78f-107">Lync Server Control Panel</span></span>

  - <span data-ttu-id="4b78f-108">Lync Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="4b78f-108">Lync Server Management Shell</span></span>

<span id="BKMK_OpenDeploymentWizard"></span>

<div>

## <a name="deployment-wizard"></a><span data-ttu-id="4b78f-109">展開ウィザード</span><span class="sxs-lookup"><span data-stu-id="4b78f-109">Deployment Wizard</span></span>

<span data-ttu-id="4b78f-110">Lync Server 2013 コンポーネントファイルを追加または削除するために、展開ウィザードをローカルで開始するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="4b78f-110">Use the following procedure to start the Deployment Wizard locally to add or remove Lync Server 2013 component files.</span></span>

<div>

## <a name="to-start-lync-server-2013-deployment-wizard"></a><span data-ttu-id="4b78f-111">Lync Server 2013 展開ウィザードを起動するには</span><span class="sxs-lookup"><span data-stu-id="4b78f-111">To start Lync Server 2013 Deployment Wizard</span></span>

1.  <span data-ttu-id="4b78f-112">Lync Server 展開ウィザードがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="4b78f-112">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="4b78f-113">[ **スタート**]、[ **すべてのプログラム**]、[ **Microsoft lync Server 2013**]、[ **lync server 展開ウィザード**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b78f-113">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

</div>

</div>

<span id="BKMK_OpenTopologyBuilder"></span>

<div>

## <a name="topology-builder"></a><span data-ttu-id="4b78f-114">トポロジ ビルダー</span><span class="sxs-lookup"><span data-stu-id="4b78f-114">Topology Builder</span></span>

<span data-ttu-id="4b78f-115">次の手順を使用して、トポロジビルダーを開き、Lync Server 2013 トポロジに展開するサーバーを定義します。</span><span class="sxs-lookup"><span data-stu-id="4b78f-115">Use the following procedure to open the Topology Builder to define the servers that you want to deploy in your Lync Server 2013 topology.</span></span>

<div>

## <a name="to-open-lync-server-2013-topology-builder-to-design-the-topology"></a><span data-ttu-id="4b78f-116">Lync Server 2013 トポロジビルダーを開いてトポロジを設計するには</span><span class="sxs-lookup"><span data-stu-id="4b78f-116">To open Lync Server 2013 Topology Builder to design the topology</span></span>

1.  <span data-ttu-id="4b78f-117">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="4b78f-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4b78f-118">トポロジを定義するには、ローカルユーザーグループのメンバーであるアカウントを使用しますが、サーバーに Lync Server 2013 をインストールするために必要なトポロジを読み取り、公開、または有効にするには、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーであり、フルコントロールのアクセス許可を持つアカウントを使用する必要があります (アーカイブファイルストアに対して使用するファイル共有の読み取り、書き込み、および変更)。トポロジビルダーが必要な随意アクセス制御リスト (Dacl) を構成できるようにするか、または同等のユーザー権限を持つアカウントを構成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="4b78f-118">You can define a topology by using an account that is a member of the local Users group, but to read, publish, or enable a topology, which is required to install Lync Server 2013 on a server, you must use an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group, and that has full control permissions (that is, read, write, and modify) on the file share that you are going to use for the archiving file store so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent user rights.</span></span>

    
    </div>

2.  <span data-ttu-id="4b78f-119">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b78f-119">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

</div>

</div>

<span id="BKMK_OpenControlPanel"></span>

<div>

## <a name="lync-server-2013-control-panel"></a><span data-ttu-id="4b78f-120">Lync Server 2013 コントロール パネル</span><span class="sxs-lookup"><span data-stu-id="4b78f-120">Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="4b78f-121">次のいずれかの手順を使用して、Lync Server 2013 コントロールパネルを開いて、環境内のサーバー、ユーザー、クライアント、デバイスの構成を管理します。</span><span class="sxs-lookup"><span data-stu-id="4b78f-121">Use one of the following procedures to open Lync Server 2013 Control Panel to manage the configuration of servers, users, clients, and devices in your environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4b78f-122">CsAdministrator の役割に割り当てられているユーザーアカウントを使用して、Lync Server 2013 コントロールパネルのすべてのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="4b78f-122">You can use a user account that is assigned to the CsAdministrator role to perform any task in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="4b78f-123">他の役割を使用して Lync Server 2013 コントロールパネルにログオンすると、実行する必要があるタスクに応じて、特定の管理タスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="4b78f-123">You can use other roles to log on to Lync Server 2013 Control Panel to perform specific administration tasks, dependent on the task you need to perform.</span></span> <span data-ttu-id="4b78f-124">たとえば、CSArchivingAdministrator を使用して Lync Server 2013 コントロールパネルのアーカイブを管理できます。</span><span class="sxs-lookup"><span data-stu-id="4b78f-124">For example, you can use CSArchivingAdministrator to administer Archiving in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="4b78f-125">役割の詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 での役割ベースのアクセス制御の計画</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b78f-125">For details about roles, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="4b78f-126">特定のタスクを実行する場合に使用できる役割の詳細については、該当タスクのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b78f-126">For details about the roles that you can use to perform a specific task, see the documentation for the task.</span></span>



</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-from-any-computer-inside-your-organizations-firewall"></a><span data-ttu-id="4b78f-127">組織のファイアウォールの内側にある任意のコンピューターから Lync Server 2013 コントロールパネルを開くには</span><span class="sxs-lookup"><span data-stu-id="4b78f-127">To open Lync Server 2013 Control Panel from any computer inside your organization’s firewall</span></span>

1.  <span data-ttu-id="4b78f-128">CsAdministrator の役割、またはタスクを実行するのに適切なユーザー権限とアクセス許可を持つその他の役割に割り当てられているユーザーアカウントから、最小画面解像度 1024 x 768 を使用して、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4b78f-128">From a user account that is assigned to the CsAdministrator role or other role that has appropriate user rights and permissions for the task to be performed, log on to any computer in your internal deployment with a minimum screen resolution of 1024 x 768.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4b78f-129">管理シンプルな uniform resource locator (URL) を構成している場合は、組織のファイアウォール内の任意のコンピューターで実行されているインターネットブラウザーから Lync Server 2013 コントロールパネルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4b78f-129">If you have configured an administration simple uniform resource locator (URL), you can access Lync Server 2013 Control Panel from an Internet browser that is running on any computer within your organization’s firewall.</span></span> <span data-ttu-id="4b78f-130">管理の簡単な URL の構成の詳細については、「展開」のドキュメントの「計画」のドキュメントの「 <A href="lync-server-2013-planning-for-simple-urls.md">Lync server 2013 での簡単な url の計画</A> 」および「 <A href="lync-server-2013-edit-or-configure-simple-urls.md">lync server 2013 での簡易 url の編集または構成</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b78f-130">For details about configuring the administration simple URL, see <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync Server 2013</A> in the Planning documentation and <A href="lync-server-2013-edit-or-configure-simple-urls.md">Edit or configure simple URLs in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

2.  <span data-ttu-id="4b78f-131">ブラウザー ウィンドウを開き、組織に対して構成されている管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="4b78f-131">Open a browser window, and then enter the Admin URL configured for your organization.</span></span>

</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-on-a-computer-running-lync-server-2013"></a><span data-ttu-id="4b78f-132">Lync server 2013 を実行しているコンピューターで Lync Server 2013 コントロールパネルを開くには</span><span class="sxs-lookup"><span data-stu-id="4b78f-132">To open Lync Server 2013 Control Panel on a computer running Lync Server 2013</span></span>

1.  <span data-ttu-id="4b78f-133">CsAdministrator の役割のメンバーであるか、またはタスクを実行するのに適切なユーザー権限とアクセス許可を持つその他の役割を持つユーザーアカウントから、Lync Server 2013 または少なくとも Lync Server 2013 管理ツールをインストールしたコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4b78f-133">From a user account that is a member of the CsAdministrator role or other role that has appropriate user rights and permissions for the task to be performed, log on to a computer on which you have installed Lync Server 2013 or, at a minimum, the Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="4b78f-134">設定を構成するには、コンピューターの最小画面解像度を 1024 x 768 にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b78f-134">To configure settings, the computer must have a minimum screen resolution of 1024 x 768.</span></span>

2.  <span data-ttu-id="4b78f-135">Lync Server 2013 コントロールパネルを開きます。 [ **スタート**]、[ **すべてのプログラム**]、[ **管理ツール**] の順にポイントし、[ **Microsoft lync server 2013**] をポイントして、[ **lync server 2013 コントロールパネル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b78f-135">Start Lync Server 2013 Control Panel: Click **Start**, click **All Programs**, point to **Administrative Tools**, point to **Microsoft Lync Server 2013**, and then click **Lync Server 2013 Control Panel**.</span></span>

</div>

</div>

<span id="BKMK_OpenManagementShell"></span>

<div>

## <a name="lync-server-2013-management-shell"></a><span data-ttu-id="4b78f-136">Lync Server 2013 管理シェル</span><span class="sxs-lookup"><span data-stu-id="4b78f-136">Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="4b78f-137">次の手順を使用して、Lync Server 2013 管理シェルを開き、コマンドラインを使用して環境内のサーバー、ユーザー、クライアント、およびデバイスを管理します。</span><span class="sxs-lookup"><span data-stu-id="4b78f-137">Use the following procedure to open Lync Server 2013 Management Shell to administer servers, users, clients, and devices in your environment by using the command line.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4b78f-138">CsAdministrator の役割に割り当てられているユーザーアカウントを使用して、Lync Server 2013 管理シェルで任意のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="4b78f-138">You can use a user account that is assigned to the CsAdministrator role to perform any task in Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="4b78f-139">特定の管理タスクを実行するには、実行する必要があるタスクに応じて、他の役割を使用してログオンできます。</span><span class="sxs-lookup"><span data-stu-id="4b78f-139">You can log on using other roles to perform specific administration tasks, depending on the task you need to perform.</span></span> <span data-ttu-id="4b78f-140">たとえば、CSArchivingAdministrator を使用することで、アーカイブ管理に管理するコマンドレットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="4b78f-140">For example, you can use CSArchivingAdministrator to run cmdlets related to Archiving administration.</span></span> <span data-ttu-id="4b78f-141">役割の詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 での役割ベースのアクセス制御の計画</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b78f-141">For details about roles, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="4b78f-142">特定のコマンドレットを実行する場合に使用できる役割の詳細については、該当コマンドレットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b78f-142">For details about the roles that you can use to run a specific cmdlet, see the documentation for the cmdlet.</span></span><BR><span data-ttu-id="4b78f-143">コマンドレットに応じて、RTCUniversalServerAdmins、RTCUniversalUserAdmins、または RTCUniversalReadOnlyAdmins の各グループのユーザー アカウントを使用して、特定のコマンドレットを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="4b78f-143">You can also run certain cmdlets by using a user account in the RTCUniversalServerAdmins, RTCUniversalUserAdmins, or RTCUniversalReadOnlyAdmins groups, depending on the cmdlet.</span></span>



</div>

<div>

## <a name="to-open-the-lync-server-2013-management-shell"></a><span data-ttu-id="4b78f-144">Lync Server 2013 管理シェルを開くには</span><span class="sxs-lookup"><span data-stu-id="4b78f-144">To open the Lync Server 2013 Management Shell</span></span>

  - <span data-ttu-id="4b78f-145">Lync Server 2013 管理シェルではなく、Windows PowerShell ウィンドウを開くと、既定で Lync Server 2013 コマンドレットを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="4b78f-145">If you open a Windows PowerShell window rather than the Lync Server 2013 Management Shell, by default you cannot run the Lync Server 2013 cmdlets.</span></span> <span data-ttu-id="4b78f-146">Windows PowerShell で Lync Server 2013 コマンドレットを実行するには、Windows PowerShell コマンドプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4b78f-146">To run the Lync Server 2013 cmdlets from within Windows PowerShell, type the following at the Windows PowerShell command prompt:</span></span>
    
    `Import-Module Lync`

  - <span data-ttu-id="4b78f-147">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b78f-147">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4b78f-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b78f-148">See Also</span></span>


[<span data-ttu-id="4b78f-149">Lync Server 2013 管理ツールのインストール</span><span class="sxs-lookup"><span data-stu-id="4b78f-149">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)  


[<span data-ttu-id="4b78f-150">Lync Server 2013 管理ツール</span><span class="sxs-lookup"><span data-stu-id="4b78f-150">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

