---
title: 'Lync Server 2013: (オプション) 応答グループの展開の確認'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify Response Group deployment
ms:assetid: 202ca4ab-8e6d-44a4-b7c8-071133074feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687989(v=OCS.15)
ms:contentKeyID: 49733579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b28fa4a83e89e446c5f4739d95fedea88769bc3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530744"
---
# <a name="optional-verify-response-group-deployment-in-lync-server-2013"></a><span data-ttu-id="395cb-102">オプションLync Server 2013 での応答グループの展開の確認</span><span class="sxs-lookup"><span data-stu-id="395cb-102">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="395cb-103">_**トピックの最終更新日:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="395cb-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="395cb-104">応答グループを構成した後、応答グループが想定どおりに機能するように構成を検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="395cb-104">After you configure Response Group, you need to verify the configuration to make sure your response groups work as expected.</span></span> <span data-ttu-id="395cb-105">少なくとも、次の種類のユーザーを使用して以下のシナリオを検証してください。</span><span class="sxs-lookup"><span data-stu-id="395cb-105">At minimum, verify the following scenarios by using the following types of users:</span></span>

<span data-ttu-id="395cb-106">**Users**</span><span class="sxs-lookup"><span data-stu-id="395cb-106">**Users**</span></span>

  - <span data-ttu-id="395cb-107">Lync Server 2013 に所属するユーザー</span><span class="sxs-lookup"><span data-stu-id="395cb-107">A user who is homed on Lync Server 2013</span></span>

  - <span data-ttu-id="395cb-108">公衆交換電話網 (PSTN) を使用する外部ユーザー</span><span class="sxs-lookup"><span data-stu-id="395cb-108">An external user who uses the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="395cb-109">Lync Server 2013 に所属するエージェント</span><span class="sxs-lookup"><span data-stu-id="395cb-109">An agent who is homed on Lync Server 2013</span></span>

<span data-ttu-id="395cb-110">**Scenarios**</span><span class="sxs-lookup"><span data-stu-id="395cb-110">**Scenarios**</span></span>

  - <span data-ttu-id="395cb-111">Lync Server 2013 ユーザーが応答グループを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="395cb-111">The Lync Server 2013 user calls the response group.</span></span>

  - <span data-ttu-id="395cb-112">外部ユーザーが応答グループを呼び出す。</span><span class="sxs-lookup"><span data-stu-id="395cb-112">The external user calls the response group.</span></span>

  - <span data-ttu-id="395cb-113">エージェントが別の通話に応答しているときにユーザーが応答グループを呼び出し、キューに入る。</span><span class="sxs-lookup"><span data-stu-id="395cb-113">A user calls the response group while the agent is on another call and goes to the queue.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

