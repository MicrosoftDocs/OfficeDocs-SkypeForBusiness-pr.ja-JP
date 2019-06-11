---
title: ベストプラクティスアナライザーを使用して展開をスキャンし、潜在的な問題がないか確認する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Best Practices Analyzer to scan your deployment for potential issues
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591343(v=OCS.15)
ms:contentKeyID: 48183359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17c7d881ebc35a4f56207fedaa8533f0a3df3c7a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a><span data-ttu-id="e7a40-102">ベストプラクティスアナライザーを使用して Lync Server 2013 の展開をスキャンし、潜在的な問題を検出する</span><span class="sxs-lookup"><span data-stu-id="e7a40-102">Using Best Practices Analyzer to scan your Lync Server 2013 deployment for potential issues</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7a40-103">_**最終更新日:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="e7a40-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="e7a40-104">ベストプラクティスアナライザースキャンを実行するには、次のように指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7a40-104">To run a Best Practices Analyzer scan, you must specify the following:</span></span>

  - <span data-ttu-id="e7a40-105">**資格情報**   スキャンを実行するには、ローカル管理者グループのメンバーであるアカウントを使用して、ベストプラクティスアナライザーがインストールされているコンピューターにログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7a40-105">**Credentials**   To run a scan, you must log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group.</span></span> <span data-ttu-id="e7a40-106">さらに、適切なスキャンを実行するために必要なユーザー権限とアクセス許可を持つユーザーアカウントを使用してログオンするか、ベストプラクティスアナライザーを実行するときに適切なユーザー権限とアクセス許可を持つ資格情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7a40-106">Additionally, you need to log on by using a user account that has the user rights and permissions required to run the appropriate scans, or you must specify credentials that have the appropriate user rights and permissions when you run Best Practices Analyzer.</span></span> <span data-ttu-id="e7a40-107">詳細については、「 [Lync Server 2013 のベストプラクティスアナライザーのグループメンバーシップとユーザー権利の要件](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7a40-107">For details, see [Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).</span></span>

  - <span data-ttu-id="e7a40-108">**スキャンのスコープ**   スキャンの範囲を指定するには、スキャンするカテゴリとサーバーを選びます。</span><span class="sxs-lookup"><span data-stu-id="e7a40-108">**Scope of scan**   To specify the scope of the scan, select the categories and servers that you want to scan.</span></span> <span data-ttu-id="e7a40-109">Lync Server 環境の特定のカテゴリ内のすべてのカテゴリ、1つ以上のカテゴリ、または1つ以上のサーバーを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="e7a40-109">You can select all categories, one or more categories, or one or more servers within a specific category in your Lync Server environment.</span></span>

  - <span data-ttu-id="e7a40-110">\*\*\*\*   現在、スキャンの種類は [正常性チェックスキャン] のみです (既定で選択されています)。</span><span class="sxs-lookup"><span data-stu-id="e7a40-110">**Type of scan**   Currently, the Health Check scan is the only type of scan available (selected by default).</span></span> <span data-ttu-id="e7a40-111">正常性チェックスキャンでは、スコープで指定されたすべてのサーバーのエラー、警告、その他の情報を含むレポートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="e7a40-111">The Health Check scan generates a report that includes errors, warnings, and other information for all servers specified in the scope.</span></span>

  - <span data-ttu-id="e7a40-112">**ネットワーク速度**   のネットワーク速度オプションには、高速 lan (100 mbps 以上)、lan (10 mbps)、高速 WAN (1.5 mbps)、または wan (64 kbps) があります。</span><span class="sxs-lookup"><span data-stu-id="e7a40-112">**Network speed**   Network speed options include Fast LAN (100 Mbps or more), LAN (10 Mbps), Fast WAN (1.5 Mbps), or WAN (64 kbps).</span></span> <span data-ttu-id="e7a40-113">スキャンを完了するための推定時間は、この設定に基づいています。</span><span class="sxs-lookup"><span data-stu-id="e7a40-113">The estimated time to complete the scan is based on this setting.</span></span> <span data-ttu-id="e7a40-114">この設定は、タイムアウト期間を設定するためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7a40-114">This setting is also used to set the time-out period.</span></span> <span data-ttu-id="e7a40-115">スキャン中は、ベストプラクティスアナライザーは、指定した時間、サーバーからの応答を待ちます。</span><span class="sxs-lookup"><span data-stu-id="e7a40-115">During the scan, the Best Practices Analyzer waits for a response from a server for a specified time.</span></span> <span data-ttu-id="e7a40-116">指定した期間内に応答を受け取らない場合は、スキャンの次のサーバーに移動します。</span><span class="sxs-lookup"><span data-stu-id="e7a40-116">If it does not receive a response within the specified time-out period, it moves to the next server in the scan.</span></span> <span data-ttu-id="e7a40-117">低速のネットワークでは、この指定されたタイムアウト期間は長いネットワーク待ち時間を考慮しています。</span><span class="sxs-lookup"><span data-stu-id="e7a40-117">On slower networks, this specified time-out period is longer to account for longer network latencies.</span></span> <span data-ttu-id="e7a40-118">このパラメーターのトポロジで最も低速のリンクを選択して、ツールが短時間でタイムアウトしないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e7a40-118">We recommend that you select the slowest link in your topology for this parameter so that the tool does not time out too quickly.</span></span>

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a><span data-ttu-id="e7a40-119">Lync Server 2013 の展開をスキャンするには</span><span class="sxs-lookup"><span data-stu-id="e7a40-119">To scan your Lync Server 2013 deployment</span></span>

1.  <span data-ttu-id="e7a40-120">[ローカル管理者] グループのメンバーであり、他に必要なユーザー権限と権限があるアカウントを使用して、ベストプラクティスアナライザーがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e7a40-120">Log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group, and has other required user rights and permissions.</span></span>

2.  <span data-ttu-id="e7a40-121">[**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[**ベストプラクティスアナライザー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7a40-121">Click **Start**, point to **All Programs**, click **Microsoft Lync Server 2013**, and then click **Best Practices Analyzer**.</span></span>

3.  <span data-ttu-id="e7a40-122">[**ようこそ**] 画面で、[**新しいスキャンのオプションを選択**します] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7a40-122">On the **Welcome** screen, click **Select options for a new scan**.</span></span>

4.  <span data-ttu-id="e7a40-123">[ **Active directory に接続する**] ページで、[ **active directory Server**] で指定された名前を確認し、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e7a40-123">On the **Connect to Active Directory** page, verify the name specified in **Active Directory Server**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="e7a40-124">コンピューターにログオンするために使用した資格情報を使ってスキャンを実行するには、[ **Active Directory サーバーに接続**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7a40-124">To run a scan using the credentials that you used to log on to the computer, click **Connect to the Active Directory server**.</span></span>
    
      - <span data-ttu-id="e7a40-125">Active Directory ドメインサービス、エッジサーバー、または Exchange Server に使用する別の資格情報を指定するには、[**詳細なログオンオプションの表示**] をクリックし、個別の資格情報が必要な各チェックボックスをオンにして、資格情報を指定します。選択されているチェックボックスごとに、[ **Active Directory サーバーに接続する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7a40-125">To specify different credentials that you want to use for Active Directory Domain Services, Edge Server, or Exchange Server, click **Show advanced logon options**, select each check box for which separate credentials are required, specify the credentials for each selected check box, and then click **Connect to the Active Directory server**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e7a40-126">スキャンを開始する前に、ベストプラクティスアナライザーがネットワークとアクセス許可のチェックを実行して、指定されたアカウントの資格情報が有効であり、ベストプラクティスアナライザーが Active Directory ドメインサービスに接続できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e7a40-126">Before beginning the scan, Best Practices Analyzer performs a network and permissions check to ensure that the specified account credentials are valid and that Best Practices Analyzer can connect to Active Directory Domain Services.</span></span> <span data-ttu-id="e7a40-127">ツールがワークグループサーバー上で実行されている場合は、ツールは境界ネットワーク (スキャンに含まれている場合) でエッジサーバーに接続できるかどうかも確認します。</span><span class="sxs-lookup"><span data-stu-id="e7a40-127">If the tool is running on a workgroup server, the tool also verifies that it can connect to Edge Servers in the perimeter network (that is, if they are included in the scan).</span></span>

    
    </div>

5.  <span data-ttu-id="e7a40-128">[**新しいベストプラクティススキャンを開始**する] ページで、スキャンに含めるオプションを選択し、ネットワークの速度を指定して、[**スキャンの開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7a40-128">On the **Start a new Best Practices scan** page, select the options that you want to include in the scan, specify the network speed, and then click **Start scanning**.</span></span>

6.  <span data-ttu-id="e7a40-129">[**スキャンが完了しました**] ページで、[**このベストプラクティススキャンのレポートを表示**します] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7a40-129">On the **Scanning Completed** page, click **View a report of this Best Practices scan**.</span></span>

7.  <span data-ttu-id="e7a40-130">[**ベストプラクティスレポートの表示**] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e7a40-130">On the **View Best Practices Report** page, do one of the following:</span></span>
    
      - <span data-ttu-id="e7a40-131">サーバーコンポーネントによって整理されたリストのレポートを表示するには、[**リストレポート**] をクリックし、[**すべての問題**] タブまたは [**情報アイテム**] タブのいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7a40-131">To view reports in a list organized by server component, click **List Reports**, and then click either the **All Issues** tab or the **Informational Items** tab.</span></span>
    
      - <span data-ttu-id="e7a40-132">結果の種類によって整理された階層リストとしてレポートを表示するには、[**ツリーレポート**] をクリックし、[**詳細表示**] タブまたは [**概要ビュー** ] タブのいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7a40-132">To view reports as a hierarchical list organized by types of results, click **Tree Reports**, and then click either the **Detailed View** tab or the **Summary View** tab.</span></span>
    
      - <span data-ttu-id="e7a40-133">他のレポートを表示するには、[**その他のレポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7a40-133">To view other reports, click **Other Reports**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e7a40-134">ベストプラクティスアナライザーレポートとその報告事項について詳しくは、「 <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Lync Server 2013 でのベストプラクティスアナライザーによって作成されたレポートの表示と操作</A>」と「<A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">ベストプラクティスアナライザーによって識別される問題の分析と解決」をご覧ください。Lync Server 2013 の</A>場合。</span><span class="sxs-lookup"><span data-stu-id="e7a40-134">For details about the Best Practices Analyzer reports and the issues they identify, see <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Viewing and working with reports created by Best Practices Analyzer in Lync Server 2013</A> and <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

