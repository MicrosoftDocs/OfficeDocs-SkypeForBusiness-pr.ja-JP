---
title: 併置された仲介サーバーをスタンドアロンの仲介サーバーに移行する (オプション)
description: 併置された仲介サーバーをスタンドアロンの仲介サーバーに移行します (オプション)。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e99eb445e8377a52901f54f52ca3933babe15571
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559423"
---
# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a><span data-ttu-id="44acf-103">併置された仲介サーバーをスタンドアロンの仲介サーバーに移行する (オプション)</span><span class="sxs-lookup"><span data-stu-id="44acf-103">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44acf-104">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="44acf-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="44acf-105">次の手順を使用して、Standard Edition サーバーまたはフロントエンド プールに併置された仲介サーバーを単一サイト展開用のスタンドアロン仲介サーバーへ移行します。</span><span class="sxs-lookup"><span data-stu-id="44acf-105">Use the procedure that follows to transition your Mediation Server, collocated on your Standard Edition server or Front End pool, to a stand-alone Mediation Server for a single-site deployment.</span></span>

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a><span data-ttu-id="44acf-106">併置された仲介サーバーをスタンドアロンの仲介サーバーに移行するには</span><span class="sxs-lookup"><span data-stu-id="44acf-106">To transition a collocated Mediation Server to a stand-alone Mediation Server</span></span>

1.  <span data-ttu-id="44acf-107">トポロジ ビルダーで既存のトポロジを開きます。</span><span class="sxs-lookup"><span data-stu-id="44acf-107">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="44acf-108">左側のウィンドウで、[**仲介プール**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="44acf-108">In the left pane, navigate to **Mediation pools**.</span></span>

3.  <span data-ttu-id="44acf-109">[**仲介プール**] を右クリックし、[**新しい仲介サーバー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="44acf-109">Right-click **Mediation pools** and select **New Mediation Server**.</span></span>

4.  <span data-ttu-id="44acf-p101">[**新しい仲介プールの定義**] ページで、新しい仲介サーバー プールの FQDN を提供します。さらに、このプールを単一サーバー プールまたは複数サーバー プールとするかを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="44acf-p101">On the **Define New Mediation Pool** page, provide the FQDN of the new Mediation Server pool. Also, select whether this pool will be a single-server or multiple-server pool, and then click **Next**.</span></span>

5.  <span data-ttu-id="44acf-112">新しい仲介サーバーによる着信通話のルーティング先となる次ホップ フロントエンド サーバー プールを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="44acf-112">Select the next hop Front End server pool to which the new Mediation Server will route inbound calls, and then click **Next**.</span></span>

6.  <span data-ttu-id="44acf-113">仲介サーバーで使用されるエッジ プールを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="44acf-113">Select the Edge pool to be used by the Mediation Server and then click **Next**.</span></span>

7.  <span data-ttu-id="44acf-p102">[**PSTN ゲートウェイの指定**] ページで、以前の PSTN ゲートウェイを仲介サーバーと関連付けます。ゲートウェイを選択し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="44acf-p102">On the **Specify PSTN gateways** page, associate the previous PSTN gateway with the Mediation Server. Select the gateway and then click **Add**.</span></span>

8.  <span data-ttu-id="44acf-116">[**完了**] をクリックして、**新しい仲介プールの定義**ウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="44acf-116">Click **Finish** to close the **Define New Mediation Pool** wizard.</span></span>

9.  <span data-ttu-id="44acf-117">[ **トポロジビルダー**] で、最上位ノードの [ **Lync Server 2013**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="44acf-117">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

10. <span data-ttu-id="44acf-118">[**操作**] ウィンドウで、[**トポロジの公開**] を選択してウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="44acf-118">From the **Actions** pane, select **Publish Topology** and complete the wizard.</span></span>

11. <span data-ttu-id="44acf-119">「展開」のドキュメントの「 [install The 仲介 server For Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) 」の手順に従って、新しい仲介サーバーにファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="44acf-119">Follow the steps in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) in the Deployment documentation to install the files on the new Mediation Server.</span></span>

12. <span data-ttu-id="44acf-120">仲介サーバーにファイルをインストールした後、トポロジ ビルダーに戻り、左側のウィンドウでプールに移動します。</span><span class="sxs-lookup"><span data-stu-id="44acf-120">After the files are installed on the Mediation Server, return to Topology Builder, and in the left pane navigate to the pool.</span></span>

13. <span data-ttu-id="44acf-121">プールを右クリックし、[**プロパティの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="44acf-121">Right-click the pool and select **Edit Properties**.</span></span>

14. <span data-ttu-id="44acf-122">[**仲介サーバー**] で、[**併置された仲介サーバーが有効**] チェック ボックスをオフにし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="44acf-122">Under **Mediation Server**, clear the check box **Collocated Mediation Server enabled** and then click **OK**.</span></span>

15. <span data-ttu-id="44acf-123">[ **トポロジビルダー**] で、最上位ノードの [ **Lync Server 2013**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="44acf-123">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

16. <span data-ttu-id="44acf-124">[**操作**] メニューで、[**トポロジの公開**] を選択してウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="44acf-124">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

