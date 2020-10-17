---
title: 'Lync Server 2013: Active Directory ドメインサービスの準備'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b3af3ce7940b8d0fb58a74b4a8f7bb0a21c5e2d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506994"
---
# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a>Lync Server 2013 での Active Directory ドメインサービスの準備

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-02-19_

Lync Server 2013 では、Lync Server 展開ウィザードを使用して Active Directory ドメインサービスを準備することや、Lync Server 管理シェルコマンドレットを直接使用することができます。 このトピックの後半の説明に従って、ldifde.exe コマンド ライン ツールをドメイン コントローラーで直接使用することもできます。

Lync Server 展開ウィザードは、各 Active Directory 準備タスクをガイドします。 展開ウィザードは、Lync Server 管理シェルコマンドレットを実行します。 このツールは、単一のドメインと単一のフォレストのトポロジ、またはその他の類似のトポロジの環境で役立ちます。

<div>


> [!IMPORTANT]  
> ドメインコントローラーが32ビットバージョンの一部のオペレーティングシステムを実行するフォレストまたはドメインに Lync Server を展開することができます (詳細については、「 <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory infrastructure 2013 の要件</A>」を参照してください)。 ただし、展開ウィザードと関連ファイルは64ビットであるため、Lync Server 展開ウィザードを使用して、これらの環境でスキーマ、フォレスト、およびドメインの準備を実行することはできません。 代わりに、32 ビット ドメイン コントローラーで ldifde.exe ファイルおよび関連する .ldf ファイルを使用して、スキーマ、フォレスト、およびドメインを準備することができます。 このトピックの後半の「コマンドレットと Ldifde.exe の使用」を参照してください。



</div>

Lync Server 管理シェルコマンドレットを使用して、リモートで、またはより複雑な環境に対してタスクを実行できます。

<div>

## <a name="active-directory-preparation-prerequisites"></a>Active Directory の準備の前提条件

Active Directory の準備手順は、Windows Server 2012、Windows Server 2012 R2、または Windows Server 2008 R2 SP1 (64 ビット) を実行しているコンピューターで実行する必要があります。 Active Directory の準備には、Lync Server 管理シェルと OCSCore が必要です。

Active Directory の準備作業を実行するには、以下のコンポーネントが必要です。

  - Lync Server コアコンポーネント (OCScore.msi)
    
    <div>
    

    > [!NOTE]  
    > Lync Server 管理シェルを Active Directory の準備のために使用する予定の場合は、最初に Lync Server 展開ウィザードを実行して、コアコンポーネントをインストールする必要があります。

    
    </div>

  - Microsoft .NET Framework 4.5
    
    <div>
    

    > [!NOTE]  
    > Windows Server 2012 および Windows Server 2012 R2 では、サーバーマネージャーを使用して .NET Framework 4.5 をインストールしてアクティブ化します。 詳細については、「 <A href="lync-server-2013-additional-software-requirements.md">Lync Server 2013 の追加ソフトウェア要件</A>」の「Microsoft .net Framework 4.5」を参照してください。 Windows Server 2008 R2 の場合は &nbsp; &nbsp; 、Microsoft web サイトから <A href="https://www.microsoft.com/download/details.aspx?id=30653">.net Framework 4.5</A> をダウンロードしてインストールします。

    
    </div>

  - リモート サーバー管理ツール (RSAT)
    
    <div>
    

    > [!NOTE]  
    > Active Directory の準備手順をドメイン コントローラーではなくメンバー サーバーで実行する場合、RSAT ツールがいくつか必要です。 サーバーマネージャーの ad DS および AD LDS ツールノードから、AD DS スナップインおよびコマンドラインツールと、Windows PowerShell の Active Directory モジュールをインストールします。

    
    </div>

  - Microsoft Visual C++ 11 (再頒布可能)
    
    <div>
    

    > [!NOTE]  
    > コンピューターにまだインストールされていない場合、セットアップで、このソフトウェアをインストールするように求められます。 パッケージは提供されているため、個別に入手する必要はありません。

    
    </div>

  - Windows PowerShell 3.0 (64 ビット)
    
    Windows Server 2012 および Windows Server 2012 R2 では、Windows PowerShell 3.0 が Lync Server 2013 インストールに含まれている必要があります。 Windows Server 2008 R2 の場合は、Windows PowerShell 3.0 にインストールするか、アップグレードする必要があります。 詳細については、「 [Windows PowerShell 3.0 For Lync Server 2013 のインストール](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。

</div>

<div>

## <a name="administrator-rights-and-roles"></a>管理者権限と役割

次の表に、Active Directory の各準備作業に必要となる管理者権限と役割を示します。

### <a name="user-rights-required-for-active-directory-preparation"></a>Active Directory の準備に必要な権限

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


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a>Active Directory の準備のコマンドレット

次の表では、AD DS の準備に使用される Lync Server 管理シェルコマンドレットを、Microsoft Office Communications Server 2007 R2 で AD DS を準備するために使用される Lcscmd.exe コマンドに比較しています。

### <a name="cmdlets-compared-to-lcscmd"></a>コマンドレットと LcsCmd の比較

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>コマンドレット</th>
<th>Log</th>
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


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a>ロックダウンされた Active Directory の要件

組織において、アクセス許可の継承が無効になっているか、認証ユーザーのアクセス許可を無効にする必要がある場合は、ドメインの準備で追加のステップを実行する必要があります。 詳細については、「 [Lync Server 2013 のロックダウンされた Active Directory ドメインサービスの準備](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)」を参照してください。

</div>

<div>

## <a name="custom-container-permissions"></a>カスタム コンテナーのアクセス許可

3 つの組み込みコンテナー (Users、Computers、および Domain Controllers) ではなく、カスタム コンテナーを使用している場合は、Authenticated Users グループにカスタム コンテナーの読み取りアクセス許可を付与する必要があります。 ドメインの準備には、コンテナーの読み取りアクセス許可が必要です。 詳細については、「 [Lync Server 2013 のドメインの準備](lync-server-2013-preparing-domains.md)」を参照してください。

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a>コマンドレットと Ldifde.exe の使用

Lync Server 展開ウィザードおよび**Install-CsAdServerSchema**コマンドレットの**スキーマの準備**手順は、64ビットオペレーティングシステムを実行しているドメインコントローラー上の Active Directory スキーマを拡張します。 32 ビット オペレーティング システムを実行しているドメイン コントローラーの Active Directory スキーマを拡張する必要がある場合は、メンバー サーバーからリモートで **Install-CsAdServerSchema** コマンドレットを実行します (推奨される方法)。 ただし、スキーマの準備をドメイン コントローラーで直接実行する必要がある場合は、Ldifde.exe ツールを使用してスキーマ ファイルをインポートできます。 Ldifde.exe ツールは、ほとんどのバージョンの Windows オペレーティング システムに付属しています。

Ldifde.exe を使用してスキーマ ファイルをインポートする場合、以前のバージョンから移行するのかクリーン インストールを実行するのかに関係なく、4 つのファイルすべてをインポートする必要があります。 これらのファイルは次の順序でインポートする必要があります。

1.  ExternalSchema. .ldf

2.  ServerSchema

3.  BackCompatSchema

4.  VersionSchema

<div>


> [!NOTE]  
> これらの 4 つの .ldf ファイルは、インストール メディアまたはダウンロードの \Support\Schema ディレクトリにあります。



</div>

Ldifde.exe を使用してスキーマ マスターであるドメイン コントローラーにこれらの 4 つのスキーマ ファイルをインポートするには、次の形式を使用します。

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

次にその例を示します。

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> b パラメーターは、別のユーザーとしてログインしている場合のみ使用します。 必要なユーザー権限の詳細については、このトピックの前半の「管理者権限と役割」を参照してください。



</div>

Ldifde.exe を使用してスキーマ マスターでないドメイン コントローラーにこれらの 4 つのスキーマ ファイルをインポートするには、次の形式を使用します。

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

Ldifde の使用の詳細については、Microsoft サポート技術情報の記事237677「LDIFDE を使用してディレクトリオブジェクトを Active Directory にインポートおよびエクスポートする」 () を参照してください [https://go.microsoft.com/fwlink/p/?linkId=132204](https://go.microsoft.com/fwlink/p/?linkid=132204) 。

</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 での Active Directory スキーマの準備](lync-server-2013-preparing-the-active-directory-schema.md)

  - [Lync Server 2013 のフォレストの準備](lync-server-2013-preparing-the-forest.md)

  - [Lync Server 2013 のドメインの準備](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

