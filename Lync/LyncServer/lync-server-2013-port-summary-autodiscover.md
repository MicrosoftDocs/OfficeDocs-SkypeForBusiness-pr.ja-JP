---
title: 'Lync Server 2013: ポートの概要-自動検出'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Autodiscover
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945642(v=OCS.15)
ms:contentKeyID: 51541497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 635f8fca3b267fa2366b66b990ec0621f58f58e4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---autodiscover-in-lync-server-2013"></a>ポートの概要-Lync Server 2013 での自動検出

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-05_

Lync Server 2013 の自動検出サービスは、ディレクターおよびフロントエンドプールのサーバー上で実行され、 `lyncdiscover.<domain>`および`lyncdiscoverinternal.<domain>`ホストレコードを使用して DNS で公開されると、クライアントが lync server の機能を検索するために使用できます。 Lync Mobile を実行しているモバイルデバイスで自動検出を使用するには、まず、自動検出サービスを実行しているすべてのディレクターおよびフロントエンドサーバーで、証明書のサブジェクトの別名の一覧を変更する必要があります。 さらに、リバースプロキシの外部 web サービス公開ルールに使用される証明書のサブジェクトの別名の一覧を変更する必要がある場合があります。

リバースプロキシでサブジェクトの別名の一覧を使用するかどうかは、自動検出サービスをポート80またはポート443に公開するかどうかに基づいて決定されます。

  - **ポート 80**   で公開されているモバイルデバイスでは、自動検出サービスへの初期クエリがポート80経由で行われる場合、証明書の変更は必要ありません。 これは、Lync を実行しているモバイルデバイスがポート80のリバースプロキシに外部でアクセスし、内部でポート8080のディレクターまたはフロントエンドサーバーにリダイレクトされるためです。

  - **発行元ポート 443**   外部 web サービス公開ルールで使用される証明書のサブジェクトの別名リストには`lyncdiscover.<sipdomain>` 、組織内の各 SIP ドメインのエントリが含まれている必要があります。
    
    <div>
    

    > [!IMPORTANT]  
    > モビリティを展開した Lync Server 2010 からの新規インストールまたはアップグレードの場合は、Mobility service の自動検出にポート80を使用するか、適切なサブジェクト名とサブジェクトの別名を使用して証明書を再発行します。 ディレクターおよびフロントエンドサーバーの証明書を確認し、選択したパスを確認します。

    
    </div>

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
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/80</p></td>
<td><p>任意</p></td>
<td><p>リバース プロキシのリスナー</p></td>
<td><p>オプションユーザーが http://&lt;publishedsitefqdn&gt;を入力した場合は、HTTPS にリダイレクトします。 また、組織で外部 web サービス公開ルール証明書を変更しない場合に、Lync を実行しているモバイルデバイス用の Office Web Apps および自動検出サービスを使用する場合にも必要です。</p></td>
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
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/8080</p></td>
<td><p>リバース プロキシの内部インターフェイス</p></td>
<td><p>フロントエンドサーバー、フロントエンドプール、ディレクター、ディレクタープール、会議用 Office Web Apps</p></td>
<td><p>組織で外部 web サービス公開ルールの証明書を変更しない場合に、Lync を実行しているモバイルデバイスに対して自動検出サービスを使用する場合は必須です。 リバース プロキシの外部インターフェイスのポート 80 に送信されるトラフィックは、そのトラフィックと内部 Web トラフィックをプールの Web サービスが区別できるように、リバース プロキシの内部インターフェイスからポート 8080 のプールにリダイレクトされます。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>リバース プロキシの内部インターフェイス</p></td>
<td><p>フロントエンドサーバー、フロントエンドプール、ディレクター、ディレクタープール、会議用 Office Web Apps</p></td>
<td><p>リバース プロキシの外部インターフェイスのポート 443 に送信されるトラフィックは、リバース プロキシの内部インターフェイスからポート 4443 のプールにリダイレクトされるため、プールの Web サービスはこのトラフィックを内部の Web トラフィックと区別できます。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

