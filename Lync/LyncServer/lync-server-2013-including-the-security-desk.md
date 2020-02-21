---
title: 'Lync Server 2013: セキュリティデスクを含む'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Including the security desk
ms:assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398299(v=OCS.15)
ms:contentKeyID: 48184084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c4f42225d4694c707e4967c198b09014ab6fa17
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196660"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="including-the-security-desk-in-lync-server-2013"></a><span data-ttu-id="5f645-102">Lync Server 2013 にセキュリティデスクを含める</span><span class="sxs-lookup"><span data-stu-id="5f645-102">Including the security desk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f645-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="5f645-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="5f645-104">会社では、セキュリティデスクを緊急電話に参加させる必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="5f645-104">Your company may require the security desk to become involved in an emergency call.</span></span> <span data-ttu-id="5f645-105">E9-1-1 展開にセキュリティデスクを統合する方法を決定するには、次の質問に答える必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f645-105">To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>

  - <span data-ttu-id="5f645-106">**緊急電話がある場合にセキュリティデスクに通知するかどうか。**</span><span class="sxs-lookup"><span data-stu-id="5f645-106">**Do you want the security desk to be notified when there is an emergency call?**</span></span>  
    <span data-ttu-id="5f645-107">Lync Server がインスタントメッセージング (IM) 通知を1つ以上のセキュリティ担当者の Lync SIP アドレスに送信するように、場所のポリシーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="5f645-107">You can configure the location policy so that Lync Server sends instant messaging (IM) alerts to the Lync SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="5f645-108">これらの通知には、緊急電話をかけた人物の名前、電話番号、場所が含まれており、セキュリティ担当者が緊急事態を支援する際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5f645-108">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>

<!-- end list -->

  - <span data-ttu-id="5f645-109">**各緊急電話でセキュリティデスクに電話をかけることができますか。**</span><span class="sxs-lookup"><span data-stu-id="5f645-109">**Do you want to conference the security desk in on each emergency call?**</span></span>  
    <span data-ttu-id="5f645-110">緊急サービスのサービスプロバイダーがサポートしている場合は、それぞれの緊急電話でコールバック番号を含めるように場所のポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="5f645-110">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call.</span></span> <span data-ttu-id="5f645-111">この番号は、プロバイダーが組織のセキュリティ担当者を緊急電話に会議するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5f645-111">This number is then used by the provider to conference your organization's security personnel into emergency calls.</span></span> <span data-ttu-id="5f645-112">この会議は、場所のポリシーで一方向 (リッスンのみ) または双方向 (双方向) に構成できます。</span><span class="sxs-lookup"><span data-stu-id="5f645-112">This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5f645-113">必要に応じて、場所ポリシーごとに異なる緊急担当者を構成できます。</span><span class="sxs-lookup"><span data-stu-id="5f645-113">If desired, you can configure different emergency personnel for each location policy.</span></span> <span data-ttu-id="5f645-114">これにより、社内のさまざまな領域に対する応答をカスタマイズしたり、ネットワークの外部ではなく、内部から発信された緊急通話に対して異なる動作を作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="5f645-114">This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network.</span></span> <span data-ttu-id="5f645-115">配布グループを使用して、通知する担当者を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5f645-115">You can use distribution groups to specify the personnel you want to notify.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

