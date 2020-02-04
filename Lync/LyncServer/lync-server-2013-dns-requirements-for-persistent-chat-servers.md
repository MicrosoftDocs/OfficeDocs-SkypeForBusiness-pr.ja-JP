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
ms.openlocfilehash: b97d3238c64173cb5f9bfcfc12dce40f987da123
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-persistent-chat-servers-in-lync-server-2013"></a>Lync Server 2013 の常設チャットサーバーの DNS 要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-06-28_

このセクションでは、常設チャットサーバーの展開に必要なドメインネームシステム (DNS) レコードについて説明します。

<div>

## <a name="dns-records-for-persistent-chat-servers"></a>常設チャットサーバーの DNS レコード

次の表は、常設チャットサーバーの展開の DNS 要件を示しています。

### <a name="dns-requirements-for-a-persistent-chat-server"></a>常設チャットサーバーの DNS 要件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>展開シナリオ</th>
<th>DNS 要件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1つの常設チャットサーバー</p></td>
<td><p>内部の A レコード。サーバーの完全修飾ドメイン名 (FQDN) を IP アドレスに解決します。</p></td>
</tr>
<tr class="even">
<td><p>常設チャットプール</p></td>
<td><p>内部の A レコード。サーバーの完全修飾ドメイン名 (FQDN) を IP アドレスに解決します。</p>
<p><strong>例</strong></p>
<p>PersistentChatServer01.contoso.com 10.10.10.1</p>
<p>PersistentChatServer02.contoso.com 10.10.10.2</p>
<p>内部の A レコード。サーバーの完全修飾ドメイン名 (FQDN) を IP アドレスに解決します。</p>
<p><strong>例</strong></p>
<p>PersistentChatPool.contoso.com 10.10.10.1</p>
<p>PersistentChatPool.contoso.com 10.10.10.2</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

