---
title: 'Lync Server 2013: Active Directory ドメイン サービスの準備'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7deb5594c0d3c009ee4b10565bc4dbe12f56d2c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a>Lync Server 2013 での Active Directory ドメイン サービスの準備

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-02-19_

Lync server 2013 では、Lync Server Deployment ウィザードを使って Active Directory ドメインサービスを準備するか、Lync Server Management Shell コマンドレットを直接使用することができます。 このトピックの後半で説明するように、ドメインコントローラーでは、ldifde コマンドラインツールを直接使用することもできます。

Lync Server 展開ウィザードの指示に従って、各 Active Directory の準備タスクを実行します。 展開ウィザードでは、Lync Server 管理シェルコマンドレットが実行されます。 このツールは、1つのドメインと1つのフォレストのトポロジ、または同様のトポロジを持つ環境で役立ちます。

<div>


> [!IMPORTANT]  
> Lync Server は、一部のオペレーティングシステムの32ビットバージョンを実行するフォレストまたはドメイン (詳細については、「 <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Lync server 2013 の Active Directory インフラストラクチャの要件</A>」を参照してください) に展開できます。 ただし、展開ウィザードとサポートファイルは64ビットのみであるため、Lync Server 展開ウィザードを使って、これらの環境でスキーマ、フォレスト、ドメインの準備を実行することはできません。 代わりに、32ビットドメインコントローラーで ldifde と関連付けられている .ldf ファイルを使用して、スキーマ、フォレスト、ドメインを準備することができます。 このトピックの後半の「コマンドレットと Ldifde の使用」セクションを参照してください。



</div>

Lync Server 管理シェルコマンドレットを使用して、リモートで、またはより複雑な環境でタスクを実行できます。

<div>

## <a name="active-directory-preparation-prerequisites"></a>Active Directory の準備の前提条件

Windows Server 2012、Windows Server 2012 R2、または Windows Server 2008 R2 SP1 (64 ビット) を実行しているコンピューターで Active Directory の準備手順を実行する必要があります。 Active Directory の準備には、Lync Server 管理シェルと OCSCore が必要です。

Active Directory の準備タスクを実行するには、次のコンポーネントが必要です。

  - Lync Server コアコンポーネント (OCScore)
    
    <div>
    

    > [!NOTE]  
    > Lync Server Management Shell を Active Directory の準備のために使用する予定がある場合は、最初に Lync Server 展開ウィザードを実行して、コアコンポーネントをインストールする必要があります。

    
    </div>

  - Microsoft .NET Framework 4.5
    
    <div>
    

    > [!NOTE]  
    > Windows Server 2012 および Windows Server 2012 R2 の場合、サーバーマネージャーを使用して .NET Framework 4.5 をインストールしてアクティブ化します。 詳細については、「 <A href="lync-server-2013-additional-software-requirements.md">Lync Server 2013 のその他のソフトウェア要件</A>」の「Microsoft .net Framework 4.5」を参照してください。 Windows Server&nbsp;2008&nbsp;R2 の場合は、Microsoft Web サイトから<A href="http://www.microsoft.com/en-us/download/details.aspx?id=30653">.net Framework 4.5</A>をダウンロードしてインストールします。

    
    </div>

  - リモートサーバー管理ツール (RSAT)
    
    <div>
    

    > [!NOTE]  
    > ドメインコントローラーではなく、メンバーサーバーで Active Directory の準備手順を実行する場合、一部の RSAT ツールが必要になります。 サーバーマネージャーの [AD DS と AD LDS ツール] ノードから、AD DS スナップインおよびコマンドラインツールと、Windows PowerShell 用 Active Directory モジュールをインストールします。

    
    </div>

  - Microsoft Visual C++ 11 再頒布可能
    
    <div>
    

    > [!NOTE]  
    > この必須コンポーネントがまだコンピューターにインストールされていない場合は、セットアップによってインストールするように求められます。 パッケージは提供されているため、別途入手する必要はありません。

    
    </div>

  - Windows PowerShell 3.0 (64 ビット)
    
    Windows Server 2012 および Windows Server 2012 R2 の場合は、Lync Server 2013 のインストールに Windows PowerShell 3.0 が含まれている必要があります。 Windows Server 2008 R2 の場合は、Windows PowerShell 3.0 をインストールまたはアップグレードする必要があります。 詳細については、「 [Lync Server 2013 用に Windows PowerShell 3.0 をインストールする](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。

</div>

<div>

## <a name="administrator-rights-and-roles"></a>管理者の権限と役割

次の表は、各 Active Directory 準備タスクに必要な管理者権限と役割を示しています。

### <a name="user-rights-required-for-active-directory-preparation"></a>Active Directory の準備に必要なユーザー権利

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
<td><p>スキーママスターのフォレストルートドメインと管理者権限の Schema Admins グループのメンバー</p></td>
</tr>
<tr class="even">
<td><p>フォレストの準備</p></td>
<td><p>フォレストの Enterprise Admins グループのメンバー</p></td>
</tr>
<tr class="odd">
<td><p>ドメインの準備</p></td>
<td><p>指定したドメインの Enterprise Admins または Domain Admins グループのメンバー</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a>Active Directory の準備コマンドレット

次の表では、AD DS を準備するために使用される Lync Server 管理シェルコマンドレットを、Microsoft Office Communications Server 2007 R2 で AD DS を準備するために使用される Lcscmd.exe コマンドに比較しています。

### <a name="cmdlets-compared-to-lcscmd"></a>Lcscmd.exe と比較したコマンドレット

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Cmdlet</th>
<th>Log</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Install-CsAdServerSchema</p></td>
<td><p>Lcscmd.exe/forest/action: SchemaPrep/schematype: Server</p></td>
</tr>
<tr class="even">
<td><p>CsAdServerSchema の入手</p></td>
<td><p>Lcscmd.exe/forest/action: CheckSchemaPrepState</p></td>
</tr>
<tr class="odd">
<td><p>CsAdForest を有効にする</p></td>
<td><p>Lcscmd.exe/forest/action: ForestPrep</p></td>
</tr>
<tr class="even">
<td><p>CsAdForest を無効にする</p></td>
<td><p>Lcscmd.exe/forest/action: ForestUnprep</p></td>
</tr>
<tr class="odd">
<td><p>CsAdForest の入手</p></td>
<td><p>Lcscmd.exe/forest/action: CheckForestPrepState</p></td>
</tr>
<tr class="even">
<td><p>使用できるようにする-CsAdDomain</p></td>
<td><p>Lcscmd.exe/domain/action: DomainPrep</p></td>
</tr>
<tr class="odd">
<td><p>無効-CsAdDomain</p></td>
<td><p>Lcscmd.exe/domain/action: ドメイン準備の解除</p></td>
</tr>
<tr class="even">
<td><p>入手-CsAdDomain</p></td>
<td><p>Lcscmd.exe/domain/action: CheckDomainPrepState</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a>ロックダウンされた Active Directory の要件

権限の継承が無効になっているか、認証されたユーザー権限を組織で無効にする必要がある場合は、ドメインの準備中に追加の手順を実行する必要があります。 詳細については、「 [Lync Server 2013 のロックダウン Active Directory ドメインサービスの準備](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)」を参照してください。

</div>

<div>

## <a name="custom-container-permissions"></a>カスタムコンテナーの権限

組織で、3つの組み込みコンテナー (ユーザー、コンピューター、ドメインコントローラー) ではなくカスタムコンテナーを使用している場合は、認証されたユーザーグループのカスタムコンテナーへの読み取りアクセス許可を付与する必要があります。 ドメインの準備には、コンテナーへの読み取りアクセス権が必要です。 詳細については、「 [Lync Server 2013 用にドメインを準備する](lync-server-2013-preparing-domains.md)」を参照してください。

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a>コマンドレットと Ldifde を使用する

Lync Server 展開ウィザードと**インストール-CsAdServerSchema**コマンドレットの [**スキーマの準備**] 手順では、64ビットオペレーティングシステムを実行しているドメインコントローラー上の Active Directory スキーマを拡張します。 32ビットオペレーティングシステムを実行しているドメインコントローラーで Active Directory スキーマを拡張する必要がある場合は、メンバーサーバーからリモートで**CsAdServerSchema**コマンドレットをリモートで実行できます (推奨される方法)。 ただし、スキーマ準備を直接ドメインコントローラーで実行する必要がある場合は、Ldifde ツールを使用してスキーマファイルをインポートできます。 Ldifde ツールには、ほとんどのバージョンの Windows オペレーティングシステムが付属しています。

スキーマファイルをインポートするために Ldifde を使用している場合は、以前のバージョンから移行するか、またはクリーンインストールを実行するかに関係なく、4つのファイルをすべてインポートする必要があります。 次の順序でインポートする必要があります。

1.  ExternalSchema. .ldf

2.  ServerSchema. .ldf

3.  BackCompatSchema

4.  VersionSchema

<div>


> [!NOTE]  
> 4つの .ldf ファイルは、インストールメディアまたはダウンロードの \Support\Schema ディレクトリにあります。



</div>

Ldifde を使用して、スキーママスターであるドメインコントローラーに4つのスキーマファイルをインポートするには、次の形式を使用します。

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

次に例を示します。

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> 別のユーザーとしてログインしている場合にのみ b パラメーターを使用します。 必要なユーザー権限について詳しくは、このトピックの「管理者の権限と役割」セクションをご覧ください。



</div>

Ldifde を使用して、スキーママスターではないドメインコントローラーに4つのスキーマファイルをインポートするには、次の形式を使用します。

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

Ldifde の使い方の詳細については、「Microsoft サポート技術情報の記事237677、「LDIFDE を使用してディレクトリオブジェクトを[http://go.microsoft.com/fwlink/p/?linkId=132204](http://go.microsoft.com/fwlink/p/?linkid=132204)Active directory にインポートおよびエクスポートする」を参照してください。

</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 での Active Directory スキーマの準備](lync-server-2013-preparing-the-active-directory-schema.md)

  - [Lync Server 2013 でのフォレストの準備](lync-server-2013-preparing-the-forest.md)

  - [Lync Server 2013 のドメインの準備](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

