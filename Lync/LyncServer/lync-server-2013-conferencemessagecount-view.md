---
title: 'Lync Server 2013: ConferenceMessageCount ビュー'
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
ms.openlocfilehash: bdba6750a24e9bc46629f4a3d264893d014f68e6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190260"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-view-in-lync-server-2013"></a><span data-ttu-id="740cf-102">Lync Server 2013 の ConferenceMessageCount ビュー</span><span class="sxs-lookup"><span data-stu-id="740cf-102">ConferenceMessageCount view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="740cf-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="740cf-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="740cf-104">ConferenceMessageCount ビューには、ユーザーが電話会議に送信したメッセージ数に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="740cf-104">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="740cf-105">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="740cf-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="740cf-106">ConferenceMessageCount ビューには、以下の列に加えて、 <A href="lync-server-2013-conferencesessiondetails-view.md">Lync Server 2013 の ConferenceSessionDetails ビュー</A>のすべての列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="740cf-106">The ConferenceMessageCount view contains all of the columns in the <A href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="740cf-107">列</span><span class="sxs-lookup"><span data-stu-id="740cf-107">Column</span></span></th>
<th><span data-ttu-id="740cf-108">データ型</span><span class="sxs-lookup"><span data-stu-id="740cf-108">Data Type</span></span></th>
<th><span data-ttu-id="740cf-109">詳細</span><span class="sxs-lookup"><span data-stu-id="740cf-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="740cf-110"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="740cf-110"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="740cf-111">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="740cf-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="740cf-112">メッセージを送信したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="740cf-112">URI of the user who sent the message.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="740cf-113"><strong>Useruritoff</strong></span><span class="sxs-lookup"><span data-stu-id="740cf-113"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="740cf-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="740cf-114">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="740cf-115">メッセージを送信したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="740cf-115">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="740cf-116">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="740cf-116">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="740cf-117"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="740cf-117"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="740cf-118">識別子</span><span class="sxs-lookup"><span data-stu-id="740cf-118">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="740cf-119">メッセージを送信したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="740cf-119">Tenant of user who sent the messages.</span></span> <span data-ttu-id="740cf-120">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="740cf-120">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="740cf-121"><strong>UserMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="740cf-121"><strong>UserMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="740cf-122">smallint</span><span class="sxs-lookup"><span data-stu-id="740cf-122">smallint</span></span></p></td>
<td><p><span data-ttu-id="740cf-123">電話会議セッション中にユーザーが送信したメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="740cf-123">Number of messages sent by the user during the conference session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

