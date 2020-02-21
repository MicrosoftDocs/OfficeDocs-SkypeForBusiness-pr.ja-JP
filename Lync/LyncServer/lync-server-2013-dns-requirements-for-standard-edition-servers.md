---
title: 'Lync Server 2013: Standard Edition サーバーの DNS 要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Standard Edition servers
ms:assetid: 3d6bbe65-e7ce-491b-a0bd-d2f7197f240d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425900(v=OCS.15)
ms:contentKeyID: 48183920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 903243e846fee2a0b874a50fb529b533c1658fc2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-standard-edition-servers-in-lync-server-2013"></a>Lync Server 2013 の Standard Edition サーバーの DNS 要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-19_

ここでは、Standard Edition サーバーの展開に必要なドメイン ネーム システム (DNS) レコードについて説明します。

<div>

## <a name="dns-records-for-standard-edition-servers"></a>Standard Edition サーバーの DNS レコード

次の表は、Lync Server 2013 Standard Edition サーバー展開の DNS 要件を示しています。

### <a name="dns-requirements-for-a-standard-edition-server"></a>Standard Edition サーバーの DNS 要件

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
<td><p>Standard Edition サーバー</p></td>
<td><p>サーバーの完全修飾ドメイン名 (FQDN) を、そのサーバーの IP アドレスに解決する内部 A レコード。</p></td>
</tr>
<tr class="even">
<td><p>自動クライアント サインイン</p></td>
<td><p>サポートされている各 SIP ドメインについて、_sipinternaltls の SRV レコード。 _tcp。&lt;サインイン&gt;のためのクライアント要求を認証およびリダイレクトする STANDARD Edition サーバーの FQDN にマップされる、ドメインのポート5061。 詳細については、「 <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Lync Server 2013 での自動クライアントサインインの DNS 要件</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>統合コミュニケーション (UC) デバイスによるデバイス更新 Web サービスの検出</p></td>
<td><p>Ucupdates-r2 という名前の内部 A レコード。&lt;デバイス更新&gt; Web サービスをホストする STANDARD Edition サーバーの IP アドレスに解決される SIP ドメイン。 UC デバイスが有効になっていても、ユーザーがデバイスにログインしたことがない場合、デバイスは、A レコードを使用して、デバイス更新 Web サービスをホストするサーバーを検出し、更新プログラムを取得できます。 この方法を実行しない場合、デバイスはユーザーが最初にログインしたときにインバンド プロビジョニングを通じてサーバー情報を取得します。</p></td>
</tr>
<tr class="even">
<td><p>HTTP トラフィックをサポートするためのリバース プロキシ</p></td>
<td><p>Web ファームの外部 FQDN を、リバース プロキシの外部 IP アドレスに解決する外部 A レコード。 クライアントと UC デバイスは、このレコードを使用してリバース プロキシに接続します。 詳細については、「計画」のドキュメントの「 <a href="lync-server-2013-determine-dns-requirements.md">Lync Server 2013 の DNS 要件を決定</a>する」を参照してください。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

