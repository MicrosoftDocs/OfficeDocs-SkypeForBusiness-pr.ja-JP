---
title: 'Lync Server 2013: アナウンスメントアプリケーションの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Announcement application
ms:assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204757(v=OCS.15)
ms:contentKeyID: 48183689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83e711eb408d0819c818157f85fbb0ff81930da7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="9e7a6-102">Lync Server 2013 のアナウンスアプリケーションの概要</span><span class="sxs-lookup"><span data-stu-id="9e7a6-102">Overview of the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e7a6-103">_**トピックの最終更新日:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="9e7a6-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="9e7a6-104">アナウンスメントアプリケーションを展開するときに、割り当てられていない番号にダイヤルしたときに実行されるアクションを決定する割り当てられていない番号の表を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e7a6-104">When you deploy the Announcement application, you need to configure an unassigned number table that determines the action to be taken when someone dials an unassigned number.</span></span> <span data-ttu-id="9e7a6-105">割り当てられていない番号の表には、組織に対して有効な電話番号の範囲が含まれており、各範囲を処理するアナウンスアプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e7a6-105">The unassigned number table contains ranges of phone numbers that are valid for the organization and specifies which Announcement application handles each range.</span></span> <span data-ttu-id="9e7a6-106">発信者が組織に対して有効な電話番号をダイヤルしたが、だれにも割り当てられていない場合、Lync Server は、割り当てられていない番号ルーティングテーブルから番号を検索し、その番号がどの範囲にあるかを識別し、その通話をアナウンスにルーティングします。その範囲に対して指定されているアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="9e7a6-106">When a caller dials a telephone number that is valid for your organization but is not assigned to anyone, Lync Server looks up the number in the unassigned number routing table, identifies which range the number falls in, and routes the call to the Announcement application specified for that range.</span></span> <span data-ttu-id="9e7a6-107">アナウンスアプリケーションは、通話に応答して、音声メッセージを再生し (そのように構成した場合)、呼び出しを切断するか、またはオペレーターなどの事前に決められた送信先に転送します。</span><span class="sxs-lookup"><span data-stu-id="9e7a6-107">The Announcement application answers the call and plays an audio message (if you configured it to do so) and then either disconnects the call or transfers it to a predetermined destination, such as to an operator.</span></span> <span data-ttu-id="9e7a6-108">Lync Server 管理シェルコマンドレットを使用して、複数のオーディオメッセージを構成したり、宛先を転送したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="9e7a6-108">You can use Lync Server Management Shell cmdlets to configure multiple audio messages or to transfer destinations.</span></span>

<span data-ttu-id="9e7a6-109">割り当てられていない番号の表の構成方法はその使用方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="9e7a6-109">How you configure the unassigned number table depends on how you want to use it.</span></span> <span data-ttu-id="9e7a6-110">使用されなくなった特定の番号が、それぞれの番号に対してカスタマイズされたメッセージを再生する必要がある場合は、これらの番号を割り当てられていない番号の表に入力することができます。</span><span class="sxs-lookup"><span data-stu-id="9e7a6-110">If you have specific numbers that are no longer in use and you want to play messages that are tailored for each number, you can enter those specific numbers in the unassigned number table.</span></span> <span data-ttu-id="9e7a6-111">たとえば、顧客サービスデスクの番号を変更した場合は、古い顧客サービス番号を入力して、それを新しい番号を提供するアナウンスに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="9e7a6-111">For example, if you changed the number for your customer service desk, you can enter the old customer service number and associate it with an announcement that gives the new number.</span></span> <span data-ttu-id="9e7a6-112">割り当てられていない番号を呼び出すユーザー (組織を退職した従業員など) に対して、一般的なメッセージを再生する場合は、組織内のすべての有効な内線番号の範囲を入力できます。</span><span class="sxs-lookup"><span data-stu-id="9e7a6-112">If you want to play a general message to anyone who calls a number that is not assigned, such as for employees who have left your organization, you can enter ranges for all the valid extensions in your organization.</span></span> <span data-ttu-id="9e7a6-113">割り当てられていない番号の表は、発信者が現在割り当てられていない番号をダイヤルしたときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9e7a6-113">The unassigned number table is invoked whenever the caller dials a number that is not currently assigned.</span></span>

<span data-ttu-id="9e7a6-114">Lync Server 2013 では、アナウンスアプリケーションは応答グループアプリケーションと共に自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9e7a6-114">In Lync Server 2013, the Announcement application is automatically installed with the Response Group application.</span></span> <span data-ttu-id="9e7a6-115">アナウンスメントおよび応答グループアプリケーションは、エンタープライズ Voip 展開の標準的なコンポーネントです。エンタープライズ Voip を展開すると、これらの両方のアプリケーションが自動的に展開されます。</span><span class="sxs-lookup"><span data-stu-id="9e7a6-115">The Announcement and Response Group applications are standard components of an Enterprise Voice deployment: When you deploy Enterprise Voice, both of these applications are automatically deployed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

