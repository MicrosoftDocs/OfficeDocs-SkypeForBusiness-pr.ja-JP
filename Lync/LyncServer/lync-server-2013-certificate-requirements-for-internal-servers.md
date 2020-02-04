---
title: 'Lync Server 2013: 内部サーバーに対する証明書要件'
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
ms.openlocfilehash: 0351ab4f54273e1eccc09992ab933525cc2527ae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736788"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a>Lync Server 2013 の内部サーバーに対する証明書要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2017-02-17_

Lync Server を実行していて、証明書を必要とする内部サーバーには、Standard Edition Server、Enterprise Edition フロントエンドサーバー、仲介サーバー、およびディレクターが含まれます。 次の表は、これらのサーバーの証明書要件を示しています。 Lync Server 証明書ウィザードを使って、これらの証明書を要求することができます。

<div>


> [!TIP]  
> ワイルドカード証明書は、フロントエンドプール、フロントエンドサーバー、またはディレクターの単純な Url に関連付けられたサブジェクトの別名でサポートされています。 ワイルドカード証明書のサポートについて詳しくは、「 <A href="lync-server-2013-wildcard-certificate-support.md">Lync Server 2013 でのワイルドカード証明書のサポート</A>」をご覧ください。



</div>

内部サーバーでは社内のエンタープライズ証明機関 (CA) を使うことをお勧めしますが、パブリック CA を使用することもできます。 統合通信 (UC) 証明書の特定の要件に準拠し、Microsoft と提携して Lync Server の証明書ウィザードで動作することを確認するパブリック Ca の一覧については、「Microsoft サポート技術情報929395」、「Exchange Server および通信サーバーのユニファイド[https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)コミュニケーション証明書パートナー」を参照してください。

他のアプリケーションやサーバー (Exchange 2013 など) との通信には、他のアプリケーションや製品でサポートされている証明書が必要です。 2013リリース、Lync Server 2013、および Exchange 2013 および SharePoint Server を含むその他の Microsoft サーバー製品については、サーバー間の認証と承認のための Open Authorization (OAuth) プロトコルをサポートしています。 詳細については、展開ドキュメントまたは運用マニュアルの「 [Lync server 2013 でサーバー間認証 (OAuth) とパートナーアプリケーションを管理する](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)」を参照してください。

Windows 7 オペレーティングシステム、windows Server 2008 オペレーティングシステム、windows Server 2008 R2 オペレーティングシステム、Windows Vista オペレーティングシステム、および Microsoft Lync Phone Edition 2013 を実行しているクライアントからの接続については、のサポートが含まれます (ただし、256 SHA-1 暗号化ハッシュ関数を使用して署名された証明書を要求します。 SHA-256 を使って外部アクセスをサポートするために、外部証明書は SHA-256 を使ってパブリック CA によって発行されます。

次の表は、フロントエンドプールと Standard Edition サーバーのサーバーロールごとの証明書要件を示しています。 これらはすべて、標準の web サーバー証明書、秘密キー、エクスポートできません。

証明書ウィザードを使用して証明書を要求するときに、サーバーの拡張キー使用法 (EKU) が自動的に構成されることに注意してください。

<div>


> [!NOTE]  
> 各証明書のフレンドリ名は、コンピューターストア内で一意である必要があります。



</div>

<div>


> [!NOTE]  
> DNS で sipinternal.contoso.com または sipexternal.contoso.com を構成している場合は、証明書のサブジェクトの代替名にそれらを追加する必要があります。



</div>

### <a name="certificates-for-standard-edition-server"></a>Standard Edition Server 用の証明書

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
<th>サブジェクトの別名</th>
<th>例</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Default</p></td>
<td><p>プールの完全修飾ドメイン名 (FQDN)</p></td>
<td><p>プールの FQDN とサーバーの FQDN</p>
<p>SIP ドメインが複数あり、自動クライアント構成が有効な場合は、証明書ウィザードによって、サポートされている各 SIP ドメインの FQDN が検出され、追加されます。</p>
<p>このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密なドメイン ネーム システム (DNS) マッチングが必要な場合は、sip.sipdomain のエントリ (所有する各 SIP ドメイン用) も必要となります。</p></td>
<td><p>SN=se01.contoso.com; SAN=se01.contoso.com</p>
<p>このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要な場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要です。</p></td>
<td><p>Standard Edition server では、サーバーの FQDN はプールの FQDN と同じです。</p>
<p>このウィザードでは、セットアップ時に指定した SIP ドメインが検出され、サブジェクトの別名に自動的に追加されます。</p>
<p>また、この証明書はサーバー間認証でも使用できます。</p></td>
</tr>
<tr class="even">
<td><p>内部 Web</p></td>
<td><p>サーバーの FQDN</p></td>
<td><p>次のうちのすべて:</p>
<ul>
<li><p>内部 Web FQDN (サーバーの FQDN と同じ)</p></li>
<li><p>会議の簡易 URL</p></li>
<li><p>ダイヤルインの簡易 URL</p></li>
<li><p>管理の簡易 URL</p></li>
<li><p>または、単純な Url のワイルドカードエントリ</p></li>
</ul></td>
<td><p>SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</p>
<p>ワイルドカード証明書使用時:</p>
<p>SN=se01.contoso.com; SAN=se01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>トポロジビルダーで内部 web FQDN を上書きすることはできません。</p>
<p>複数の条件を満たす単純な Url がある場合は、それらのすべてを対象の代替名として含める必要があります。</p>
<p>簡易 URL エントリではワイルドカード エントリがサポートされます。</p></td>
</tr>
<tr class="odd">
<td><p>外部 Web</p></td>
<td><p>サーバーの FQDN</p></td>
<td><p>次のうちのすべて:</p>
<ul>
<li><p>外部 Web FQDN</p></li>
<li><p>ダイヤルインの簡易 URL</p></li>
<li><p>SIP ドメインごとの会議の簡易 URL</p></li>
<li><p>または、単純な Url のワイルドカードエントリ</p></li>
</ul></td>
<td><p>SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</p>
<p>ワイルドカード証明書使用時:</p>
<p>SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>複数の条件を満たす単純な Url がある場合は、それらのすべてを対象の代替名として含める必要があります。</p>
<p>簡易 URL エントリではワイルドカード エントリがサポートされます。</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a>フロントエンドプールのフロントエンドサーバー用の証明書

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
<th>サブジェクトの別名</th>
<th>例</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Default</p></td>
<td><p>プールの FQDN</p></td>
<td><p>サーバーのプールと FQDN の FQDN。</p>
<p>SIP ドメインが複数あり、自動クライアント構成が有効な場合は、証明書ウィザードによって、サポートされている各 SIP ドメインの FQDN が検出され、追加されます。</p>
<p>このプールがクライアント用の自動ログオンサーバーであり、かつ厳密な DNS 一致がグループポリシーで必要となる場合は、sipdomain (SIP ドメインごとに) を入力する必要もあります。</p></td>
<td><p>SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com </p>
<p>このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要な場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要です。</p></td>
<td><p>このウィザードでは、セットアップ時に指定した SIP ドメインが検出され、サブジェクトの別名に自動的に追加されます。</p>
<p>また、この証明書はサーバー間認証でも使用できます。</p></td>
</tr>
<tr class="even">
<td><p>Web 内部</p></td>
<td><p>プールの FQDN</p></td>
<td><p>次のうちのすべて:</p>
<ul>
<li><p>内部 Web FQDN (サーバーの FQDN とは異なる)</p></li>
<li><p>サーバーの FQDN</p></li>
<li><p>Lync プールの FQDN</p></li>
<li><p>会議の簡易 URL</p></li>
<li><p>ダイヤルインの簡易 URL</p></li>
<li><p>管理の簡易 URL</p></li>
<li><p>または、単純な Url のワイルドカードエントリ</p></li>
</ul></td>
<td><p>SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</p>
<p>ワイルドカード証明書使用時:</p>
<p>SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>複数の条件を満たす単純な Url がある場合は、それらのすべてを対象の代替名として含める必要があります。</p>
<p>簡易 URL エントリではワイルドカード エントリがサポートされます。</p></td>
</tr>
<tr class="odd">
<td><p>外部 Web</p></td>
<td><p>プールの FQDN</p></td>
<td><p>次のうちのすべて:</p>
<ul>
<li><p>外部 Web FQDN</p></li>
<li><p>ダイヤルインの簡易 URL</p></li>
<li><p>管理の簡易 URL</p></li>
<li><p>または、単純な Url のワイルドカードエントリ</p></li>
</ul></td>
<td><p>SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</p>
<p>ワイルドカード証明書使用時:</p>
<p>SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>複数の条件を満たす単純な Url がある場合は、それらのすべてを対象の代替名として含める必要があります。</p>
<p>簡易 URL エントリではワイルドカード エントリがサポートされます。</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a>ディレクター用の証明書

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
<th>サブジェクトの別名</th>
<th>例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Default</p></td>
<td><p>ディレクタープールの FQDN</p></td>
<td><p>ディレクタープールの FQDN の fqdn。</p>
<p>このプールがクライアント用の自動ログオンサーバーであり、かつ厳密な DNS 一致がグループポリシーで必要となる場合は、sipdomain (SIP ドメインごとに) を入力する必要もあります。</p></td>
<td><p>SN = dir-pool.contoso.com;SAN = dir-pool.contoso.com;SAN = dir01</p>
<p>このディレクタープールがクライアント用の自動ログオンサーバーであり、かつ厳密な DNS 一致がグループポリシーで必要な場合は、SAN = sip-pstn を使用する必要もあります。サン = sip-pstn</p></td>
</tr>
<tr class="even">
<td><p>Web 内部</p></td>
<td><p>サーバーの FQDN</p></td>
<td><p>次のうちのすべて:</p>
<ul>
<li><p>内部 Web FQDN (サーバーの FQDN と同じ)</p></li>
<li><p>サーバーの FQDN</p></li>
<li><p>Lync プールの FQDN</p></li>
<li><p>会議の簡易 URL</p></li>
<li><p>ダイヤルインの簡易 URL</p></li>
<li><p>管理の簡易 URL</p></li>
<li><p>または、単純な Url のワイルドカードエントリ</p></li>
</ul></td>
<td><p>SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</p>
<p>SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=*.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>外部 Web</p></td>
<td><p>サーバーの FQDN</p></td>
<td><p>次のうちのすべて:</p>
<ul>
<li><p>外部 Web FQDN</p></li>
<li><p>ダイヤルインの簡易 URL</p></li>
<li><p>管理の簡易 URL</p></li>
<li><p>または、単純な Url のワイルドカードエントリ</p></li>
</ul></td>
<td><p>ディレクターの外部 web FQDN は、フロントエンドプールまたはフロントエンドサーバーと異なっている必要があります。</p>
<p>SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</p>
<p>SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=*.contoso.com</p></td>
</tr>
</tbody>
</table>


スタンドアロンの仲介サーバープールを使用している場合、それぞれの仲介サーバーには、次の表に示す証明書が必要です。 フロントエンドサーバーによって仲介サーバーがある場合は、このトピックの前半の「フロントエンドプールの証明書」の表に記載されている証明書を参照してください。

### <a name="certificates-for-stand-alone-mediation-server"></a>スタンドアロンの仲介サーバー用の証明書

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
<th>サブジェクトの別名</th>
<th>例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Default</p></td>
<td><p>プールの FQDN</p></td>
<td><p>プールの FQDN</p>
<p>プールメンバーサーバーの FQDN</p></td>
<td><p>SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a>Survivable Branch Appliance 用の証明書

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
<th>サブジェクトの別名</th>
<th>例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Default</p></td>
<td><p>アプライアンスの FQDN</p></td>
<td><p>フェデレーション.&lt;SIPDOMAIN&gt; (SIP ドメインごとに1つのエントリが必要)</p></td>
<td><p>SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のワイルドカード証明書のサポート](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

