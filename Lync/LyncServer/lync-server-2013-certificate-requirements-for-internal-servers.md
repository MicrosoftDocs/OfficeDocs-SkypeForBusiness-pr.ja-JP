---
title: 'Lync Server 2013: 内部サーバーの証明書要件'
description: 'Lync Server 2013: 内部サーバーの証明書要件。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for internal servers
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398094(v=OCS.15)
ms:contentKeyID: 48183270
ms.date: 02/17/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc1a627dd762c849b848087a96e00e19d320ef01
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575213"
---
# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a>Lync Server 2013 の内部サーバーの証明書要件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2017-02-17_

Lync Server を実行していて、証明書を必要とする内部サーバーには、Standard Edition サーバー、Enterprise Edition フロントエンドサーバー、仲介サーバー、ディレクターがあります。 次の表に、これらのサーバーの証明書要件を示します。 Lync Server 証明書ウィザードを使用して、これらの証明書を要求できます。

<div>


> [!TIP]  
> ワイルドカード証明書は、フロントエンドプール、フロントエンドサーバー、またはディレクターの簡易 Url に関連付けられたサブジェクトの別名に対してサポートされています。 ワイルドカード証明書のサポートの詳細については、「 <A href="lync-server-2013-wildcard-certificate-support.md">Lync Server 2013 のワイルドカード証明書のサポート</A>」を参照してください。



</div>

内部サーバーには内部のエンタープライズ証明機関 (CA) をお勧めしますが、パブリック CA を使用することもできます。 統合コミュニケーション (UC) 証明書の特定の要件に準拠した証明書を提供し、Microsoft と提携して Lync Server 証明書ウィザードを使用できるようにするパブリック Ca の一覧については、「Microsoft Knowledge Base 929395 の記事「Exchange Server と通信サーバーのための統合コミュニケーション証明書パートナー」 () を参照してください [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834) 。

Exchange 2013 などの他のアプリケーションやサーバーと通信するには、他のアプリケーションと製品でサポートされている証明書が必要です。 2013リリース、Lync Server 2013、および Exchange 2013 および SharePoint Server を含むその他の Microsoft サーバー製品については、サーバー間の認証と承認のための Open Authorization (OAuth) プロトコルをサポートしています。 詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「 [Lync server 2013 でのサーバー間認証 (OAuth) およびパートナーアプリケーションの管理](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 」を参照してください。

Windows 7 オペレーティングシステム、Windows Server 2008 オペレーティングシステム、Windows Server 2008 R2 オペレーティングシステム、Windows Vista オペレーティングシステム、および Microsoft Lync Phone Edition を実行しているクライアントからの接続については、Lync Server 2013 では、SHA-256 暗号化ハッシュ関数を使用して署名された証明書をサポートしていますが、必須ではありません。 SHA-256 を使用する外部アクセスをサポートするには、SHA-256 を使用するパブリック CA が外部証明書を発行する必要があります。

次の表に、フロント エンド プールと Standard Edition サーバーの各サーバーの役割における証明書要件を示します。 これらはすべて、標準 Web サーバー、秘密キー、エクスポート不可能です。

サーバーの拡張キー使用法 (EKU) は、証明書ウィザードを使って証明書を要求する際に自動的に構成されます。

<div>


> [!NOTE]  
> 各証明書のフレンドリ名は、コンピューターストア内で一意である必要があります。



</div>

<div>


> [!NOTE]  
> DNS で sipinternal.contoso.com または sipexternal.contoso.com を構成した場合は、証明書のサブジェクトの別名に追加する必要があります。



</div>

### <a name="certificates-for-standard-edition-server"></a>Standard Edition サーバーの証明書

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>証明書</th>
<th>サブジェクト名/共通名</th>
<th>サブジェクト名の別名</th>
<th>例</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>既定値</p></td>
<td><p>プールの完全修飾ドメイン名 (FQDN)</p></td>
<td><p>プールの FQDN およびサーバーの FQDN</p>
<p>SIP ドメインが複数あり、自動クライアント構成が有効にされている場合は、証明書ウィザードで、サポートされている各 SIP ドメイン FQDN が検出され、追加されます。</p>
<p>このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密なドメイン ネーム システム (DNS) マッチングが必要となる場合は、sip.sipdomain のエントリ (存在するそれぞれの SIP 用) も必要となります。</p></td>
<td><p>SN = se01。SAN = se01</p>
<p>このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要となります。</p></td>
<td><p>Standard Edition サーバーに関しては、サーバー FQDN とプール FQDN は同じです。</p>
<p>このウィザードでは、セットアップ時に指定した SIP ドメインが検出され、サブジェクト名の別名に自動的に追加されます。</p>
<p>この証明書は、サーバー間認証に使用することもできます。</p></td>
</tr>
<tr class="even">
<td><p>内部 Web</p></td>
<td><p>サーバーの FQDN</p></td>
<td><p>次のうちのすべて:</p>
<ul>
<li><p>内部 Web FQDN (サーバーの FQDN と同じ)</p></li>
<li><p>簡単な会議 URL</p></li>
<li><p>簡単なダイヤルイン URL</p></li>
<li><p>簡単な管理 URL</p></li>
<li><p>または、簡易 URL のワイルドカード エントリ</p></li>
</ul></td>
<td><p>SN = se01。SAN = se01。SAN = contoso .com。SAN = fabrikam .comSAN = ダイヤルイン。SAN = 管理</p>
<p>ワイルドカード証明書使用時:</p>
<p>SN = se01。SAN = se01。SAN = * .com</p></td>
<td><p>トポロジビルダーで内部 web FQDN を上書きすることはできません。</p>
<p>会議の簡易 URL が複数存在する場合、それらすべてをサブジェクト名の別名として含める必要があります。</p>
<p>簡易 URL エントリにはワイルドカード エントリがサポートされます。</p></td>
</tr>
<tr class="odd">
<td><p>外部 Web</p></td>
<td><p>サーバーの FQDN</p></td>
<td><p>次のうちのすべて:</p>
<ul>
<li><p>外部 Web FQDN</p></li>
<li><p>簡単なダイヤルイン URL</p></li>
<li><p>SIP ドメインごとに単純な Url を満たす</p></li>
<li><p>または、簡易 URL のワイルドカード エントリ</p></li>
</ul></td>
<td><p>SN = se01。SAN = webcon01。SAN = contoso .com。SAN = fabrikam .comSAN = ダイヤルイン .com</p>
<p>ワイルドカード証明書使用時:</p>
<p>SN = se01。SAN = webcon01。SAN = * .com</p></td>
<td><p>会議の簡易 URL が複数存在する場合、それらすべてをサブジェクト名の別名として含める必要があります。</p>
<p>簡易 URL エントリにはワイルドカード エントリがサポートされます。</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a>フロント エンド プールのフロント エンド サーバーの証明書

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>証明書</th>
<th>サブジェクト名/共通名</th>
<th>サブジェクト名の別名</th>
<th>例</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>既定値</p></td>
<td><p>プールの FQDN</p></td>
<td><p>プールの FQDN およびサーバーの FQDN。</p>
<p>SIP ドメインが複数あり、自動クライアント構成が有効にされている場合は、証明書ウィザードで、サポートされている各 SIP ドメイン FQDN が検出され、追加されます。</p>
<p>このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、sip.sipdomain のエントリ (存在するそれぞれの SIP 用) も必要となります。</p></td>
<td><p>SN = eepool。SAN = eepool、SAN = ee01</p>
<p>このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要となります。</p></td>
<td><p>このウィザードでは、セットアップ時に指定した SIP ドメインが検出され、サブジェクト名の別名に自動的に追加されます。</p>
<p>この証明書は、サーバー間認証に使用することもできます。</p></td>
</tr>
<tr class="even">
<td><p>内部 Web</p></td>
<td><p>プールの FQDN</p></td>
<td><p>次のうちのすべて:</p>
<ul>
<li><p>内部 web FQDN (サーバーの FQDN と同じではない)</p></li>
<li><p>サーバーの FQDN</p></li>
<li><p>Lync プールの FQDN</p></li>
<li><p>簡単な会議 URL</p></li>
<li><p>簡単なダイヤルイン URL</p></li>
<li><p>簡単な管理 URL</p></li>
<li><p>または、簡易 URL のワイルドカード エントリ</p></li>
</ul></td>
<td><p>SN = ee01。SAN = ee01。SAN = contoso .com。SAN = fabrikam .comSAN = ダイヤルイン。SAN = 管理</p>
<p>ワイルドカード証明書使用時:</p>
<p>SN = ee01。SAN = ee01。SAN = * .com</p></td>
<td><p>会議の簡易 URL が複数存在する場合、それらすべてをサブジェクト名の別名として含める必要があります。</p>
<p>簡易 URL エントリにはワイルドカード エントリがサポートされます。</p></td>
</tr>
<tr class="odd">
<td><p>外部 Web</p></td>
<td><p>プールの FQDN</p></td>
<td><p>次のうちのすべて:</p>
<ul>
<li><p>外部 Web FQDN</p></li>
<li><p>簡単なダイヤルイン URL</p></li>
<li><p>簡単な管理 URL</p></li>
<li><p>または、簡易 URL のワイルドカード エントリ</p></li>
</ul></td>
<td><p>SN = ee01。SAN = webcon01。SAN = contoso .com。SAN = fabrikam .comSAN = ダイヤルイン .com</p>
<p>ワイルドカード証明書使用時:</p>
<p>SN = ee01。SAN = webcon01。SAN = * .com</p></td>
<td><p>会議の簡易 URL が複数存在する場合、それらすべてをサブジェクト名の別名として含める必要があります。</p>
<p>簡易 URL エントリにはワイルドカード エントリがサポートされます。</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a>ディレクターの証明書

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>証明書</th>
<th>サブジェクト名/共通名</th>
<th>サブジェクト名の別名</th>
<th>例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>既定値</p></td>
<td><p>ディレクター プールの FQDN</p></td>
<td><p>ディレクターの FQDN、ディレクター プールの FQDN</p>
<p>このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、sip.sipdomain のエントリ (存在するそれぞれの SIP 用) も必要となります。</p></td>
<td><p>SN = pool.contoso.com;SAN = pool.contoso.com;SAN = dir01</p>
<p>このディレクター プールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要となります。</p></td>
</tr>
<tr class="even">
<td><p>内部 Web</p></td>
<td><p>サーバーの FQDN</p></td>
<td><p>次のうちのすべて:</p>
<ul>
<li><p>内部 Web FQDN (サーバーの FQDN と同じ)</p></li>
<li><p>サーバーの FQDN</p></li>
<li><p>Lync プールの FQDN</p></li>
<li><p>簡単な会議 URL</p></li>
<li><p>簡単なダイヤルイン URL</p></li>
<li><p>簡単な管理 URL</p></li>
<li><p>または、簡易 URL のワイルドカード エントリ</p></li>
</ul></td>
<td><p>SN = dir01。SAN = dir01。SAN = contoso .com。SAN = fabrikam .comSAN = ダイヤルイン。SAN = 管理</p>
<p>SN = dir01。SAN = dir01 (SAN = * .com)</p></td>
</tr>
<tr class="odd">
<td><p>外部 Web</p></td>
<td><p>サーバーの FQDN</p></td>
<td><p>次のうちのすべて:</p>
<ul>
<li><p>外部 Web FQDN</p></li>
<li><p>簡単なダイヤルイン URL</p></li>
<li><p>簡単な管理 URL</p></li>
<li><p>または、簡易 URL のワイルドカード エントリ</p></li>
</ul></td>
<td><p>ディレクターの外部 web FQDN は、フロントエンドプールまたはフロントエンドサーバーとは別のものにする必要があります。</p>
<p>SN = dir01。SAN = directorwebcon01、SAN = 「contoso .com」SAN = fabrikam .comSAN = ダイヤルイン .com</p>
<p>SN = dir01。SAN = directorwebcon01 (SAN = * .com)</p></td>
</tr>
</tbody>
</table>


スタンドアロン仲介サーバー プールが存在する場合、プール内の仲介サーバーごとに、次の表に示す証明書が必要です。仲介サーバーがフロント エンド サーバーと併置されている場合、前の「フロント エンド プールのフロント エンド サーバーの証明書」の表に記載されていた証明書で十分です。

### <a name="certificates-for-stand-alone-mediation-server"></a>スタンドアロンの仲介サーバーの証明書

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>証明書</th>
<th>サブジェクト名/共通名</th>
<th>サブジェクト名の別名</th>
<th>例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>既定値</p></td>
<td><p>プールの FQDN</p></td>
<td><p>プールの FQDN</p>
<p>プール メンバー サーバーの FQDN</p></td>
<td><p>SN = medsvr-pool.contoso.net;SAN = medsvr-pool.contoso.net;SAN = medsvr01</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a>存続可能ブランチ アプライアンスの証明書

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>証明書</th>
<th>サブジェクト名/共通名</th>
<th>サブジェクト名の別名</th>
<th>例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>既定値</p></td>
<td><p>アプライアンスの FQDN</p></td>
<td><p>SIP。 &lt;microsoft.rtc.management.xds.sipdomain &gt; (SIP ドメインごとに1つのエントリが必要)</p></td>
<td><p>SN = sba01;SAN = sip。SAN: fabrikam. .com</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのワイルドカード証明書のサポート](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

