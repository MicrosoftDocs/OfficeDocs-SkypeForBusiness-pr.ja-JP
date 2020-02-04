---
title: 'Lync Server 2013: お知らせアプリケーションの概要'
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
ms.openlocfilehash: a4c1b9210fcb0734b305a30d27c77b4e81257909
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755461"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="98772-102">Lync Server 2013 のお知らせアプリケーションの概要</span><span class="sxs-lookup"><span data-stu-id="98772-102">Overview of the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98772-103">_**最終更新日:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="98772-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="98772-104">アナウンスメントアプリケーションを展開するときに、割り当てられていない番号をダイヤルしたときに実行されるアクションを決定する、割り当てられていない番号テーブルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98772-104">When you deploy the Announcement application, you need to configure an unassigned number table that determines the action to be taken when someone dials an unassigned number.</span></span> <span data-ttu-id="98772-105">割り当てられていない番号テーブルには、組織で有効な電話番号の範囲が含まれており、各範囲を処理するアナウンスメントアプリケーションが指定されています。</span><span class="sxs-lookup"><span data-stu-id="98772-105">The unassigned number table contains ranges of phone numbers that are valid for the organization and specifies which Announcement application handles each range.</span></span> <span data-ttu-id="98772-106">発信者が組織で有効な電話番号をダイヤルしても、すべてのユーザーに割り当てられていない場合、Lync Server は、割り当てられていない番号ルーティングテーブルの番号を検索して、どの範囲の番号が一致しているかを特定し、その通話をお知らせにルーティングします。その範囲に対して指定されたアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="98772-106">When a caller dials a telephone number that is valid for your organization but is not assigned to anyone, Lync Server looks up the number in the unassigned number routing table, identifies which range the number falls in, and routes the call to the Announcement application specified for that range.</span></span> <span data-ttu-id="98772-107">アナウンスメントアプリケーションは、通話に応答し、音声メッセージを再生し (設定している場合)、電話を切断するか、オペレーターなどの事前に定義された宛先に転送します。</span><span class="sxs-lookup"><span data-stu-id="98772-107">The Announcement application answers the call and plays an audio message (if you configured it to do so) and then either disconnects the call or transfers it to a predetermined destination, such as to an operator.</span></span> <span data-ttu-id="98772-108">Lync Server Management Shell コマンドレットを使用して、複数の音声メッセージを構成するか、または移行先を転送することができます。</span><span class="sxs-lookup"><span data-stu-id="98772-108">You can use Lync Server Management Shell cmdlets to configure multiple audio messages or to transfer destinations.</span></span>

<span data-ttu-id="98772-p102">割り当てられていない番号の表の構成方法はその使用方法によって異なります。現在使用されていない特定の番号があり、各番号用に作成したメッセージを再生する必要がある場合、これらの特定の番号を割り当てられていない番号の表に入力できます。たとえば、顧客サービス デスクの番号を変更した場合、古い顧客サービス番号を入力して、新しい番号を知らせるアナウンスをその番号に関連付けることができます。組織から離れた従業員の番号など、割り当てられていない番号を呼び出す発信者に対して一般的なメッセージを再生する必要がある場合、組織内のすべての有効な内線番号の範囲を入力できます。割り当てられていない番号の表は、発信者が現在割り当てられていない番号をダイヤルすると常に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="98772-p102">How you configure the unassigned number table depends on how you want to use it. If you have specific numbers that are no longer in use and you want to play messages that are tailored for each number, you can enter those specific numbers in the unassigned number table. For example, if you changed the number for your customer service desk, you can enter the old customer service number and associate it with an announcement that gives the new number. If you want to play a general message to anyone who calls a number that is not assigned, such as for employees who have left your organization, you can enter ranges for all the valid extensions in your organization. The unassigned number table is invoked whenever the caller dials a number that is not currently assigned.</span></span>

<span data-ttu-id="98772-114">Lync Server 2013 では、応答グループアプリケーションを使用して、アナウンスメントアプリケーションが自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="98772-114">In Lync Server 2013, the Announcement application is automatically installed with the Response Group application.</span></span> <span data-ttu-id="98772-115">お知らせと応答グループのアプリケーションは、エンタープライズ Voip 展開の標準的なコンポーネントです。エンタープライズボイスを展開すると、これらの両方のアプリケーションが自動的に展開されます。</span><span class="sxs-lookup"><span data-stu-id="98772-115">The Announcement and Response Group applications are standard components of an Enterprise Voice deployment: When you deploy Enterprise Voice, both of these applications are automatically deployed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

