---
title: 'Lync Server 2013: IIS 構成'
TOCTitle: IIS 構成
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48273322
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の IIS 構成

 

_**トピックの最終更新日:** 2016-12-08_

この手順を正常に完了するには、少なくともローカル管理者またはドメイン ユーザーとして、サーバーにログオンしている必要があります。

Lync Server 2013Standard Edition の フロント エンド サーバーまたはプール内の最初の フロント エンド サーバーを構成およびインストールする前に、 インターネット インフォメーション サービス (IIS) のサーバーの役割および Web サービスをインストールおよび構成します。


> [!IMPORTANT]
> 組織で IIS およびすべての Web サービスをシステム ドライブ以外のドライブに配置する必要がある場合は、Lync Server 2013 の管理ツールを初めてインストールするときに、[セットアップ] ダイアログ ボックスで Lync Server 2013 ファイルのインストール先パスを変更できます。管理ツールは、IIS をインストールする前にインストールします。OCSCore.msi などのセットアップ ファイルをこのパスにインストールすると、残りの Lync Server 2013 ファイルもこのドライブに展開されます。詳細については、「<A href="lync-server-2013-install-lync-server-administrative-tools.md">Lync Server 2013 管理ツールをインストールする</A>」を参照してください。IIS のインストール時に Windows サーバー マネージャーによって展開された INETPUB を再配置する方法の詳細については、<A class=uri href="http://go.microsoft.com/fwlink/?linkid=216888">http://go.microsoft.com/fwlink/?linkid=216888</A> を参照してください。



次の表に、必要な IIS 7.5 の役割サービスを示します。

### IIS 7.5 の役割サービス

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
<td><p>HTTP 共通機能インストール済み</p></td>
<td><p>静的コンテンツ</p></td>
</tr>
<tr class="even">
<td><p>HTTP 共通機能インストール済み</p></td>
<td><p>既定のドキュメント</p></td>
</tr>
<tr class="odd">
<td><p>HTTP 共通機能インストール済み</p></td>
<td><p>HTTP エラー</p></td>
</tr>
<tr class="even">
<td><p>アプリケーション開発</p></td>
<td><p>ASP.NET</p>
<p>Windows Server 2012 では ASP.NET4.5 も必要</p></td>
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
<td><p>状態と診断</p></td>
<td><p>HTTP ロギング機能</p></td>
</tr>
<tr class="odd">
<td><p>状態と診断</p></td>
<td><p>ログ ツール</p></td>
</tr>
<tr class="even">
<td><p>状態と診断</p></td>
<td><p>追跡</p></td>
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
<td><p>要求のフィルタリング</p></td>
</tr>
<tr class="odd">
<td><p>パフォーマンス</p></td>
<td><p>静的コンテンツ圧縮</p>
<p>動的コンテンツ圧縮</p></td>
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


Windows Server 2008 R2 SP1 x64 オペレーティング システムの場合は、 Windows PowerShell 2.0 を使用できます。最初に ServerManager モジュールをインポートしてから、IIS 7.5 の役割および役割サービスをインストールする必要があります。

```
Import-Module ServerManager
```
   
```
Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
```

> [!NOTE]
> 匿名認証は、IIS サーバーの役割と共に既定でインストールされます。匿名認証は、IIS をインストールした後に管理することができます。詳細については、「匿名認証を有効にする (IIS 7)」( <a href="http://go.microsoft.com/fwlink/?linkid=203935" class="uri">http://go.microsoft.com/fwlink/?linkid=203935</a>) を参照してください。


次の表に、Windows Server 2012 と Windows Server 2012 R2 に必要な IIS 8.0 および IIS 8.5 の役割サービスを示します。

> [!NOTE]
> Windows Server 2012 および Windows Server 2012 R2 の場合は、Add-WindowsFeature コマンドレットは Install-WindowsFeature コマンドレットに置き換えられています。詳細については、「<a href="http://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</a>」を参照してください。</td>
</tr>
</tbody>
</table>


### IIS 8.0 および IIS 8.5 の役割サービス

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
<td><p>共通の HTTP 機能</p></td>
<td><p>既定のドキュメント</p></td>
</tr>
<tr class="odd">
<td><p>共通の HTTP 機能</p></td>
<td><p>ディレクトリ参照</p></td>
</tr>
<tr class="even">
<td><p>共通の HTTP 機能</p></td>
<td><p>HTTP エラー</p></td>
</tr>
<tr class="odd">
<td><p>共通の HTTP 機能</p></td>
<td><p>静的コンテンツ</p></td>
</tr>
<tr class="even">
<td><p>共通の HTTP 機能</p></td>
<td><p>HTTP リダイレクト</p></td>
</tr>
<tr class="odd">
<td><p>状態と診断</p></td>
<td><p>HTTP ロギング機能</p></td>
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
<td><p>追跡</p></td>
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
<td><p>.Net Extensibility 3.5</p></td>
</tr>
<tr class="even">
<td><p>アプリケーション開発</p></td>
<td><p>.Net Extensibility 4.5</p></td>
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
<td><p>IIS 6 メタベース互換</p></td>
</tr>
<tr class="even">
<td><p>管理ツール</p></td>
<td><p>IIS 管理スクリプトおよびツール</p></td>
</tr>
<tr class="odd">
<td><p>.Net 3.5 Framework 機能</p></td>
<td><p>.Net 3.5 Framework</p></td>
</tr>
<tr class="even">
<td><p>.Net 4.5 Framework 機能</p></td>
<td><p>.Net Framework 4.5</p></td>
</tr>
<tr class="odd">
<td><p>.Net 4.5 Framework 機能</p></td>
<td><p>ASP.Net 4.5</p></td>
</tr>
<tr class="even">
<td><p>.Net 4.5 Framework 機能</p></td>
<td><p>HTTP アクティブ化</p></td>
</tr>
<tr class="odd">
<td><p>.Net 4.5 Framework 機能</p></td>
<td><p>TCP ポート共有</p></td>
</tr>
<tr class="even">
<td><p>バックグラウンド インテリジェント転送サービス</p></td>
<td><p>IIS サーバー拡張機能</p></td>
</tr>
<tr class="odd">
<td><p>インクおよび手書きサービス</p></td>
<td><p>インクおよび手書きサービス</p></td>
</tr>
<tr class="even">
<td><p>メディア ファンデーション</p></td>
<td><p>メディア ファンデーション</p></td>
</tr>
<tr class="odd">
<td><p>ユーザー インターフェイスおよびインフラストラクチャ</p></td>
<td><p>グラフィック管理ツールおよびインフラストラクチャ</p></td>
</tr>
<tr class="even">
<td><p>ユーザー インターフェイスおよびインフラストラクチャ</p></td>
<td><p>デスクトップ エクスペリエンス</p></td>
</tr>
<tr class="odd">
<td><p>ユーザー インターフェイスおよびインフラストラクチャ</p></td>
<td><p>サーバー グラフィック シェル</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation 3.5</p></td>
<td><p>Windows Identity Foundation 3.5</p></td>
</tr>
<tr class="odd">
<td><p>Windows プロセス アクティブ化サービス</p></td>
<td><p>プロセス モデル</p></td>
</tr>
<tr class="even">
<td><p>Windows プロセス アクティブ化サービス</p></td>
<td><p>構成 API</p></td>
</tr>
</tbody>
</table>


Windows Server 2012 および Windows Server 2012 R2 では、Windows PowerShell 3.0 を使用して IIS の必要条件をインストールできます。Windows PowerShell 3.0 で ServerManager モジュールを使用して、次のように入力します。

```
Import-Module ServerManager
```
```
Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
```

> [!IMPORTANT]
> Windows Server 2012 では、Windows Server 2012 ソース メディアのある場所を定義する –Source パラメーターが追加されました。メディアは DVD ドライブとして定義するか (例: D:\Sources\Sxs)、メディア ファイルがコピーされているネットワーク共有に定義 (例: \\\\fileserver\windows2012\sources\Sxs) できます。



## 関連項目

#### 概念

[Lync Server 2013 のフロントエンド プールおよび Standard Edition サーバーの IIS 要件](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

