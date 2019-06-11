---
title: 'Lync Server 2013: (オプション) 応答グループの展開を確認する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Verify Response Group deployment
ms:assetid: 202ca4ab-8e6d-44a4-b7c8-071133074feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687989(v=OCS.15)
ms:contentKeyID: 49733579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3b031ab8fdaac5249146faedafcc23517040b3a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-response-group-deployment-in-lync-server-2013"></a><span data-ttu-id="ba5d1-102">省略Lync Server 2013 での応答グループの展開を確認する</span><span class="sxs-lookup"><span data-stu-id="ba5d1-102">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba5d1-103">_**最終更新日:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="ba5d1-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="ba5d1-104">応答グループを構成したら、応答グループが期待どおりに動作するように構成を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba5d1-104">After you configure Response Group, you need to verify the configuration to make sure your response groups work as expected.</span></span> <span data-ttu-id="ba5d1-105">少なくとも、次の種類のユーザーを使用して以下のシナリオを検証してください。</span><span class="sxs-lookup"><span data-stu-id="ba5d1-105">At minimum, verify the following scenarios by using the following types of users:</span></span>

<span data-ttu-id="ba5d1-106">**ユーザー**</span><span class="sxs-lookup"><span data-stu-id="ba5d1-106">**Users**</span></span>

  - <span data-ttu-id="ba5d1-107">Lync Server 2013 をホームとしているユーザー</span><span class="sxs-lookup"><span data-stu-id="ba5d1-107">A user who is homed on Lync Server 2013</span></span>

  - <span data-ttu-id="ba5d1-108">公衆交換電話網 (PSTN) を使用する外部ユーザー</span><span class="sxs-lookup"><span data-stu-id="ba5d1-108">An external user who uses the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="ba5d1-109">Lync Server 2013 をホームとしているエージェント</span><span class="sxs-lookup"><span data-stu-id="ba5d1-109">An agent who is homed on Lync Server 2013</span></span>

<span data-ttu-id="ba5d1-110">**シナリオ**</span><span class="sxs-lookup"><span data-stu-id="ba5d1-110">**Scenarios**</span></span>

  - <span data-ttu-id="ba5d1-111">Lync Server 2013 ユーザーが応答グループを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ba5d1-111">The Lync Server 2013 user calls the response group.</span></span>

  - <span data-ttu-id="ba5d1-112">外部ユーザーが応答グループを呼び出す。</span><span class="sxs-lookup"><span data-stu-id="ba5d1-112">The external user calls the response group.</span></span>

  - <span data-ttu-id="ba5d1-113">エージェントが別の通話に応答しているときにユーザーが応答グループを呼び出し、キューに入る。</span><span class="sxs-lookup"><span data-stu-id="ba5d1-113">A user calls the response group while the agent is on another call and goes to the queue.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

