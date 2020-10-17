---
title: 'Lync Server 2013: ポートの概要-リバースプロキシ'
description: 'Lync Server 2013: ポートの概要-リバースプロキシ。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Reverse proxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48184251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf07800c91f5a28165eb05e14e2d775758460f50
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555253"
---
# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a>ポートの概要-Lync Server 2013 のリバースプロキシ

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-15_

リバース プロキシには、ファイアウォールとポート/プロトコルに関して最小限の要件があります。

  - 外部ファイアウォールの要件は、HTTPS/TCP/443 とオプションの HTTP/TCP/80 です。 HTTPS は、SSL と、リバースプロキシを介してセキュリティで保護された TLS 通信に使用されます。 証明書を変更するときに自動検出サービスへのアクセスを許可することを選択すると、HTTP が使用されます。コストを正当化できないかどうかがわからない場合があります。

  - クライアントは、HTTPS 上の Office Web Apps サーバーに接続することを予期しています。 Office Web Apps サーバーは、HTTPS/TCP/443 上の内部クライアントから通信する必要があります。 推奨される構成は、リバースプロキシから Office Web Apps サーバーへの HTTPS/TCP/443 を許可することです。

  - ポート8080は、リバースプロキシの内部インターフェイスからフロントエンドサーバー、フロントエンドプール仮想 IP (VIP)、またはオプションのディレクターまたはディレクタープール VIP にトラフィックをルーティングするために使用されます。 ポート TCP 8080 は、外部 web サービス公開ルールの証明書の変更が望ましくない状況 (たとえば、多数の SIP ドメインがある場合) で、Lync を実行しているモバイルデバイスで自動検出サービスを検索するために必要です。 必要な SAN エントリを含む新しい証明書を取得する場合は、TCP ポート 8080 は不要であるため、省略可能です。

  - ポート4443はリバースプロキシの内部インターフェイスからフロントエンドサーバー、フロントエンドプールの仮想 IP (VIP)、またはオプションのディレクターまたはディレクタープールの VIP へのトラフィックに使用されます。
    
    ![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")  
    
    <div>
    

    > [!WARNING]  
    > 標準 Edition サーバーまたは中央管理ストアの役割を管理するフロントエンドプールからの tcp トラフィックをポート4443の内部展開に、リバースプロキシからの4443と混同しないようにしてください。

    
    </div>

<div>

## <a name="port-and-protocol-details"></a>ポートとプロトコルの詳細

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a>リバース プロキシ サーバーのファイアウォールの詳細: 外部インターフェイス

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>プロトコル/TCP または UDP/ポート</th>
<th>送信元 IP アドレス</th>
<th>宛先 IP アドレス</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/80</p></td>
<td><p>任意</p></td>
<td><p>リバース プロキシのリスナー</p></td>
<td><p>オプションユーザーが http://publishedsitefqdn を入力した場合は、HTTPS にリダイレクト &lt; &gt; します。</p>
<p>また、組織で外部 web サービス公開ルール証明書を変更しない場合に、Lync を実行しているモバイルデバイス用の Office Web Apps および自動検出サービスを使用する場合にも必要です。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>リバース プロキシのリスナー</p></td>
<td><p>アドレス帳のダウンロード、アドレス帳の Web クエリサービス、自動検出、クライアント更新、会議コンテンツ、デバイス更新、グループ拡張、会議用 Office Web アプリ、ダイヤルイン会議、および会議。</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a>リバース プロキシ サーバーのファイアウォールの詳細: 内部インターフェイス

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>プロトコル/TCP または UDP/ポート</th>
<th>送信元 IP アドレス</th>
<th>宛先 IP アドレス</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/8080</p></td>
<td><p>リバース プロキシの内部インターフェイス</p></td>
<td><p>フロントエンドサーバー、フロントエンドプール、ディレクター、ディレクタープール</p></td>
<td><p>組織で外部 web サービス公開ルールの証明書を変更しない場合に、Lync を実行しているモバイルデバイスに対して自動検出サービスを使用する場合は必須です。</p>
<p>リバース プロキシの外部インターフェイスのポート 80 に送信されるトラフィックは、そのトラフィックと内部 Web トラフィックをプールの Web サービスが区別できるように、リバース プロキシの内部インターフェイスからポート 8080 のプールにリダイレクトされます。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>リバース プロキシの内部インターフェイス</p></td>
<td><p>フロントエンドサーバー、フロントエンドプール、ディレクター、ディレクタープール</p></td>
<td><p>リバース プロキシの外部インターフェイスのポート 443 に送信されるトラフィックは、リバース プロキシの内部インターフェイスからポート 4443 のプールにリダイレクトされるため、プールの Web サービスはこのトラフィックを内部の Web トラフィックと区別できます。</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP/443</p></td>
<td><p>リバース プロキシの内部インターフェイス</p></td>
<td><p>会議用の Office Web Apps</p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

