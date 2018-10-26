---
title: 'Lync Server 2013: Active Directory ドメイン サービスの準備'
TOCTitle: Active Directory ドメイン サービスの準備
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48272614
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Active Directory ドメイン サービスの準備

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server 2013 では、Lync Server 展開ウィザード を使用して Active Directory ドメイン サービス を準備したり、Lync Server 管理シェル コマンドレットを直接使用したりできます。このトピックの後半で説明するように、ldifde.exe コマンド ライン ツールをドメイン コントローラーで直接使用することもできます。

Lync Server 展開ウィザードでは、Active Directory の各準備作業が示されます。展開ウィザードでは、Lync Server 管理シェル コマンドレットを実行します。このツールは、単一のドメインと単一のフォレストのトポロジ、またはその他の類似のトポロジの環境で役立ちます。


> [!IMPORTANT]
> Lync Server は、ドメイン コントローラーによっていくつかのオペレーティング システムの 32 ビット版が実行されているフォレストまたはドメイン内に展開できます (詳細については、「<A href="lync-server-2013-active-directory-infrastructure-requirements.md">Lync Server 2013 に関する Active Directory インフラストラクチャの要件</A>」を参照してください)。ただし、展開ウィザードとサポート ファイルは 64 ビットのみなので、Lync Server 展開ウィザードを使用して、これらの環境でスキーマ、フォレスト、およびドメインの準備を実行することはできません。代わりに、32 ビットのドメイン コントローラー上で ldifde.exe ファイルおよび関連する .ldf ファイルを使用して、スキーマ、フォレスト、およびドメインを準備できます。このトピックの後半の「コマンドレットと Ldifde.exe の使用」を参照してください。



Lync Server 管理シェル コマンドレットを使用すると、リモートで作業を実行することも、より複雑な環境で作業を実行することもできます。

## Active Directory の準備の前提条件

Windows Server 2012、Windows Server 2012 R2、または Windows Server 2008 R2 SP1 (64 ビット) を実行しているコンピューターで、Active Directory の準備手順を実行する必要があります。Active Directory の準備には、Lync Server 管理シェルおよび OCSCore が必要です。

Active Directory の準備作業を実行するには、以下のコンポーネントが必要です。

  - Lync Server のコア コンポーネント (OCScore.msi)
    
    > [!NOTE]
    > Active Directory の準備に Lync Server 管理シェルを使用する場合、最初に Lync Server 展開ウィザードを実行してコア コンポーネントをインストールする必要があります。


  - Microsoft .NET Framework 4.5
    
    > [!NOTE]
    > Windows Server 2012 および Windows Server 2012 R2 の場合、サーバー マネージャーを使用して .NET Framework 4.5 をインストールしてアクティブ化します。詳細については、「<a href="lync-server-2013-additional-software-requirements.md">Lync Server 2013 の追加ソフトウェア要件</a>」の「Microsoft .NET Framework 4.5」を参照してください。 Windows Server 2008 R2 の場合は、Microsoft Web サイトの <a href="http://www.microsoft.com/en-us/download/details.aspx?id=30653">.Net Framework 4.5</a> をダウンロードしてインストールしてください。


  - リモート サーバー管理ツール (RSAT)
    
    > [!NOTE]
    > Active Directory の準備手順をドメイン コントローラーではなくメンバー サーバーで実行する場合、RSAT ツールがいくつか必要です。サーバー マネージャーの AD DS および AD LDS ツール ノードから AD DS スナップイン、コマンド ライン ツール、および Windows PowerShell 用の Active Directory モジュールをインストールします。


  - Microsoft Visual C++ 11 (再頒布可能)
    
    > [!NOTE]
    > コンピューターにまだインストールされていない場合、セットアップで、このソフトウェアをインストールするように求められます。パッケージは提供されているため、個別に入手する必要はありません。


  - Windows PowerShell 3.0 (64 ビット)
    
    Windows Server 2012 および Windows Server 2012 R2 の場合、Windows PowerShell 3.0 が Lync Server 2013 のインストールに含まれる必要があります。 Windows Server 2008 R2 の場合は、Windows PowerShell 3.0 をインストールするかそれにアップグレードする必要があります。詳細については、「[Lync Server 2013 用の Windows PowerShell 3.0 のインストール](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。

## 管理者権限と役割

次の表に、Active Directory の各準備作業に必要となる管理者権限と役割を示します。

### Active Directory の準備に必要な権限

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>手順</th>
<th>権限または役割</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>スキーマの準備</p></td>
<td><p>フォレストのルート ドメインの Schema Admins グループのメンバーで、スキーマ マスターにおける管理者権限を持つメンバー</p></td>
</tr>
<tr class="even">
<td><p>フォレストの準備</p></td>
<td><p>フォレストの Enterprise Admins グループのメンバー</p></td>
</tr>
<tr class="odd">
<td><p>ドメインの準備</p></td>
<td><p>指定のドメインの Enterprise Admins グループまたは Domain Admins グループのメンバー</p></td>
</tr>
</tbody>
</table>


## Active Directory の準備のコマンドレット

次の表では、AD DS の準備に使用される Lync Server 管理シェルコマンドレットと Microsoft Office Communications Server 2007 R2 における AD DS の準備に使用される LcsCmd コマンドを比較しています。

### コマンドレットと LcsCmd の比較

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>コマンドレット</th>
<th>LcsCmd</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Install-CsAdServerSchema</p></td>
<td><p>Lcscmd /forest /action:SchemaPrep /SchemaType:Server</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdServerSchema</p></td>
<td><p>Lcscmd /forest /action:CheckSchemaPrepState</p></td>
</tr>
<tr class="odd">
<td><p>Enable-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:ForestPrep</p></td>
</tr>
<tr class="even">
<td><p>Disable-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:ForestUnprep</p></td>
</tr>
<tr class="odd">
<td><p>Get-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:CheckForestPrepState</p></td>
</tr>
<tr class="even">
<td><p>Enable-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action:DomainPrep</p></td>
</tr>
<tr class="odd">
<td><p>Disable-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action: DomainUnprep</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action:CheckDomainPrepState</p></td>
</tr>
</tbody>
</table>


## ロックダウンされた Active Directory の要件

組織において、アクセス許可の継承が無効になっているか、認証ユーザーのアクセス許可を無効にする必要がある場合は、ドメインの準備で追加のステップを実行する必要があります。詳細については、「[Lync Server 2013 でのロックダウンされた Active Directory ドメイン サービスの準備](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)」を参照してください。

## カスタム コンテナーのアクセス許可

3 つの組み込みコンテナー (Users、Computers、および Domain Controllers) ではなく、カスタム コンテナーを使用している場合は、Authenticated Users グループにカスタム コンテナーの読み取りアクセス許可を付与する必要があります。ドメインの準備には、コンテナーの読み取りアクセス許可が必要です。詳細については、「[Lync Server 2013 のドメインの準備](lync-server-2013-preparing-domains.md)」を参照してください。

## コマンドレットと Ldifde.exe の使用

Lync Server 展開ウィザードの **スキーマの準備**手順および **Install-CsAdServerSchema** コマンドレットを実行すると、64 ビット オペレーティング システムを実行しているドメイン コントローラーの Active Directory スキーマを拡張できます。32 ビット オペレーティング システムを実行しているドメイン コントローラーの Active Directory スキーマを拡張する必要がある場合は、メンバー サーバーからリモートで **Install-CsAdServerSchema** コマンドレットを実行します (推奨される方法)。ただし、スキーマの準備をドメイン コントローラーで直接実行する必要がある場合は、Ldifde.exe ツールを使用してスキーマ ファイルをインポートできます。Ldifde.exe ツールは、ほとんどのバージョンの Windows オペレーティング システムに付属しています。

Ldifde.exe を使用してスキーマ ファイルをインポートする場合、以前のバージョンから移行するのかクリーン インストールを実行するのかに関係なく、4 つのファイルすべてをインポートする必要があります。これらのファイルは次の順序でインポートする必要があります。

1.  ExternalSchema.ldf

2.  ServerSchema.ldf

3.  BackCompatSchema.ldf

4.  VersionSchema.ldf

> [!NOTE]
> これらの 4 つの .ldf ファイルは、インストール メディアまたはダウンロードの \Support\Schema ディレクトリにあります。


Ldifde.exe を使用してスキーマ マスターであるドメイン コントローラーにこれらの 4 つのスキーマ ファイルをインポートするには、次の形式を使用します。

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

次に例を示します。

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

> [!NOTE]
> b パラメーターは、別のユーザーとしてログインしている場合のみ使用します。必要なユーザー権限の詳細については、このトピックの前半の「管理者権限と役割」を参照してください。


Ldifde.exe を使用してスキーマ マスターでないドメイン コントローラーにこれらの 4 つのスキーマ ファイルをインポートするには、次の形式を使用します。

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

Ldifde の使用に関する詳細については、Microsoft サポート技術情報の記事 237677「LDIFDE を使用したディレクトリ オブジェクトの Active Directory へのインポート/エクスポート」([http://go.microsoft.com/fwlink/?linkid=132204\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=132204%26clcid=0x411)) を参照してください。

## このセクション中

  - [Lync Server 2013 での Active Directory スキーマの準備](lync-server-2013-preparing-the-active-directory-schema.md)

  - [Lync Server 2013 でのフォレストの準備](lync-server-2013-preparing-the-forest.md)

  - [Lync Server 2013 のドメインの準備](lync-server-2013-preparing-domains.md)

