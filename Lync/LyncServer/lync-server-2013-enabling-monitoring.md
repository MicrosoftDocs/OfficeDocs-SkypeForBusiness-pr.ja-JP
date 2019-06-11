---
title: 'Lync Server 2013: 監視を有効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling monitoring
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49733584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2b13028390328e93a9e90636962dedea8ea8ec9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-monitoring-in-lync-server-2013"></a><span data-ttu-id="0341b-102">Lync Server 2013 で監視を有効にする</span><span class="sxs-lookup"><span data-stu-id="0341b-102">Enabling monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0341b-103">_**最終更新日:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="0341b-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="0341b-104">統合データ収集エージェントは、各フロントエンドサーバーに自動的にインストールされ、アクティブ化されますが、Microsoft Lync Server 2013 のインストールが完了した時点で自動的に監視データの収集が開始されるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="0341b-104">Although the unified data collection agents are automatically installed and activated on each Front End server, that does not mean that you will automatically begin to collect monitoring data the moment you finish installing Microsoft Lync Server 2013.</span></span> <span data-ttu-id="0341b-105">代わりに、フロントエンドサーバー/フロントエンドプールを監視データベースに関連付ける必要があります。また、グローバルスコープまたはサイトの範囲で、通話の詳細記録 (CDR) および品質のエクスペリエンス (QoE) の監視を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0341b-105">Instead, you must do two things: you must associate your Front End servers/Front End pools with a monitoring database, and you must enable call detail recording (CDR) and/or Quality of Experience (QoE) monitoring at the global scope and/or the site scope.</span></span>

<span data-ttu-id="0341b-106">フロントエンドサーバーまたはフロントエンドプールと監視データベースの関連付けの詳細な手順については、展開ガイドの「 [Lync Server 2013 でのフロントエンドプールへの監視ストアの関連付け](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0341b-106">For step-by-step instructions on associating Front End servers or Front End pools with a monitoring database, see the topic [Associating a monitoring store with a Front End pool in Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) in the Deployment guide.</span></span> <span data-ttu-id="0341b-107">この関連付けが行われた後、新しい Lync サーバートポロジが公開された後でも、監視データを収集することはできません。</span><span class="sxs-lookup"><span data-stu-id="0341b-107">After these associations have been made, and after your new Lync Server topology has been published, you will still not be able to collect monitoring data.</span></span> <span data-ttu-id="0341b-108">これは、Lync Server 2013 をインストールしたときに、既定では CDR と QoE のデータ収集が無効になるためです。</span><span class="sxs-lookup"><span data-stu-id="0341b-108">That's because, by default, both CDR and QoE data collection is disabled when you install Lync Server 2013.</span></span>

<span data-ttu-id="0341b-109">データの収集を開始するには、CDR または QoE の監視を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0341b-109">In order to begin data collection you will need to enable CDR and/or QoE monitoring.</span></span> <span data-ttu-id="0341b-110">(CDR と QoE の両方の監視を有効にする必要はありません。必要に応じて、他の種類を無効のままにして、1つの種類の監視を有効にすることができます)。グローバルスコープで CDR の監視を有効にするには、Lync Server 管理シェルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0341b-110">(Note that you do not have to enable both CDR and QoE monitoring; if you prefer, you can enable one type of monitoring while leaving the other type disabled.) To enable CDR monitoring at the global scope run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

<span data-ttu-id="0341b-111">または、Lync Server 2013 コントロールパネル内から CDR の監視を有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0341b-111">Alternatively, you can enable CDR monitoring from within the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="0341b-112">Lync Server コントロールパネル内で、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0341b-112">From within the Lync Server Control Panel, complete the following procedure:</span></span>

1.  <span data-ttu-id="0341b-113">[**モニタリング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0341b-113">Click **Monitoring**.</span></span>

2.  <span data-ttu-id="0341b-114">[**通話の詳細記録**] タブで、[**グローバル**設定] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="0341b-114">On the **Call Detail Recording** tab, double-click the **Global** setting.</span></span>

3.  <span data-ttu-id="0341b-115">[**通話の詳細記録 (CDR) の設定**] ウィンドウで、[ **CDRs の監視を有効にする**] を選び、[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0341b-115">In the **Edit Call Detail Recording (CDR) Setting** pane, select **Enable monitoring of CDRs** and then click **Commit**.</span></span>

<span data-ttu-id="0341b-116">グローバルスコープで QoE の監視を有効にするには、Lync Server 管理シェルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0341b-116">To enable QoE monitoring at the global scope, run this command from within the Lync Server Management Shell:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

<span data-ttu-id="0341b-117">必要に応じて、Lync Server コントロールパネル内から QoE の監視を有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0341b-117">If you prefer, you can also enable QoE monitoring from within the Lync Server Control Panel.</span></span> <span data-ttu-id="0341b-118">コントロールパネルで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0341b-118">From within the Control Panel, complete the following procedure:</span></span>

1.  <span data-ttu-id="0341b-119">[**モニタリング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0341b-119">Click **Monitoring**.</span></span>

2.  <span data-ttu-id="0341b-120">[**エクスペリエンスの品質データ**] タブで、[**グローバル**設定] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="0341b-120">On the **Quality of Experience Data** tab, double-click the **Global** setting.</span></span>

3.  <span data-ttu-id="0341b-121">[ **Quality Of Experience (qoe) の設定**] ウィンドウで、[ **qoe データの監視を有効にする**] を選び、[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0341b-121">In the **Edit Quality of Experience (QoE) Setting** pane, select **Enable monitoring of QoE data** and then click **Commit**.</span></span>

<span data-ttu-id="0341b-122">既に説明したように、上の例ではグローバルスコープで監視を有効にします。つまり、ユーザーは組織全体で CDR と QoE の監視を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0341b-122">As noted, the preceding examples enable monitoring at the global scope; that is, they enable CDR and QoE monitoring throughout your organization.</span></span> <span data-ttu-id="0341b-123">または、サイトのスコープで個別の CDR と QoE の構成設定を作成して、各サイトの監視を個別に有効または無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0341b-123">Alternatively, you can create separate CDR and QoE configuration settings at the site scope, and then selectively enable or disable monitoring for each site.</span></span> <span data-ttu-id="0341b-124">たとえば、Redmond サイトで CDR の監視を有効にしていても、ダブリンサイトの CDR 監視を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="0341b-124">For example, you could enable CDR monitoring for your Redmond site, yet disable CDR monitoring for your Dublin site.</span></span> <span data-ttu-id="0341b-125">監視構成の設定を管理する方法について詳しくは、「 [Lync Server 2013 での通話の詳細の記録と音質の設定](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0341b-125">For more information on managing your monitoring configuration settings, see the Deployment guide topic [Configuring call detail recording and Quality of Experience settings in Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

