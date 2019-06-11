---
title: 'Lync Server 2013: Standard Edition サーバーの DNS 要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Standard Edition servers
ms:assetid: 3d6bbe65-e7ce-491b-a0bd-d2f7197f240d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425900(v=OCS.15)
ms:contentKeyID: 48183920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19c5e04f23428b073e544b040ed07dc852f1da4c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-standard-edition-servers-in-lync-server-2013"></a>Lync Server 2013 での Standard Edition サーバーの DNS 要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-06-19_

このセクションでは、Standard Edition サーバーの展開に必要なドメインネームシステム (DNS) レコードについて説明します。

<div>

## <a name="dns-records-for-standard-edition-servers"></a>Standard Edition サーバーの DNS レコード

次の表では、Lync Server 2013 Standard Edition server の展開の DNS 要件を示します。

### <a name="dns-requirements-for-a-standard-edition-server"></a>Standard Edition Server の DNS 要件

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
<td><p>内部の A レコード。サーバーの完全修飾ドメイン名 (FQDN) を IP アドレスに解決します。</p></td>
</tr>
<tr class="even">
<td><p>自動クライアントサインイン</p></td>
<td><p>サポートされている各 SIP ドメインについて、_sipinternaltls の SRV レコード。 _tcp&lt;サインイン&gt;のためのクライアント要求を認証してリダイレクトする標準エディションサーバーの FQDN にマップされる、ポート5061経由のドメイン。 詳細については、「 <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Lync Server 2013 での自動クライアントサインインの DNS 要件</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>ユニファイドコミュニケーション (UC) デバイスによるデバイス更新 Web サービスの検出</p></td>
<td><p>"Ucupdates-r2" という名前の内部 A レコード。&lt;デバイス更新&gt; Web サービスをホストしている STANDARD Edition サーバーの IP アドレスに解決される SIP ドメイン。 UC デバイスが有効になっている状態で、ユーザーがデバイスにログインしたことがない場合、A レコードによってデバイス更新 Web サービスをホストするサーバーがデバイスで検出され、更新プログラムが取得されます。 そうしないと、デバイスは、ユーザーが初めてログインしたときに、インバンドプロビジョニングでサーバー情報を取得します。</p></td>
</tr>
<tr class="even">
<td><p>HTTP トラフィックをサポートする逆プロキシ</p></td>
<td><p>外部の web ファーム FQDN をリバースプロキシの外部 IP アドレスに解決する外部の A レコード。 クライアントと UC デバイスこのレコードを使ってリバースプロキシに接続します。 詳細については、「計画ドキュメントの「 <a href="lync-server-2013-determine-dns-requirements.md">Lync Server 2013 の DNS 要件を決定</a>する」を参照してください。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

