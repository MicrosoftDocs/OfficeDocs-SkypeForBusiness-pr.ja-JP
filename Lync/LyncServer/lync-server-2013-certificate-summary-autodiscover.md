---
title: 'Lync Server 2013: 証明書の概要-自動検出'
description: 'Lync Server 2013: 証明書の概要-自動検出。'
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
ms.openlocfilehash: ae421401421434a4c4069c1d90ee287dfb016997
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574713"
---
# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a>証明書の概要-Lync Server 2013 での自動検出

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-14_

Lync Server 2013 自動検出サービスは、ディレクターおよびフロントエンドプールサーバー上で実行され、DNS で公開されると、Lync クライアントがサーバーとユーザーサービスを検索するために使用できます。 Lync Server 2010 からアップグレードし、モビリティを展開しない場合は、クライアントで自動検出を使用する前に、自動検出サービスを実行しているすべてのディレクターおよびフロントエンドサーバーで、証明書のサブジェクトの別名の一覧を変更する必要があります。 さらに、リバースプロキシの外部 web サービス公開ルールに使用される証明書のサブジェクトの別名の一覧を変更する必要がある場合があります。

リバースプロキシでサブジェクトの別名の一覧を使用するかどうかは、自動検出サービスをポート80またはポート443に公開するかどうかに基づいて決定されます。

  - **ポート 80**     で公開自動検出サービスへの最初のクエリがポート80で行われる場合、証明書の変更は必要ありません。 これは、Lync を実行しているモバイルデバイスがポート80のリバースプロキシに外部でアクセスし、内部でポート8080のディレクターまたはフロントエンドサーバーにブリッジされるためです。 詳細については、「 [Lync Server 2013 でのモビリティの技術的な要件](lync-server-2013-technical-requirements-for-mobility.md)」セクションの「ポート80を使用した初期の自動検出プロセス」を参照してください。

  - **ポート 443**     で公開外部 web サービス公開ルールで使用される証明書のサブジェクトの別名リストには、lyncdiscover が含まれている必要があり*ます。 \<sipdomain\> * 組織内の各 SIP ドメインのエントリ。
    
    <div>
    

    > [!IMPORTANT]  
    > HTTPS over HTTP を使用することを強くお勧めします。 HTTPS は、証明書を使用してトラフィックを暗号化します。 HTTP では暗号化が提供されず、送信されるデータはプレーンテキストになります。

    
    </div>

内部証明機関を使用した証明書の再発行は、通常、単純なプロセスです。 しかし、web サービス公開ルールで使用されるパブリック証明書の場合、複数のサブジェクトの別名エントリを追加すると、コストがかかることがあります。 この問題を回避するために、ポート80経由の最初の自動検出接続をサポートします。その後、ディレクターまたはフロントエンドサーバーのポート8080にリダイレクトされます。

<div>


> [!NOTE]  
> Lync Server 2013 インフラストラクチャが内部証明機関 (CA) から発行された内部証明書を使用し、ワイヤレス接続をサポートすることを計画している場合は、内部 CA からのルート証明書チェーンをモバイルデバイスにインストールするか、Lync Server 2013 インフラストラクチャのパブリック証明書に変更する必要があります。



</div>

このトピックでは、ディレクター、フロントエンドサーバー、およびリバースプロキシに必要な追加のサブジェクトの別名について説明します。 追加されたサブジェクトの別名 (SAN) のみが参照されます。 証明書の他のエントリに関するガイダンスについては、「計画」のセクションを参照してください。 詳細については、「 [lync server 2013 のディレクターのシナリオ](lync-server-2013-scenarios-for-the-director.md)」、「 [lync server 2013 の外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」、および「 [lync server 2013 のリバースプロキシの](lync-server-2013-scenarios-for-reverse-proxy.md)シナリオ」を参照してください。

次の表は、ディレクタープール、フロントエンドプール、リバースプロキシの自動検出 SAN エントリを定義しています。

### <a name="director-pool-certificate-requirements"></a>ディレクター プールの証明書の要件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>説明</th>
<th>サブジェクト名の別名エントリ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部自動検出サービス URL</p></td>
<td><p>SAN = lyncdiscoverinternal。 &lt;内部ドメイン名&gt;</p></td>
</tr>
<tr class="even">
<td><p>外部自動検出サービス URL</p></td>
<td><p>SAN = lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 新しく更新された証明書を新しい SAN エントリと共に既定の証明書に割り当てます。 または、SAN = * を使用することもできます。 &lt;microsoft.rtc.management.xds.sipdomain &gt; 。



</div>

### <a name="front-end-pool-certificate-requirements"></a>フロント エンド プールの証明書の要件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>説明</th>
<th>サブジェクト名の別名エントリ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部自動検出サービス URL</p></td>
<td><p>SAN = lyncdiscoverinternal。 &lt;内部ドメイン名&gt;</p></td>
</tr>
<tr class="even">
<td><p>外部自動検出サービス URL</p></td>
<td><p>SAN = lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 新しく更新された証明書を新しい SAN エントリと共に既定の証明書に割り当てます。 または、SAN = * を使用することもできます。 &lt;microsoft.rtc.management.xds.sipdomain&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>リバース プロキシ (パブリック CA) の証明書の要件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>説明</th>
<th>サブジェクト名の別名エントリ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部自動検出サービス URL</p></td>
<td><p>SAN = lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 新しく更新された証明書を、リバースプロキシ上の SSL リスナーに新しい SAN エントリで割り当てます。



</div>

</div>

<span> </span>

</div>

</div>

</div>

