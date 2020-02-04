---
title: 'Lync Server 2013: クライアントブートストラップポリシーの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring client bootstrapping policies
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425941(v=OCS.15)
ms:contentKeyID: 48184031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8258063645267fb12801548ddfdeae1b4ef7c795
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a>Lync Server 2013 でクライアントブートストラップポリシーを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-21_

グループ ポリシー管理コンソール (GPMC) とグループ ポリシー オブジェクト エディターは、グループ ポリシーを管理するために使用するツールです。 Office グループポリシー管理用テンプレートに含まれている Lync 2013 の管理用テンプレートには、ドメインのグループポリシーオブジェクト用に構成したレジストリベースのポリシー設定が含まれています。これには、adml (ADML) 管理用テンプレートが含まれています。 ADML ファイルは、ADMX ファイルに対する言語固有の補完ファイルです。 それぞれの ADMX および ADML ファイルには、単一の Office アプリケーションに関するポリシー設定が含まれています。 詳細については、Office 2013 ドキュメントの「Office 2013 管理用テンプレートファイル (ADMX、ADML)」 <http://go.microsoft.com/fwlink/p/?linkid=267516>を参照してください。

Lync 2013 には、ユーザーが初めてサーバーにサインインする前に構成することを検討する必要がある、いくつかのクライアントブートストラップポリシーがあります。 たとえば、サインインが完了するまでクライアントで使用する既定のサーバーとセキュリティモードなどです。 グループポリシーを使って、ユーザーのコンピューターのレジストリでこれらの設定を行ってから、サインインして、サーバーからインバンドのプロビジョニング設定を受信することができます。 次の表に、Lync 2013 で利用できるグループポリシー設定を示します。

### <a name="group-policy-settings-for-lync-2013"></a>Lync 2013 のグループポリシー設定

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
<td><p>サーバーを指定する<br />
ConfigurationMode</p></td>
<td><p>サインイン時に使用するトランスポートとサーバーの識別2013方法を指定します。 この設定では、次の値を指定します。</p>
<ul>
<li><p>ServerAddressExternal: 外部ファイアウォールの外側からの接続時に、フェデレーションからの連絡先とクライアントで使用されるサーバー名または IP アドレスを指定します。</p></li>
<li><p>ServerAddressInternal: 組織ファイアウォールの内側にあるクライアントからの接続に使用されるサーバー名または IP アドレスを指定します。</p></li>
<li><p>Transport: 伝送制御プロトコル (TCP) またはトランスポート層セキュリティ (TLS) のいずれかを指定します。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>サポートされているその他のサーバーバージョン<br />
(ConfiguredServerCheckValues)</p></td>
<td><p>既定でサポートされているサーバーのバージョンに加えて、Lync Server 2013 がログオンするサーバーのバージョン名の一覧をセミコロンで区切って指定します。</p></td>
</tr>
<tr class="odd">
<td><p>サインイン失敗ログの自動アップロードを無効にする (DisableAutomaticSendTracing)</p></td>
<td><p>サインインの失敗ログを、分析のために Lync Server に自動的にアップロードします。 サインインが成功した場合は、ログは自動的にアップロードされません。 このポリシーが構成されていない場合は、次のように動作します。</p>
<dl>
<dt><span></span></dt>
<dd><p>Lync Online ユーザーの場合: サインインエラーログは、自動的にアップロードされます。</p>
</dd>
<dt><span></span></dt>
<dd><p>Lync オンプレミスユーザーの場合: アップロードする前に、ユーザーに確認のダイアログボックスが表示されます。</p>
</dd>
</dl>
<p>この設定が無効になっている場合、サインインログは lync オンプレミスと Lync Online の両方のユーザーの Lync サーバーに自動的にアップロードされます。 この設定を有効にすると、サインインログが自動的にアップロードされることはありません。</p></td>
</tr>
<tr class="even">
<td><p>SIP 接続の HTTP フォールバックを無効にする<br />
(DisableHttpConnect)</p></td>
<td><p>TLS または TCP が利用できない場合に、Lync Server が HTTP を使用してサーバーに接続するのを防ぎます。 既定では、Lync は最初に TLS または TCP を使用してサーバーに接続しようとし、次のいずれのトランスポート方法も成功しなかった場合、Lync は HTTP を使って接続を試みます。 このポリシーを使用して、フォールバック HTTP 接続の試行を無効にします。</p></td>
</tr>
<tr class="odd">
<td><p>ログオン資格情報を要求する<br />
(DisableNTCredentials)</p></td>
<td><p>SIP サーバーへのサインイン時に、ユーザーが Lync のログオン資格情報を使って、自動的に Windows 資格情報を使用しないようにする必要があります。</p></td>
</tr>
<tr class="even">
<td><p>サーバーのバージョンチェックを無効にする<br />
(DisableServerCheck)</p></td>
<td><p>このポリシーを1に設定すると、Lync がサインイン前にサーバー名とバージョンを確認できなくなります。 既定では、サインイン前に Lync によってこれらのチェックが行われます。</p></td>
</tr>
<tr class="odd">
<td><p>BITS を使用してアドレス帳サービスファイルをダウンロードできるようにする<br />
(EnableBitsForGalDownload)</p></td>
<td><p>Lync がバックグラウンドインテリジェント転送サービス (BITS) を使用して、アドレス帳サービスファイルをダウンロードできるようにします。</p></td>
</tr>
<tr class="even">
<td><p>SIP セキュリティモードを構成する<br />
(EnableSIPHighSecurityMode)</p></td>
<td><p>Lync がインスタントメッセージの送受信をより安全に行えるようにします。 このポリシーは、Windows .NET または Microsoft Exchange Server サービスに対して無効です。</p>
<p>このポリシー設定を構成しないと、Lync で任意のトランスポートを使用できます。 ただし、TLS を使っておらず、サーバーがユーザーを認証する場合は、NTLM 認証または Kerberos 認証のいずれかを使用する必要があります。</p></td>
</tr>
<tr class="odd">
<td><p>グローバルアドレス帳のダウンロードの最初の遅延<br />
(GalDownloadInitialDelay)</p></td>
<td><p>グローバル アドレス一覧 (GAL) のダウンロードが始まるまでの時間を指定します。既定値は 60 分です。つまり、サーバーでは GAL ファイルのダウンロードがランダムに 0 ～ 60 分間延期されます。</p></td>
</tr>
<tr class="even">
<td><p>ユーザーが Microsoft Lync を実行できないようにする<br />
(PreventRun)</p></td>
<td><p>ユーザーが Lync を実行できないようにします。 このポリシー設定は、コンピューターの構成とユーザーの構成の両方で構成できますが、コンピューターの構成のポリシー設定が優先されます。</p></td>
</tr>
<tr class="odd">
<td><p>ユーザーパスワードの保存を許可する<br />
(SavePassword)</p></td>
<td><p>Lync でパスワードを保存できるようにします。</p></td>
</tr>
<tr class="even">
<td><p>SIP 圧縮モードを構成する<br />
(SipCompression)</p></td>
<td><p>SIP 圧縮をオンにするときを定義します。既定では、アダプターのスピードに基づいて SIP 圧縮が有効化されます。このポリシーを設定すると、サインインの時間が長くなる可能性があることに注意してください。</p></td>
</tr>
<tr class="odd">
<td><p>信頼済みドメインリスト<br />
TrustModelData</p></td>
<td><p>ユーザーの SIP ドメインのプレフィックスに一致しない信頼されたドメインをリストします。</p></td>
</tr>
</tbody>
</table>


サーバー上で構成されたポリシーは、ユーザーによって構成されたグループ ポリシー設定やクライアント オプションよりも優先されます。次の表に、競合が発生した場合の設定の優先順位をまとめます。

### <a name="group-policy-precedence"></a>グループ ポリシーの優先順位

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
<td><p>Lync Server 2013 インバンドプロビジョニング</p></td>
</tr>
<tr class="even">
<td><p>両面</p></td>
<td><p>HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>HKEY_CURRENT_USER \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>Lync 2013 の [Lync-オプション] ダイアログボックス</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a>Lync 2013 管理用テンプレートファイルを使用してグループポリシー設定を定義するには

1.  言語に依存しないすべての ADMX ファイルを含めるルートレベル フォルダーを作成します。たとえば、ドメイン コントローラーの次の場所で、中央ストア用のルート フォルダーを作成します。
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > この手順では、ドメインで複数のコンピューターを管理することを想定しています。この場合、テンプレートをプライマリ ドメイン コントローラーの Sysvol フォルダーにある中央ストアに保存します。これにより、ドメインの管理用テンプレート用のレプリケートされた中央の保存場所が提供されます。

    
    </div>

2.  使用する言語ごとのサブフォルダーを作成します。これらのサブフォルダーには、言語固有の ADML リソース ファイルが含められます。たとえば、米国英語 (EN-US) 用のサブフォルダーを次の場所で作成します。
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

