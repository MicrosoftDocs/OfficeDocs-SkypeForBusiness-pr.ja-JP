---
title: 'Lync Server 2013: 監視サーバーレポートの表示と分析'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing and analyzing monitoring server reports
ms:assetid: 4dd448f1-01d2-49b2-b109-0728f36566b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720332(v=OCS.15)
ms:contentKeyID: 63969599
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e4fce6cf17601d2a68a07a3b832e6b50c10b759
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a><span data-ttu-id="b7467-102">Lync Server 2013 で監視サーバーレポートを表示および分析する</span><span class="sxs-lookup"><span data-stu-id="b7467-102">Viewing and analyzing monitoring server reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7467-103">_**最終更新日:** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="b7467-103">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="b7467-104">サーバーレポートを監視すると、音声品質のさまざまな測定が行われ、エンドユーザーに配信される QoE が監視されます。</span><span class="sxs-lookup"><span data-stu-id="b7467-104">Monitoring Server reports provides several different measures of voice quality to monitor the QoE that is being delivered to end-users.</span></span> <span data-ttu-id="b7467-105">さらに、Monitoring Server には、組織のネットワークの使用状況やメディア品質の傾向を監視したり、発生したメディアの品質に関する問題のトラブルシューティングに使用できる、いくつかの組み込みレポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b7467-105">Additionally, Monitoring Server includes several built-in reports that your organization can use to watch usage and media quality trends on your organization's network and troubleshoot media quality issues that arise.</span></span>

<span data-ttu-id="b7467-106">毎日および毎週の操作でサーバーレポートの監視を行う主な部分は、次のようにメディア品質レポートを表示して分析することです。</span><span class="sxs-lookup"><span data-stu-id="b7467-106">A primary part of keeping Monitoring Server Reports interesting for daily and weekly operations is viewing and analyzing Media Quality Reports, in particular:</span></span>

  - <span data-ttu-id="b7467-107">QoE サマリー/トレンドレポート</span><span class="sxs-lookup"><span data-stu-id="b7467-107">QoE Summary/Trend Reports</span></span>

  - <span data-ttu-id="b7467-108">QoE のパフォーマンスレポート</span><span class="sxs-lookup"><span data-stu-id="b7467-108">QoE Performance Reports</span></span>

<div>

## <a name="view-reports-from-the-monitoring-server"></a><span data-ttu-id="b7467-109">監視サーバーからレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="b7467-109">View reports from the monitoring server</span></span>

1.  <span data-ttu-id="b7467-110">Web ブラウザーから、SQL reporting services をホストしているサーバーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="b7467-110">From a web browser, locate your servers hosting the SQL reporting services.</span></span>

2.  <span data-ttu-id="b7467-111">ブラウザー画面から必要なレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="b7467-111">View the required reports from the browser screen.</span></span>

3.  <span data-ttu-id="b7467-112">省略エクスポートオプションと必要な出力形式を選択して、レポートをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="b7467-112">(Optional) Export a report by selecting the export option and the required output format.</span></span>

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a><span data-ttu-id="b7467-113">通話の詳細記録 (CDR) を構成する</span><span class="sxs-lookup"><span data-stu-id="b7467-113">Configure call detail recording (CDR)</span></span>

1.  <span data-ttu-id="b7467-114">RTCUniversalServerAdmins グループのメンバーであるか (同等の権限を持つ)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b7467-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent permissions), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="b7467-115">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b7467-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="b7467-116">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**通話詳細記録**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7467-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="b7467-117">[**通話詳細記録**] ページで、表から適切なサイトをクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7467-117">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="b7467-118">[削除] を有効にするには、[**監視サーバーに対して消去を有効**にする] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b7467-118">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="b7467-119">[**通話の詳細記録を保持する期間 (日数)]:** 通話の詳細レコーディングの保持期間の最大値を選びます。</span><span class="sxs-lookup"><span data-stu-id="b7467-119">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>

7.  <span data-ttu-id="b7467-120">[**エラー報告データの最大保持期間 (日)**] で、 エラー報告を保持する必要のある最大日数を選択します。</span><span class="sxs-lookup"><span data-stu-id="b7467-120">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>

8.  <span data-ttu-id="b7467-121">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7467-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="configure-qoe"></a><span data-ttu-id="b7467-122">QoE の構成</span><span class="sxs-lookup"><span data-stu-id="b7467-122">Configure QoE</span></span>

1.  <span data-ttu-id="b7467-123">RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b7467-123">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="b7467-124">詳細については、「Delegate Setup Permissions」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7467-124">For details, see Delegate Setup Permissions.</span></span>

2.  <span data-ttu-id="b7467-125">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b7467-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="b7467-126">左側のナビゲーション バーで [**監視とアーカイブ**] をクリックし、[**QoE データ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7467-126">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="b7467-127">[**QoE データ**] ページで、表から該当するサイトをクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7467-127">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="b7467-128">[削除] を有効にするには、[**監視サーバーに対して消去を有効**にする] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b7467-128">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="b7467-129">[**通話を継続する] の [最長時間 (日数)]:** qoe データを保持する最大日数を選びます。</span><span class="sxs-lookup"><span data-stu-id="b7467-129">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that QoE data should be retained.</span></span>

7.  <span data-ttu-id="b7467-130">[コミット] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7467-130">Click Commit.</span></span>

</div>

<div>

## <a name="change-the-archiving-policy"></a><span data-ttu-id="b7467-131">アーカイブポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="b7467-131">Change the archiving policy</span></span>

1.  <span data-ttu-id="b7467-132">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b7467-132">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b7467-133">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b7467-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="b7467-134">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7467-134">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="b7467-135">ポリシーの一覧の [**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7467-135">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="b7467-136">[**アーカイブ ポリシーの編集 - グローバル**] で、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b7467-136">In **Edit Archiving Policy - Global**, do the following:</span></span>

6.  <span data-ttu-id="b7467-137">展開の内部アーカイブを有効または無効にするには、[**内部通信をアーカイブ**する] チェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="b7467-137">To enable or disable internal archiving for the deployment, select or clear the **Archive internal communications** check box.</span></span>

7.  <span data-ttu-id="b7467-138">展開の外部アーカイブを有効または無効にするには、[**外部の通信をアーカイブ**する] チェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="b7467-138">To enable or disable external archiving for the deployment, select or clear the **Archive external communications** check box.</span></span>

8.  <span data-ttu-id="b7467-139">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7467-139">Click **Commit**.</span></span>

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a><span data-ttu-id="b7467-140">ユーザーにアーカイブポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="b7467-140">Apply an archiving policy to a user</span></span>

1.  <span data-ttu-id="b7467-141">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b7467-141">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b7467-142">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b7467-142">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="b7467-143">左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="b7467-143">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="b7467-144">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7467-144">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="b7467-145">[**アーカイブポリシー**] の [ **Lync Server ユーザーの編集**] で、適用するアーカイブユーザーポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b7467-145">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>

6.  <span data-ttu-id="b7467-146">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7467-146">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b7467-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7467-147">See Also</span></span>


[<span data-ttu-id="b7467-148">Lync Server 2013 で監視レポートを使用する</span><span class="sxs-lookup"><span data-stu-id="b7467-148">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
[<span data-ttu-id="b7467-149">Lync Server 2013 のサーバーパフォーマンスレポート</span><span class="sxs-lookup"><span data-stu-id="b7467-149">Server Performance Report in Lync Server 2013</span></span>](lync-server-2013-server-performance-report.md)  
[<span data-ttu-id="b7467-150">Lync Server 2013 のメディア品質比較レポート</span><span class="sxs-lookup"><span data-stu-id="b7467-150">Media Quality Comparison Report in Lync Server 2013</span></span>](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

