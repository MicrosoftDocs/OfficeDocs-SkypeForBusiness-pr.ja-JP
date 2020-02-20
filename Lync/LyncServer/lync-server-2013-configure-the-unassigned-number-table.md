---
title: 'Lync Server 2013: 割り当てられていない番号の表を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the unassigned number table
ms:assetid: eaa01986-e92f-4328-acf6-4e46c4306a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399053(v=OCS.15)
ms:contentKeyID: 48185908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef82a5976769543f83dc4656cf09eb64b94d7571
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a><span data-ttu-id="52b39-102">Lync Server 2013 で割り当てられていない番号の表を構成する</span><span class="sxs-lookup"><span data-stu-id="52b39-102">Configure the unassigned number table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52b39-103">_**トピックの最終更新日:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="52b39-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="52b39-104">Lync Server 2013 では、組織で有効になっているが、ユーザーまたは電話に割り当てられていない電話番号への着信呼び出しに対して実行される処理を指定できます。</span><span class="sxs-lookup"><span data-stu-id="52b39-104">In Lync Server 2013, you can specify what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or phone.</span></span> <span data-ttu-id="52b39-105">発信者は、メッセージを聞くことも、別の宛先にルーティングすることもできます。またはその両方を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="52b39-105">Callers can hear a message, or can be routed to another destination, or both.</span></span>

<span data-ttu-id="52b39-106">割り当てられていない番号の表の構成方法はその使用方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="52b39-106">How you configure the unassigned number table depends on how you want to use it.</span></span> <span data-ttu-id="52b39-107">組織の有効な内線番号すべて、割り当てられていない内線番号のみ、または両方の種類の番号の組み合わせで、この表を構成できます。</span><span class="sxs-lookup"><span data-stu-id="52b39-107">You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers.</span></span> <span data-ttu-id="52b39-108">割り当てられていない番号の表には、割り当てられている番号と割り当てられていない番号を両方入れることができますが、現在割り当てられていない番号を発信者がダイヤルしたときのみ呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="52b39-108">The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned.</span></span> <span data-ttu-id="52b39-109">有効な内線番号すべてを割り当てられていない番号の表に入れる場合、テーブルを再構成しなくても、ユーザーが組織を離れたとき必ず行う処理を指定できます。</span><span class="sxs-lookup"><span data-stu-id="52b39-109">If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table.</span></span> <span data-ttu-id="52b39-110">割り当てられていない拡張子を表に含める場合は、特定の番号に対して発生する操作を変更できます。</span><span class="sxs-lookup"><span data-stu-id="52b39-110">If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers.</span></span> <span data-ttu-id="52b39-111">たとえば、顧客サービスデスクの拡張機能を変更した場合は、古い顧客サービス番号を表に含めて、新しい番号を提供するアナウンスに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="52b39-111">For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="52b39-112">割り当てられていない番号の表を構成する前に、システムにアナウンスが定義されているか、Exchange ユニファイドメッセージング (UM) 自動応答が設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="52b39-112">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="52b39-113">他のユーザーが割り当てられていない番号を呼び出すと、Lync Server は、未使用の番号の表を上から順に検索し、最初の一致する範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="52b39-113">When someone calls an unassigned number, Lync Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="52b39-114">そのため、最後の手段として実行するアクションは、テーブルの最後の範囲に対して指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52b39-114">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="52b39-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="52b39-115">In This Section</span></span>

<span data-ttu-id="52b39-116">[Lync server 2013 で割り当てられていない番号範囲を作成または変更](lync-server-2013-create-or-modify-an-unassigned-number-range.md)する[lync server 2013 でアナウンスを作成](lync-server-2013-create-an-announcement.md)する</span><span class="sxs-lookup"><span data-stu-id="52b39-116">[Create or modify an unassigned number range in Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [Create an announcement in Lync Server 2013](lync-server-2013-create-an-announcement.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

