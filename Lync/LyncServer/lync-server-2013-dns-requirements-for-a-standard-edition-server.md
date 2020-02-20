---
title: 'Lync Server 2013: Standard Edition サーバーの DNS 要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for a Standard Edition server
ms:assetid: 5d1daf54-6e60-4ce0-9254-7d57a0835fa4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204936(v=OCS.15)
ms:contentKeyID: 48184259
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cdd7a32519fe510819f82619c9086b22b820a52
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-a-standard-edition-server-in-lync-server-2013"></a>Lync Server 2013 の Standard Edition サーバーの DNS 要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-22_

ここでは、Standard Edition サーバーの展開に必要なドメイン ネーム システム (DNS) レコードについて説明します。

<div>

## <a name="dns-records-for-standard-edition-servers"></a>Standard Edition サーバーの DNS レコード

次の表は、Lync Server 2013 Standard Edition サーバー展開の DNS 要件を示しています。


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
<td><p>Ucupdates-r2 という名前の内部 A レコード。&lt;デバイス更新&gt; Web サービスをホストする STANDARD Edition サーバーの IP アドレスに解決される SIP ドメイン。 UC デバイスが有効になっていても、ユーザーがデバイスにログインしたことがない場合、デバイスは、A レコードを使用して、デバイス更新 Web サービスをホストするサーバーを検出し、更新プログラムを取得できます。 この方法を実行しない場合、デバイスはユーザーが最初にログインしたときにインバンド プロビジョニングを通じてサーバー情報を取得します。 詳細については、「操作」のドキュメントの「 <a href="lync-server-2013-device-update-web-service.md">Device Update Web service In Lync Server 2013</a> 」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>HTTP トラフィックをサポートするためのリバース プロキシ</p></td>
<td><p>Web ファームの外部 FQDN を、リバース プロキシの外部 IP アドレスに解決する外部 A レコード。 クライアントと UC デバイスは、このレコードを使用してリバース プロキシに接続します。 詳細については、「計画」のドキュメントの「 <a href="lync-server-2013-determine-dns-requirements.md">Lync Server 2013 の DNS 要件を決定</a>する」を参照してください。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での自動クライアントサインインの DNS 要件](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)  
[Lync Server 2013 の DNS 要件を決定する](lync-server-2013-determine-dns-requirements.md)  


[Lync Server 2013 のデバイス更新 Web サービス](lync-server-2013-device-update-web-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

