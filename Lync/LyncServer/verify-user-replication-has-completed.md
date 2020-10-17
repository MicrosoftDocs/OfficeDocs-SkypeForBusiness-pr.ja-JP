---
title: ユーザー レプリケーションの完了の確認
description: ユーザーのレプリケーションが完了したことを確認します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48183441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60bca44fcce811c29b1633bd4d3a39f832851885
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555483"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="e9ddf-103">ユーザー レプリケーションの完了の確認</span><span class="sxs-lookup"><span data-stu-id="e9ddf-103">Verify user replication has completed</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9ddf-104">_**トピックの最終更新日:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="e9ddf-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="e9ddf-105">最初のレプリケーションが完了していないため、Active Directory ドメインサービス (AD DS) と Lync Server 2013 データベース間のユーザー情報が同期されていないために、 **csuser** コマンドレットを実行しているときにエラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="e9ddf-105">When running the **Move-CsUser** cmdlet, you may experience a failure because user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="e9ddf-106">Lync Server 2013 のユーザーレプリケーターサービスの初期同期が正常に完了するまでにかかる時間は、Lync Server 2013 プールをホストしている Active Directory フォレスト内でホストされているドメインコントローラーの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="e9ddf-106">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="e9ddf-107">Lync Server 2013 のユーザーレプリケーターサービスの初期同期処理は、Lync Server 2013 フロントエンドサーバーが初めて起動されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="e9ddf-107">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="e9ddf-108">その後、この同期はユーザー レプリケーターの間隔に基づいて行われます。</span><span class="sxs-lookup"><span data-stu-id="e9ddf-108">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="e9ddf-109">**Move-CsUser** コマンドレットを実行する前に、次の手順を実行して、ユーザーのレプリケーションが完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e9ddf-109">Complete the following steps to verify user replication has completed before running the **Move-CsUser** cmdlet.</span></span>

<div>

## <a name="to-verify-user-replication-has-completed"></a><span data-ttu-id="e9ddf-110">ユーザーのレプリケーションが完了したことを確認するには</span><span class="sxs-lookup"><span data-stu-id="e9ddf-110">To verify user replication has completed</span></span>

1.  <span data-ttu-id="e9ddf-111">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="e9ddf-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="e9ddf-112">[**スタート**] メニューをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9ddf-112">Click the **Start** menu, and then click **Run**.</span></span>

3.  <span data-ttu-id="e9ddf-113">「**eventvwr.exe**」と入力し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9ddf-113">Enter **eventvwr.exe** and then click **OK**.</span></span>

4.  <span data-ttu-id="e9ddf-114">イベント ビューアーで、[**アプリケーションとサービス ログ**] をクリックして展開し、[Lync Server] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e9ddf-114">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

5.  <span data-ttu-id="e9ddf-115">[**操作**] ウィンドウで [**現在のログをフィルター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9ddf-115">In the **Actions** pane click **Filter Current Log**.</span></span>

6.  <span data-ttu-id="e9ddf-116">[**イベント ソース**] ボックスの一覧の [**LS User Replicator**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9ddf-116">From the **Event sources** list, click **LS User Replicator**.</span></span>

7.  <span data-ttu-id="e9ddf-117">Enter キーを押して **\<All Event IDs\>** **30024** と入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9ddf-117">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

8.  <span data-ttu-id="e9ddf-118">フィルターが適用されたイベントの一覧の [**全般**] タブで、ユーザーのレプリケーションが正常に完了したことを示す項目を探します。</span><span class="sxs-lookup"><span data-stu-id="e9ddf-118">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

