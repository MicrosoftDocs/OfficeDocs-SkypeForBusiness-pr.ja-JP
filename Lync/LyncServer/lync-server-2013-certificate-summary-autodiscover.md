---
title: 'Lync Server 2013: 証明書の概要-自動検出'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Autodiscover
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945616(v=OCS.15)
ms:contentKeyID: 51541451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8956c8a0ed4e149f336e6670aaf5b262f1868748
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a>証明書の概要-Lync Server 2013 での自動検出

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-14_

Lync Server 2013 自動検出サービスは、監督およびフロントエンドプールサーバー上で実行され、DNS で公開されると、Lync クライアントがサーバーおよびユーザーサービスを見つけるために使うことができます。 Lync Server 2010 からアップグレードしていて、モビリティを展開していない場合は、クライアントで自動検出を使用できるようにする前に、自動検出サービスを実行しているすべてのディレクターおよびフロントエンドサーバーで、証明書のサブジェクトの代替名の一覧を変更する必要があります。 さらに、リバースプロキシの外部 web サービス公開ルールに使用されている証明書のサブジェクト代替名の一覧を変更することが必要になる場合もあります。

リバースプロキシでサブジェクト代替名の一覧を使用するかどうかは、自動検出サービスをポート80またはポート443のどちらに発行するかに基づいて決定されます。

  - **ポート 80**   で公開自動検出サービスへの最初のクエリがポート80経由で発生した場合、証明書の変更は必要ありません。 これは、Lync を実行しているモバイルデバイスは、ポート80の逆プロキシに外部からアクセスして、ポート8080の内部でディレクターまたはフロントエンドサーバーにブリッジするためです。 詳細については、「 [Lync Server 2013 でのモビリティの技術要件](lync-server-2013-technical-requirements-for-mobility.md)」を参照してください。「ポート80を使った最初の自動検出プロセス」を参照してください。

  - **ポート 443**   で公開される外部 web サービス公開ルールで使われる証明書のサブジェクトの別名リストは、lyncdiscover を含む必要があり*ます。\<組織\> *内の各 SIP ドメインの sipdomain エントリ。
    
    <div>
    

    > [!IMPORTANT]  
    > HTTP 経由で HTTPS を使用することを強くお勧めします。 HTTPS は、証明書を使ってトラフィックを暗号化します。 HTTP では暗号化は提供されず、送信されたデータはすべてプレーンテキストになります。

    
    </div>

内部証明機関を使った証明書の再発行は、通常、単純なプロセスです。 ただし、web サービスの公開ルールで使用されているパブリック証明書の場合、複数のサブジェクト代替名エントリを追加すると、負荷が高くなる可能性があります。 この問題を回避するには、ポート80経由の最初の自動検出接続をサポートします。その後、ディレクターまたはフロントエンドサーバー上のポート8080にリダイレクトされます。

<div>


> [!NOTE]  
> Lync Server 2013 インフラストラクチャで内部証明機関 (CA) から発行された内部証明書を使用していて、ワイヤレス接続のモバイルデバイスをサポートする予定の場合は、内部 CA からのルート証明書チェーンをインストールする必要があります。モバイルデバイスの場合、または Lync Server 2013 インフラストラクチャの公開証明書に変更する必要があります。



</div>

このトピックでは、監督、フロントエンドサーバー、リバースプロキシに必要な追加サブジェクトの代替名について説明します。 追加されたサブジェクト代替名 (SAN) のみが参照されます。 証明書の他のエントリに関するガイダンスについては、計画セクションを参照してください。 詳細については、「lync [server 2013 のディレクターのシナリオ](lync-server-2013-scenarios-for-the-director.md)」、「 [lync server 2013 の外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」、「 [lync server 2013 でのリバースプロキシの](lync-server-2013-scenarios-for-reverse-proxy.md)シナリオ」を参照してください。

次の表では、ディレクタープール、フロントエンドプール、リバースプロキシの自動検出 SAN エントリを定義しています。

### <a name="director-pool-certificate-requirements"></a>ディレクタープール証明書の要件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>説明</th>
<th>サブジェクトの代替名エントリ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部自動検出サービス URL</p></td>
<td><p>SAN = lyncdiscoverinternal。&lt;内部ドメイン名&gt;</p></td>
</tr>
<tr class="even">
<td><p>外部自動検出サービスの URL</p></td>
<td><p>SAN = lyncdiscover。&lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 新しい SAN エントリを使って、新しく更新された証明書を既定の証明書に割り当てます。 または、SAN = * を使用することもできます。&lt;sipdomain&gt;。



</div>

### <a name="front-end-pool-certificate-requirements"></a>フロントエンドプール証明書の要件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>説明</th>
<th>サブジェクトの代替名エントリ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部自動検出サービス URL</p></td>
<td><p>SAN = lyncdiscoverinternal。&lt;内部ドメイン名&gt;</p></td>
</tr>
<tr class="even">
<td><p>外部自動検出サービスの URL</p></td>
<td><p>SAN = lyncdiscover。&lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 新しい SAN エントリを使って、新しく更新された証明書を既定の証明書に割り当てます。 または、SAN = * を使用することもできます。&lt;sipdomain&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>リバースプロキシ (パブリック CA) 証明書の要件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>説明</th>
<th>サブジェクトの代替名エントリ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部自動検出サービスの URL</p></td>
<td><p>SAN = lyncdiscover。&lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 新しい SAN エントリを使って、新しく更新された証明書をリバースプロキシの SSL リスナーに割り当てます。



</div>

</div>

<span> </span>

</div>

</div>

</div>

