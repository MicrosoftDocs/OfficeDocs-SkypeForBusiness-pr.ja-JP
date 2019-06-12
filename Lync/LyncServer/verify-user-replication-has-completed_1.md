---
title: ユーザー レプリケーションの完了の確認
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13f4fbd2e0d0236f9dc404ffa84ab2f0ce385e2a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847922"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="39abd-102">ユーザー レプリケーションの完了の確認</span><span class="sxs-lookup"><span data-stu-id="39abd-102">Verify user replication has completed</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39abd-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="39abd-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="39abd-104">**CsLegacyUser**コマンドレットを実行しているときに、最初のレプリケーションが完了していないため、Active Directory ドメインサービス (AD DS) と Lync Server 2013 データベースの同期が無効になっているために、エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="39abd-104">When running the **Move-CsLegacyUser** cmdlet, you may experience a failure due to user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases being out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="39abd-105">Lync Server 2013 ユーザーレプリケーターサービスの初回の同期が正常に完了するまでにかかる時間は、Lync Server 2013 プールをホストしている Active Directory フォレストでホストされているドメインコントローラーの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="39abd-105">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="39abd-106">Lync server 2013 ユーザーレプリケーターサービスの初期同期処理は、Lync Server 2013 フロントエンドサーバーが初めて起動されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="39abd-106">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="39abd-107">その後、同期はユーザーレプリケーターの間隔に基づいています。</span><span class="sxs-lookup"><span data-stu-id="39abd-107">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="39abd-108">次の手順を実行して、 **CsLegacyUser**コマンドレットを実行する前にユーザーレプリケーションが完了していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="39abd-108">Complete the following steps to verify user replication has completed before running the **Move-CsLegacyUser** cmdlet.</span></span>

<div>

## <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="39abd-109">ユーザーの複製が完了したことを確認するには</span><span class="sxs-lookup"><span data-stu-id="39abd-109">To verify that user replication has completed</span></span>

1.  <span data-ttu-id="39abd-110">Lync Server 2013 フロントエンドサーバーから、[**スタート**] メニューをクリックし、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39abd-110">From the Lync Server 2013 Front End server, click the **Start** menu, and then click **Run**.</span></span>

2.  <span data-ttu-id="39abd-111">**Eventvwr.exe**と入力して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39abd-111">Enter **eventvwr.exe** and then click **OK**.</span></span>

3.  <span data-ttu-id="39abd-112">イベントビューアーで [**アプリケーションとサービスログ**] をクリックして展開し、[Lync Server] を選択します。</span><span class="sxs-lookup"><span data-stu-id="39abd-112">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

4.  <span data-ttu-id="39abd-113">**操作**ウィンドウで、[**現在のログをフィルター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39abd-113">In the **Actions** pane click **Filter Current Log**.</span></span>

5.  <span data-ttu-id="39abd-114">[**イベントソース**] ボックスの一覧の [ **LS ユーザーレプリケーター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39abd-114">From the **Event sources** list, click **LS User Replicator**.</span></span>

6.  <span data-ttu-id="39abd-115">\*\* \<すべてのイベント id\> **に**30024\*\*と入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39abd-115">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

7.  <span data-ttu-id="39abd-116">[フィルター処理されたイベント] ボックスの一覧の **[全般**] タブで、ユーザーの複製が正常に完了したことを示すエントリを探します。</span><span class="sxs-lookup"><span data-stu-id="39abd-116">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

