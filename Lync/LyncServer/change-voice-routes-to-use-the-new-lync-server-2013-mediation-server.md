---
title: 新しい Lync Server 2013 仲介サーバーを使用するように音声ルートを変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change voice routes to use the new Lync Server 2013 Mediation Server
ms:assetid: acd487b3-377c-46bf-9f71-fe6152002664
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205162(v=OCS.15)
ms:contentKeyID: 48185069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34c4ea975225eb685acaa1843e324ffa720a93e9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499664"
---
# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a><span data-ttu-id="14cdf-102">新しい Lync Server 2013 仲介サーバーを使用するように音声ルートを変更する</span><span class="sxs-lookup"><span data-stu-id="14cdf-102">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14cdf-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="14cdf-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="14cdf-104">この手順では、従来の Office Communications Server 2007 R2 仲介サーバーではなく、Lync Server 2013 仲介サーバーを使用するように音声ルートを変更します。</span><span class="sxs-lookup"><span data-stu-id="14cdf-104">This procedure changes the voice routes to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a><span data-ttu-id="14cdf-105">新しい仲介サーバーを使用するように音声ルートを変更するには</span><span class="sxs-lookup"><span data-stu-id="14cdf-105">To change the voice routes to use the new Mediation Server</span></span>

1.  <span data-ttu-id="14cdf-106">Lync Server 2013 コントロール パネル</span><span class="sxs-lookup"><span data-stu-id="14cdf-106">Lync Server 2013 Control Panel</span></span>

2.  <span data-ttu-id="14cdf-107">左ウィンドウで、[**音声のルーティング**]、[**ルート**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="14cdf-107">In the left pane, select **Voice Routing** and then **Route**.</span></span>

3.  <span data-ttu-id="14cdf-108">[**新規**] をクリックして、新しい音声ルートを作成します。</span><span class="sxs-lookup"><span data-stu-id="14cdf-108">Click **New** to create a New Voice Route.</span></span>

4.  <span data-ttu-id="14cdf-109">次のフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="14cdf-109">Fill in the following fields:</span></span>
    
      - <span data-ttu-id="14cdf-p101">[**名前**]: 音声ルートのわかりやすい名前を入力します。このドキュメントでは、**W15PSTNRoute** を使用します。</span><span class="sxs-lookup"><span data-stu-id="14cdf-p101">**Name**: Type a descriptive name of the voice route. For this document we will use **W15PSTNRoute**.</span></span>
    
      - <span data-ttu-id="14cdf-112">[**説明**]: 音声ルートの簡単な説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="14cdf-112">**Description**: Type a short description of the voice route.</span></span>

5.  <span data-ttu-id="14cdf-p102">[**関連付けられているゲートウェイ**] より前の残りのすべてのセクションをスキップします。[**追加**] をクリックします。新しいデフォルト ゲートウェイを選択し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14cdf-p102">Skip all remaining sections until you reach **Associated gateways**. Click **Add**. Select the new default gateway and click **OK**.</span></span>

6.  <span data-ttu-id="14cdf-116">[**関連付けられている PSTN 使用法**] で、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14cdf-116">Under **Associated PSTN Usages**, click **Select**.</span></span>

7.  <span data-ttu-id="14cdf-117">[**PSTN 使用法レコードの選択**] ページで、レコードの名前を選択し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14cdf-117">From the **Select PSTN Usage Record** page, select a record name and then click **OK**.</span></span>

8.  <span data-ttu-id="14cdf-118">[**新規音声ルート**] ページで、[**OK**] をクリックして [**音声ルート**] を作成します。</span><span class="sxs-lookup"><span data-stu-id="14cdf-118">From the **New Voice Route** page, click **OK** to create the **Voice Route**.</span></span>

9.  <span data-ttu-id="14cdf-119">[**音声のルーティング**] ページで、[**ルート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="14cdf-119">From the **Voice Routing** page, select **Route**.</span></span>

10. <span data-ttu-id="14cdf-120">新しく作成されたルートを一覧の先頭に移動し、[**コミット**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="14cdf-120">Move the newly created route to the top of the list and then select **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

