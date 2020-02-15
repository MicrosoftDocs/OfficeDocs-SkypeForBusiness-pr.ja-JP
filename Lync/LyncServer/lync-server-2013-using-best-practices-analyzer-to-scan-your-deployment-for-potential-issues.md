---
title: ベストプラクティスアナライザーを使用して展開をスキャンし、潜在的な問題を検出する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Best Practices Analyzer to scan your deployment for potential issues
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591343(v=OCS.15)
ms:contentKeyID: 48183359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afda261fc3e57750afaabbf349eb31631adea275
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a><span data-ttu-id="bb775-102">ベストプラクティスアナライザーを使用して Lync Server 2013 の展開で問題が発生する可能性のある問題をスキャンする</span><span class="sxs-lookup"><span data-stu-id="bb775-102">Using Best Practices Analyzer to scan your Lync Server 2013 deployment for potential issues</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb775-103">_**トピックの最終更新日:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="bb775-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="bb775-104">ベスト プラクティス アナライザーのスキャンを実行する場合は、次の指定を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb775-104">To run a Best Practices Analyzer scan, you must specify the following:</span></span>

  - <span data-ttu-id="bb775-105">**資格情報**   スキャンを実行するには、ローカルの Administrators グループのメンバーであるアカウントを使用して、ベストプラクティスアナライザーがインストールされているコンピューターにログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb775-105">**Credentials**   To run a scan, you must log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group.</span></span> <span data-ttu-id="bb775-106">また、ログオンに使用するユーザー アカウントには、適切なスキャンを実行するために必要なユーザー権限とアクセス許可が割り当てられているか、ベスト プラクティス アナライザーの実行時に適切なユーザー権限とアクセス許可を持つ資格情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb775-106">Additionally, you need to log on by using a user account that has the user rights and permissions required to run the appropriate scans, or you must specify credentials that have the appropriate user rights and permissions when you run Best Practices Analyzer.</span></span> <span data-ttu-id="bb775-107">詳細については、「 [Lync Server 2013 のベストプラクティスアナライザーのグループメンバーシップとユーザー権限要件](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb775-107">For details, see [Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).</span></span>

  - <span data-ttu-id="bb775-108">**スキャンのスコープ**   スキャンの範囲を指定するには、スキャンするカテゴリとサーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="bb775-108">**Scope of scan**   To specify the scope of the scan, select the categories and servers that you want to scan.</span></span> <span data-ttu-id="bb775-109">Lync Server 環境では、特定のカテゴリ内のすべてのカテゴリ、1つ以上のカテゴリ、または1つ以上のサーバーを選択できます。</span><span class="sxs-lookup"><span data-stu-id="bb775-109">You can select all categories, one or more categories, or one or more servers within a specific category in your Lync Server environment.</span></span>

  - <span data-ttu-id="bb775-110">**スキャンの種類**   現時点では、正常性チェックスキャンは利用可能な唯一の種類のスキャンです (既定で選択されています)。</span><span class="sxs-lookup"><span data-stu-id="bb775-110">**Type of scan**   Currently, the Health Check scan is the only type of scan available (selected by default).</span></span> <span data-ttu-id="bb775-111">正常性チェックでは、範囲内で指定されたすべてのサーバーを対象として、エラー、警告、およびその他の情報を示すレポートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="bb775-111">The Health Check scan generates a report that includes errors, warnings, and other information for all servers specified in the scope.</span></span>

  - <span data-ttu-id="bb775-112">**ネットワーク速度**   のネットワーク速度のオプションには、高速 lan (100 mbps 以上)、LAN (10 mbps)、高速 WAN (1.5 Mbps)、または wan (64 kbps) があります。</span><span class="sxs-lookup"><span data-stu-id="bb775-112">**Network speed**   Network speed options include Fast LAN (100 Mbps or more), LAN (10 Mbps), Fast WAN (1.5 Mbps), or WAN (64 kbps).</span></span> <span data-ttu-id="bb775-113">スキャンの実行にかかる推定時間は、この設定に基づいて算出されます。</span><span class="sxs-lookup"><span data-stu-id="bb775-113">The estimated time to complete the scan is based on this setting.</span></span> <span data-ttu-id="bb775-114">また、この設定はタイムアウト時間の設定にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="bb775-114">This setting is also used to set the time-out period.</span></span> <span data-ttu-id="bb775-115">スキャンの実行中、ベスト プラクティス アナライザーは、サーバーから応答が返るのを指定時間内待ちます。</span><span class="sxs-lookup"><span data-stu-id="bb775-115">During the scan, the Best Practices Analyzer waits for a response from a server for a specified time.</span></span> <span data-ttu-id="bb775-116">その間に応答が返らなかった場合、ベスト プラクティス アナライザーは、次のサーバーのスキャンに移ります。</span><span class="sxs-lookup"><span data-stu-id="bb775-116">If it does not receive a response within the specified time-out period, it moves to the next server in the scan.</span></span> <span data-ttu-id="bb775-117">低速のネットワークでは、指定されるタイムアウト時間がより長くなるため、ネットワーク待ち時間が長くなります。</span><span class="sxs-lookup"><span data-stu-id="bb775-117">On slower networks, this specified time-out period is longer to account for longer network latencies.</span></span> <span data-ttu-id="bb775-118">ベスト プラクティス アナライザーが短時間でタイムアウトすることがないように、このパラメーターにはトポロジ内で最も低速のリンクを選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bb775-118">We recommend that you select the slowest link in your topology for this parameter so that the tool does not time out too quickly.</span></span>

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a><span data-ttu-id="bb775-119">Lync Server 2013 の展開をスキャンするには</span><span class="sxs-lookup"><span data-stu-id="bb775-119">To scan your Lync Server 2013 deployment</span></span>

1.  <span data-ttu-id="bb775-120">ベスト プラクティス アナライザーがインストールされているコンピューターにログオンします。このログオンに使用するアカウントは、ローカルの Administrators グループのメンバーで、かつその他必要なユーザー権限とアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb775-120">Log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group, and has other required user rights and permissions.</span></span>

2.  <span data-ttu-id="bb775-121">[**スタート**] をクリックし、[**すべてのプログラム**] をポイントします。次に、[ **Microsoft Lync Server 2013**] をクリックし、[**ベストプラクティスアナライザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb775-121">Click **Start**, point to **All Programs**, click **Microsoft Lync Server 2013**, and then click **Best Practices Analyzer**.</span></span>

3.  <span data-ttu-id="bb775-122">[**Welcome**] 画面で、[**Select options for a new scan**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb775-122">On the **Welcome** screen, click **Select options for a new scan**.</span></span>

4.  <span data-ttu-id="bb775-123">[**Connect to Active Directory**] ページで、[**Active Directory Server**] に指定されている名前を確認し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bb775-123">On the **Connect to Active Directory** page, verify the name specified in **Active Directory Server**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="bb775-124">コンピューターへのログオンに使用した資格情報を使用してスキャンするには、[**Connect to the Active Directory server**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb775-124">To run a scan using the credentials that you used to log on to the computer, click **Connect to the Active Directory server**.</span></span>
    
      - <span data-ttu-id="bb775-125">Active Directory ドメイン サービス、エッジ サーバー、または Exchange Server に使用する別の資格情報を指定するには、[**Show advanced logon options**] をクリックし、必要な資格情報を示すチェック ボックスを個々にオンにします。次に、オンにした各チェック ボックスの資格情報を指定し、[**Connect to the Active Directory server**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb775-125">To specify different credentials that you want to use for Active Directory Domain Services, Edge Server, or Exchange Server, click **Show advanced logon options**, select each check box for which separate credentials are required, specify the credentials for each selected check box, and then click **Connect to the Active Directory server**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="bb775-p105">スキャンを開始する前に、ベスト プラクティス アナライザーはネットワークとアクセス許可のチェックを実行して、指定されたアカウント資格情報が有効で、ベスト プラクティス アナライザーが Active Directory ドメイン サービスに接続できるかどうかを確認します。ベスト プラクティス アナライザーをワークグループ サーバー上で実行すると、ベスト プラクティス アナライザーが境界ネットワーク内にあるエッジ サーバーに接続できるかどうか (つまり、これらのエッジ サーバーがスキャンに含まれるかどうか) も確認されます。</span><span class="sxs-lookup"><span data-stu-id="bb775-p105">Before beginning the scan, Best Practices Analyzer performs a network and permissions check to ensure that the specified account credentials are valid and that Best Practices Analyzer can connect to Active Directory Domain Services. If the tool is running on a workgroup server, the tool also verifies that it can connect to Edge Servers in the perimeter network (that is, if they are included in the scan).</span></span>

    
    </div>

5.  <span data-ttu-id="bb775-128">[**Start a new Best Practices scan**] ページで、スキャンに含めるオプションを選択し、ネットワークの速度を指定して、[**Start scanning**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb775-128">On the **Start a new Best Practices scan** page, select the options that you want to include in the scan, specify the network speed, and then click **Start scanning**.</span></span>

6.  <span data-ttu-id="bb775-129">[**Scanning Completed**] ページで、[**View a report of this Best Practices scan**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb775-129">On the **Scanning Completed** page, click **View a report of this Best Practices scan**.</span></span>

7.  <span data-ttu-id="bb775-130">[**View Best Practices Report**] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bb775-130">On the **View Best Practices Report** page, do one of the following:</span></span>
    
      - <span data-ttu-id="bb775-131">各レポートをサーバー コンポーネント別に分類してリストに表示するには、[**List Reports**] をクリックし、[**All Issues**] タブまたは [**Informational Items**] タブのどちらかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb775-131">To view reports in a list organized by server component, click **List Reports**, and then click either the **All Issues** tab or the **Informational Items** tab.</span></span>
    
      - <span data-ttu-id="bb775-132">各レポートを結果の種類別に分類した階層リストとして表示するには、[**Tree Reports**] をクリックし、[**Detailed View**] タブまたは [**Summary View**] タブのどちらかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb775-132">To view reports as a hierarchical list organized by types of results, click **Tree Reports**, and then click either the **Detailed View** tab or the **Summary View** tab.</span></span>
    
      - <span data-ttu-id="bb775-133">その他のレポートを表示するには、[**Other Reports**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb775-133">To view other reports, click **Other Reports**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="bb775-134">ベストプラクティスアナライザーのレポートと、そのレポートで特定される問題の詳細については、「 <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Lync server 2013 のベストプラクティスアナライザーによって作成されたレポートの表示と操作</A>」および「 <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">lync server 2013 でのベストプラクティスアナライザーによって識別される問題の分析と解決</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb775-134">For details about the Best Practices Analyzer reports and the issues they identify, see <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Viewing and working with reports created by Best Practices Analyzer in Lync Server 2013</A> and <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

