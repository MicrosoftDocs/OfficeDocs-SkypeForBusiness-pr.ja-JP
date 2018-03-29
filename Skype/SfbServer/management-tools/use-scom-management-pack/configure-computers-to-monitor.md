---
title: 監視対象の Skype for Business Server コンピューターの構成
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b24ea184-4b3e-4277-a244-157afb4b368b
description: '概要: は、Operations Manager エージェントにファイルをインストール、監視対象サーバー 2015 のビジネス コンピューターの Skype と System Center のプロキシとして動作するコンピューターを構成します。'
ms.openlocfilehash: bbf2abfe2617b8bc03dd56d3ecdafc25643ba17e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a><span data-ttu-id="43ffa-103">監視対象の Skype for Business Server コンピューターの構成</span><span class="sxs-lookup"><span data-stu-id="43ffa-103">Configure the Skype for Business Server computers that will be monitored</span></span>
 
<span data-ttu-id="43ffa-104">**の概要:**Operations Manager エージェントにファイルをインストール、監視対象サーバー 2015 のビジネス コンピューターの Skype と System Center のプロキシとして動作するコンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="43ffa-104">**Summary:** Install the Operations Manager agent files on the Skype for Business Server 2015 computer to be monitored, and configure the computer to act as a System Center proxy.</span></span>
  
<span data-ttu-id="43ffa-105">ビジネス サーバー 2015 のコンピューターを監視するには、各 Skype では、自己管理サーバーにその存在を報告する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43ffa-105">Each Skype for Business Server 2015 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="43ffa-106">このプロセスを有効にするために、監視する各コンピューターに Operations Manager エージェント ファイルをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="43ffa-106">To enable this process, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="43ffa-107">エージェント ファイルをインストールした後、System Center プロキシとして動作するようにコンピューターを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43ffa-107">After installing the agent files, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="43ffa-108">必ず最初にインストールしている Skype をビジネス サーバーのこれらの手順を実行する前にこれらのコンピューターで構成します。</span><span class="sxs-lookup"><span data-stu-id="43ffa-108">Be sure that you have first installed and configured Skype for Business Server on these computers before carrying out these procedures.</span></span>
  
## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a><span data-ttu-id="43ffa-109">境界ネットワーク外にある監視ノードの証明書のインストール</span><span class="sxs-lookup"><span data-stu-id="43ffa-109">Installing a Certificate on a Watcher Node Located Outside the Perimeter Network</span></span>
<span data-ttu-id="43ffa-110"><a name="watcher_node_outside"> </a></span><span class="sxs-lookup"><span data-stu-id="43ffa-110"></span></span>

<span data-ttu-id="43ffa-111">システム センター オペレーション マネージャー エージェントが境界で実行されているが (、外部代理トランザクション監視ノードなど)、企業の外部ネットワークなど、Skype ビジネス エッジ サーバーの)、または、Active Directory の信頼間の境界をする必要があります。システム センター オペレーション マネージャー ゲートウェイ サーバーの構成。</span><span class="sxs-lookup"><span data-stu-id="43ffa-111">System Center Operations Manager agents running in a perimeter network (such as a Skype for Business Server Edge Server), outside of the enterprise (such as an external synthetic transaction watcher node), or across an Active Directory trust boundary, may require the configuration of a System Center Operations Manager Gateway Server.</span></span> <span data-ttu-id="43ffa-112">このサーバーの役割により、ルート管理サーバーと信頼関係を持たないエージェントは警告を出すことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="43ffa-112">This server role enables agents that do not have a trust relationship with the Root Management Server to raise alerts.</span></span> <span data-ttu-id="43ffa-113">詳細については、[運用マネージャー 2012 でゲートウェイ サーバーを管理する](https://technet.microsoft.com/en-us/library/hh212823.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43ffa-113">For details, see [Managing Gateway Servers in Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh212823.aspx).</span></span>
  
<span data-ttu-id="43ffa-114">これらの場所のいずれかでエージェントを展開する場合を要求し、System Center Operations Manager にアラートを送信するウォッチャー ノードを有効にする証明書を構成する必要がもあります。</span><span class="sxs-lookup"><span data-stu-id="43ffa-114">If you deploy an agent in one of these locations, you will also need to request and configure a certificate that enables the watcher node to send alerts to System Center Operations Manager.</span></span> <span data-ttu-id="43ffa-115">このプロセスを簡略化には、Operations Manager チームが作成を要求し、監視ノード コンピューターで適切な種類の証明書をインストールできるようにするユーティリティのセットです。</span><span class="sxs-lookup"><span data-stu-id="43ffa-115">To simplify this process, the Operations Manager team has created a set of utilities that enable you to request and install the correct type of certificate on the watcher node computer.</span></span> <span data-ttu-id="43ffa-116">詳細については、し、これらのユーティリティをダウンロードするには、[非ドメイン参加しているエージェント作成を簡単に証明書の生成ウィザードを使用しての証明書の取得](http://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43ffa-116">For details, and to download these utilities, see [Obtaining Certificates for Non-Domain Joined Agents Made Easy with Certificate Generation Wizard](http://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).</span></span>
  
### <a name="installing-the-operation-manager-agent-files"></a><span data-ttu-id="43ffa-117">Operation Manager エージェント ファイルのインストール</span><span class="sxs-lookup"><span data-stu-id="43ffa-117">Installing the Operation Manager Agent Files</span></span>

1. <span data-ttu-id="43ffa-118">System Center セットアップ メディアで、[**SetupOM.exe**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="43ffa-118">On your System Center setup media, double-click **Setup.exe**.</span></span>
    
2. <span data-ttu-id="43ffa-119">システム センター操作マネージャー セットアップ ウィザードで、[**操作マネージャー エージェントのインストール**、インストールのオプション] の下には、[エージェントのインストール] をクリックします</span><span class="sxs-lookup"><span data-stu-id="43ffa-119">In the System Center Operation Manager setup wizard, click **Install Operations Manager Agent**, from Install Agent under Optional Installations</span></span>
    
3. <span data-ttu-id="43ffa-120">System Center セットアップ ウィザードで、システム センター操作マネージャーのセットアップ ウィザードのページへようこそ] で、**次へ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43ffa-120">In the System Center setup wizard, on the Welcome to the System Center Operations Manager Setup wizard page, click **Next**.</span></span>
    
4. <span data-ttu-id="43ffa-121">コピー先のフォルダー] ページで、[操作マネージャー エージェントのファイルがインストールされ、[**次へ**] をクリックする、フォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="43ffa-121">On the Destination Folder page, select the folder where the Operations Manager Agent files will be installed and click **Next**.</span></span>
    
5. <span data-ttu-id="43ffa-122">[管理グループの構成] ページで、[**管理グループ情報の指定**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43ffa-122">On the Management Group Configuration page, select **Specify Management Group information** and click **Next**.</span></span>
    
6. <span data-ttu-id="43ffa-123">[管理グループの構成] ページで、**管理グループ名**] ボックスに、オペレーション マネージャーの管理グループの名前を入力し、Operations Manager サーバーのホスト名を入力し (たとえば、atl の scom-001)**管理サーバーで**ボックスです。</span><span class="sxs-lookup"><span data-stu-id="43ffa-123">On the Management Group Configuration page, type the name of your Operations Manager Management Group in the **Management Group Name** box, and then type the host name of your Operations Manager server (for example, atl-scom-001) in the **Management Server** box.</span></span> <span data-ttu-id="43ffa-124">Operations Manager が使用するポート番号を変更した場合は、[**管理サーバー ポート**] ボックスに新しいポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="43ffa-124">If you changed the port number used by Operations Manager, enter the new port number in the **Management Server Port** box.</span></span> <span data-ttu-id="43ffa-125">そうしない場合は、ポートを既定の値 5723 のままにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43ffa-125">Otherwise, leave the port at the default value of 5723, and then click **Next**.</span></span>
    
7. <span data-ttu-id="43ffa-126">[エージェント アクション アカウント] ページで、[**ローカル システム**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43ffa-126">On the Agent Action Account page, select **Local System** and click **Next**.</span></span>
    
8. <span data-ttu-id="43ffa-127">[Microsoft Update] ページで、[**Microsoft Update を使用しない**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43ffa-127">On the Microsoft Update page, select **I don't want to use Microsoft Update** and click **Next**.</span></span>
    
9. <span data-ttu-id="43ffa-128">[インストールの準備完了] ページで、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43ffa-128">On the Ready to Install page, click **Install**.</span></span>
    
10. <span data-ttu-id="43ffa-129">完了システム センター操作マネージャーのセットアップ ウィザード ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43ffa-129">On the Completing the System Center Operations Manager Setup wizard page, click **Finish**.</span></span>
    
11. <span data-ttu-id="43ffa-130">[**終了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43ffa-130">Click **Exit**.</span></span>
    
<span data-ttu-id="43ffa-131">System Center 2012 では、 **[スタート] ボタン**、**すべてのプログラム**をクリックすると、 **System Center オペレーション マネージャー 2012**をクリックし、 **2012年マネージャー シェルの操作**によって、エージェントが作成されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="43ffa-131">For System Center 2012, you can verify that the agent has been created by clicking **Start**, clicking **All Programs**, clicking **System Center Operations Manager 2012**, and then clicking **Operations 2012 Manager Shell**.</span></span> <span data-ttu-id="43ffa-132">Operations Manager シェルで、次の Windows PowerShell コマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="43ffa-132">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>
```
Get-SCOMAgent
```

<span data-ttu-id="43ffa-133">すべての Operations Manager エージェントの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="43ffa-133">A list of all your Operations Manager agents will appear.</span></span>
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a><span data-ttu-id="43ffa-134">System Center 検出に関与する Skype for Business Server コンピューターの構成</span><span class="sxs-lookup"><span data-stu-id="43ffa-134">Configuring the Skype for Business Server Computer to Participate in System Center Discovery</span></span>
<span data-ttu-id="43ffa-135"><a name="watcher_node_outside"> </a></span><span class="sxs-lookup"><span data-stu-id="43ffa-135"></span></span>

<span data-ttu-id="43ffa-136">ビジネス サーバー エージェントの新しい Skype は、System Center Operations Manager の検出プロセスでに参加することを確認、System Center Operations Manager コンソールがインストールされている各コンピューターで次の手順を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="43ffa-136">To make sure that your new Skype for Business Server agent participates in the discovery process for System Center Operations Manager, you must complete the following procedure on each computer where the System Center Operations Manager console has been installed:</span></span>
  
1. <span data-ttu-id="43ffa-137">[管理] タブで、[**管理対象のエージェント**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43ffa-137">On the Administration tab, click **Agent Managed**.</span></span>
    
2. <span data-ttu-id="43ffa-138">[**検出ウィザード**] をクリックし、コンピューターを検出するためのウィザードを完了させます。</span><span class="sxs-lookup"><span data-stu-id="43ffa-138">Click on **Discovery Wizard** and complete the wizard for the computer to be discovered.</span></span>
    
3. <span data-ttu-id="43ffa-139">正常性エージェント サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="43ffa-139">Reboot the Health Agent service.</span></span> <span data-ttu-id="43ffa-140">サービスを再起動すると、強制的に新しいコンピューターの検出が実行されます。</span><span class="sxs-lookup"><span data-stu-id="43ffa-140">Rebooting the service will force discovery of the new machine.</span></span> <span data-ttu-id="43ffa-141">サービスを再起動しない場合は、System Center Operations Manager で、新しいコンピューターが検出される前に、4 時間に限りがかかります。</span><span class="sxs-lookup"><span data-stu-id="43ffa-141">If you do not reboot the service, it could take as long as 4 hours before the new machine is discovered by System Center Operations Manager.</span></span> 
    
4. <span data-ttu-id="43ffa-142">Operations Manager のイベント ログに、エラー イベントが記録されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="43ffa-142">Verify that no error events were recorded in the Operations Manager event log.</span></span>
    
5. <span data-ttu-id="43ffa-143">一覧の [エージェントの管理」の下で、エージェントが正常にプッシュされたコンピューターが表示され、エージェントを手動でインストールされているコンピューターの「保留中の管理」の下に表示されます、コンピューター名をクリックして、および承認します。</span><span class="sxs-lookup"><span data-stu-id="43ffa-143">The computer where the agent is pushed successfully will be shown under "Agent Managed" list and the computer where agent was installed manually will be shown under "Pending Management", click on the computer name and approve.</span></span>
    
6. <span data-ttu-id="43ffa-p107">コンピューターの名前を右クリックし、[**プロパティ**] をクリックします。[プロパティ] ダイアログ ボックスの [セキュリティ] タブで、[**このエージェントをプロキシとして動作させ、他のコンピューター上の管理オブジェクトを検出する**] を選択し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43ffa-p107">Right-click the name of the computer, and then click **Properties**. In the Properties dialog box, on the Security tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>
    

