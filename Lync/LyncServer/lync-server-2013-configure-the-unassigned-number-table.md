---
title: 'Lync Server 2013: 割り当てられていない番号の表の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the unassigned number table
ms:assetid: eaa01986-e92f-4328-acf6-4e46c4306a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399053(v=OCS.15)
ms:contentKeyID: 48185908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c59b44b31eececd002434b74085be85eaec9cbec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840311"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a><span data-ttu-id="46c6c-102">Lync Server 2013 での割り当てられていない番号の表の構成</span><span class="sxs-lookup"><span data-stu-id="46c6c-102">Configure the unassigned number table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46c6c-103">_**最終更新日:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="46c6c-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="46c6c-104">Lync Server 2013 では、組織で有効であっても、ユーザーまたは電話に割り当てられていない電話番号への着信通話に対して実行される処理を指定できます。</span><span class="sxs-lookup"><span data-stu-id="46c6c-104">In Lync Server 2013, you can specify what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or phone.</span></span> <span data-ttu-id="46c6c-105">発信者はメッセージを聞くことができます。または、別の送信先またはその両方にルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="46c6c-105">Callers can hear a message, or can be routed to another destination, or both.</span></span>

<span data-ttu-id="46c6c-p102">割り当てられていない番号の表の構成方法はその使用方法によって異なります。組織の有効な内線番号すべて、割り当てられていない内線番号のみ、または両方の種類の番号の組み合わせで、この表を構成できます。割り当てられていない番号の表には、割り当てられている番号と割り当てられていない番号を両方入れることができますが、現在割り当てられていない番号を発信者がダイヤルしたときのみ呼び出されます。有効な内線番号すべてを割り当てられていない番号の表に入れる場合、テーブルを再構成しなくても、ユーザーが組織を離れたとき必ず行う処理を指定できます。割り当てられていない内線番号を表に入れる場合、特定の番号について行う処理を変更できます。たとえば、顧客サービス デスクの内線番号を変更する場合、古い顧客サービス番号を表に入れ、新しい番号を知らせるアナウンスをそれに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="46c6c-p102">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="46c6c-112">[割り当てられていない番号] テーブルを構成する前に、システムで既にお知らせを定義するか、Exchange ユニファイドメッセージング (UM) 自動応答を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46c6c-112">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="46c6c-113">ユーザーが割り当てられていない番号を呼び出した場合、Lync Server は、未割り当ての番号テーブルを上から下に検索し、最初の一致する範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="46c6c-113">When someone calls an unassigned number, Lync Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="46c6c-114">したがって、最後の手段として実行される処理は、表の最終範囲に指定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="46c6c-114">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="46c6c-115">このセクション中</span><span class="sxs-lookup"><span data-stu-id="46c6c-115">In This Section</span></span>

<span data-ttu-id="46c6c-116">[Lync Server 2013 で、割り当てられていない番号範囲を作成または変更](lync-server-2013-create-or-modify-an-unassigned-number-range.md)する[Lync Server 2013 でお知らせを作成](lync-server-2013-create-an-announcement.md)する</span><span class="sxs-lookup"><span data-stu-id="46c6c-116">[Create or modify an unassigned number range in Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [Create an announcement in Lync Server 2013](lync-server-2013-create-an-announcement.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

