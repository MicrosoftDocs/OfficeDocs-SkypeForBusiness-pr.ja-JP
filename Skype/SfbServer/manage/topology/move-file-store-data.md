---
title: Skype ビジネス サーバー用の新しいファイル ストアにデータをファイル ストアの移動
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: ビジネス サーバーの展開、Skype のファイル ストアとしての機能になっているファイル サーバーを削除する必要がありますかは、現在の変更を保存使用できないその他のために必要な場合、新しい共有を作成する必要があります。 次の手順を実行する必要があります。
ms.openlocfilehash: a80e6b4e039f7423a3e622062b6bee237ee00947
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20992309"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a><span data-ttu-id="b120e-104">Skype ビジネス サーバー用の新しいファイル ストアにデータをファイル ストアの移動</span><span class="sxs-lookup"><span data-stu-id="b120e-104">Move File Store Data to a New File Store in Skype for Business Server</span></span>
 
<span data-ttu-id="b120e-105">ビジネス サーバーの展開、Skype のファイル ストアとしての機能になっているファイル サーバーを削除する必要がありますかは、現在の変更を保存使用できないその他のために必要な場合、新しい共有を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b120e-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="b120e-106">次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b120e-106">Then you need to perform the following steps:</span></span>
  
1. <span data-ttu-id="b120e-107">ビジネス サーバー サービスを削除するファイル ストアを使用するの Skype を終了します。</span><span class="sxs-lookup"><span data-stu-id="b120e-107">Shut down the Skype for Business Server services that use the file store that you plan to remove.</span></span>
    
2. <span data-ttu-id="b120e-108">トポロジ ビルダーのファイル ストアを定義し、格納する新しいファイルを展開で使用できるようにするのには変更を公開します。</span><span class="sxs-lookup"><span data-stu-id="b120e-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>
    
3. <span data-ttu-id="b120e-109">新しいファイル ストアにデータを移行します。</span><span class="sxs-lookup"><span data-stu-id="b120e-109">Move the data to the new file store.</span></span>
    
4. <span data-ttu-id="b120e-110">サーバーまたはサービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="b120e-110">Restart the servers or services.</span></span>
    
5. <span data-ttu-id="b120e-111">オプションで、古いファイル共有とファイル フォルダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="b120e-111">Optionally, remove the old file share and file folder.</span></span>
    
### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="b120e-112">ファイル ストアのデータを新しいファイル ストアに移動するには</span><span class="sxs-lookup"><span data-stu-id="b120e-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="b120e-113">ビジネス サーバー、管理ツールの Skype がインストールされている RTCUniversersalServerAdmins または CsServerAdministrator のグループのメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b120e-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server, Administrative Tools are installed.</span></span>
    
2.  <span data-ttu-id="b120e-114">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="b120e-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="b120e-115">左側のナビゲーション バーで **[トポロジ]** をクリックし、**[状態]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b120e-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span> 
    
4. <span data-ttu-id="b120e-116">各ディレクター プール、ディレクター、Standard Edition サーバー、およびフロント エンド プールを削除するファイル ストアを使用する、サーバーまたはプールを選択して**アクション**を**すべてのサービスの停止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b120e-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span> 
    
5. <span data-ttu-id="b120e-117">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="b120e-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
6. <span data-ttu-id="b120e-118">開始トポロジ ビルダー: [**スタート**] ボタン [**すべてのプログラム**] をクリックして、 **Skype**、 **Skype**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b120e-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>
    
7. <span data-ttu-id="b120e-119">ファイル ストアを使用するサーバーまたはプールを選び、次を行います。</span><span class="sxs-lookup"><span data-stu-id="b120e-119">Select a server or pool that uses the file store, and do the following:</span></span>
    
   <span data-ttu-id="b120e-120">a.</span><span class="sxs-lookup"><span data-stu-id="b120e-120">a.</span></span> <span data-ttu-id="b120e-121">サーバーまたはプールを右クリックし、**[プロパティの編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b120e-121">Right-click the server or pool, and then click **Edit Properties**.</span></span> 
    
   <span data-ttu-id="b120e-122">b.</span><span class="sxs-lookup"><span data-stu-id="b120e-122">b.</span></span> <span data-ttu-id="b120e-123">**[プロパティの編集]** で、**[関連付け]** の **[ファイル ストア]** にある **[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b120e-123">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>
    
   <span data-ttu-id="b120e-124">c.</span><span class="sxs-lookup"><span data-stu-id="b120e-124">c.</span></span> <span data-ttu-id="b120e-125">**[新しいファイル ストアの定義]** の **[ファイル サーバーの FQDN]** で、ファイル サーバーの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="b120e-125">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server.</span></span> <span data-ttu-id="b120e-126">**[ファイル共有]** で、新しいファイル共有のフォルダー名を入力し、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b120e-126">Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b120e-127">この手順では、トポロジ ビルダーで使用するための新しいファイル ストアを定義します。</span><span class="sxs-lookup"><span data-stu-id="b120e-127">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="b120e-128">その定義は一度だけ行い、サーバーごとに定義する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b120e-128">You define it only once, not for each server.</span></span> <span data-ttu-id="b120e-129">トポロジを公開する前に、定義したファイル共有を、定義したファイル サーバー上に作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b120e-129">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="b120e-130">詳細については、[フロント エンドのファイル ストアの定義](http://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b120e-130">For details, see [Define the File Store for the Front End](http://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span></span> 
  
8. <span data-ttu-id="b120e-131">ファイル ストアを使用する各サーバーまたはプールでは、次を行います。</span><span class="sxs-lookup"><span data-stu-id="b120e-131">For each server or pool that uses the file store, do the following:</span></span>
    
   <span data-ttu-id="b120e-132">a.</span><span class="sxs-lookup"><span data-stu-id="b120e-132">a.</span></span> <span data-ttu-id="b120e-133">サーバーまたはプールを右クリックし、**[プロパティの編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b120e-133">Right-click the server or pool, and then click **Edit properties**.</span></span>
    
   <span data-ttu-id="b120e-134">b.</span><span class="sxs-lookup"><span data-stu-id="b120e-134">b.</span></span> <span data-ttu-id="b120e-135">**[プロパティの編集]** で、**[関連付け]** の **[ファイル ストア]** で新しいファイル共有を選び **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b120e-135">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>
    
9. <span data-ttu-id="b120e-136">トポロジを公開、レプリケーション ・ ステータスをチェックして、Skype、必要に応じてビジネス サーバーの展開ウィザードを実行しています。</span><span class="sxs-lookup"><span data-stu-id="b120e-136">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="b120e-137">詳細については、 [Lync Server を削除してコンポーネントの一般的な手順](http://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b120e-137">For details, see [Common Procedures for Removing Lync Servers and Components](http://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span></span>
    
10. <span data-ttu-id="b120e-138">コマンド プロンプトを起動します。 [**スタート**] ボタン**を実行**するには、をクリックし、cmd.exe と入力します。</span><span class="sxs-lookup"><span data-stu-id="b120e-138">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>
    
11. <span data-ttu-id="b120e-139">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b120e-139">At the command line, type the following:</span></span>
    
     ```
     Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>

     ```

    > [!TIP]
    > <span data-ttu-id="b120e-140">/S スイッチはファイル、ディレクトリ、およびサブディレクトリをコピーします。</span><span class="sxs-lookup"><span data-stu-id="b120e-140">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="b120e-141">/XF スイッチは Meeting.Active という名前のファイルをすべてスキップします。</span><span class="sxs-lookup"><span data-stu-id="b120e-141">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="b120e-142">/MT スイッチを備えた現在のバージョンの robocopy.exe は、複数のスレッドを使用してコピーの速度を大幅に高めています。</span><span class="sxs-lookup"><span data-stu-id="b120e-142">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="b120e-143">/LOG スイッチ、C:\Logfiles\log.txt の形式でディレクトリ パスとログ ファイル名を使用します。</span><span class="sxs-lookup"><span data-stu-id="b120e-143">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="b120e-144">このスイッチは、指定された場所で操作のログ ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="b120e-144">This switch creates a log file of operations at the named location.</span></span> 
  
12. <span data-ttu-id="b120e-145">データのコピーが完了すると、Lync Server コントロール パネルでは、**トポロジ**をクリックし、**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b120e-145">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>
    
13. <span data-ttu-id="b120e-146">サービスを停止した各サーバーまたはプールでは、サーバーまたはプールを選び、**[操作]**、**[すべてのサービスを開始する]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b120e-146">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span> 
    
14. <span data-ttu-id="b120e-147">古いファイル ストアをトポロジから削除し、トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="b120e-147">Remove the old file store from the topology and then publish the topology.</span></span> <span data-ttu-id="b120e-148">詳細については、[ファイル ストアを削除する](http://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b120e-148">For details, see [Remove a file store](http://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span></span>
    
15. <span data-ttu-id="b120e-149">(省略可能) 削除したファイル ストアを含むコンピューターに、ローカルの Administrators グループまたは Domain Admins グループのメンバーとしてログオンし、古いファイル共有とディレクトリを削除します。</span><span class="sxs-lookup"><span data-stu-id="b120e-149">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b120e-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="b120e-150">See also</span></span>


[<span data-ttu-id="b120e-151">別のファイル ストアへのサーバーの再割り当てください。</span><span class="sxs-lookup"><span data-stu-id="b120e-151">Reassign a Server to a Different File Store</span></span>](http://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)
  
[<span data-ttu-id="b120e-152">ファイル ストアを削除します。</span><span class="sxs-lookup"><span data-stu-id="b120e-152">Remove a file store</span></span>](http://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)

