---
title: 監視対象の Skype for Business Server コンピューターを構成する
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: Skype for Business Server 2019 コンピューターに Operations Manager エージェントファイルをインストールして監視し、システムセンタープロキシとして動作するようにコンピューターを構成します。'
ms.openlocfilehash: ebf859b633a0da047d61a7b0d55c430f81a02401
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150564"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a><span data-ttu-id="3856f-103">監視対象の Skype for Business Server コンピューターを構成する</span><span class="sxs-lookup"><span data-stu-id="3856f-103">Configure the Skype for Business Server computers that will be monitored</span></span>

<span data-ttu-id="3856f-104">**概要:** 監視対象の Skype for Business Server 2019 コンピューターに Operations Manager エージェントファイルをインストールし、System Center プロキシとして動作するようにコンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="3856f-104">**Summary:** Install the Operations Manager agent files on the Skype for Business Server 2019 computer to be monitored, and configure the computer to act as a System Center proxy.</span></span>

<span data-ttu-id="3856f-105">監視する各 Skype for Business Server 2019 コンピューターは、管理サーバーへのその存在を自己報告できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3856f-105">Each Skype for Business Server 2019 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="3856f-106">このプロセスを有効にするには、監視する各コンピューターに Operations Manager エージェントファイルをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3856f-106">To enable this process, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="3856f-107">エージェントファイルをインストールした後、システムセンタープロキシとして動作するようにコンピューターを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3856f-107">After installing the agent files, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="3856f-108">これらの手順を実行する前に、これらのコンピューターで Skype for Business Server を最初にインストールして構成したことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3856f-108">Be sure that you have first installed and configured Skype for Business Server on these computers before carrying out these procedures.</span></span>

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a><span data-ttu-id="3856f-109">境界ネットワーク外にある監視ノードの証明書のインストール</span><span class="sxs-lookup"><span data-stu-id="3856f-109">Installing a Certificate on a Watcher Node Located Outside the Perimeter Network</span></span>
<span data-ttu-id="3856f-110"><a name="watcher_node_outside"> </a></span><span class="sxs-lookup"><span data-stu-id="3856f-110"><a name="watcher_node_outside"> </a></span></span>

<span data-ttu-id="3856f-111">境界ネットワーク (Skype for Business Server エッジサーバーなど)、エンタープライズ外部 (外部代理トランザクション監視ノードなど)、または Active Directory 信頼境界を越えて実行されている System Center Operations Manager エージェントは、System Center Operations Manager ゲートウェイサーバーの構成。</span><span class="sxs-lookup"><span data-stu-id="3856f-111">System Center Operations Manager agents running in a perimeter network (such as a Skype for Business Server Edge Server), outside of the enterprise (such as an external synthetic transaction watcher node), or across an Active Directory trust boundary, may require the configuration of a System Center Operations Manager Gateway Server.</span></span> <span data-ttu-id="3856f-112">このサーバーの役割によって、ルート管理サーバーとの信頼関係を持たないエージェントがアラートを発生させることができます。</span><span class="sxs-lookup"><span data-stu-id="3856f-112">This server role enables agents that do not have a trust relationship with the Root Management Server to raise alerts.</span></span> <span data-ttu-id="3856f-113">詳細については、「 [Operations Manager 2012 でゲートウェイサーバーを管理する](https://technet.microsoft.com/library/hh212823.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3856f-113">For details, see [Managing Gateway Servers in Operations Manager 2012](https://technet.microsoft.com/library/hh212823.aspx).</span></span>

<span data-ttu-id="3856f-114">これらのいずれかの場所にエージェントを展開する場合は、監視ノードが System Center Operations Manager に通知を送信できるようにする証明書を要求して構成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="3856f-114">If you deploy an agent in one of these locations, you will also need to request and configure a certificate that enables the watcher node to send alerts to System Center Operations Manager.</span></span> <span data-ttu-id="3856f-115">このプロセスを簡単にするため、Operations Manager チームは、正しい種類の証明書を要求して監視ノード コンピューターにインストールできる一連のユーティリティを作成しました。</span><span class="sxs-lookup"><span data-stu-id="3856f-115">To simplify this process, the Operations Manager team has created a set of utilities that enable you to request and install the correct type of certificate on the watcher node computer.</span></span> <span data-ttu-id="3856f-116">詳細について、およびこれらのユーティリティをダウンロードするには、「[証明書の生成ウィザードを使用して簡単にドメインに参加していないエージェントの証明書を取得](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3856f-116">For details, and to download these utilities, see [Obtaining Certificates for Non-Domain Joined Agents Made Easy with Certificate Generation Wizard](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).</span></span>

### <a name="installing-the-operation-manager-agent-files"></a><span data-ttu-id="3856f-117">Operation Manager エージェントファイルのインストール</span><span class="sxs-lookup"><span data-stu-id="3856f-117">Installing the Operation Manager Agent Files</span></span>

1. <span data-ttu-id="3856f-118">System Center セットアップメディアで **、setup.exe をダブルクリックし**ます。</span><span class="sxs-lookup"><span data-stu-id="3856f-118">On your System Center setup media, double-click **Setup.exe**.</span></span>

2. <span data-ttu-id="3856f-119">System Center Operation Manager セットアップウィザードで、[オプションのインストール] の [エージェントのインストールからの**Operations Manager エージェントのインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3856f-119">In the System Center Operation Manager setup wizard, click **Install Operations Manager Agent**, from Install Agent under Optional Installations</span></span>

3. <span data-ttu-id="3856f-120">System Center setup ウィザードの [System Center Operations Manager セットアップウィザードへようこそ] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3856f-120">In the System Center setup wizard, on the Welcome to the System Center Operations Manager Setup wizard page, click **Next**.</span></span>

4. <span data-ttu-id="3856f-121">[保存先フォルダー] ページで、Operations Manager エージェントファイルをインストールするフォルダーを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3856f-121">On the Destination Folder page, select the folder where the Operations Manager Agent files will be installed and click **Next**.</span></span>

5. <span data-ttu-id="3856f-122">[管理グループの構成] ページで、[**管理グループ情報の指定**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3856f-122">On the Management Group Configuration page, select **Specify Management Group information** and click **Next**.</span></span>

6. <span data-ttu-id="3856f-123">[管理グループの構成] ページで、[管理**グループ名**] ボックスに Operations Manager 管理グループの名前を入力し、[**管理サーバー** ] ボックスに、operations manager サーバーのホスト名 (たとえば、「atl-scom-001」) を入力します。</span><span class="sxs-lookup"><span data-stu-id="3856f-123">On the Management Group Configuration page, type the name of your Operations Manager Management Group in the **Management Group Name** box, and then type the host name of your Operations Manager server (for example, atl-scom-001) in the **Management Server** box.</span></span> <span data-ttu-id="3856f-124">Operations Manager で使用されるポート番号を変更した場合は、[**管理サーバーのポート**] ボックスに新しいポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="3856f-124">If you changed the port number used by Operations Manager, enter the new port number in the **Management Server Port** box.</span></span> <span data-ttu-id="3856f-125">それ以外の場合は、ポートを既定値の5723のままにして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3856f-125">Otherwise, leave the port at the default value of 5723, and then click **Next**.</span></span>

7. <span data-ttu-id="3856f-126">[エージェントアクションアカウント] ページで、[**ローカルシステム**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3856f-126">On the Agent Action Account page, select **Local System** and click **Next**.</span></span>

8. <span data-ttu-id="3856f-127">[Microsoft Update] ページで、[ **Microsoft update を使用しない**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3856f-127">On the Microsoft Update page, select **I don't want to use Microsoft Update** and click **Next**.</span></span>

9. <span data-ttu-id="3856f-128">[インストールの準備完了] ページで、[ **インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3856f-128">On the Ready to Install page, click **Install**.</span></span>

10. <span data-ttu-id="3856f-129">[System Center Operations Manager セットアップウィザードを完了しています] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3856f-129">On the Completing the System Center Operations Manager Setup wizard page, click **Finish**.</span></span>

11. <span data-ttu-id="3856f-130">**[終了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3856f-130">Click **Exit**.</span></span>

<span data-ttu-id="3856f-131">System Center 2012 では、[**スタート**]、[**すべてのプログラム**]、[ **System Center Operations Manager 2012**]、[ **operations 2012 Manager シェル**] の順にクリックして、エージェントが作成されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3856f-131">For System Center 2012, you can verify that the agent has been created by clicking **Start**, clicking **All Programs**, clicking **System Center Operations Manager 2012**, and then clicking **Operations 2012 Manager Shell**.</span></span> <span data-ttu-id="3856f-132">Operations Manager シェルで、次の Windows PowerShell コマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3856f-132">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>
```PowerShell
Get-SCOMAgent
```

<span data-ttu-id="3856f-133">Operations Manager エージェントの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3856f-133">A list of all your Operations Manager agents will appear.</span></span>
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a><span data-ttu-id="3856f-134">System Center Discovery に参加するように Skype for Business Server コンピュータを構成する</span><span class="sxs-lookup"><span data-stu-id="3856f-134">Configuring the Skype for Business Server Computer to Participate in System Center Discovery</span></span>
<span data-ttu-id="3856f-135"><a name="watcher_node_outside"> </a></span><span class="sxs-lookup"><span data-stu-id="3856f-135"><a name="watcher_node_outside"> </a></span></span>

<span data-ttu-id="3856f-136">System Center operations manager の検出プロセスに新しい Skype for Business Server エージェントが参加するようにするには、System Center Operations Manager コンソールがインストールされている各コンピューターで次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3856f-136">To make sure that your new Skype for Business Server agent participates in the discovery process for System Center Operations Manager, you must complete the following procedure on each computer where the System Center Operations Manager console has been installed:</span></span>

1. <span data-ttu-id="3856f-137">[管理] タブで、[**管理対象のエージェント**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3856f-137">On the Administration tab, click **Agent Managed**.</span></span>

2. <span data-ttu-id="3856f-138">**探索ウィザード**をクリックして、コンピューターが検出されるようにウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="3856f-138">Click on **Discovery Wizard** and complete the wizard for the computer to be discovered.</span></span>

3. <span data-ttu-id="3856f-139">正常性エージェントサービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="3856f-139">Reboot the Health Agent service.</span></span> <span data-ttu-id="3856f-140">サービスを再起動すると、新しいコンピューターが強制的に検出されます。</span><span class="sxs-lookup"><span data-stu-id="3856f-140">Rebooting the service will force discovery of the new machine.</span></span> <span data-ttu-id="3856f-141">サービスを再起動しない場合は、System Center Operations Manager によって新しいコンピューターが検出されるまでに4時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="3856f-141">If you do not reboot the service, it could take as long as 4 hours before the new machine is discovered by System Center Operations Manager.</span></span>

4. <span data-ttu-id="3856f-142">Operations Manager イベントログにエラーイベントが記録されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3856f-142">Verify that no error events were recorded in the Operations Manager event log.</span></span>

5. <span data-ttu-id="3856f-143">エージェントが正常にプッシュされたコンピューターは、[エージェントで管理] 一覧に表示され、エージェントが手動でインストールされたコンピューターは [保留中の管理] の下に表示されます。 [コンピューター名] をクリックして、を承認します。</span><span class="sxs-lookup"><span data-stu-id="3856f-143">The computer where the agent is pushed successfully will be shown under "Agent Managed" list and the computer where agent was installed manually will be shown under "Pending Management", click on the computer name and approve.</span></span>

6. <span data-ttu-id="3856f-144">コンピューターの名前を右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3856f-144">Right-click the name of the computer, and then click **Properties**.</span></span> <span data-ttu-id="3856f-145">[プロパティ] ダイアログ ボックスの [セキュリティ] タブで、[**このエージェントをプロキシとして動作させ、他のコンピューター上の管理オブジェクトを検出する**] を選択し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3856f-145">In the Properties dialog box, on the Security tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>


