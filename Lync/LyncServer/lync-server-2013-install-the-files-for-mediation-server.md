---
title: 'Lync Server 2013: 仲介サーバーのファイルのインストール'
description: 'Lync Server 2013: 仲介サーバーのファイルをインストールします。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the files for Mediation Server
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412998(v=OCS.15)
ms:contentKeyID: 48185772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea1fc20fb91328d116a4aee62b96b95aa3e270eb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574073"
---
# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="63749-103">Lync Server 2013 での仲介サーバーのファイルのインストール</span><span class="sxs-lookup"><span data-stu-id="63749-103">Install the files for Mediation Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63749-104">_**トピックの最終更新日:** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="63749-104">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="63749-105">この手順を正常に完了するには、少なくとも、ローカル管理者および少なくとも RTCUniversalReadOnlyAdmins グループのメンバーシップを持つドメインユーザーとしてサーバーにログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="63749-105">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>

<span data-ttu-id="63749-106">このトピックの手順を使用して、Lync server 2013 展開ウィザードを実行し、トポロジビルダーを使用してプールを定義して発行したときに、仲介サーバープールに追加したコンピューターに仲介サーバーのファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="63749-106">Use the steps in this topic to run Lync Server 2013 Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool when you used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="63749-107">ファイル仲介サーバーをインストールするときは、仲介サーバープール内の各コンピューターが必要とする証明書をインストールして割り当てます。</span><span class="sxs-lookup"><span data-stu-id="63749-107">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span>

<span data-ttu-id="63749-108">このサイトでは、フロントエンドプールまたは Standard Edition サーバーに併置された仲介サーバーを既に展開している場合は、このトピックを省略してもかまいません。その代わりに、 [Lync server 2013 でのトランクの構成](lync-server-2013-configuring-trunks.md)を続行します。</span><span class="sxs-lookup"><span data-stu-id="63749-108">At this site, if you have already deployed Mediation Servers collocated on the Front End pools or Standard Edition server, you can skip this topic and, instead, continue to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="63749-109">このトピックでは、「展開」のドキュメントの「Lync server 2013 のトポロジビルダーでの <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">仲介サーバーの定義</A> 」および「 <A href="lync-server-2013-publish-the-topology.md">lync server 2013 でのトポロジの公開</A> 」の説明に従って、スタンドアロンの仲介サーバープールを既に定義して公開していることを前提としています。さらに、仲介サーバープール内のコンピューターが、lync Server 2013 の「 <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">エンタープライズ voip の前提</A> 条件」で説明されている前提条件と、 <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Lync server 2013 のエンタープライズ voip のセキュリティおよび構成の前提</A>条件を満たしていることを確認していること。</span><span class="sxs-lookup"><span data-stu-id="63749-109">This topic assumes that you have already defined and published a stand-alone Mediation Server pool as described in <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Define a Mediation Server in Topology Builder in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation, and that you have verified that the computers in the Mediation Server pool meet the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="63749-110">スタンドアロンの仲介サーバープールのファイルをインストールするには</span><span class="sxs-lookup"><span data-stu-id="63749-110">To install the files for a stand-alone Mediation Server pool</span></span>

1.  <span data-ttu-id="63749-111">インストールメディアから、[ \<installation media\> \*\* \\ Setup \\ amd64 \\Setup.exe**] を右クリックし、[**管理者として実行\*\*] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63749-111">From the installation media, right-click \<installation media\>**\\Setup\\amd64\\Setup.exe**, and then click **Run as Administrator**.</span></span>

2.  <span data-ttu-id="63749-112">[ **インストール先** ] ページで、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63749-112">On the **Installation Location** page, click **OK**.</span></span>

3.  <span data-ttu-id="63749-113">[ **使用許諾契約書** ] ページで、[ **同意**します] をクリックし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63749-113">On the **End User License Agreement** page, click **I accept**, and then click **OK**.</span></span> <span data-ttu-id="63749-114">(続行する必要があります。)</span><span class="sxs-lookup"><span data-stu-id="63749-114">(Required to continue.)</span></span>

4.  <span data-ttu-id="63749-115">[ **Lync server 2010 展開ウィザード** ] ページで、[ **lync Server システムのインストールまたは更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63749-115">On the **Lync Server 2010 Deployment Wizard** page, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="63749-116">[ **ステップ 1: ローカル構成ストアのインストール**] の横にある [ **実行**] をクリックし、画面の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="63749-116">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>

6.  <span data-ttu-id="63749-117">[ **中央管理ストアのローカルレプリカの構成** ] ページで、既定の [ **中央管理ストアから直接取得**する] をそのまま使用し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63749-117">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>

7.  <span data-ttu-id="63749-118">[ **コマンドの実行** ] ページで、タスクの状態が [ **完了**] と表示されたら、[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63749-118">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

8.  <span data-ttu-id="63749-119">[ **手順 2: Lync Server コンポーネントのセットアップまたは削除**] の横にある [ **実行**] をクリックし、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63749-119">Next to **Step 2: Setup or Remove Lync Server Components**, click **Run**, and then click **Next**.</span></span>

9.  <span data-ttu-id="63749-120">[ **コマンドの実行** ] ページで、タスクの状態が [ **完了**] と表示されたら、[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63749-120">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

10. <span data-ttu-id="63749-121">[ **手順 3: 証明書の要求、インストール、または割り当て**] の横にある [ **実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63749-121">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span> <span data-ttu-id="63749-122">画面に表示される指示に従って、既定の設定をそのまま適用します。</span><span class="sxs-lookup"><span data-stu-id="63749-122">Follow the instructions on the screen, accepting the default settings.</span></span> <span data-ttu-id="63749-123">仲介サーバーは1つの証明書を必要とするため、 **手順 3** を2回実行します。1回は必要な証明書を発行し、もう一度割り当てるには。</span><span class="sxs-lookup"><span data-stu-id="63749-123">The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>

11. <span data-ttu-id="63749-124">証明書が発行されて正しく割り当てられたら、[ **ステップ 4: サービスの開始**] の横にある [ **実行**] をクリックし、画面に表示される指示に従います。</span><span class="sxs-lookup"><span data-stu-id="63749-124">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>

12. <span data-ttu-id="63749-125">**手順 4**が正常に完了したら、サーバーを再起動し、domainadmins グループのメンバーとしてサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="63749-125">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>

13. <span data-ttu-id="63749-126">Lync Server コントロールパネルを実行しているコンピューターで、[Lync Server コントロールパネル] の [ **トポロジ** ] ページで、仲介サーバーのサービスの状態が緑のチェックマークとして表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="63749-126">On the computer where you are running Lync Server Control Panel, verify on the **Topology** page of Lync Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="63749-127">代わりに赤い X が表示される場合は、仲介サーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="63749-127">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="63749-128">[ **操作** ] メニューの [ **すべてのサービスの開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63749-128">On the **Action** menu, click **Start All Services**.</span></span>

<span data-ttu-id="63749-129">仲介サーバープールに複数のコンピューターを追加した場合は、仲介サーバープール内の他のすべてのコンピューターで、この手順の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="63749-129">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="63749-130">他のコンピューターに対して仲介サーバー用のファイルをインストールする必要がない場合は、「configure [トランク In Lync server 2013](lync-server-2013-configuring-trunks.md) 」の手順に従って、この仲介サーバープール (またはサイト内のすべての仲介サーバー) とそのピアとの間のトランク接続の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="63749-130">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="63749-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="63749-131">See Also</span></span>


[<span data-ttu-id="63749-132">Lync Server 2013 の内部サーバーの証明書要件</span><span class="sxs-lookup"><span data-stu-id="63749-132">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

