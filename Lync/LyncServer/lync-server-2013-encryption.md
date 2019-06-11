---
title: 'Lync Server 2013: 暗号化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Encryption for Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59893874
ms.date: 09/14/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01c989213b050bdb536e95a8a42e8f7b35292eaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="encryption-for-lync-server-2013"></a>Lync Server 2013 の暗号化

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2017-09-14_

Microsoft Lync Server 2013 は、TLS と MTLS を使ってインスタントメッセージを暗号化します。 トラフィックが内部ネットワークに限定されているか、内部ネットワークの境界を越えるかに関係なく、MTLS は、サーバー間のすべてのトラフィックに必要です。 TLS は必須ではありませんが、仲介サーバーとメディアゲートウェイ間で行うことを強くお勧めします。 この接続に TLS を構成する場合は MTLS も必要です。 そのため、ゲートウェイは、仲介サーバーによって信頼されている CA からの証明書を使って構成する必要があります。

<div>


> [!NOTE]  
> SSL 3.0 に関するセキュリティ アドバイザリが 2014 年に公開されました。 Lync Server 2013 での SSL 3.0 の無効化はサポートされています。 セキュリティアドバイザリの詳細については、 <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>を参照してください。



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="証券" alt="security" />セキュリティメモ:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>最強の暗号化プロトコルを使用するために、Lync Server 2013 は次の順序で TLS 暗号化プロトコルをクライアントに提供します。 <strong>tls 1.2</strong> 、 <strong>tls 1.1</strong>、 <strong>tls 1.0</strong>。 TLS は Lync Server 2013 の重要な部分であるため、サポートされている環境を維持するために必要です。</td>
</tr>
</tbody>
</table>


</div>

クライアント間トラフィックの要件は、トラフィックが社内のファイアウォールを通過するかどうかによって異なります。 厳密には、すべての内部トラフィックで TLS を使うことができます。この場合、インスタントメッセージは暗号化され、TCP は使用されません。

次の表に、各種トラフィックのプロトコル要件をまとめます。

### <a name="traffic-protection"></a>トラフィックの保護

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>トラフィックの種類</th>
<th>保護用プロトコル</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>サーバー間</p></td>
<td><p>MTLS</p></td>
</tr>
<tr class="even">
<td><p>クライアントからサーバー</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>インスタント メッセージングとプレゼンス</p></td>
<td><p>TLS (TLS 用に構成されている場合)</p></td>
</tr>
<tr class="even">
<td><p>オーディオとビデオ、メディアのデスクトップ共有</p></td>
<td><p>SRTP</p></td>
</tr>
<tr class="odd">
<td><p>デスクトップ共有 (シグナリング)</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="even">
<td><p>Web 会議</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>会議コンテンツのダウンロード、アドレス帳のダウンロード、配布グループの拡張</p></td>
<td><p>HTTPS</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a>メディアの暗号化

メディア トラフィックは、RTP トラフィックに対して機密性、認証、反射攻撃保護を提供する RTP (Real-Time Transport Protocol) のプロファイルである SRTP (Secure RTP) を使用して暗号化されます。 さらに、仲介サーバーと内部ネクスト ホップの間で双方向に流れるメディアも SRTP を使用して暗号化されます。 仲介サーバーとメディアゲートウェイ間の両方向のメディアフローは、既定では暗号化されません。 仲介サーバーはメディアゲートウェイへの暗号化をサポートしていますが、ゲートウェイは、MTLS と証明書のストレージをサポートしている必要があります。

<div>


> [!NOTE]  
> オーディオ/ビデオ (A/V) は、新しいバージョンの Windows Live Messenger でサポートされています。 Windows Live Messenger との間で A/V フェデレーションを実装している場合は、Lync Server の暗号化レベルも変更する必要があります。 既定では、暗号化レベルは "必須" です。 Lync Server 管理シェルを使用して、この設定を [サポート] に変更する必要があります。 詳細については、展開ドキュメントの「 <A href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013 での外部ユーザーアクセスの展開</A>」を参照してください。



</div>

オーディオおよびビデオのメディアトラフィックは、Microsoft Lync 2013 と Windows Live クライアントの間で暗号化されません。

</div>

<div>

## <a name="fips"></a>FIPS

Lync Server 2013 と Microsoft Exchange Server 2013 は、Windows Server オペレーティングシステムがシステム暗号化用 FIPS 140-2 アルゴリズムを使用するように構成されている場合に、米国連邦情報処理標準 (FIPS) 140-2 アルゴリズムのサポートと共に動作します。 FIPS サポートを実装するには、Lync Server 2013 を実行している各サーバーでサポートされるように構成する必要があります。 FIPS 準拠アルゴリズムの使用、および FIPS サポートの実装方法の詳細については、「Microsoft サポート技術情報の記事 811833 (「システム暗号化: 暗号化、ハッシュ、署名のための FIPS 準拠アルゴリズムを使用する」のセキュリティ) を参照してください。Windows XP と windows の以降のバージョンでの設定[http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)。 Exchange 2010 の FIPS 140-2 のサポートと制限事項の詳細については、「Exchange 2010 SP1 と FIPS [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)準拠アルゴリズムのサポート」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

