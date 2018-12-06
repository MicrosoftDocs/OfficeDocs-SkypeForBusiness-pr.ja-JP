---
title: 'Lync Server 2013: 内部サーバーに対する証明書要件'
TOCTitle: 内部サーバーに対する証明書要件
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398094(v=OCS.15)
ms:contentKeyID: 48271118
ms.date: 02/18/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の内部サーバーに対する証明書要件

 

_**トピックの最終更新日:** 2017-02-17_

Lync Server を実行し、証明書を必要とする内部サーバーには、Standard Edition サーバー、Enterprise Edition フロントエンド サーバー、仲介サーバー、およびディレクターが含まれます。次の表に、これらのサーバーの証明書要件を示します。Lync Server 証明書ウィザードを使用して、これらの証明書を要求できます。


> [!TIP]
> フロント エンド プール、フロント エンド サーバー、またはディレクターの簡易 URL と関連付けられるサブジェクト名の別名には、ワイルドカード証明書がサポートされます。ワイルドカード証明書のサポートの詳細については、「<A href="lync-server-2013-wildcard-certificate-support.md">Lync Server 2013 のワイルドカード証明書のサポート</A>」を参照してください。



内部サーバーには内部のエンタープライズ証明機関 (CA) をお勧めしますが、公的 CA を使用することもできます。統合コミュニケーション (UC) 証明書の特定の要件を満たす証明書を提供し、Microsoft と提携してその証明書を Lync Server 証明書ウィザードで使用できるようにしている公的 CA の一覧については、次の Microsoft サポート技術情報 929395 の記事「統合コミュニケーション証明書パートナー Exchange Server と Communications Server」([http://go.microsoft.com/fwlink/?linkid=202834\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=202834%26clcid=0x411)) を参照してください。

Exchange 2013 など、他のアプリケーションやサーバーとの通信には、その他のアプリケーションや製品でサポートされている証明書が必要です。2013 リリースの場合、Lync Server 2013 をはじめとする Microsoft サーバー製品 (Exchange 2013 や SharePoint Server を含む) は、サーバー間の認証および承認で OAuth (Open Authorization) プロトコルをサポートしています。詳細については、「展開」または「操作」のドキュメントの「[Lync Server 2013 でのサーバー間認証 (Oauth) およびパートナー アプリケーションの管理](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)」を参照してください。

Windows 7 オペレーティング システム、Windows Server 2008 オペレーティング システム、Windows Server 2008 R2 オペレーティング システム、Windows Vista オペレーティング システム、および Microsoft Lync Phone Edition を実行するクライアントから接続する場合、Lync Server 2013 は SHA-256 暗号ハッシュ関数を使用して署名した証明書をサポートします (ただし、こうした証明書は必須ではありません)。SHA-256 を使用する外部アクセスをサポートするには、SHA-256 を使用するパブリック CA が外部証明書を発行する必要があります。

次の表に、フロントエンド プールと Standard Edition サーバーの各サーバーの役割における証明書要件を示します。これらはすべて、標準 Web サーバー、秘密キー、エクスポート不可能です。

サーバーの拡張キー使用法 (EKU) は、証明書ウィザードを使って証明書を要求するときに自動的に構成されます。

> [!NOTE]
> 各証明書のフレンドリ名は、コンピューター ストアで一意である必要があります。


> [!NOTE]
> DNS に sipinternal.contoso.com または sipexternal.contoso.com が構成してある場合は、証明書のサブジェクト名の別名にそれらを追加する必要があります。


### Standard Edition サーバーの証明書

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
<th>サブジェクト名/ 共通名</th>
<th>サブジェクト名の別名</th>
<th>例</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>既定</p></td>
<td><p>プールの完全修飾ドメイン名 (FQDN)</p></td>
<td><p>プールの FQDN およびサーバーの FQDN</p>
<p>SIP ドメインが複数あり、自動クライアント構成が有効にされている場合は、証明書ウィザードで、サポートされている各 SIP ドメイン FQDN が検出され、追加されます。</p>
<p>このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密なドメイン ネーム システム (DNS) マッチングが必要となる場合は、sip.sipdomain のエントリ (存在するそれぞれの SIP 用) も必要となります。</p></td>
<td><p>SN=se01.contoso.com、SAN=se01.contoso.com</p>
<p>このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要となります。</p></td>
<td><p>Standard Edition サーバーに関しては、サーバー FQDN とプール FQDN は同じです。</p>
<p>このウィザードでは、セットアップ時に指定した SIP ドメインが検出され、サブジェクト名の別名に自動的に追加されます。</p>
<p>また、この証明書はサーバー間認証でも使用できます。</p></td>
</tr>
<tr class="even">
<td><p>内部 Web</p></td>
<td><p>サーバーの FQDN</p></td>
<td><p>次のうちのすべて:</p>
<ul>
<li><p>内部 Web FQDN (サーバーの FQDN と同じ)</p></li>
<li><p>簡単な会議 URL</p></li>
<li><p>簡単なダイヤルイン URL</p></li>
<li><p>簡単な管理 URL</p>
<p></p></li>
<li><p>または、簡易 URL のワイルドカード エントリ</p></li>
</ul>
<p></p></td>
<td><p>SN=se01.contoso.com、SAN=se01.contoso.com、SAN=meet.contoso.com、SAN=meet.fabrikam.com、SAN=dialin.contoso.com、SAN=admin.contoso.com</p>
<p>ワイルドカード証明書使用時:</p>
<p>SN=se01.contoso.com、SAN=se01.contoso.com、SAN=*.contoso.com</p></td>
<td><p>トポロジ ビルダーでは内部 Web FQDN を上書きできません。</p>
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
<li><p>SIP ドメインごとの簡単な会議 URL</p></li>
<li><p>または、簡易 URL のワイルドカード エントリ</p></li>
</ul></td>
<td><p>SN=se01.contoso.com、SAN=webcon01.contoso.com、SAN=meet.contoso.com、SAN=meet.fabrikam.com、SAN=dialin.contoso.com</p>
<p>ワイルドカード証明書使用時:</p>
<p>SN=se01.contoso.com、SAN=webcon01.contoso.com、SAN=*.contoso.com</p></td>
<td><p>会議の簡易 URL が複数存在する場合、それらすべてをサブジェクト名の別名として含める必要があります。</p>
<p>簡易 URL エントリにはワイルドカード エントリがサポートされます。</p></td>
</tr>
</tbody>
</table>


### フロントエンド プールのフロントエンド サーバーの証明書

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
<th>サブジェクト名/ 共通名</th>
<th>サブジェクト名の別名</th>
<th>例</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>既定</p></td>
<td><p>プールの FQDN</p></td>
<td><p>プールの FQDN およびサーバーの FQDN。</p>
<p>SIP ドメインが複数あり、自動クライアント構成が有効にされている場合は、証明書ウィザードで、サポートされている各 SIP ドメイン FQDN が検出され、追加されます。</p>
<p>このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、sip.sipdomain のエントリ (存在するそれぞれの SIP 用) も必要となります。</p></td>
<td><p>SN=eepool.contoso.com、SAN=eepool.contoso.com、SAN=ee01.contoso.com</p>
<p>このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要となります。</p></td>
<td><p>このウィザードでは、セットアップ時に指定した SIP ドメインが検出され、サブジェクト名の別名に自動的に追加されます。</p>
<p>また、この証明書はサーバー間認証でも使用できます。</p></td>
</tr>
<tr class="even">
<td><p>内部 Web</p></td>
<td><p>プールの FQDN</p></td>
<td><p>次のうちのすべて:</p>
<ul>
<li><p>内部 Web FQDN (サーバーの FQDN とは異なる)</p></li>
<li><p>サーバーの FQDN</p></li>
<li><p>Lync プールの FQDN</p></li>
<li><p>簡単な会議 URL</p></li>
<li><p>簡単なダイヤルイン URL</p></li>
<li><p>簡単な管理 URL</p></li>
<li><p>または、簡易 URL のワイルドカード エントリ</p></li>
</ul>
<p></p></td>
<td><p>SN=ee01.contoso.com、SAN=ee01.contoso.com、SAN=meet.contoso.com、SAN=meet.fabrikam.com、SAN=dialin.contoso.com、SAN=admin.contoso.com</p>
<p>ワイルドカード証明書使用時:</p>
<p>SN=ee01.contoso.com、SAN=ee01.contoso.com、SAN=*.contoso.com</p></td>
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
<td><p>SN=ee01.contoso.com、SAN=webcon01.contoso.com、SAN=meet.contoso.com、SAN=meet.fabrikam.com、SAN=dialin.contoso.com</p>
<p>ワイルドカード証明書使用時:</p>
<p>SN=ee01.contoso.com、SAN=webcon01.contoso.com、SAN=*.contoso.com</p></td>
<td><p>会議の簡易 URL が複数存在する場合、それらすべてをサブジェクト名の別名として含める必要があります。</p>
<p>簡易 URL エントリにはワイルドカード エントリがサポートされます。</p></td>
</tr>
</tbody>
</table>


### ディレクターの証明書

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
<th>サブジェクト名/ 共通名</th>
<th>サブジェクト名の別名</th>
<th>例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>既定</p></td>
<td><p>ディレクター プールの FQDN</p></td>
<td><p>ディレクターの FQDN、ディレクター プールの FQDN</p>
<p>このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、sip.sipdomain のエントリ (存在するそれぞれの SIP 用) も必要となります。</p></td>
<td><p>SN=dir-pool.contoso.com、SAN=dir-pool.contoso.com、SAN=dir01.contoso.com</p>
<p>このディレクター プールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要となります。</p></td>
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
</ul>
<p></p></td>
<td><p>SN=dir01.contoso.com、SAN=dir01.contoso.com、SAN=meet.contoso.com、SAN=meet.fabrikam.com、SAN=dialin.contoso.com、SAN=admin.contoso.com</p>
<p>SN=dir01.contoso.com、SAN=dir01.contoso.com、SAN=*.contoso.com</p></td>
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
<td><p>ディレクターの外部 Web FQDN は、フロント エンド プールまたは フロント エンド サーバーとは異なります。</p>
<p>SN=dir01.contoso.com、SAN=directorwebcon01.contoso.com、SAN=meet.contoso.com、SAN=meet.fabrikam.com、SAN=dialin.contoso.com</p>
<p>SN=dir01.contoso.com、SAN=directorwebcon01.contoso.com、SAN=*.contoso.com</p></td>
</tr>
</tbody>
</table>


スタンドアロン仲介サーバー プールが存在する場合、プール内の仲介サーバーごとに、次の表に示す証明書が必要です。仲介サーバーがフロントエンド サーバーと併置されている場合、前の「フロントエンド プールのフロントエンド サーバーの証明書」の表に記載されていた証明書で十分です。

### スタンドアロンの仲介サーバーの証明書

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
<th>サブジェクト名/ 共通名</th>
<th>サブジェクト名の別名</th>
<th>例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>既定</p></td>
<td><p>プールの FQDN</p></td>
<td><p>プールの FQDN</p>
<p>プール メンバー サーバーの FQDN</p></td>
<td><p>SN=medsvr-pool.contoso.net、SAN=medsvr-pool.contoso.net、SAN=medsvr01.contoso.net</p></td>
</tr>
</tbody>
</table>


### 存続可能ブランチ アプライアンスの証明書

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
<th>サブジェクト名/ 共通名</th>
<th>サブジェクト名の別名</th>
<th>例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>既定</p></td>
<td><p>アプライアンスの FQDN</p></td>
<td><p>SIP.&lt;sipdomain&gt; (SIP ドメインごとに 1 つのエントリが必要)</p></td>
<td><p>SN=sba01.contoso.net、SAN=sip.contoso.com、SAN=sip.fabrikam.com</p></td>
</tr>
</tbody>
</table>


## 関連項目

#### 概念

[Lync Server 2013 のワイルドカード証明書のサポート](lync-server-2013-wildcard-certificate-support.md)

