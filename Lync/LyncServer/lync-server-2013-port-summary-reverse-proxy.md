---
title: 'Lync Server 2013: ポートの概要 - リバース プロキシ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Reverse proxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48184251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a86b993a35210934f5ebef61464c11a153bf297
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a>ポートの概要 - Lync Server 2013 のリバース プロキシ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-15_

リバースプロキシには、ファイアウォールとポート/プロトコルの最小要件があります。

  - 外部ファイアウォールの要件として、HTTPS/TCP/443 と、オプションの HTTP/TCP/80 が挙げられます。 HTTPS は、SSL と TLS のセキュリティ保護された通信に、リバースプロキシ経由で使用されます。 証明書を変更するときに、自動検出サービスへのアクセスを許可することを選んだ場合、HTTP が使用されます。

  - クライアントは、HTTPS で Office Web Apps サーバーに連絡することを想定しています。 Office Web Apps サーバーは、HTTPS/TCP/443 上の内部クライアントからの通信を想定しています。 推奨される構成では、リバースプロキシから Office Web Apps サーバーへの HTTPS/TCP/443 の使用を許可します。

  - ポート8080は、リバースプロキシの内部インターフェイスからフロントエンドサーバー、フロントエンドプール仮想 IP (VIP)、またはオプションのディレクターまたはディレクタープール VIP にトラフィックをルーティングするために使用されます。 ポート TCP 8080 は、Lync を実行しているモバイルデバイスで、自動検出サービスを検索するために必要です (たとえば、多数の SIP ドメインがある場合など)。 必要な SAN エントリを使用して新しい証明書を取得する場合、ポート TCP 8080 は不要であり、省略可能です。

  - ポート4443は、リバースプロキシ内部インターフェイスからフロントエンドサーバー、フロントエンドプール仮想 IP (VIP)、またはオプションのディレクターまたはディレクタープール VIP へのトラフィックに使用されます。
    
    ![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")  
    
    <div>
    

    > [!WARNING]  
    > 4443とリバースプロキシの間の TCP トラフィックを、標準エディションサーバーまたは全体管理ストアの役割を管理するフロントエンドプールの内部4443展開に混同しないでください。

    
    </div>

<div>

## <a name="port-and-protocol-details"></a>ポートとプロトコルの詳細

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a>リバースプロキシサーバーのファイアウォールの詳細: 外部インターフェイス

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocol/TCP または UDP/ポート</th>
<th>ソース IP アドレス</th>
<th>宛先 IP アドレス</th>
<th>ノート</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/80</p></td>
<td><p>任意</p></td>
<td><p>リバースプロキシリスナー</p></td>
<td><p>省略ユーザーが http://&lt;publishedsitefqdn&gt;を入力した場合に HTTPS にリダイレクトします。</p>
<p>また、会議用の Office Web Apps および Lync を実行しているモバイルデバイスで、組織が外部 Web サービス公開ルールの証明書を変更しない場合には、自動検出サービスを使用する必要があります。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/443</p></td>
<td><p>任意</p></td>
<td><p>リバースプロキシリスナー</p></td>
<td><p>アドレス帳のダウンロード、アドレス帳 Web クエリサービス、自動検出、クライアント更新、会議コンテンツ、デバイス更新プログラム、グループ拡張、会議用の Office Web アプリ、ダイヤルイン会議、会議。</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a>リバースプロキシサーバーのファイアウォールの詳細: 内部インターフェイス

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocol/TCP または UDP/ポート</th>
<th>ソース IP アドレス</th>
<th>宛先 IP アドレス</th>
<th>ノート</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/8080</p></td>
<td><p>内部のリバースプロキシインターフェイス</p></td>
<td><p>フロントエンドサーバー、フロントエンドプール、ディレクター、ディレクタープール</p></td>
<td><p>組織で外部 web サービス公開ルールの証明書を変更しない場合に、Lync を実行しているモバイルデバイスで自動検出サービスを使用する場合に必要です。</p>
<p>リバースプロキシの外部インターフェイスでポート80に送信されるトラフィックは、プール Web サービスが内部の web トラフィックと区別できるように、リバースプロキシの内部インターフェイスからポート8080上のプールにリダイレクトされます。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>内部のリバースプロキシインターフェイス</p></td>
<td><p>フロントエンドサーバー、フロントエンドプール、ディレクター、ディレクタープール</p></td>
<td><p>リバースプロキシの外部インターフェイスでポート443に送信されるトラフィックは、プール web サービスが内部の web トラフィックと区別できるように、リバースプロキシの内部インターフェイスからポート4443上のプールにリダイレクトされます。</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP/443</p></td>
<td><p>内部のリバースプロキシインターフェイス</p></td>
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

