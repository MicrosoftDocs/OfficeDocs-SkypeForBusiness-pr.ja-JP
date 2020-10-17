---
title: 'Lync Server 2013: 暗号化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Encryption for Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59893874
ms.date: 09/14/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4fca7065c18ab67fce1940adccce6b9071f3373
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533334"
---
# <a name="encryption-for-lync-server-2013"></a>Lync Server 2013 の暗号化

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2017-09-14_

Microsoft Lync Server 2013 は TLS と MTLS を使用してインスタントメッセージを暗号化します。 すべてのサーバー間トラフィックは、トラフィックが内部ネットワークに限定されているか、または内部ネットワーク境界を越えているかに関係なく、MTLS を必要とします。 TLS はオプションですが、仲介サーバーとメディアゲートウェイ間で強く推奨されます。 このリンクで TLS が構成されている場合は、MTLS が必要です。 そのため、仲介サーバーによって信頼されている CA からの証明書を使用してゲートウェイを構成する必要があります。

<div>


> [!NOTE]  
> SSL 3.0 に関するセキュリティアドバイザリは、2014で公開されました。 Lync Server 2013 で SSL 3.0 を無効にする方法はサポートされています。 セキュリティアドバイザリの詳細については、「」を参照してください <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A> 。



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="security" alt="security" />セキュリティに関する注意事項:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>最強の暗号化プロトコルが使用されるように、Lync Server 2013 は tls 暗号化プロトコルを次の順序でクライアントに提供します。 <strong>tls 1.2</strong> 、 <strong>tls 1.1</strong>、 <strong>tls 1.0</strong>。 TLS は Lync Server 2013 の重要な部分であるため、サポートされている環境を維持するために必要です。</td>
</tr>
</tbody>
</table>


</div>

クライアント間のトラフィックに対する要件は、そのトラフィックが内部の企業ファイアウォールを越えるかどうかによって異なります。厳密に言えば、内部のトラフィックでは、TLS を使用することも (インスタント メッセージが暗号化される)、TCP を使用することも (インスタント メッセージが暗号化されない) できます。

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
<td><p>クライアントからサーバーへ</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>インスタント メッセージングおよびプレゼンス</p></td>
<td><p>TLS (TLS 用に構成されている場合)</p></td>
</tr>
<tr class="even">
<td><p>オーディオとビデオ、およびメディアのデスクトップ共有</p></td>
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

メディアトラフィックは、セキュリティで保護された RTP (SRTP) を使用して暗号化されます。 Real-Time トランスポートプロトコル (RTP) のプロファイルは、機密性、認証、および再生攻撃保護を RTP トラフィックに提供します。 さらに、仲介サーバーとその内部の次ホップの間で双方向に流れるメディアも、SRTP を使用して暗号化されます。 仲介サーバーとメディアゲートウェイ間の両方の方向に流れるメディアは、既定では暗号化されません。 仲介サーバーはメディアゲートウェイへの暗号化をサポートできますが、ゲートウェイは、証明書の MTLS と記憶域をサポートする必要があります。

<div>


> [!NOTE]  
> 音声/ビデオ (A/V) は、新しいバージョンの Windows Live Messenger でサポートされています。 Windows Live Messenger で音声ビデオ フェデレーションを実装する場合は、Lync Server の暗号化レベルを変更する必要もあります。 既定では、暗号化レベルは "必須" です。 Lync Server 管理シェルを使用して、この設定を [サポート] に変更する必要があります。 詳細については、「展開」のドキュメントの「Deployment <A href="lync-server-2013-deploying-external-user-access.md">external user access In Lync Server 2013</A> 」を参照してください。



</div>

音声およびビデオのメディアトラフィックは、Microsoft Lync 2013 と Windows Live クライアントの間では暗号化されません。

</div>

<div>

## <a name="fips"></a>使う

Lync Server 2013 と Microsoft Exchange Server 2013 は、Windows Server オペレーティングシステムがシステム暗号化用の FIPS 140-2 アルゴリズムを使用するように構成されている場合、連邦情報処理規格 (FIPS) の140-2 アルゴリズムをサポートするように動作します。 FIPS サポートを実装するには、Lync Server 2013 を実行している各サーバーをサポートするように構成する必要があります。 FIPS 準拠アルゴリズムの使用方法、および FIPS サポートを実装する方法の詳細については、「Microsoft サポート技術情報の記事811833」を参照してください。 Windows XP 以降のバージョンの Windows では、「システム暗号化: 暗号化、ハッシュ、署名に FIPS 準拠アルゴリズムを使用する」のセキュリティ設定を有効にした場合の影響 [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833) 。 Exchange 2010 の FIPS 140-2 サポートおよび制限事項の詳細については、「Exchange 2010 SP1 とサポート」の「FIPS 準拠アルゴリズムのサポート」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

