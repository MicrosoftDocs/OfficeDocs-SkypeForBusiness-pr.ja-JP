---
title: 'Lync Server 2013: 監視の有効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling monitoring
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49733584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f07ea86bfeb9bd13f8fb3c4f34d114af075e6150
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-monitoring-in-lync-server-2013"></a><span data-ttu-id="4898a-102">Lync Server 2013 での監視の有効化</span><span class="sxs-lookup"><span data-stu-id="4898a-102">Enabling monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4898a-103">_**トピックの最終更新日:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="4898a-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="4898a-104">統合データ収集エージェントは各フロントエンドサーバーに自動的にインストールされ、アクティブ化されますが、Microsoft Lync Server 2013 のインストールが完了すると、自動的に監視データの収集が開始されるということではありません。</span><span class="sxs-lookup"><span data-stu-id="4898a-104">Although the unified data collection agents are automatically installed and activated on each Front End server, that does not mean that you will automatically begin to collect monitoring data the moment you finish installing Microsoft Lync Server 2013.</span></span> <span data-ttu-id="4898a-105">その代わりに、フロントエンドサーバーとフロントエンドプールを監視データベースに関連付ける必要があります。また、通話詳細記録 (CDR) および Quality of Experience (QoE) の監視をグローバルスコープまたはサイトスコープで有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4898a-105">Instead, you must do two things: you must associate your Front End servers/Front End pools with a monitoring database, and you must enable call detail recording (CDR) and/or Quality of Experience (QoE) monitoring at the global scope and/or the site scope.</span></span>

<span data-ttu-id="4898a-106">フロントエンドサーバーまたはフロントエンドプールを監視データベースに関連付ける詳細な手順については、「展開ガイド」の「 [Lync Server 2013 でのフロントエンドプールへの監視ストアの関連付け](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4898a-106">For step-by-step instructions on associating Front End servers or Front End pools with a monitoring database, see the topic [Associating a monitoring store with a Front End pool in Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) in the Deployment guide.</span></span> <span data-ttu-id="4898a-107">これらの関連付けが終わり、新しい Lync Server トポロジを公開しても、まだ監視データを収集することはできません。</span><span class="sxs-lookup"><span data-stu-id="4898a-107">After these associations have been made, and after your new Lync Server topology has been published, you will still not be able to collect monitoring data.</span></span> <span data-ttu-id="4898a-108">これは、既定では、Lync Server 2013 をインストールすると、CDR と QoE のデータ収集の両方が無効になるためです。</span><span class="sxs-lookup"><span data-stu-id="4898a-108">That's because, by default, both CDR and QoE data collection is disabled when you install Lync Server 2013.</span></span>

<span data-ttu-id="4898a-109">データ収集を開始するには、CDR 監視と QoE 監視のどちらかまたは両方を有効にする必要があります (CDR 監視と QoE 監視を両方とも有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4898a-109">In order to begin data collection you will need to enable CDR and/or QoE monitoring.</span></span> <span data-ttu-id="4898a-110">(必要に応じて、1つの種類の監視を有効にして、もう一方の種類を無効のままにすることができます)。グローバルスコープで CDR 監視を有効にするには、Lync Server 管理シェルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4898a-110">(Note that you do not have to enable both CDR and QoE monitoring; if you prefer, you can enable one type of monitoring while leaving the other type disabled.) To enable CDR monitoring at the global scope run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

<span data-ttu-id="4898a-111">または、Lync Server 2013 コントロールパネル内から CDR の監視を有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4898a-111">Alternatively, you can enable CDR monitoring from within the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="4898a-112">Lync Server コントロールパネル内から、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4898a-112">From within the Lync Server Control Panel, complete the following procedure:</span></span>

1.  <span data-ttu-id="4898a-113">[**監視**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4898a-113">Click **Monitoring**.</span></span>

2.  <span data-ttu-id="4898a-114">[**通話詳細記録**] タブで、[**グローバル**] 設定をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="4898a-114">On the **Call Detail Recording** tab, double-click the **Global** setting.</span></span>

3.  <span data-ttu-id="4898a-115">[**編集 通話詳細記録 (CDR) 設定**] ウィンドウで、[**CDR の監視を有効にする**] を選択し、[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4898a-115">In the **Edit Call Detail Recording (CDR) Setting** pane, select **Enable monitoring of CDRs** and then click **Commit**.</span></span>

<span data-ttu-id="4898a-116">グローバルスコープで QoE 監視を有効にするには、Lync Server 管理シェルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4898a-116">To enable QoE monitoring at the global scope, run this command from within the Lync Server Management Shell:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

<span data-ttu-id="4898a-117">必要に応じて、Lync Server コントロールパネル内から QoE 監視を有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4898a-117">If you prefer, you can also enable QoE monitoring from within the Lync Server Control Panel.</span></span> <span data-ttu-id="4898a-118">コントロール パネル内で、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4898a-118">From within the Control Panel, complete the following procedure:</span></span>

1.  <span data-ttu-id="4898a-119">[**監視**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4898a-119">Click **Monitoring**.</span></span>

2.  <span data-ttu-id="4898a-120">[**QoE データ**] タブで、[**グローバル**] 設定をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="4898a-120">On the **Quality of Experience Data** tab, double-click the **Global** setting.</span></span>

3.  <span data-ttu-id="4898a-121">[**編集 Quality of Experience (QoE) 設定**] ウィンドウで、[**QoE データの監視を有効にする**] を選択し、[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4898a-121">In the **Edit Quality of Experience (QoE) Setting** pane, select **Enable monitoring of QoE data** and then click **Commit**.</span></span>

<span data-ttu-id="4898a-122">前述したように、前述の例では、グローバルスコープで監視を有効にします。つまり、組織全体での CDR と QoE の監視を有効にします。</span><span class="sxs-lookup"><span data-stu-id="4898a-122">As noted, the preceding examples enable monitoring at the global scope; that is, they enable CDR and QoE monitoring throughout your organization.</span></span> <span data-ttu-id="4898a-123">または、サイトスコープで個別の CDR と QoE の構成設定を作成してから、各サイトの監視を選択的に有効または無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4898a-123">Alternatively, you can create separate CDR and QoE configuration settings at the site scope, and then selectively enable or disable monitoring for each site.</span></span> <span data-ttu-id="4898a-124">たとえば、Redmond サイトで CDR 監視を有効にしても、ダブリンサイトの CDR 監視を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4898a-124">For example, you could enable CDR monitoring for your Redmond site, yet disable CDR monitoring for your Dublin site.</span></span> <span data-ttu-id="4898a-125">監視構成設定の管理の詳細については、「 [Lync Server 2013 の通話詳細記録と qoe (Quality Of Experience) の設定を構成する](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md)」トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4898a-125">For more information on managing your monitoring configuration settings, see the Deployment guide topic [Configuring call detail recording and Quality of Experience settings in Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

