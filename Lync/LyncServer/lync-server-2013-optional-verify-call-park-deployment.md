---
title: 'Lync Server 2013: (オプション) コールパーク展開の確認'
description: 'Lync Server 2013: (オプション) コールパーク展開を確認します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify Call Park deployment
ms:assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413076(v=OCS.15)
ms:contentKeyID: 48185952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 772392a3a791ed57c3220d80e9bd510d8803debb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541933"
---
# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a><span data-ttu-id="cbee2-103">オプションLync Server 2013 でのコールパーク展開の確認</span><span class="sxs-lookup"><span data-stu-id="cbee2-103">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbee2-104">_**トピックの最終更新日:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="cbee2-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="cbee2-105">コールパークをインストールして構成した後、構成を検証して、駐車が期待どおりに動作することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbee2-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="cbee2-106">少なくとも、以下を確認してください。</span><span class="sxs-lookup"><span data-stu-id="cbee2-106">At minimum, verify the following:</span></span>

  - <span data-ttu-id="cbee2-107">コールパークが有効になっていて、ユーザーが通話をパークできるユーザーを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cbee2-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cbee2-108">このテストを実行する直前に、音声ポリシーでコールパークを有効にした場合、その通話が参加しているユーザーは、Lync Server からサインアウトしてから再度サインインする必要があります。転送通話リストにコールパークオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cbee2-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Lync Server, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span>

    
    </div>

  - <span data-ttu-id="cbee2-109">オービット番号をダイヤルして、電話を取ります。</span><span class="sxs-lookup"><span data-stu-id="cbee2-109">Dial the orbit number to retrieve the call.</span></span>

  - <span data-ttu-id="cbee2-p102">別の通話を保留して、保留した通話がタイムアウトするようにして、リングバックは取らないようにします。タイムアウトした通話が **OnTimeoutURI** で指定されているフォールバック宛先に正しくルーティングされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cbee2-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

