---
title: 'Lync Server 2013: (オプション) コールパークの展開を確認する'
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
ms.openlocfilehash: 5cfc0d62bcfabe1a5bcddfb069d95b18aa0d30d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a><span data-ttu-id="36d8b-102">省略Lync Server 2013 でのコールパークの展開を確認する</span><span class="sxs-lookup"><span data-stu-id="36d8b-102">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36d8b-103">_**最終更新日:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="36d8b-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="36d8b-104">コールパークのインストールと構成が完了したら、構成を確認して、パーキングと着信の取得が期待どおりに動作することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36d8b-104">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="36d8b-105">少なくとも、以下を確認してください。</span><span class="sxs-lookup"><span data-stu-id="36d8b-105">At minimum, verify the following:</span></span>

  - <span data-ttu-id="36d8b-106">コールパークが有効になっていて、ユーザが通話をパークしているユーザに電話をかけます。</span><span class="sxs-lookup"><span data-stu-id="36d8b-106">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="36d8b-107">このテストを実行する前に、音声ポリシーでコールパークを有効にしている場合は、その通話を保留にしているユーザーが Lync Server からサインアウトしてから、もう一度サインインすると、[着信の転送] リストの [コールパーク] オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="36d8b-107">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Lync Server, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span>

    
    </div>

  - <span data-ttu-id="36d8b-108">オービット番号をダイヤルして、電話を取ります。</span><span class="sxs-lookup"><span data-stu-id="36d8b-108">Dial the orbit number to retrieve the call.</span></span>

  - <span data-ttu-id="36d8b-p102">別の通話を保留して、保留した通話がタイムアウトするようにして、リングバックは取らないようにします。タイムアウトした通話が **OnTimeoutURI** で指定されているフォールバック宛先に正しくルーティングされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="36d8b-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

