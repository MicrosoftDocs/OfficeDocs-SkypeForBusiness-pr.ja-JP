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
ms.openlocfilehash: 3fc5f963ab9b0181463e3bf065baa61730c9fd0d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a><span data-ttu-id="dc695-102">Lync Server 2013 での監視サーバーレポートの表示と分析</span><span class="sxs-lookup"><span data-stu-id="dc695-102">Viewing and analyzing monitoring server reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc695-103">_**トピックの最終更新日:** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="dc695-103">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="dc695-104">監視サーバーレポートでは、エンドユーザーに配信されている QoE を監視するために、さまざまな音声品質の測定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="dc695-104">Monitoring Server reports provides several different measures of voice quality to monitor the QoE that is being delivered to end-users.</span></span> <span data-ttu-id="dc695-105">さらに、監視サーバーには、組織のネットワークで利用状況やメディア品質の傾向を監視し、発生したメディア品質の問題のトラブルシューティングに使用できる組み込みのレポートがいくつか含まれています。</span><span class="sxs-lookup"><span data-stu-id="dc695-105">Additionally, Monitoring Server includes several built-in reports that your organization can use to watch usage and media quality trends on your organization's network and troubleshoot media quality issues that arise.</span></span>

<span data-ttu-id="dc695-106">毎日および毎週の操作について監視サーバーレポートを保持する主な部分は、特にメディア品質レポートを表示および分析することです。</span><span class="sxs-lookup"><span data-stu-id="dc695-106">A primary part of keeping Monitoring Server Reports interesting for daily and weekly operations is viewing and analyzing Media Quality Reports, in particular:</span></span>

  - <span data-ttu-id="dc695-107">QoE の概要/傾向レポート</span><span class="sxs-lookup"><span data-stu-id="dc695-107">QoE Summary/Trend Reports</span></span>

  - <span data-ttu-id="dc695-108">QoE パフォーマンスレポート</span><span class="sxs-lookup"><span data-stu-id="dc695-108">QoE Performance Reports</span></span>

<div>

## <a name="view-reports-from-the-monitoring-server"></a><span data-ttu-id="dc695-109">監視サーバーからレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="dc695-109">View reports from the monitoring server</span></span>

1.  <span data-ttu-id="dc695-110">Web ブラウザーから、SQL reporting services をホストしているサーバーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="dc695-110">From a web browser, locate your servers hosting the SQL reporting services.</span></span>

2.  <span data-ttu-id="dc695-111">ブラウザーの画面から必要なレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="dc695-111">View the required reports from the browser screen.</span></span>

3.  <span data-ttu-id="dc695-112">オプションエクスポートオプションと必要な出力形式を選択して、レポートをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="dc695-112">(Optional) Export a report by selecting the export option and the required output format.</span></span>

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a><span data-ttu-id="dc695-113">通話詳細記録 (CDR) を構成する</span><span class="sxs-lookup"><span data-stu-id="dc695-113">Configure call detail recording (CDR)</span></span>

1.  <span data-ttu-id="dc695-114">RTCUniversalServerAdmins グループのメンバーである (またはそれと同等のアクセス許可を持つ) ユーザーアカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="dc695-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent permissions), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="dc695-115">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="dc695-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="dc695-116">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**通話詳細記録**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc695-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="dc695-117">[**通話詳細記録**] ページで、表から適切なサイトをクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc695-117">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="dc695-118">削除を有効にするには、[**監視サーバーの削除を有効**にする] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc695-118">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="dc695-119">[**通話詳細記録の最大保持期間**(日)] で、通話詳細記録を保持する最大日数を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc695-119">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>

7.  <span data-ttu-id="dc695-120">[**エラー報告データの最大保持期間 (日)**] で、 エラー報告を保持する必要のある最大日数を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc695-120">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>

8.  <span data-ttu-id="dc695-121">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc695-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="configure-qoe"></a><span data-ttu-id="dc695-122">QoE を構成する</span><span class="sxs-lookup"><span data-stu-id="dc695-122">Configure QoE</span></span>

1.  <span data-ttu-id="dc695-123">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="dc695-123">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="dc695-124">詳細については、「セットアップのアクセス許可の委任」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc695-124">For details, see Delegate Setup Permissions.</span></span>

2.  <span data-ttu-id="dc695-125">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="dc695-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="dc695-126">左側のナビゲーション バーで [**監視とアーカイブ**] をクリックし、[**QoE データ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc695-126">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="dc695-127">[**QoE データ**] ページで、表から該当するサイトをクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc695-127">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="dc695-128">削除を有効にするには、[**監視サーバーの削除を有効**にする] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc695-128">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="dc695-129">[**通話詳細記録の最大保持期間**(日)] で、qoe データを保持する最大日数を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc695-129">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that QoE data should be retained.</span></span>

7.  <span data-ttu-id="dc695-130">[確定] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc695-130">Click Commit.</span></span>

</div>

<div>

## <a name="change-the-archiving-policy"></a><span data-ttu-id="dc695-131">アーカイブポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="dc695-131">Change the archiving policy</span></span>

1.  <span data-ttu-id="dc695-132">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="dc695-132">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dc695-133">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="dc695-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="dc695-134">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc695-134">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="dc695-135">ポリシー一覧の **[グローバル]** をクリックし、**[編集]** をクリックしてから、**[詳細の表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc695-135">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="dc695-136">**[アーカイブ ポリシーの編集 - グローバル]** で、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dc695-136">In **Edit Archiving Policy - Global**, do the following:</span></span>

6.  <span data-ttu-id="dc695-137">展開の内部アーカイブを有効または無効にするには、[**内部通信をアーカイブ**する] チェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="dc695-137">To enable or disable internal archiving for the deployment, select or clear the **Archive internal communications** check box.</span></span>

7.  <span data-ttu-id="dc695-138">展開の外部アーカイブを有効または無効にするには、[**外部通信をアーカイブ**する] チェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="dc695-138">To enable or disable external archiving for the deployment, select or clear the **Archive external communications** check box.</span></span>

8.  <span data-ttu-id="dc695-139">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc695-139">Click **Commit**.</span></span>

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a><span data-ttu-id="dc695-140">ユーザーへのアーカイブポリシーの適用</span><span class="sxs-lookup"><span data-stu-id="dc695-140">Apply an archiving policy to a user</span></span>

1.  <span data-ttu-id="dc695-141">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="dc695-141">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dc695-142">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="dc695-142">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="dc695-143">左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="dc695-143">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="dc695-144">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc695-144">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="dc695-145">[ **Lync Server ユーザーの編集**] の [**アーカイブポリシー**] で、適用するアーカイブユーザーポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="dc695-145">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>

6.  <span data-ttu-id="dc695-146">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc695-146">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dc695-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc695-147">See Also</span></span>


[<span data-ttu-id="dc695-148">Lync Server 2013 での監視レポートの使用</span><span class="sxs-lookup"><span data-stu-id="dc695-148">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
[<span data-ttu-id="dc695-149">Lync Server 2013 のサーバーパフォーマンスレポート</span><span class="sxs-lookup"><span data-stu-id="dc695-149">Server Performance Report in Lync Server 2013</span></span>](lync-server-2013-server-performance-report.md)  
[<span data-ttu-id="dc695-150">Lync Server 2013 のメディア品質比較レポート</span><span class="sxs-lookup"><span data-stu-id="dc695-150">Media Quality Comparison Report in Lync Server 2013</span></span>](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

