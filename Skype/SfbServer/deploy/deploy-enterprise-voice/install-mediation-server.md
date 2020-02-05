---
title: Skype for Business Server に仲介サーバー用のファイルをインストールする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '概要: Skype for Business Server に仲介サーバー用のファイルをインストールする方法について説明します。'
ms.openlocfilehash: 4dc4c9971b74bf27d0f516ed70484646b666a845
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767120"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a><span data-ttu-id="bbfc0-103">Skype for Business Server に仲介サーバー用のファイルをインストールする</span><span class="sxs-lookup"><span data-stu-id="bbfc0-103">Install the files for Mediation Server in Skype for Business Server</span></span>
 
<span data-ttu-id="bbfc0-104">**概要:** Skype for Business Server に仲介サーバー用のファイルをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bbfc0-104">**Summary:** Learn how to install the files for Mediation Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="bbfc0-105">この手順を正常に完了するには、少なくともローカルの管理者または RTCUniversalReadOnlyAdmins グループのメンバーシップを持つドメイン ユーザーとして、サーバーにログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbfc0-105">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>
  
<span data-ttu-id="bbfc0-106">このトピックの手順を使用して、Skype for Business Server Deployment ウィザードを実行し、[トポロジビルダー] を使用してプールを定義して発行した後に、仲介サーバープールに追加したコンピューターに仲介サーバー用のファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="bbfc0-106">Use the steps in this topic to run Skype for Business Server Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool after you have used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="bbfc0-107">ファイル仲介サーバーをインストールする場合は、仲介サーバープール内の各コンピューターに必要な証明書もインストールして割り当てます。</span><span class="sxs-lookup"><span data-stu-id="bbfc0-107">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="bbfc0-108">このトピックでは、「 [Skype For Business server のトポロジビルダーで仲介サーバーを展開](deploy-a-mediation-server.md)する」に記載されているように、既に自分のトポロジにスタンドアロンの仲介サーバープールを定義して公開していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="bbfc0-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool in your topology, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md).</span></span> 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="bbfc0-109">スタンドアロンの仲介サーバー プールにファイルをインストールするには</span><span class="sxs-lookup"><span data-stu-id="bbfc0-109">To install the files for a stand-alone Mediation Server pool</span></span>

1. <span data-ttu-id="bbfc0-110">インストールメディアから [ _ \<インストール\>メディア_ **\Setup\amd64\Setup.exe**] を右クリックし、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbfc0-110">From the installation media, right-click  _\<installation media\>_ **\Setup\amd64\Setup.exe**, and then click **Run as Administrator**.</span></span>
    
2. <span data-ttu-id="bbfc0-111">[**インストール先**] ページで、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbfc0-111">On the **Installation Location** page, click **OK**.</span></span>
    
3. <span data-ttu-id="bbfc0-p102">[**使用許諾契約書**] ページで [**同意する**] をクリックし、[**OK**] をクリックします (操作を続行する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="bbfc0-p102">On the **End User License Agreement** page, click **I accept**, and then click **OK**. (Required to continue.)</span></span>
    
4. <span data-ttu-id="bbfc0-114">Skype for **Business Server 展開ウィザード**のページで、[ **Skype For business Server システムのインストールまたは更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbfc0-114">On the **Skype for Business Server Deployment Wizard** page, click **Install or Update Skype for Business Server System**.</span></span>
    
5. <span data-ttu-id="bbfc0-115">[**ステップ 1: ローカル構成ストアのインストール**] の横の [**実行**] をクリックし、画面の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="bbfc0-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>
    
6. <span data-ttu-id="bbfc0-116">[**中央管理ストアのローカル レプリカの構成**] ページで、既定の [**中央管理ストアから直接取得する**] を受け入れ、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbfc0-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="bbfc0-117">[**コマンドの実行**] ページで、タスクの状態が [**完了**] と表示されたら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbfc0-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
8. <span data-ttu-id="bbfc0-118">**「手順 2: Skype For Business Server コンポーネントのセットアップまたは削除**」の横にある [**実行**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbfc0-118">Next to **Step 2: Setup or Remove Skype for Business Server Components**, click **Run**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="bbfc0-119">[**コマンドの実行**] ページで、タスクの状態が [**完了**] と表示されたら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbfc0-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
10. <span data-ttu-id="bbfc0-p103">[**ステップ 3: 証明書の要求、インストール、または割り当て**] の横にある [**実行**] をクリックします。画面に表示される指示に従って、既定の設定を承諾します。仲介サーバーには証明書が 1 つ必要なため、[**ステップ 3**] を 2 回実行します。つまり、1 回目で必要な証明書を発行して、2 回目で割り当てを行います。</span><span class="sxs-lookup"><span data-stu-id="bbfc0-p103">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**. Follow the instructions on the screen, accepting the default settings. The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>
    
11. <span data-ttu-id="bbfc0-123">証明書を発行し正しく割り当てたら、[**ステップ 4: サービスの開始**] の横の [**実行**] をクリックし、画面の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="bbfc0-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>
    
12. <span data-ttu-id="bbfc0-124">[**ステップ 4**] が正常に完了したら、サーバーを再起動し、DomainAdmins グループのメンバーとしてサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="bbfc0-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>
    
13. <span data-ttu-id="bbfc0-125">Skype for business Server コントロールパネルを実行しているコンピューターで、仲介サーバーのサービスの状態が緑色のチェックマークとして表示される、[Skype for Business Server] コントロールパネルの [**トポロジ**] ページを確認します。</span><span class="sxs-lookup"><span data-stu-id="bbfc0-125">On the computer where you are running Skype for Business Server Control Panel, verify on the **Topology** page of Skype for Business Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="bbfc0-126">代わりに赤い X が表示される場合は、仲介サーバーを選びます。</span><span class="sxs-lookup"><span data-stu-id="bbfc0-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="bbfc0-127">[**操作**] メニューの [**すべてのサービスを開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbfc0-127">On the **Action** menu, click **Start All Services**.</span></span> 
    
<span data-ttu-id="bbfc0-128">複数のコンピューターを仲介サーバープールに追加した場合は、仲介サーバープール内の他のすべてのコンピューターで、この手順の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bbfc0-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="bbfc0-129">他のコンピューターに対して仲介サーバー用のファイルをインストールする必要がない場合は、「 [Skype For Business Server で trunks を構成](configure-trunks.md)する」の手順に従って、この仲介サーバープール (またはサイト内のすべての仲介サーバー) とピアの間のトランク接続の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="bbfc0-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configure trunks in Skype for Business Server](configure-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

