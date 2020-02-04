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
ms.openlocfilehash: 945e3ed9d532f27676e250c29ab415646bd967ec
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---autodiscover-in-lync-server-2013"></a>ポートの概要-Lync Server 2013 での自動検出

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-03-05_

Lync Server 2013 自動検出サービスは、監督およびフロントエンドプールサーバー上で実行され、 `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` host レコードを使って DNS で公開されると、クライアントで使用して lync server の機能を見つけることができます。 Lync Mobile を実行しているモバイルデバイスで自動検出を使用するには、自動検出サービスを実行しているすべてのディレクターおよびフロントエンドサーバーで、証明書のサブジェクトの代替名の一覧を変更する必要があります。 さらに、リバースプロキシの外部 web サービス公開ルールに使用されている証明書のサブジェクト代替名の一覧を変更することが必要になる場合もあります。

リバースプロキシでサブジェクト代替名の一覧を使用するかどうかは、自動検出サービスをポート80またはポート443のどちらに発行するかに基づいて決定されます。

  - **ポート 80**   でのモバイルデバイス向けに公開された、自動検出サービスへの初期クエリがポート80経由で行われる場合、証明書の変更は必要ありません。 これは、Lync を実行しているモバイルデバイスは、ポート80の逆プロキシに外部からアクセスして、ポート8080の内部でディレクターまたはフロントエンドサーバーにリダイレクトされるためです。

  - **ポート 443**   で公開外部 web サービス公開ルールによって使用される証明書のサブジェクト代替名の`lyncdiscover.<sipdomain>`一覧には、組織内の各 SIP ドメインのエントリが含まれている必要があります。
    
    <div>
    

    > [!IMPORTANT]  
    > モビリティを展開した Lync Server 2010 からの新規インストールまたはアップグレードの場合は、モビリティサービスの自動検出にポート80を使用するか、適切なサブジェクト名とサブジェクトの代替名を指定して再発行された証明書を使います。 監督とフロントエンドサーバー上の証明書を確認して、選択したパスを確認します。

    
    </div>

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
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/80</p></td>
<td><p>任意</p></td>
<td><p>リバースプロキシリスナー</p></td>
<td><p>省略ユーザーが http://&lt;publishedsitefqdn&gt;を入力した場合に HTTPS にリダイレクトします。 また、会議用の Office Web Apps および Lync を実行しているモバイルデバイスで、組織が外部 Web サービス公開ルールの証明書を変更しない場合には、自動検出サービスを使用する必要があります。</p></td>
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
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/8080</p></td>
<td><p>内部のリバースプロキシインターフェイス</p></td>
<td><p>フロントエンドサーバー、フロントエンドプール、ディレクター、ディレクタープール、会議用 Office Web Apps</p></td>
<td><p>組織で外部 web サービス公開ルールの証明書を変更しない場合に、Lync を実行しているモバイルデバイスで自動検出サービスを使用する場合に必要です。 リバースプロキシの外部インターフェイスでポート80に送信されるトラフィックは、プール Web サービスが内部の web トラフィックと区別できるように、リバースプロキシの内部インターフェイスからポート8080上のプールにリダイレクトされます。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>内部のリバースプロキシインターフェイス</p></td>
<td><p>フロントエンドサーバー、フロントエンドプール、ディレクター、ディレクタープール、会議用 Office Web Apps</p></td>
<td><p>リバースプロキシの外部インターフェイスでポート443に送信されるトラフィックは、プール web サービスが内部の web トラフィックと区別できるように、リバースプロキシの内部インターフェイスからポート4443上のプールにリダイレクトされます。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

