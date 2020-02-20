---
title: ユーザーのレプリケーションが完了したことを確認する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b526bd5dc6c451d8e8bd9998043d20a7c185f6b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="01016-102">ユーザーのレプリケーションが完了したことを確認する</span><span class="sxs-lookup"><span data-stu-id="01016-102">Verify user replication has completed</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01016-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="01016-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="01016-104">**Move-cslegacyuser**コマンドレットを実行しているときに、最初のレプリケーションが完了していないため、Active Directory ドメインサービス (AD DS) と Lync Server 2013 データベースの間のユーザー情報が同期されていないために障害が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="01016-104">When running the **Move-CsLegacyUser** cmdlet, you may experience a failure due to user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases being out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="01016-105">Lync Server 2013 のユーザーレプリケーターサービスの初期同期が正常に完了するまでにかかる時間は、Lync Server 2013 プールをホストしている Active Directory フォレスト内でホストされているドメインコントローラーの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="01016-105">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="01016-106">Lync Server 2013 のユーザーレプリケーターサービスの初期同期処理は、Lync Server 2013 フロントエンドサーバーが初めて起動されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="01016-106">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="01016-107">それ以降は、ユーザー レプリケーターの間隔に基づいて同期が行われます。</span><span class="sxs-lookup"><span data-stu-id="01016-107">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="01016-108">**Move-CsLegacyUser** コマンドレットを実行する前に次の手順を実行し、ユーザーのレプリケーションが完了していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="01016-108">Complete the following steps to verify user replication has completed before running the **Move-CsLegacyUser** cmdlet.</span></span>

<div>

## <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="01016-109">ユーザーのレプリケーションが完了していることを確認するには</span><span class="sxs-lookup"><span data-stu-id="01016-109">To verify that user replication has completed</span></span>

1.  <span data-ttu-id="01016-110">Lync Server 2013 フロントエンドサーバーから、[**スタート**] メニューをクリックし、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01016-110">From the Lync Server 2013 Front End server, click the **Start** menu, and then click **Run**.</span></span>

2.  <span data-ttu-id="01016-111">「**eventvwr.exe**」と入力し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01016-111">Enter **eventvwr.exe** and then click **OK**.</span></span>

3.  <span data-ttu-id="01016-112">イベント ビューアーで、[**アプリケーションとサービス ログ**] をクリックして展開し、[Lync Server] を選択します。</span><span class="sxs-lookup"><span data-stu-id="01016-112">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

4.  <span data-ttu-id="01016-113">[**操作**] ウィンドウで [**現在のログをフィルター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01016-113">In the **Actions** pane click **Filter Current Log**.</span></span>

5.  <span data-ttu-id="01016-114">[**イベント ソース**] ボックスの一覧の [**LS User Replicator**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01016-114">From the **Event sources** list, click **LS User Replicator**.</span></span>

6.  <span data-ttu-id="01016-115">\*\* \<すべてのイベント id\> **に**30024\*\*と入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01016-115">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

7.  <span data-ttu-id="01016-116">フィルターが適用されたイベントの一覧の [**全般**] タブで、ユーザーのレプリケーションが正常に完了したことを示す項目を探します。</span><span class="sxs-lookup"><span data-stu-id="01016-116">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

