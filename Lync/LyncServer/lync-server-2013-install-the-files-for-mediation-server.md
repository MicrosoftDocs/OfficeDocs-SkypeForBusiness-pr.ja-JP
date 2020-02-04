---
title: 'Lync Server 2013: 仲介サーバー用のファイルをインストールする'
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
ms.openlocfilehash: c84d5fc2c863e0e56af275a4bee084652742eeac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763681"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="930e2-102">Lync Server 2013 で仲介サーバー用のファイルをインストールする</span><span class="sxs-lookup"><span data-stu-id="930e2-102">Install the files for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="930e2-103">_**最終更新日:** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="930e2-103">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="930e2-104">この手順を正常に完了するには、少なくともローカルの管理者または RTCUniversalReadOnlyAdmins グループのメンバーシップを持つドメイン ユーザーとして、サーバーにログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="930e2-104">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>

<span data-ttu-id="930e2-105">このトピックの手順を使用して、Lync Server 2013 展開ウィザードを実行し、トポロジビルダーを使用してプールを定義して発行するときに、仲介サーバープールに追加したコンピューターに仲介サーバー用のファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="930e2-105">Use the steps in this topic to run Lync Server 2013 Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool when you used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="930e2-106">ファイル仲介サーバーをインストールする場合は、仲介サーバープール内の各コンピューターに必要な証明書もインストールして割り当てます。</span><span class="sxs-lookup"><span data-stu-id="930e2-106">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span>

<span data-ttu-id="930e2-107">このサイトでは、フロントエンドプールまたは Standard Edition サーバーに併置されている仲介サーバーを既に展開している場合は、このトピックをスキップすることができます。代わりに、 [Lync server 2013 での trunks の構成](lync-server-2013-configuring-trunks.md)を続行します。</span><span class="sxs-lookup"><span data-stu-id="930e2-107">At this site, if you have already deployed Mediation Servers collocated on the Front End pools or Standard Edition server, you can skip this topic and, instead, continue to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="930e2-108">このトピックでは、「 <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Lync server 2013 のトポロジビルダーでの仲介サーバーの定義</A>」の説明に従って、スタンドアロンの仲介サーバープールを既に定義して公開していることを前提とし、展開ドキュメントで<A href="lync-server-2013-publish-the-topology.md">lync server 2013 でトポロジを公開</A>し、仲介サーバーのプール内のコンピューターが<A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">lync server 2013 の</A><A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">セキュリティと構成の前提条件を満たしてLync Server 2013 での音声</A></span><span class="sxs-lookup"><span data-stu-id="930e2-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool as described in <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Define a Mediation Server in Topology Builder in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation, and that you have verified that the computers in the Mediation Server pool meet the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="930e2-109">スタンドアロンの仲介サーバー プールにファイルをインストールするには</span><span class="sxs-lookup"><span data-stu-id="930e2-109">To install the files for a stand-alone Mediation Server pool</span></span>

1.  <span data-ttu-id="930e2-110">インストールメディアから\<[インストールメディア\>**\\のセットアップ\\amd64\\**] を右クリックし、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="930e2-110">From the installation media, right-click \<installation media\>**\\Setup\\amd64\\Setup.exe**, and then click **Run as Administrator**.</span></span>

2.  <span data-ttu-id="930e2-111">[**インストール先**] ページで、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="930e2-111">On the **Installation Location** page, click **OK**.</span></span>

3.  <span data-ttu-id="930e2-p102">[**使用許諾契約書**] ページで [**同意する**] をクリックし、[**OK**] をクリックします (操作を続行する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="930e2-p102">On the **End User License Agreement** page, click **I accept**, and then click **OK**. (Required to continue.)</span></span>

4.  <span data-ttu-id="930e2-114">**Lync server 2010 展開ウィザード**のページで、[ **lync Server System のインストールまたは更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="930e2-114">On the **Lync Server 2010 Deployment Wizard** page, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="930e2-115">[**ステップ 1: ローカル構成ストアのインストール**] の横の [**実行**] をクリックし、画面の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="930e2-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>

6.  <span data-ttu-id="930e2-116">[**中央管理ストアのローカル レプリカの構成**] ページで、既定の [**中央管理ストアから直接取得する**] を受け入れ、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="930e2-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>

7.  <span data-ttu-id="930e2-117">[**コマンドの実行**] ページで、タスクの状態が [**完了**] と表示されたら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="930e2-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

8.  <span data-ttu-id="930e2-118">**「手順 2: Lync サーバーコンポーネントをセットアップまたは削除**する」の横にある [**実行**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="930e2-118">Next to **Step 2: Setup or Remove Lync Server Components**, click **Run**, and then click **Next**.</span></span>

9.  <span data-ttu-id="930e2-119">[**コマンドの実行**] ページで、タスクの状態が [**完了**] と表示されたら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="930e2-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

10. <span data-ttu-id="930e2-p103">[**ステップ 3: 証明書の要求、インストール、または割り当て**] の横にある [**実行**] をクリックします。画面に表示される指示に従って、既定の設定を承諾します。仲介サーバーには証明書が 1 つ必要なため、[**ステップ 3**] を 2 回実行します。つまり、1 回目で必要な証明書を発行して、2 回目で割り当てを行います。</span><span class="sxs-lookup"><span data-stu-id="930e2-p103">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**. Follow the instructions on the screen, accepting the default settings. The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>

11. <span data-ttu-id="930e2-123">証明書を発行し正しく割り当てたら、[**ステップ 4: サービスの開始**] の横の [**実行**] をクリックし、画面の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="930e2-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>

12. <span data-ttu-id="930e2-124">[**ステップ 4**] が正常に完了したら、サーバーを再起動し、DomainAdmins グループのメンバーとしてサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="930e2-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>

13. <span data-ttu-id="930e2-125">Lync Server コントロールパネルを実行しているコンピューターで、仲介サーバーのサービスの状態が緑色のチェックマークとして表示される、Lync Server コントロールパネルの [**トポロジ**] ページを確認します。</span><span class="sxs-lookup"><span data-stu-id="930e2-125">On the computer where you are running Lync Server Control Panel, verify on the **Topology** page of Lync Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="930e2-126">代わりに赤い X が表示される場合は、仲介サーバーを選びます。</span><span class="sxs-lookup"><span data-stu-id="930e2-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="930e2-127">[**操作**] メニューの [**すべてのサービスを開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="930e2-127">On the **Action** menu, click **Start All Services**.</span></span>

<span data-ttu-id="930e2-128">複数のコンピューターを仲介サーバープールに追加した場合は、仲介サーバープール内の他のすべてのコンピューターで、この手順の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="930e2-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="930e2-129">他のコンピューターに対して仲介サーバー用のファイルをインストールする必要がない場合は、「 [Lync server 2013 で trunks を構成](lync-server-2013-configuring-trunks.md)する」の手順に従って、この仲介サーバープール (またはサイト内のすべての仲介サーバー) とピアの間のトランク接続の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="930e2-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="930e2-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="930e2-130">See Also</span></span>


[<span data-ttu-id="930e2-131">Lync Server 2013 の内部サーバーに対する証明書要件</span><span class="sxs-lookup"><span data-stu-id="930e2-131">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

