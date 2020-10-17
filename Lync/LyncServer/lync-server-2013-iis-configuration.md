---
title: 'Lync Server 2013: IIS 構成'
description: 'Lync Server 2013: IIS 構成。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 901aca7bf5ff8824b54e93754569a6ef5defc10e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554873"
---
# <a name="iis-configuration-in-lync-server-2013"></a>Lync Server 2013 の IIS 構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-02-17_

この手順を正常に完了するには、少なくともローカル管理者とドメインユーザーとしてサーバーにログオンしている必要があります。

プール内の Lync Server 2013、Standard Edition、または最初のフロントエンドサーバー用のフロントエンドサーバーを構成およびインストールする前に、インターネットインフォメーションサービス (IIS) のサーバーの役割と Web サービスをインストールして構成します。

<div class=" ">


> [!IMPORTANT]  
> IIS およびすべての Web サービスをシステムドライブ以外のドライブに配置する必要がある組織では、最初に Lync Server 2013 管理ツールをインストールするときに、[セットアップ] ダイアログボックスで Lync Server 2013 ファイルのインストール場所のパスを変更することができます。 IIS をインストールする前に、管理ツールをインストールします。 このパスにセットアップファイル (OCSCore.msi を含む) をインストールすると、残りの Lync Server 2013 ファイルもこのドライブに展開されます。 Dtails については、「 <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 管理ツール</A>」を参照してください。 IIS のインストール時に Windows Server Manager によって展開された INETPUB の再配置方法の詳細については、「」を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A> 。



</div>

次の表は、必要な IIS 7.5 の役割サービスを示しています。

### <a name="iis-75-role-services"></a>IIS 7.5 の役割サービス

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>役割の見出し</th>
<th>役割サービス</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>インストールされている共通の HTTP 機能</p></td>
<td><p>静的コンテンツ</p></td>
</tr>
<tr class="even">
<td><p>インストールされている共通の HTTP 機能</p></td>
<td><p>既定のドキュメント</p></td>
</tr>
<tr class="odd">
<td><p>インストールされている共通の HTTP 機能</p></td>
<td><p>HTTP エラー</p></td>
</tr>
<tr class="even">
<td><p>アプリケーション開発</p></td>
<td><p>ASP.NET</p>
<p>Windows Server 2012 にも、ASP.DLL 4.5 が必要です。</p></td>
</tr>
<tr class="odd">
<td><p>アプリケーション開発</p></td>
<td><p>.NET 拡張機能</p></td>
</tr>
<tr class="even">
<td><p>アプリケーション開発</p></td>
<td><p>Internet Server API (ISAPI) 拡張機能</p></td>
</tr>
<tr class="odd">
<td><p>アプリケーション開発</p></td>
<td><p>ISAPI フィルター</p></td>
</tr>
<tr class="even">
<td><p>正常性と診断</p></td>
<td><p>HTTP ログ</p></td>
</tr>
<tr class="odd">
<td><p>正常性と診断</p></td>
<td><p>ログツール</p></td>
</tr>
<tr class="even">
<td><p>正常性と診断</p></td>
<td><p>・</p></td>
</tr>
<tr class="odd">
<td><p>セキュリティ</p></td>
<td><p>匿名認証 (既定でインストールされ、有効になっています)</p></td>
</tr>
<tr class="even">
<td><p>セキュリティ</p></td>
<td><p>Windows 認証</p></td>
</tr>
<tr class="odd">
<td><p>セキュリティ</p></td>
<td><p>クライアント証明書マッピング認証</p></td>
</tr>
<tr class="even">
<td><p>セキュリティ</p></td>
<td><p>要求フィルター</p></td>
</tr>
<tr class="odd">
<td><p>パフォーマンス</p></td>
<td><p>静的なコンテンツの圧縮</p>
<p>動的なコンテンツの圧縮</p></td>
</tr>
<tr class="even">
<td><p>管理ツール</p></td>
<td><p>IIS 管理コンソール</p></td>
</tr>
<tr class="odd">
<td><p>管理ツール</p></td>
<td><p>IIS 管理スクリプトおよびツール</p></td>
</tr>
</tbody>
</table>


Windows Server 2008 R2 SP1 x64 オペレーティングシステムでは、Windows PowerShell 2.0 を使用できます。 最初に ServerManager モジュールをインポートしてから、IIS 7.5 の役割および役割サービスをインストールする必要があります。

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> 匿名認証は、IIS サーバーの役割と共に既定でインストールされます。 IIS をインストールした後で、匿名認証を管理することができます。 詳細については、「」の「匿名認証 (IIS 7) を有効にする」を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A> 。



</div>

次の表は、Windows Server 2012 および Windows Server 2012 R2 に必要な IIS 8.0 および IIS 8.5 の役割サービスを示しています。

<div class=" ">


> [!NOTE]  
> Windows Server 2012 および Windows Server 2012 R2 では、Add-WindowsFeature コマンドレットは Install-WindowsFeature コマンドレットに置き換えられました。 詳細については、「 <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">Install</A>」を参照してください。



</div>

### <a name="iis-80-and-iis-85-role-services"></a>IIS 8.0 および IIS 8.5 の役割サービス

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>役割の見出し</th>
<th>役割サービス</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Web サーバー (IIS)</p></td>
<td><p>Web サーバー</p></td>
</tr>
<tr class="even">
<td><p>HTTP 共通機能</p></td>
<td><p>既定のドキュメント</p></td>
</tr>
<tr class="odd">
<td><p>HTTP 共通機能</p></td>
<td><p>ディレクトリの参照</p></td>
</tr>
<tr class="even">
<td><p>HTTP 共通機能</p></td>
<td><p>HTTP エラー</p></td>
</tr>
<tr class="odd">
<td><p>HTTP 共通機能</p></td>
<td><p>静的コンテンツ</p></td>
</tr>
<tr class="even">
<td><p>共通の HTTP 機能</p></td>
<td><p>HTTP リダイレクト</p></td>
</tr>
<tr class="odd">
<td><p>状態と診断</p></td>
<td><p>HTTP ログ</p></td>
</tr>
<tr class="even">
<td><p>状態と診断</p></td>
<td><p>ログ ツール</p></td>
</tr>
<tr class="odd">
<td><p>状態と診断</p></td>
<td><p>要求監視</p></td>
</tr>
<tr class="even">
<td><p>状態と診断</p></td>
<td><p>・</p></td>
</tr>
<tr class="odd">
<td><p>セキュリティ</p></td>
<td><p>要求のフィルタリング</p></td>
</tr>
<tr class="even">
<td><p>セキュリティ</p></td>
<td><p>基本認証</p></td>
</tr>
<tr class="odd">
<td><p>セキュリティ</p></td>
<td><p>クライアント証明書マッピング認証</p></td>
</tr>
<tr class="even">
<td><p>セキュリティ</p></td>
<td><p>Windows 認証</p></td>
</tr>
<tr class="odd">
<td><p>アプリケーション開発</p></td>
<td><p>.Net 拡張機能3.5</p></td>
</tr>
<tr class="even">
<td><p>アプリケーション開発</p></td>
<td><p>.Net 拡張機能4.5</p></td>
</tr>
<tr class="odd">
<td><p>アプリケーション開発</p></td>
<td><p>ASP.Net 3.5</p></td>
</tr>
<tr class="even">
<td><p>アプリケーション開発</p></td>
<td><p>ASP.Net 4.5</p></td>
</tr>
<tr class="odd">
<td><p>アプリケーション開発</p></td>
<td><p>ISAPI 拡張機能</p></td>
</tr>
<tr class="even">
<td><p>アプリケーション開発</p></td>
<td><p>ISAPI フィルター</p></td>
</tr>
<tr class="odd">
<td><p>アプリケーション開発</p></td>
<td><p>サーバー側インクルード</p></td>
</tr>
<tr class="even">
<td><p>管理ツール</p></td>
<td><p>IIS 管理コンソール</p></td>
</tr>
<tr class="odd">
<td><p>管理ツール</p></td>
<td><p>IIS 6 メタベースの互換性</p></td>
</tr>
<tr class="even">
<td><p>管理ツール</p></td>
<td><p>IIS 管理スクリプトおよびツール</p></td>
</tr>
<tr class="odd">
<td><p>.Net 3.5 Framework の機能</p></td>
<td><p>.Net 3.5 Framework</p></td>
</tr>
<tr class="even">
<td><p>.Net 4.5 Framework の機能</p></td>
<td><p>.Net Framework 4.5</p></td>
</tr>
<tr class="odd">
<td><p>.Net 4.5 Framework の機能</p></td>
<td><p>ASP.Net 4.5</p></td>
</tr>
<tr class="even">
<td><p>.Net 4.5 Framework の機能</p></td>
<td><p>HTTP ライセンス認証</p></td>
</tr>
<tr class="odd">
<td><p>.Net 4.5 Framework の機能</p></td>
<td><p>TCP ポート共有</p></td>
</tr>
<tr class="even">
<td><p>バックグラウンドインテリジェント転送サービス</p></td>
<td><p>IIS サーバー拡張機能</p></td>
</tr>
<tr class="odd">
<td><p>インクと手書きサービス</p></td>
<td><p>インクと手書きサービス</p></td>
</tr>
<tr class="even">
<td><p>メディアファンデーション</p></td>
<td><p>メディアファンデーション</p></td>
</tr>
<tr class="odd">
<td><p>ユーザーインターフェイスとインフラストラクチャ</p></td>
<td><p>グラフィカルな管理ツールおよびインフラストラクチャ</p></td>
</tr>
<tr class="even">
<td><p>ユーザーインターフェイスとインフラストラクチャ</p></td>
<td><p>デスクトップ環境</p></td>
</tr>
<tr class="odd">
<td><p>ユーザーインターフェイスとインフラストラクチャ</p></td>
<td><p>サーバーのグラフィカルシェル</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation 3.5</p></td>
<td><p>Windows Identity Foundation 3.5</p></td>
</tr>
<tr class="odd">
<td><p>Windows プロセスアクティブ化サービス</p></td>
<td><p>プロセスモデル</p></td>
</tr>
<tr class="even">
<td><p>Windows プロセスアクティブ化サービス</p></td>
<td><p>構成 Api</p></td>
</tr>
</tbody>
</table>


Windows Server 2012 および Windows Server 2012 R2 では、Windows PowerShell 3.0 を使用して IIS の要件をインストールできます。 Windows PowerShell 3.0 で ServerManager モジュールを使用して、次のように入力します。

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> Windows Server 2012 を使用した新機能– Source パラメーターは、Windows Server 2012 のソースメディアがある場所を定義します。 メディアは、DVD ドライブ (D:\sources\sxs)。など)、またはメディアファイルがコピーされたネットワーク共有 (たとえば、Fileserver\windows2012\sources\Sxs) として定義でき \\ ます。



</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のフロントエンドプールおよび Standard Edition サーバーの IIS 要件](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

