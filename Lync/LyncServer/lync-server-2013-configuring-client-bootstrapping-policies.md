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
ms.openlocfilehash: 457702a4b237493beb8ca5dfe1e2d7ce9b3d2654
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a>Lync Server 2013 でのクライアントブートストラップポリシーの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

グループポリシー管理コンソール (GPMC) とグループポリシーオブジェクトエディタは、グループポリシーの管理に使用するツールです。 Office グループポリシー管理用テンプレートに含まれるのは、ドメイン内のグループポリシーオブジェクトに対して構成するレジストリベースのポリシー設定が含まれている Lync 2013 admx (ADMX) および adml (ADML) 管理用テンプレートです。 ADML ファイルは、ADMX ファイルに対して言語固有の補完を備えています。 各 ADMX および ADML ファイルには、1つの Office アプリケーションのポリシー設定が含まれています。 詳細については、Office 2013 のドキュメントの「Office 2013 管理用テンプレートファイル (ADMX, ADML) <https://go.microsoft.com/fwlink/p/?linkid=267516>」を参照してください。

Lync 2013 では、ユーザーが初めてサーバーにサインインする前に構成を考慮する必要があるクライアントブートストラップポリシーがいくつかあります。 たとえば、サインインが完了するまでクライアントが使用する既定のサーバーおよびセキュリティモード。 グループポリシーを使用して、ユーザーのコンピューターのレジストリでこれらの設定を行い、サインインしてから、サーバーからインバンドプロビジョニング設定を受信することができます。 次の表に、Lync 2013 で使用できるグループポリシー設定を示します。

### <a name="group-policy-settings-for-lync-2013"></a>Lync 2013 のグループ ポリシー設定

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
<td><p>Lync 2013 がサインイン時に使用するトランスポートおよびサーバーを識別する方法を指定します。 この設定では、以下のことを指定します。</p>
<ul>
<li><p>ServerAddressExternal: 外部ファイアウォールの外側から接続する場合に、クライアントとフェデレーション連絡先が使用するサーバー名または IP アドレスを指定します。</p></li>
<li><p>ServerAddressInternal: クライアントが組織のファイアウォールの内側から接続するときに使用されるサーバー名または IP アドレスを指定します。</p></li>
<li><p>Transport: 伝送制御プロトコル (TCP) またはトランスポート層セキュリティ (TLS) のどちらかを指定します。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>サポートされているその他のサーバーバージョン<br />
(ConfiguredServerCheckValues)</p></td>
<td><p>既定でサポートされているサーバーのバージョンに加えて、Lync Server 2013 がログオン先とするサーバーバージョンの名前の一覧をセミコロンで区切って指定します。</p></td>
</tr>
<tr class="odd">
<td><p>サインイン失敗ログの自動アップロードを無効にする (Disableautomatic Sendtracing)</p></td>
<td><p>サインインエラーログを分析のために Lync Server に自動的にアップロードします。 サインインに成功した場合、ログは自動的にアップロードされません。 このポリシーが構成されていない場合、次の処理が行われます。</p>
<dl>
<dt><span></span></dt>
<dd><p>Lync Online ユーザーの場合: サインイン失敗ログは自動的にアップロードされます。</p>
</dd>
<dt><span></span></dt>
<dd><p>Lync オンプレミスユーザーの場合: アップロードする前に、ユーザーに確認のダイアログボックスが表示されます。</p>
</dd>
</dl>
<p>この設定を無効にすると、lync オンプレミスと Lync Online の両方のユーザーのサインインログが Lync Server に自動的にアップロードされます。 この設定を有効にした場合、サインインログは自動的にアップロードされることはありません。</p></td>
</tr>
<tr class="even">
<td><p>SIP 接続の HTTP フォールバックを無効にする<br />
(DisableHttpConnect)</p></td>
<td><p>TLS または TCP が使用できない場合、Lync Server が HTTP を使用してサーバーに接続できないようにします。 既定では、Lync は最初に TLS または TCP を使用してサーバーに接続しようとし、次のどちらのトランスポート方法も成功しないと、Lync は HTTP を使用して接続しようとします。 このポリシーは、フォールバックの HTTP 接続試行を無効にするために使用します。</p></td>
</tr>
<tr class="odd">
<td><p>ログオン資格情報が必要<br />
DisableNTCredentials</p></td>
<td><p>ユーザーは、SIP サーバーへのサインイン時に Windows 資格情報を自動的に使用するのではなく、Lync のログオン資格情報を提供する必要があります。</p></td>
</tr>
<tr class="even">
<td><p>サーバーバージョンチェックを無効にする<br />
(DisableServerCheck)</p></td>
<td><p>このポリシーを1に設定すると、Lync がサインインする前にサーバー名とバージョンを確認できなくなります。 既定では、Lync はサインインする前にこれらのチェックを行います。</p></td>
</tr>
<tr class="odd">
<td><p>アドレス帳サービスファイルをダウンロードするために BITS を使用できるようにする<br />
(EnableBitsForGalDownload)</p></td>
<td><p>Lync でバックグラウンドインテリジェント転送サービス (BITS) を使用して、アドレス帳サービスのファイルをダウンロードできるようにします。</p></td>
</tr>
<tr class="even">
<td><p>SIP セキュリティモードを構成する<br />
(EnableSIPHighSecurityMode)</p></td>
<td><p>Lync は、より安全にインスタントメッセージを送受信することができます。 このポリシーは、Windows .NET または Microsoft Exchange Server サービスに対して無効です。</p>
<p>このポリシー設定を構成しない場合、Lync は任意のトランスポートを使用できます。 ただし、TLS を使用せず、サーバーがユーザーを認証する場合は、Lync で NTLM 認証または Kerberos 認証のいずれかを使用する必要があります。</p></td>
</tr>
<tr class="odd">
<td><p>グローバルアドレス帳のダウンロードの初期遅延<br />
(GalDownloadInitialDelay)</p></td>
<td><p>グローバルアドレス一覧 (GAL) がダウンロードされるまでの期間を指定します。 既定値は60分です。これは、サーバーが0から60分の間のランダムな期間、GAL ファイルのダウンロードを遅延させることを意味します。</p></td>
</tr>
<tr class="even">
<td><p>ユーザーが Microsoft Lync を実行できないようにする<br />
(PreventRun)</p></td>
<td><p>ユーザーが Lync を実行できないようにします。 このポリシー設定は、コンピューターの構成とユーザーの構成の両方で構成できますが、コンピューターの構成のポリシー設定が優先されます。</p></td>
</tr>
<tr class="odd">
<td><p>ユーザーパスワードの保存を許可する<br />
SavePassword</p></td>
<td><p>Lync がパスワードを保存できるようにします。</p></td>
</tr>
<tr class="even">
<td><p>SIP 圧縮モードを構成する<br />
(SipCompression)</p></td>
<td><p>SIP 圧縮を有効にするタイミングを指定します。 既定では、SIP 圧縮はアダプターの速度に基づいて有効になっています。 このポリシーを設定すると、サインインの時間が長くなる可能性があることに注意してください。</p></td>
</tr>
<tr class="odd">
<td><p>信頼されたドメインの一覧<br />
TrustModelData</p></td>
<td><p>顧客 SIP ドメインのプレフィックスに一致しない信頼されたドメインを一覧表示します。</p></td>
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
<th>Precedence</th>
<th>設定の場所と方法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1-d</p></td>
<td><p>Lync Server 2013 インバンドプロビジョニング</p></td>
</tr>
<tr class="even">
<td><p>pbm-2</p></td>
<td><p>HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="odd">
<td><p>1/3</p></td>
<td><p>HKEY_CURRENT_USER \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="even">
<td><p>2/4</p></td>
<td><p>Lync 2013 の [Lync-オプション] ダイアログボックス</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a>Lync 2013 管理用テンプレートファイルを使用してグループポリシー設定を定義するには

1.  すべての言語に依存しない ADMX ファイルを含むルートレベルのフォルダーを作成します。 たとえば、次の場所で、ドメインコントローラーの中央ストアのルートフォルダーを作成します。
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > この手順では、ドメイン内の複数のコンピューターを管理することを前提としています。 この場合は、プライマリドメインコントローラーの Sysvol フォルダーにある中央ストアにテンプレートを格納します。 これはドメインの管理用テンプレートのためのレプリケートされた集中格納場所となります。

    
    </div>

2.  使用する言語ごとにサブフォルダーを作成します。 これらのサブフォルダーには、言語固有の ADML リソースファイルが含まれています。 たとえば、次の場所に米国英語 (EN-US) のサブフォルダーを作成します。
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

