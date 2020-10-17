---
title: 'Lync Server 2013: 常設チャットサーバーの DNS 要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Persistent Chat Servers
ms:assetid: f7531374-d7ed-4b63-ae81-02294cb4496a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205391(v=OCS.15)
ms:contentKeyID: 48185857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 055a55498247cdde540ceca44cc33187e2b9baca
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501384"
---
# <a name="dns-requirements-for-persistent-chat-servers-in-lync-server-2013"></a><span data-ttu-id="30193-102">Lync Server 2013 の常設チャットサーバーの DNS 要件</span><span class="sxs-lookup"><span data-stu-id="30193-102">DNS requirements for Persistent Chat Servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30193-103">_**トピックの最終更新日:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="30193-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="30193-104">このセクションでは、常設チャットサーバーの展開に必要なドメインネームシステム (DNS) レコードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="30193-104">This section describes the Domain Name System (DNS) records that are required for deployment of Persistent Chat Servers.</span></span>

<div>

## <a name="dns-records-for-persistent-chat-servers"></a><span data-ttu-id="30193-105">常設チャット サーバー用 DNS レコード</span><span class="sxs-lookup"><span data-stu-id="30193-105">DNS Records for Persistent Chat Servers</span></span>

<span data-ttu-id="30193-106">次の表では、常設チャットサーバーの展開の DNS 要件を指定します。</span><span class="sxs-lookup"><span data-stu-id="30193-106">The following table specifies DNS requirements for Persistent Chat Server deployment.</span></span>

### <a name="dns-requirements-for-a-persistent-chat-server"></a><span data-ttu-id="30193-107">常設チャット サーバーの DNS 要件</span><span class="sxs-lookup"><span data-stu-id="30193-107">DNS Requirements for a Persistent Chat Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30193-108">展開シナリオ</span><span class="sxs-lookup"><span data-stu-id="30193-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="30193-109">DNS 要件</span><span class="sxs-lookup"><span data-stu-id="30193-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30193-110">1 つの常設チャット サーバー</span><span class="sxs-lookup"><span data-stu-id="30193-110">One Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="30193-111">サーバーの完全修飾ドメイン名 (FQDN) を、そのサーバーの IP アドレスに解決する内部 A レコード。</span><span class="sxs-lookup"><span data-stu-id="30193-111">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30193-112">Persistent Chat プール</span><span class="sxs-lookup"><span data-stu-id="30193-112">Persistent Chat pool</span></span></p></td>
<td><p><span data-ttu-id="30193-113">サーバーの完全修飾ドメイン名 (FQDN) を、そのサーバーの IP アドレスに解決する内部 A レコード。</span><span class="sxs-lookup"><span data-stu-id="30193-113">An internal A record that resolves the fully qualified domain name (FQDN) of the servers to its IP address.</span></span></p>
<p><span data-ttu-id="30193-114"><strong>例</strong></span><span class="sxs-lookup"><span data-stu-id="30193-114"><strong>Example</strong></span></span></p>
<p><span data-ttu-id="30193-115">PersistentChatServer01.contoso.com 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="30193-115">PersistentChatServer01.contoso.com     10.10.10.1</span></span></p>
<p><span data-ttu-id="30193-116">PersistentChatServer02.contoso.com 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="30193-116">PersistentChatServer02.contoso.com     10.10.10.2</span></span></p>
<p><span data-ttu-id="30193-117">サーバーの完全修飾ドメイン名 (FQDN) を、そのサーバーの IP アドレスに解決する内部 A レコード。</span><span class="sxs-lookup"><span data-stu-id="30193-117">An internal A record that resolves the fully qualified domain name (FQDN) of the servers to its IP address.</span></span></p>
<p><span data-ttu-id="30193-118"><strong>例</strong></span><span class="sxs-lookup"><span data-stu-id="30193-118"><strong>Example</strong></span></span></p>
<p><span data-ttu-id="30193-119">PersistentChatPool.contoso.com 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="30193-119">PersistentChatPool.contoso.com    10.10.10.1</span></span></p>
<p><span data-ttu-id="30193-120">PersistentChatPool.contoso.com 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="30193-120">PersistentChatPool.contoso.com    10.10.10.2</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

