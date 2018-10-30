---
title: Lync Server 2013 でのクライアント ブートストラップ ポリシーの構成
TOCTitle: Lync Server 2013 でのクライアント ブートストラップ ポリシーの構成
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425941(v=OCS.15)
ms:contentKeyID: 48271938
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのクライアント ブートストラップ ポリシーの構成

 

_**トピックの最終更新日:** 2016-12-08_

グループ ポリシー管理コンソール (GPMC) とグループ ポリシー オブジェクト エディターは、グループ ポリシーを管理するために使用するツールです。Office グループ ポリシー管理用テンプレートと共に組み込まれる Lync 2013.admx (ADMX) および .adml (ADML) 管理用テンプレートには、ドメイン内のグループ ポリシー オブジェクト用に構成するレジストリ ベースのポリシー設定が含まれています。ADML ファイルは、ADMX ファイルに対する言語固有の補完ファイルです。それぞれの ADMX および ADML ファイルには、単一の Office アプリケーションに関するポリシー設定が含まれています。

Lync 2013 では、ユーザーがサーバーに初めてサインインする前に、いくつかのクライアント ブートストラップ ポリシー (たとえば、サインインが完了するまでクライアントが使用する既定のサーバーやセキュリティー モード) を構成しておく必要があります。これらの設定は、クライアントがサインインしてサーバーからインバンド プロビジョニング設定を受信し始める前に、グループ ポリシーを使用してユーザーのコンピューター レジストリで構成できます。次の表は、Lync 2013 で使用可能なグループ ポリシー設定をリストしています。

### Lync 2013 用のグループ ポリシー設定

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>グループ ポリシー設定</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Specify Server<br />
(ConfigurationMode)</p></td>
<td><p>Lync 2013 でサインイン中に使用されるトランスポートとサーバーの識別方法を指定します。この設定では、次の値を指定します。</p>
<ul>
<li><p>ServerAddressExternal: 外部ファイアウォールの外側からの接続時に、フェデレーションからの連絡先とクライアントで使用されるサーバー名または IP アドレスを指定します。</p></li>
<li><p>ServerAddressInternal: 組織ファイアウォールの内側にあるクライアントからの接続に使用されるサーバー名または IP アドレスを指定します。</p></li>
<li><p>Transport: 伝送制御プロトコル (TCP) またはトランスポート層セキュリティ (TLS) のいずれかを指定します。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Additional server versions supported<br />
(ConfiguredServerCheckValues)</p></td>
<td><p>既定でサポートされているサーバー バージョンに加えて、Lync Server 2013 のログオン先となるサーバー バージョンの名前がセミコロンで区切られた一覧を指定します。</p></td>
</tr>
<tr class="odd">
<td><p>Disable automatic upload of sign-in failure logs (DisableAutomaticSendTracing)</p></td>
<td><p>分析のために、サインイン エラーのログを自動的に Lync Server にアップロードします。サインインが成功した場合は、ログは自動的にアップロードされません。このポリシーが構成されていない場合は、以下のことが発生します。</p>
<dl>
<dt><span></span></dt>
<dd><p>Lync Online ユーザーの場合、サインイン エラーのログは自動的にアップロードされます。</p>
</dd>
<dt><span></span></dt>
<dd><p>Lync 社内ユーザーの場合、アップロードの前に、確認のダイアログ ボックスがユーザーに表示されます。</p>
</dd>
</dl>
<p>この設定が無効の場合、サインイン ログは Lync の社内ユーザーと Lync Online ユーザー両方の Lync Server に自動的にアップロードされます。この設定が有効の場合は、サインイン ログは自動的にアップロードされません。</p></td>
</tr>
<tr class="even">
<td><p>Disable HTTP fallback for SIP connection<br />
(DisableHttpConnect)</p></td>
<td><p>TLS または TCP が使用できない場合に、Lync Server が HTTP を使用してサーバーへの接続を試行しないようにします。既定では、Lync はまず TLS または TCP を使用してサーバーへの接続を試行します。どちらの転送方法も成功しなかった場合には、Lync は HTTP を使用して接続を試行します。このポリシーは、フォールバックの HTTP 接続試行を無効にするために使用します。</p></td>
</tr>
<tr class="odd">
<td><p>Require logon credentials<br />
(DisableNTCredentials)</p></td>
<td><p>SIP サーバーへのサインイン中に、Windows 資格情報を自動的に使用するのではなく、ユーザーに Lync ログオン資格情報の入力を要求します。</p></td>
</tr>
<tr class="even">
<td><p>Disable server version check<br />
(DisableServerCheck)</p></td>
<td><p>このポリシーを 1 に設定すると、Lync はサインイン前にサーバー名とバージョンをチェックしなくなります。既定では、サインイン前に Lync でこれらのチェックが行われます。</p></td>
</tr>
<tr class="odd">
<td><p>Enable using BITS to download Address Book Service files<br />
(EnableBitsForGalDownload)</p></td>
<td><p>Lync でバックグラウンド インテリジェント転送サービス (BITS) 使用して、アドレス帳サービスのファイルをダウンロードできるようにします。</p></td>
</tr>
<tr class="even">
<td><p>Configure SIP security mode<br />
(EnableSIPHighSecurityMode)</p></td>
<td><p>Lync でインスタント メッセージをより安全に送受信できるようにします。このポリシーは、Windows .NET または Microsoft Exchange Server サービスに対して無効です。</p>
<p>このポリシー設定を構成しない場合は、Lync ではどのトランスポートも利用できるようになります。ただし、TLS が使用されない場合、およびサーバーでユーザーが認証される場合には、Lync で NTLM または Kerberos のどちらかの認証が使用される必要があります。</p></td>
</tr>
<tr class="odd">
<td><p>Global Address Book Download Initial Delay<br />
(GalDownloadInitialDelay)</p></td>
<td><p>グローバル アドレス一覧 (GAL) のダウンロードが始まるまでの時間を指定します。既定値は 60 分です。つまり、サーバーでは GAL ファイルのダウンロードがランダムに 0 ～ 60 分間延期されます。</p></td>
</tr>
<tr class="even">
<td><p>Prevent users from running Microsoft Lync<br />
(PreventRun)</p></td>
<td><p>ユーザーが Lync を実行できないようにします。このポリシー設定は、コンピューターの構成とユーザーの構成の両方で構成できますが、コンピューターの構成のポリシー設定が優先されます。</p></td>
</tr>
<tr class="odd">
<td><p>Allow storage of user passwords<br />
(SavePassword)</p></td>
<td><p>Lync にパスワードを保存できるようにします。</p></td>
</tr>
<tr class="even">
<td><p>Configure SIP compression mode<br />
(SipCompression)</p></td>
<td><p>SIP 圧縮をオンにするときを定義します。既定では、アダプターのスピードに基づいて SIP 圧縮が有効化されます。このポリシーを設定すると、サインインの時間が長くなる可能性があることに注意してください。</p></td>
</tr>
<tr class="odd">
<td><p>Trusted Domain List<br />
(TrustModelData)</p></td>
<td><p>ユーザーの SIP ドメインのプレフィックスに一致しない信頼されたドメインをリストします。</p></td>
</tr>
</tbody>
</table>


サーバー上で構成されたポリシーは、ユーザーによって構成されたグループ ポリシー設定やクライアント オプションよりも優先されます。次の表に、競合が発生した場合の設定の優先順位をまとめます。

### グループ ポリシーの優先順位

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>優先順位</th>
<th>設定の場所と方法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Lync Server 2013 のインバンド プロビジョニング</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>Lync 2013 の [Lync - オプション] ダイアログ ボックス</p></td>
</tr>
</tbody>
</table>


## Lync 2013 管理用テンプレート ファイルを使用してグループ ポリシー設定を定義するには

1.  言語に依存しないすべての ADMX ファイルを含めるルートレベル フォルダーを作成します。たとえば、ドメイン コントローラーの次の場所で、中央ストア用のルート フォルダーを作成します。
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > この手順では、ドメインで複数のコンピューターを管理することを想定しています。この場合、テンプレートをプライマリ ドメイン コントローラーの Sysvol フォルダーにある中央ストアに保存します。これにより、ドメインの管理用テンプレート用のレプリケートされた中央の保存場所が提供されます。


2.  使用する言語ごとのサブフォルダーを作成します。これらのサブフォルダーには、言語固有の ADML リソース ファイルが含められます。たとえば、米国英語 (EN-US) 用のサブフォルダーを次の場所で作成します。
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

ADMX ファイルの詳細については、「グループ ポリシー管理での ADMX ファイルの使用に関するステップ バイ ステップ ガイド」([http://go.microsoft.com/fwlink/?linkid=75124\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=75124%26clcid=0x411)) を参照してください。

