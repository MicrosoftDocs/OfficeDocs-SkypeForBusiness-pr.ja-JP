---
title: ビジネス サーバーの Skype での仲介サーバーのファイルをインストールします。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: '概要: ビジネス サーバーの Skype での仲介サーバーのファイルをインストールする方法を説明します。'
ms.openlocfilehash: b3314e5443a7aa881fa849fd3e3b5b639f72664e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21002482"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a><span data-ttu-id="a89d3-103">ビジネス サーバーの Skype での仲介サーバーのファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a89d3-103">Install the files for Mediation Server in Skype for Business Server</span></span>
 
<span data-ttu-id="a89d3-104">**の概要:** ビジネス サーバーの Skype での仲介サーバーのファイルをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a89d3-104">**Summary:** Learn how to install the files for Mediation Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="a89d3-105">この手順を正常に完了するには、少なくともローカルの管理者または RTCUniversalReadOnlyAdmins グループのメンバーシップを持つドメイン ユーザーとして、サーバーにログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a89d3-105">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>
  
<span data-ttu-id="a89d3-106">Skype の仲介サーバーのプールおよびを定義するのにトポロジ ビルダーを使用した後に、仲介サーバー プールに追加したコンピューターにファイルをインストールするのにはビジネス サーバーの展開ウィザードを実行するのには、このトピックの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="a89d3-106">Use the steps in this topic to run Skype for Business Server Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool after you have used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="a89d3-107">仲介サーバーのファイルをインストールする場合もインストールして仲介サーバー プール内の各コンピューターに必要な証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a89d3-107">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a89d3-108">このトピックには、 [Skype のビジネス サーバーで、トポロジ ビルダーでの仲介サーバーの展開](deploy-a-mediation-server.md)で説明するよう既に定義しているトポロジでは、スタンドアロンの仲介サーバー プールを発行が想定しています。</span><span class="sxs-lookup"><span data-stu-id="a89d3-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool in your topology, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md).</span></span> 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="a89d3-109">スタンドアロンの仲介サーバー プールにファイルをインストールするには</span><span class="sxs-lookup"><span data-stu-id="a89d3-109">To install the files for a stand-alone Mediation Server pool</span></span>

1. <span data-ttu-id="a89d3-110">インストール メディアを右クリックし、_\<インストール メディア\>_ **\Setup\amd64\Setup.exe**、し、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a89d3-110">From the installation media, right-click  _\<installation media\>_ **\Setup\amd64\Setup.exe**, and then click **Run as Administrator**.</span></span>
    
2. <span data-ttu-id="a89d3-111">[**インストール先**] ページで、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a89d3-111">On the **Installation Location** page, click **OK**.</span></span>
    
3. <span data-ttu-id="a89d3-p102">[**使用許諾契約書**] ページで [**同意する**] をクリックし、[**OK**] をクリックします (操作を続行する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="a89d3-p102">On the **End User License Agreement** page, click **I accept**, and then click **OK**. (Required to continue.)</span></span>
    
4. <span data-ttu-id="a89d3-114">**Skype**ビジネス サーバーの展開ウィザードのページで、**サーバーのビジネス システムの更新プログラムの Skype をインストールまたは**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a89d3-114">On the **Skype for Business Server Deployment Wizard** page, click **Install or Update Skype for Business Server System**.</span></span>
    
5. <span data-ttu-id="a89d3-115">[**ステップ 1: ローカル構成ストアのインストール**] の横の [**実行**] をクリックし、画面の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="a89d3-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>
    
6. <span data-ttu-id="a89d3-116">[**中央管理ストアのローカル レプリカの構成**] ページで、既定の [**中央管理ストアから直接取得する**] を受け入れ、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a89d3-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="a89d3-117">[**コマンドの実行**] ページで、タスクの状態が [**完了**] と表示されたら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a89d3-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
8. <span data-ttu-id="a89d3-118">横に**ステップ 2: セットアップまたは削除の Skype ビジネス サーバー コンポーネントの**を**実行**するにはをクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a89d3-118">Next to **Step 2: Setup or Remove Skype for Business Server Components**, click **Run**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="a89d3-119">[**コマンドの実行**] ページで、タスクの状態が [**完了**] と表示されたら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a89d3-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
10. <span data-ttu-id="a89d3-p103">[**ステップ 3: 証明書の要求、インストール、または割り当て**] の横にある [**実行**] をクリックします。画面に表示される指示に従って、既定の設定を承諾します。仲介サーバーには証明書が 1 つ必要なため、[**ステップ 3**] を 2 回実行します。つまり、1 回目で必要な証明書を発行して、2 回目で割り当てを行います。</span><span class="sxs-lookup"><span data-stu-id="a89d3-p103">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**. Follow the instructions on the screen, accepting the default settings. The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>
    
11. <span data-ttu-id="a89d3-123">証明書を発行し正しく割り当てたら、[**ステップ 4: サービスの開始**] の横の [**実行**] をクリックし、画面の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="a89d3-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>
    
12. <span data-ttu-id="a89d3-124">[**ステップ 4**] が正常に完了したら、サーバーを再起動し、DomainAdmins グループのメンバーとしてサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a89d3-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>
    
13. <span data-ttu-id="a89d3-125">ビジネス サーバーのコントロール パネルの Skype を実行しているコンピューターに仲介サーバーのサービスの状態が緑のチェック マークとして表示されているビジネス サーバーのコントロール パネルの [**トポロジ**] ページで Skype を確認します。</span><span class="sxs-lookup"><span data-stu-id="a89d3-125">On the computer where you are running Skype for Business Server Control Panel, verify on the **Topology** page of Skype for Business Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="a89d3-126">赤色の X が表示された場合は、仲介サーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="a89d3-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="a89d3-127">[**操作**] メニューで、**すべてのサービスの開始**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a89d3-127">On the **Action** menu, click **Start All Services**.</span></span> 
    
<span data-ttu-id="a89d3-128">仲介サーバー プールに複数のコンピューターを追加する場合は、仲介サーバー プール内の他のすべてのコンピューターでこの手順で手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a89d3-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="a89d3-129">場合は、他のコンピューター用の仲介サーバーのファイルをインストールする必要はありませんは、この仲介サーバー プール (またはすべての仲介との間のトランク接続の設定を構成するのには[Skype ビジネス サーバー用に構成するトランク](configure-trunks.md)の手順を実行し、サイト サーバー) とそのピア。</span><span class="sxs-lookup"><span data-stu-id="a89d3-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configure trunks in Skype for Business Server](configure-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

