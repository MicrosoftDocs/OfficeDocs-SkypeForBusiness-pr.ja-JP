---
title: 新しい Lync Server 2013 仲介サーバーを使用するようにボイスルートを変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
TOCTitle: Change voice routes to use the new Lync Server 2013 Mediation Server
ms:assetid: acd487b3-377c-46bf-9f71-fe6152002664
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205162(v=OCS.15)
ms:contentKeyID: 48185069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba933ec7c51b62e7f5008ad9f767a0695c88ebb2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36232920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a><span data-ttu-id="10b48-102">新しい Lync Server 2013 仲介サーバーを使用するようにボイスルートを変更する</span><span class="sxs-lookup"><span data-stu-id="10b48-102">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10b48-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="10b48-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="10b48-104">この手順では、従来の Office Communications Server 2007 R2 仲介サーバーではなく、Lync Server 2013 仲介サーバーを使用するように、ボイスルートを変更します。</span><span class="sxs-lookup"><span data-stu-id="10b48-104">This procedure changes the voice routes to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a><span data-ttu-id="10b48-105">新しい仲介サーバーを使用するようにボイスルートを変更するには</span><span class="sxs-lookup"><span data-stu-id="10b48-105">To change the voice routes to use the new Mediation Server</span></span>

1.  <span data-ttu-id="10b48-106">Lync Server 2013 コントロール パネル</span><span class="sxs-lookup"><span data-stu-id="10b48-106">Lync Server 2013 Control Panel</span></span>

2.  <span data-ttu-id="10b48-107">左側のウィンドウで、[**音声ルーティング**]、[Route] の**順**に選択します。</span><span class="sxs-lookup"><span data-stu-id="10b48-107">In the left pane, select **Voice Routing** and then **Route**.</span></span>

3.  <span data-ttu-id="10b48-108">[**新規**] をクリックして、新しいボイスルートを作成します。</span><span class="sxs-lookup"><span data-stu-id="10b48-108">Click **New** to create a New Voice Route.</span></span>

4.  <span data-ttu-id="10b48-109">次のフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="10b48-109">Fill in the following fields:</span></span>
    
      - <span data-ttu-id="10b48-110">**名前**: ボイスルートのわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="10b48-110">**Name**: Type a descriptive name of the voice route.</span></span> <span data-ttu-id="10b48-111">このドキュメントでは、 **W15PSTNRoute**を使用します。</span><span class="sxs-lookup"><span data-stu-id="10b48-111">For this document we will use **W15PSTNRoute**.</span></span>
    
      - <span data-ttu-id="10b48-112">[ **Description (説明**): ボイスルートの短い説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="10b48-112">**Description**: Type a short description of the voice route.</span></span>

5.  <span data-ttu-id="10b48-113">**関連するゲートウェイ**に到達するまで、残りのすべてのセクションをスキップします。</span><span class="sxs-lookup"><span data-stu-id="10b48-113">Skip all remaining sections until you reach **Associated gateways**.</span></span> <span data-ttu-id="10b48-114">[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10b48-114">Click **Add**.</span></span> <span data-ttu-id="10b48-115">新しいデフォルトゲートウェイを選択して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10b48-115">Select the new default gateway and click **OK**.</span></span>

6.  <span data-ttu-id="10b48-116">[**関連する PSTN 使用**] で、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10b48-116">Under **Associated PSTN Usages**, click **Select**.</span></span>

7.  <span data-ttu-id="10b48-117">**[PSTN 使用状況レコードの選択**] ページからレコード名を選び、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10b48-117">From the **Select PSTN Usage Record** page, select a record name and then click **OK**.</span></span>

8.  <span data-ttu-id="10b48-118">[**新しいボイスルーティング**] ページで [ **OK** ] をクリックして、**ボイスルート**を作成します。</span><span class="sxs-lookup"><span data-stu-id="10b48-118">From the **New Voice Route** page, click **OK** to create the **Voice Route**.</span></span>

9.  <span data-ttu-id="10b48-119">[**音声ルーティング**] ページで、[**ルーティング**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="10b48-119">From the **Voice Routing** page, select **Route**.</span></span>

10. <span data-ttu-id="10b48-120">新しく作成されたルートを一覧の一番上に移動して、[**コミット**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="10b48-120">Move the newly created route to the top of the list and then select **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

