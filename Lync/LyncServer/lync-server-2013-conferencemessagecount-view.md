---
title: 'Lync Server 2013: ConferenceMessageCount view'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceMessageCount view
ms:assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688129(v=OCS.15)
ms:contentKeyID: 49733727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73944e1561b88301b740fcb52cf301645154c6e7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-view-in-lync-server-2013"></a><span data-ttu-id="e34f3-102">Lync Server 2013 での ConferenceMessageCount の表示</span><span class="sxs-lookup"><span data-stu-id="e34f3-102">ConferenceMessageCount view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e34f3-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e34f3-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e34f3-104">ConferenceMessageCount ビューには、ユーザーが会議に送信したメッセージの数に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="e34f3-104">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="e34f3-105">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="e34f3-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e34f3-106">ConferenceMessageCount ビューには、 <A href="lync-server-2013-conferencesessiondetails-view.md">Lync Server 2013 の ConferenceSessionDetails ビュー</A>のすべての列に加えて、以下の列も含まれています。</span><span class="sxs-lookup"><span data-stu-id="e34f3-106">The ConferenceMessageCount view contains all of the columns in the <A href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e34f3-107">列</span><span class="sxs-lookup"><span data-stu-id="e34f3-107">Column</span></span></th>
<th><span data-ttu-id="e34f3-108">データ型</span><span class="sxs-lookup"><span data-stu-id="e34f3-108">Data Type</span></span></th>
<th><span data-ttu-id="e34f3-109">詳細</span><span class="sxs-lookup"><span data-stu-id="e34f3-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e34f3-110"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="e34f3-110"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e34f3-111">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e34f3-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e34f3-112">メッセージを送信したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="e34f3-112">URI of the user who sent the message.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e34f3-113"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e34f3-113"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e34f3-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e34f3-114">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e34f3-115">メッセージを送信したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="e34f3-115">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="e34f3-116">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e34f3-116">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e34f3-117"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e34f3-117"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e34f3-118">長さ</span><span class="sxs-lookup"><span data-stu-id="e34f3-118">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e34f3-119">メッセージを送信したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="e34f3-119">Tenant of user who sent the messages.</span></span> <span data-ttu-id="e34f3-120">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e34f3-120">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e34f3-121"><strong>UserMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="e34f3-121"><strong>UserMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="e34f3-122">smallint</span><span class="sxs-lookup"><span data-stu-id="e34f3-122">smallint</span></span></p></td>
<td><p><span data-ttu-id="e34f3-123">会議セッション中にユーザーによって送信されたメッセージの数です。</span><span class="sxs-lookup"><span data-stu-id="e34f3-123">Number of messages sent by the user during the conference session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

