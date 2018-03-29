---
title: Skype for Business Server 2015 でのアーカイブ データベース オプションの変更
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: '概要: は、Skype のビジネス サーバー 2015 用のアーカイブのデータベース オプションを変更する方法を説明します。'
ms.openlocfilehash: 5bb7ee9329cc3fa7a0795115f9a0d11768ab7aa4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="change-archiving-database-options-in-skype-for-business-server-2015"></a><span data-ttu-id="b89d3-103">Skype for Business Server 2015 でのアーカイブ データベース オプションの変更</span><span class="sxs-lookup"><span data-stu-id="b89d3-103">Change Archiving database options in Skype for Business Server 2015</span></span>

<span data-ttu-id="b89d3-104">**の概要:**ビジネス サーバー 2015 の Skype 用のアーカイブのデータベース オプションを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b89d3-104">**Summary:** Learn how to change archiving database options for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b89d3-105">SQL Server のストレージを使用して、ユーザーのいずれかのストレージをアーカイブするためのアーカイブを展開する場合は、次のデータベース記憶域の変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b89d3-105">If you deploy archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>
  
- <span data-ttu-id="b89d3-106">アーカイブ ・ ストレージの別の SQL Server データベースを使用します。</span><span class="sxs-lookup"><span data-stu-id="b89d3-106">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="b89d3-107">これには、プライマリのアーカイブ データベースと SQL Server のミラーリングを使用する任意のデータベースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b89d3-107">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>
    
- <span data-ttu-id="b89d3-108">アーカイブ ・ データと Exchange サーバー上のファイルを格納する Microsoft Exchange の統合に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="b89d3-108">Switch to Microsoft Exchange integration to store archiving data and files on Exchange servers.</span></span> <span data-ttu-id="b89d3-109">すべてのユーザーが、Exchange サーバー上に置かれている、配置内のすべてのユーザーの Microsoft Exchange の記憶域を使用する場合は、トポロジの SQL Server ストア データベースを削除してください。</span><span class="sxs-lookup"><span data-stu-id="b89d3-109">If all your users are homed on your Exchange servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span> 
    
<span data-ttu-id="b89d3-110">これらの変更のいずれかをするためには、トポロジ ビルダーを実行、変更を加え、トポロジを再度発行します。</span><span class="sxs-lookup"><span data-stu-id="b89d3-110">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="b89d3-111">Exchange サーバーではないビジネス ユーザーに Skype がない限り、 **SQL Server のアーカイブを保存**または**ストアを有効にする SQL Server のミラーリング**についてを指定しません。</span><span class="sxs-lookup"><span data-stu-id="b89d3-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Skype for Business users who are not homed on Exchange servers.</span></span>
  
## <a name="change-archiving-database-options"></a><span data-ttu-id="b89d3-112">アーカイブ データベース オプションの変更</span><span class="sxs-lookup"><span data-stu-id="b89d3-112">Change Archiving database options</span></span>

1. <span data-ttu-id="b89d3-113">ビジネス サーバーでは、Skype を実行しているコンピューター上に、Skype ビジネス サーバー管理ツールをインストールするにログオンまたはローカルの Users グループ (または同等のユーザー権限を持つアカウント) のメンバーであるアカウントを使用しています。</span><span class="sxs-lookup"><span data-stu-id="b89d3-113">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b89d3-114">ローカルの Users グループのメンバーであるアカウントを使用してトポロジを定義することができますが、トポロジでは、必要なコンポーネントをトポロジに追加するのを公開するには、 **Domain Admins**グループと**RTCUniversalSer のメンバーであるアカウントを使用する必要があります。verAdmins**グループがフル コントロールのアクセス許可 (つまり、読み取り、書き込み、および変更) は、トポロジ ビルダーで必要な随意アクセス制御を構成することができますビジネス サーバーのファイル ストアの Skype を使用しているファイル共有のリスト (Dacl)、または同等の権利を持つアカウントです。</span><span class="sxs-lookup"><span data-stu-id="b89d3-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Skype for Business Server file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="b89d3-115">トポロジ ビルダーを起動します。</span><span class="sxs-lookup"><span data-stu-id="b89d3-115">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="b89d3-116">コンソール プールで、アーカイブを展開したフロントエンド プールに移動し、データベース オプションを変更するフロントエンド プールの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b89d3-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>
    
4. <span data-ttu-id="b89d3-117">[**アクション**] メニューの [**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b89d3-117">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="b89d3-118">[**プロパティの編集**] ダイアログ ボックスで、[**全般**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b89d3-118">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="b89d3-119">[**アーカイブ**] まで下方向にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="b89d3-119">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="b89d3-120">[**アーカイブ**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b89d3-120">In **Archiving**, do the following:</span></span>
    
  - <span data-ttu-id="b89d3-121">別の既存の SQL Server ストアに変更するには、[**SQL Server ストアのアーカイブ**] ドロップダウン リスト ボックスで、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b89d3-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
    
  - <span data-ttu-id="b89d3-122">既存の SQL Server ストアを使用するには、ドロップダウン リスト ボックスで、使用する SQL Server ストアの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b89d3-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
  - <span data-ttu-id="b89d3-123">新しい SQL Server ストアを定義するには、[**新規**] をクリックし、[**新しい SQL Server ストアの定義**] ダイアログ ボックスで次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b89d3-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
    
    - <span data-ttu-id="b89d3-124">既存の SQL Server ストアを使用するには、ドロップダウン リスト ボックスで、使用する SQL Server ストアの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b89d3-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
    - <span data-ttu-id="b89d3-125">新しい SQL Server ストアを指定するには、[**新規**作成] をクリックし**新しい SQL Server ストアの定義**] ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b89d3-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="b89d3-126">**SQL Server の FQDN**を新しい SQL Server ストアを作成するサーバーの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="b89d3-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
      - <span data-ttu-id="b89d3-127">既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b89d3-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
      - <span data-ttu-id="b89d3-128">ミラーリングの関係で指定された SQL Server のインスタンスがある場合、**ミラーリングの関係ではこの SQL インスタンス**] チェック ボックスをオンを選択し、**ミラー ・ ポートの番号**] ボックスで、ポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="b89d3-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
  - <span data-ttu-id="b89d3-129">ミラーリング用に SQL Server ストアを追加するか、SQL Server ストア ミラーリングとして別の既存の SQL Server ストアに変更するには、[**SQL Server ストア ミラーリングの有効化**] を選択して、以下の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b89d3-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
    
    - <span data-ttu-id="b89d3-130">ミラーリングは、 **SQL Server のアーカイブ ストア ミラー** 」ドロップ ダウン リスト ボックスで、既存の SQL Server ストアを使用するには、ミラーリングに使用する SQL Server のストアの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b89d3-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
    - <span data-ttu-id="b89d3-131">ミラーリング用の新しい SQL Server ストアを指定するに [**新規**作成] をクリックし、**新しい SQL Server ストアの定義**] ダイアログ ボックスでの操作を行います次のいずれか。</span><span class="sxs-lookup"><span data-stu-id="b89d3-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
      <span data-ttu-id="b89d3-132">a.</span><span class="sxs-lookup"><span data-stu-id="b89d3-132">a.</span></span> <span data-ttu-id="b89d3-133">**SQL Server の FQDN**を新しい SQL Server ストアを作成する SQL Server の FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="b89d3-133">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
      <span data-ttu-id="b89d3-134">b.</span><span class="sxs-lookup"><span data-stu-id="b89d3-134">b.</span></span> <span data-ttu-id="b89d3-135">既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b89d3-135">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
      <span data-ttu-id="b89d3-136">c.</span><span class="sxs-lookup"><span data-stu-id="b89d3-136">c.</span></span> <span data-ttu-id="b89d3-137">ミラーリングの関係で指定された SQL Server のインスタンスがある場合、**ミラーリングの関係ではこの SQL インスタンス**] チェック ボックスをオンを選択し、**ミラー ・ ポートの番号**] ボックスで、ポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="b89d3-137">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
  - <span data-ttu-id="b89d3-138">SQL Server のミラーリングを有効にして追加またはミラーリング監視 (、第 3 に、独立した SQL Server インスタンスを SQL Server のサーバーとミラーのプライマリ ・ インスタンスの稼働状態を検出することができます)、SQL Server を変更する場合は、ミラーリング監視を使用して SQL Server の**を選択するには自動フェイル オーバー機能を有効にする**チェック ボックスをオンし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b89d3-138">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
      <span data-ttu-id="b89d3-139">a.</span><span class="sxs-lookup"><span data-stu-id="b89d3-139">a.</span></span> <span data-ttu-id="b89d3-140">**SQL Server の FQDN**では、ミラーリング監視をミラーリングする新しい SQL Server を作成するサーバーの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="b89d3-140">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
      <span data-ttu-id="b89d3-141">b.</span><span class="sxs-lookup"><span data-stu-id="b89d3-141">b.</span></span> <span data-ttu-id="b89d3-142">既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、ミラーリング監視で使用するインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b89d3-142">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
      <span data-ttu-id="b89d3-143">c.</span><span class="sxs-lookup"><span data-stu-id="b89d3-143">c.</span></span> <span data-ttu-id="b89d3-144">ミラーリングの関係で指定された SQL Server のインスタンスがある場合、**ミラーリングの関係ではこの SQL インスタンス**] チェック ボックスをオンを選択し、**ミラー ・ ポートの番号**] ボックスで、ポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="b89d3-144">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
  - <span data-ttu-id="b89d3-145">Microsoft Exchange の統合アーカイブ ・ データと (配置内のすべてのユーザーは、Exchange サーバー上に置かれている) 場合に、Exchange サーバー上のファイルを保存するには、データベースをアーカイブするためのすべての情報を削除します。</span><span class="sxs-lookup"><span data-stu-id="b89d3-145">To switch to Microsoft Exchange integration to store archiving data and files on Exchange servers (if all users in your deployment are homed on your Exchange servers), delete all information for Archiving databases.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b89d3-146">ビジネス ユーザーが Exchange サーバーではないため、Skype を使っている場合、情報を格納する SQL Server を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="b89d3-146">If you have any Skype for Business users who are not homed on Exchange servers, do not delete the SQL Server store information.</span></span> 
  
8. <span data-ttu-id="b89d3-147">構成を保存するには、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b89d3-147">To save the configuration, click **OK**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b89d3-148">トポロジ ビルダーで行った変更は、新しいトポロジを公開するまで有効になりません。</span><span class="sxs-lookup"><span data-stu-id="b89d3-148">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="b89d3-149">詳細については、[ビジネス サーバー 2015 の Skype で既存の展開へのアーカイブ ・ データベースの追加](../../deploy/deploy-archiving/add-archiving-databases.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b89d3-149">For details, see [Add archiving databases to an existing deployment in Skype for Business Server 2015](../../deploy/deploy-archiving/add-archiving-databases.md).</span></span> 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a><span data-ttu-id="b89d3-150">Windows PowerShell を使用したアーカイブ データベースの場所の変更</span><span class="sxs-lookup"><span data-stu-id="b89d3-150">Change the location of the Archiving database by using Windows PowerShell</span></span>

<span data-ttu-id="b89d3-151">ほとんどの場合は、アーカイブ サーバーをインストールするときに指定されたアーカイブ データベースの場所を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b89d3-151">In most cases, you will not need to change the location of the Archiving database, which is specified when you install Archiving Server.</span></span> <span data-ttu-id="b89d3-152">ただし、ハードウェア障害や他の問題が発生した場合は、**Set-CsArchivingServer** コマンドレットを使用して、アーカイブ サーバーが新しいデータベースを参照するように設定できます。</span><span class="sxs-lookup"><span data-stu-id="b89d3-152">However, if a hardware failure or other problem should occur, you can point Archiving Server to a new database by using the **Set-CsArchivingServer** cmdlet.</span></span>
  
<span data-ttu-id="b89d3-153">次の例の ArchivingServer:atl のアーカイブ データベースの場所を変更するの cs-001.contoso.com アーカイブ サーバーです。</span><span class="sxs-lookup"><span data-stu-id="b89d3-153">The following example changes the location of the Archiving database for the ArchivingServer:atl-cs-001.contoso.com Archiving Server.</span></span> <span data-ttu-id="b89d3-154">この例では、新しいデータベースが ArchivingDatabase:atl-sql-001.contoso.com に置かれます。</span><span class="sxs-lookup"><span data-stu-id="b89d3-154">In this example, the new database is located at ArchivingDatabase:atl-sql-001.contoso.com:</span></span>
  
```
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


