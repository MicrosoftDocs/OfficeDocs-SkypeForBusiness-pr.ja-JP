---
title: Skype for Business Server に仲介サーバーのファイルをインストールする
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: '概要: Skype for Business Server で仲介サーバーのファイルをインストールする方法について説明します。'
ms.openlocfilehash: 80f25d9fab37555d5b4e9dc3d610c5c9037c934d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830797"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a><span data-ttu-id="9d46e-103">Skype for Business Server に仲介サーバーのファイルをインストールする</span><span class="sxs-lookup"><span data-stu-id="9d46e-103">Install the files for Mediation Server in Skype for Business Server</span></span>
 
<span data-ttu-id="9d46e-104">**概要:** Skype for Business Server で仲介サーバーのファイルをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9d46e-104">**Summary:** Learn how to install the files for Mediation Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="9d46e-105">この手順を正常に完了するには、少なくとも、ローカル管理者および少なくとも RTCUniversalReadOnlyAdmins グループのメンバーシップを持つドメイン ユーザーとしてサーバーにログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d46e-105">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>
  
<span data-ttu-id="9d46e-106">このトピックの手順を使用して、Skype for Business Server 展開ウィザードを実行して、トポロジ ビルダーを使用してプールを定義および公開した後に仲介サーバー プールに追加したコンピューターに仲介サーバーのファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="9d46e-106">Use the steps in this topic to run Skype for Business Server Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool after you have used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="9d46e-107">ファイル仲介サーバーをインストールする場合は、仲介サーバー プール内の各コンピューターに必要な証明書もインストールして割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d46e-107">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9d46e-108">このトピックでは [、Skype for Business Server](deploy-a-mediation-server.md)のトポロジ ビルダーでの仲介サーバーの展開の説明に従って、トポロジにスタンドアロンの仲介サーバー プールを既に定義して公開済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d46e-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool in your topology, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md).</span></span> 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="9d46e-109">スタンドアロンの仲介サーバー プールのファイルをインストールするには</span><span class="sxs-lookup"><span data-stu-id="9d46e-109">To install the files for a stand-alone Mediation Server pool</span></span>

1. <span data-ttu-id="9d46e-110">インストール メディアで、アプリケーションを右クリック  _\<installation media\>_ **\Setup\amd64\Setup.exe、[** 管理者として実行] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9d46e-110">From the installation media, right-click  _\<installation media\>_ **\Setup\amd64\Setup.exe**, and then click **Run as Administrator**.</span></span>
    
2. <span data-ttu-id="9d46e-111">[インストール場所 **] ページで\*\*\*\*、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9d46e-111">On the **Installation Location** page, click **OK**.</span></span>
    
3. <span data-ttu-id="9d46e-112">[使用許諾契約 **書] ページで、[** 同意する] をクリックし **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9d46e-112">On the **End User License Agreement** page, click **I accept**, and then click **OK**.</span></span> <span data-ttu-id="9d46e-113">(続行するには必須)。</span><span class="sxs-lookup"><span data-stu-id="9d46e-113">(Required to continue.)</span></span>
    
4. <span data-ttu-id="9d46e-114">**[Skype for Business Server 展開ウィザード] ページ** で **、[Skype for Business Server システムのインストールまたは更新] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9d46e-114">On the **Skype for Business Server Deployment Wizard** page, click **Install or Update Skype for Business Server System**.</span></span>
    
5. <span data-ttu-id="9d46e-115">[手順 **1: ローカル構成ストア** のインストール] の横にある [実行] をクリックし、画面の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="9d46e-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>
    
6. <span data-ttu-id="9d46e-116">[中央 **管理ストアのローカル** レプリカの構成] ページで、既定の [中央管理ストアから直接取得] を受け入れ、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="9d46e-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="9d46e-117">[実行中 **のコマンド] ページ** で、タスクの状態が [完了] と表示されている場合 **は、[完了**] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="9d46e-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
8. <span data-ttu-id="9d46e-118">[ステップ **2: Skype for Business Server** コンポーネントのセットアップまたは削除] の横にある [実行] をクリックし、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="9d46e-118">Next to **Step 2: Setup or Remove Skype for Business Server Components**, click **Run**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="9d46e-119">[実行中 **のコマンド] ページ** で、タスクの状態が [完了] と表示されている場合 **は、[完了**] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="9d46e-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
10. <span data-ttu-id="9d46e-120">[手順 **3: 証明書の要求、インストール、または割り** 当て] の横にある [実行] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="9d46e-120">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span> <span data-ttu-id="9d46e-121">画面の指示に従って、既定の設定を受け入れる。</span><span class="sxs-lookup"><span data-stu-id="9d46e-121">Follow the instructions on the screen, accepting the default settings.</span></span> <span data-ttu-id="9d46e-122">仲介サーバーには 1 つの証明書が必要なので、手順 3 を **2** 回実行します。1 回は必要な証明書を発行し、もう 1 回は割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d46e-122">The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>
    
11. <span data-ttu-id="9d46e-123">証明書が発行され、正しく割り当てられたら、[手順 **4:** サービスの開始] の横にある [実行] をクリックし、画面の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="9d46e-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>
    
12. <span data-ttu-id="9d46e-124">手順 **4 が** 正常に完了したら、サーバーを再起動し、DomainAdmins グループのメンバーとしてサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9d46e-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>
    
13. <span data-ttu-id="9d46e-125">Skype for Business Server コントロール パネルを実行しているコンピューターで、Skype for Business Server コントロール パネルの [トポロジ] ページで、仲介サーバーのサービスの状態が緑色のチェック マークで表示されるのを確認します。 </span><span class="sxs-lookup"><span data-stu-id="9d46e-125">On the computer where you are running Skype for Business Server Control Panel, verify on the **Topology** page of Skype for Business Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="9d46e-126">代わりに赤い X が表示される場合は、仲介サーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="9d46e-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="9d46e-127">[操作] **メニューの** [すべてのサービスの開始 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9d46e-127">On the **Action** menu, click **Start All Services**.</span></span> 
    
<span data-ttu-id="9d46e-128">仲介サーバー プールに複数のコンピューターを追加した場合は、仲介サーバー プール内の他のすべてのコンピューターで、この手順の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9d46e-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="9d46e-129">他のコンピューター用に仲介サーバー用のファイルをインストールする必要はない場合は [、「Skype for Business Server](configure-trunks.md) でトランクを構成する」の手順に従って、この仲介サーバー プール (またはサイト内のすべての仲介サーバー) とそのピア間のトランク接続の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="9d46e-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configure trunks in Skype for Business Server](configure-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

