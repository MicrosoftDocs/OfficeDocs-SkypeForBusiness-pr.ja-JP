---
title: ファイル ストア データを Skype for Business Server 2015 の新しいファイル ストアに移動する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/30/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 現在 Skype for Business Server 2015 展開のファイル ストアとして機能しているファイル サーバーを削除する必要がある場合、または現在のファイル ストアを使用できない他の変更を行う必要がある場合は、まず新しい共有を作成する必要があります。 次に、次の手順を実行する必要があります。
ms.openlocfilehash: 2d65e517b10a76013fbeb332b183b5b816e99083
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119646"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server-2015"></a><span data-ttu-id="46e7e-104">ファイル ストア データを Skype for Business Server 2015 の新しいファイル ストアに移動する</span><span class="sxs-lookup"><span data-stu-id="46e7e-104">Move File Store Data to a New File Store in Skype for Business Server 2015</span></span>

<span data-ttu-id="46e7e-105">現在 Skype for Business Server 2015 展開のファイル ストアとして機能しているファイル サーバーを削除する必要がある場合、または現在のファイル ストアを使用できない他の変更を行う必要がある場合は、まず新しい共有を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46e7e-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server 2015 deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="46e7e-106">次に、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46e7e-106">Then you need to perform the following steps:</span></span>

1. <span data-ttu-id="46e7e-107">削除する予定のファイル ストアを使用する Skype for Business Server 2015 サービスをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="46e7e-107">Shut down the Skype for Business Server 2015 services that use the file store that you plan to remove.</span></span>

2. <span data-ttu-id="46e7e-108">トポロジ ビルダーでファイル ストアを定義し、変更を発行して、新しいファイル ストアを展開で使用できます。</span><span class="sxs-lookup"><span data-stu-id="46e7e-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>

3. <span data-ttu-id="46e7e-109">データを新しいファイル ストアに移動します。</span><span class="sxs-lookup"><span data-stu-id="46e7e-109">Move the data to the new file store.</span></span>

4. <span data-ttu-id="46e7e-110">サーバーまたはサービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="46e7e-110">Restart the servers or services.</span></span>

5. <span data-ttu-id="46e7e-111">必要に応じて、古いファイル共有とファイル フォルダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="46e7e-111">Optionally, remove the old file share and file folder.</span></span>

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="46e7e-112">ファイル ストアのデータを新しいファイル ストアに移動するには</span><span class="sxs-lookup"><span data-stu-id="46e7e-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="46e7e-113">Skype for Business Server 2015 管理ツールがインストールされている RTCUniversersalServerAdmins または CsServerAdministrator グループのメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="46e7e-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server 2015, Administrative Tools are installed.</span></span>

2. <span data-ttu-id="46e7e-114">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="46e7e-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="46e7e-115">左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46e7e-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>

4. <span data-ttu-id="46e7e-116">削除する予定のファイル ストアを使用するディレクター プール、ディレクター、Standard Edition サーバー、およびフロントエンド プールごとに、サーバーまたはプールを選択し、[アクション]をクリックし、[すべてのサービスの停止] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46e7e-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span>

5. <span data-ttu-id="46e7e-117">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="46e7e-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

6. <span data-ttu-id="46e7e-118">トポロジ ビルダーの開始: [**スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business Server 2015]** をクリックし **、[Skype for Business Server 2015Topology Builder] をクリックします**。 </span><span class="sxs-lookup"><span data-stu-id="46e7e-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>

7. <span data-ttu-id="46e7e-119">ファイル ストアを使用するサーバーまたはプールを選択し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="46e7e-119">Select a server or pool that uses the file store, and do the following:</span></span>

8. <span data-ttu-id="46e7e-120">サーバーまたはプールを右クリックし、[プロパティの編集] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="46e7e-120">Right-click the server or pool, and then click **Edit Properties**.</span></span>

9. <span data-ttu-id="46e7e-121">[ **プロパティの編集]** の [ **関連付け]** の [ファイル ストア] **で**、[新規] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="46e7e-121">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>

10. <span data-ttu-id="46e7e-122">[ **新しいファイル ストアの定義**] の [ファイル サーバー **FQDN]** で、ファイル サーバーの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="46e7e-122">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server.</span></span> <span data-ttu-id="46e7e-123">[ **ファイル共有] で**、新しいファイル共有のフォルダー名を入力し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="46e7e-123">Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="46e7e-124">この手順では、トポロジ ビルダーで使用する新しいファイル ストアを定義します。</span><span class="sxs-lookup"><span data-stu-id="46e7e-124">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="46e7e-125">サーバーごとにではなく、1 回だけ定義します。</span><span class="sxs-lookup"><span data-stu-id="46e7e-125">You define it only once, not for each server.</span></span> <span data-ttu-id="46e7e-126">トポロジを公開する前に、定義されたファイル共有を定義されたファイル サーバーに作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46e7e-126">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="46e7e-127">詳細については、「[フロント エンドのファイル ストアの定義](/previous-versions/office/communications/gg133895(v=ocs.14))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46e7e-127">For details, see [Define the File Store for the Front End](/previous-versions/office/communications/gg133895(v=ocs.14)).</span></span>

11. <span data-ttu-id="46e7e-128">ファイル ストアを使用するサーバーまたはプールごとに、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="46e7e-128">For each server or pool that uses the file store, do the following:</span></span>

12. <span data-ttu-id="46e7e-129">サーバーまたはプールを右クリックし、[プロパティの編集] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="46e7e-129">Right-click the server or pool, and then click **Edit properties**.</span></span>

13. <span data-ttu-id="46e7e-130">[ **プロパティの編集]** の [ **関連付** け] の [ファイル ストア **] で**、新しいファイル共有を選択し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="46e7e-130">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>

14. <span data-ttu-id="46e7e-131">トポロジを発行し、レプリケーションの状態を確認し、必要に応じて Skype for Business Server 展開ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="46e7e-131">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="46e7e-132">詳細については、「[Common Procedures for Removing Lync Servers and Components](/previous-versions/office/skype-server-2010/gg195688(v=ocs.14))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46e7e-132">For details, see [Common Procedures for Removing Lync Servers and Components](/previous-versions/office/skype-server-2010/gg195688(v=ocs.14)).</span></span>

15. <span data-ttu-id="46e7e-133">コマンド プロンプトを開始する: [スタート] **をクリックし**、[ **実行**] をクリックし、「コマンド プロンプト」と入力cmd.exe。</span><span class="sxs-lookup"><span data-stu-id="46e7e-133">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>

16. <span data-ttu-id="46e7e-134">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="46e7e-134">At the command line, type the following:</span></span>

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > <span data-ttu-id="46e7e-135">/S スイッチは、ファイル、ディレクトリ、サブディレクトリをコピーします。</span><span class="sxs-lookup"><span data-stu-id="46e7e-135">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="46e7e-136">/XF スイッチは、Meeting.Active という名前のファイルをスキップします。</span><span class="sxs-lookup"><span data-stu-id="46e7e-136">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="46e7e-137">/MT スイッチを備えた現在のバージョンの robocopy.exe は、複数のスレッドを使用してコピーの速度を大幅に高めています。</span><span class="sxs-lookup"><span data-stu-id="46e7e-137">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="46e7e-138">/LOG スイッチの場合は、ディレクトリ パスとログ ファイル名をディレクトリ パスの形式でC:\Logfiles\log.txt。</span><span class="sxs-lookup"><span data-stu-id="46e7e-138">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="46e7e-139">このスイッチは、指定された場所に操作のログ ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="46e7e-139">This switch creates a log file of operations at the named location.</span></span>

17. <span data-ttu-id="46e7e-140">データ コピーが完了したら、Lync Server コントロール パネルで [トポロジ] をクリックし、[状態] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="46e7e-140">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>

18. <span data-ttu-id="46e7e-141">サービスを停止したサーバーまたはプールごとに、サーバーまたはプールを選択し、[アクション]をクリックし、[すべてのサービスの開始 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="46e7e-141">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span>

19. <span data-ttu-id="46e7e-142">古いファイル ストアをトポロジから削除し、トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="46e7e-142">Remove the old file store from the topology and then publish the topology.</span></span> <span data-ttu-id="46e7e-143">詳細については、「[Remove a file store](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46e7e-143">For details, see [Remove a file store](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14)).</span></span>

20. <span data-ttu-id="46e7e-144">(省略可能) 削除したファイル ストアを含むコンピューターに、ローカルの Administrators グループまたは Domain Admins グループのメンバーとしてログオンし、古いファイル共有とディレクトリを削除します。</span><span class="sxs-lookup"><span data-stu-id="46e7e-144">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="46e7e-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="46e7e-145">See also</span></span>

<span data-ttu-id="46e7e-146">[サーバーの異なるファイル ストアへの再割り当て](/previous-versions/office/skype-server-2010/gg195633(v=ocs.14))</span><span class="sxs-lookup"><span data-stu-id="46e7e-146">[Reassign a Server to a Different File Store](/previous-versions/office/skype-server-2010/gg195633(v=ocs.14))</span></span>

<span data-ttu-id="46e7e-147">[ファイル ストアを削除する](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))</span><span class="sxs-lookup"><span data-stu-id="46e7e-147">[Remove a file store](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))</span></span>