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
ms.openlocfilehash: d792626a973a790313b2cdc1bd9df9092175f28a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="including-the-security-desk-in-lync-server-2013"></a><span data-ttu-id="453c4-102">Lync Server 2013 にセキュリティデスクを含める</span><span class="sxs-lookup"><span data-stu-id="453c4-102">Including the security desk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="453c4-103">_**最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="453c4-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="453c4-p101">会社によっては、セキュリティ デスクを緊急通話と関連させる必要があるかもしれません。セキュリティ デスクを E9-1-1 の展開に統合する方法を決定するには、以下の内容を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="453c4-p101">Your company may require the security desk to become involved in an emergency call. To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>

  - <span data-ttu-id="453c4-106">**緊急電話をセキュリティ デスクに通知するか。**</span><span class="sxs-lookup"><span data-stu-id="453c4-106">**Do you want the security desk to be notified when there is an emergency call?**</span></span>  
    <span data-ttu-id="453c4-107">Lync Server がインスタントメッセージング (IM) の通知を1つまたは複数のセキュリティ担当者の Lync SIP アドレスに送信するように、場所のポリシーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="453c4-107">You can configure the location policy so that Lync Server sends instant messaging (IM) alerts to the Lync SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="453c4-108">これらの通知には、緊急電話を発信した人物の名前、番号、および場所が含まれており、セキュリティ担当者による緊急事態の支援を容易にします。</span><span class="sxs-lookup"><span data-stu-id="453c4-108">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>

<!-- end list -->

  - <span data-ttu-id="453c4-109">**緊急電話ごとにセキュリティ デスクと協議するか。**</span><span class="sxs-lookup"><span data-stu-id="453c4-109">**Do you want to conference the security desk in on each emergency call?**</span></span>  
    <span data-ttu-id="453c4-p103">緊急サービスのサービス プロバイダーがサポートしている場合は、場所ポリシーを構成して、各緊急電話にコールバック番号を含めることができます。プロバイダーはこの番号を使用して、組織のセキュリティ担当者が緊急電話に参加できるようにします。この場合、場所ポリシーで、一方向 (聞き取りのみ) で参加するか、または両方向 (双方向) で参加するかを構成できます。</span><span class="sxs-lookup"><span data-stu-id="453c4-p103">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call. This number is then used by the provider to conference your organization's security personnel into emergency calls. This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="453c4-p104">必要に応じて、場所ポリシーごとに異なる緊急担当者を構成できます。これにより、社内の領域によって応答をカスタマイズしたり、緊急電話がネットワークの内部からのものか外部からのものであるかによって、緊急電話の動作を変えたりすることができます。配布グループを使用すると、通知する担当者を指定できます。</span><span class="sxs-lookup"><span data-stu-id="453c4-p104">If desired, you can configure different emergency personnel for each location policy. This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network. You can use distribution groups to specify the personnel you want to notify.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

