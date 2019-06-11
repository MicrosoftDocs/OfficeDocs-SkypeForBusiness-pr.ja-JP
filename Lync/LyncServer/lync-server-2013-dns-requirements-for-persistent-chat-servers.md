---
title: 'Lync Server 2013: 常設チャットサーバーの DNS 要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Persistent Chat Servers
ms:assetid: f7531374-d7ed-4b63-ae81-02294cb4496a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205391(v=OCS.15)
ms:contentKeyID: 48185857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1f52fde1ee1034f453fe62f2aa3aa44d04b389c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-persistent-chat-servers-in-lync-server-2013"></a><span data-ttu-id="df533-102">Lync Server 2013 の常設チャットサーバーの DNS 要件</span><span class="sxs-lookup"><span data-stu-id="df533-102">DNS requirements for Persistent Chat Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df533-103">_**最終更新日:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="df533-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="df533-104">このセクションでは、常設チャットサーバーの展開に必要なドメインネームシステム (DNS) レコードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="df533-104">This section describes the Domain Name System (DNS) records that are required for deployment of Persistent Chat Servers.</span></span>

<div>

## <a name="dns-records-for-persistent-chat-servers"></a><span data-ttu-id="df533-105">常設チャットサーバーの DNS レコード</span><span class="sxs-lookup"><span data-stu-id="df533-105">DNS Records for Persistent Chat Servers</span></span>

<span data-ttu-id="df533-106">次の表は、常設チャットサーバーの展開の DNS 要件を示しています。</span><span class="sxs-lookup"><span data-stu-id="df533-106">The following table specifies DNS requirements for Persistent Chat Server deployment.</span></span>

### <a name="dns-requirements-for-a-persistent-chat-server"></a><span data-ttu-id="df533-107">常設チャットサーバーの DNS 要件</span><span class="sxs-lookup"><span data-stu-id="df533-107">DNS Requirements for a Persistent Chat Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="df533-108">展開シナリオ</span><span class="sxs-lookup"><span data-stu-id="df533-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="df533-109">DNS 要件</span><span class="sxs-lookup"><span data-stu-id="df533-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="df533-110">1つの常設チャットサーバー</span><span class="sxs-lookup"><span data-stu-id="df533-110">One Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="df533-111">内部の A レコード。サーバーの完全修飾ドメイン名 (FQDN) を IP アドレスに解決します。</span><span class="sxs-lookup"><span data-stu-id="df533-111">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df533-112">常設チャットプール</span><span class="sxs-lookup"><span data-stu-id="df533-112">Persistent Chat pool</span></span></p></td>
<td><p><span data-ttu-id="df533-113">内部の A レコード。サーバーの完全修飾ドメイン名 (FQDN) を IP アドレスに解決します。</span><span class="sxs-lookup"><span data-stu-id="df533-113">An internal A record that resolves the fully qualified domain name (FQDN) of the servers to its IP address.</span></span></p>
<p><span data-ttu-id="df533-114"><strong>例</strong></span><span class="sxs-lookup"><span data-stu-id="df533-114"><strong>Example</strong></span></span></p>
<p><span data-ttu-id="df533-115">PersistentChatServer01.contoso.com 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="df533-115">PersistentChatServer01.contoso.com     10.10.10.1</span></span></p>
<p><span data-ttu-id="df533-116">PersistentChatServer02.contoso.com 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="df533-116">PersistentChatServer02.contoso.com     10.10.10.2</span></span></p>
<p><span data-ttu-id="df533-117">内部の A レコード。サーバーの完全修飾ドメイン名 (FQDN) を IP アドレスに解決します。</span><span class="sxs-lookup"><span data-stu-id="df533-117">An internal A record that resolves the fully qualified domain name (FQDN) of the servers to its IP address.</span></span></p>
<p><span data-ttu-id="df533-118"><strong>例</strong></span><span class="sxs-lookup"><span data-stu-id="df533-118"><strong>Example</strong></span></span></p>
<p><span data-ttu-id="df533-119">PersistentChatPool.contoso.com 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="df533-119">PersistentChatPool.contoso.com    10.10.10.1</span></span></p>
<p><span data-ttu-id="df533-120">PersistentChatPool.contoso.com 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="df533-120">PersistentChatPool.contoso.com    10.10.10.2</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

