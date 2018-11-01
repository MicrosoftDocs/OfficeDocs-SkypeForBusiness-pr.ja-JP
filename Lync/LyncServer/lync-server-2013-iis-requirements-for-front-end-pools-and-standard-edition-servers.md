---
title: 'Lync Server 2013: フロントエンド プールおよび Standard Edition サーバーの IIS 要件'
TOCTitle: フロントエンド プールおよび Standard Edition サーバーの IIS 要件
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg399038(v=OCS.15)
ms:contentKeyID: 48273908
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のフロントエンド プールおよび Standard Edition サーバーの IIS 要件

 

_**トピックの最終更新日:** 2016-12-08_

Standard Edition サーバー、フロントエンド サーバー、およびディレクターの場合には、次の目的のために Lync Server 2013 のインストーラーで仮想ディレクトリが インターネット インフォメーション サービス (IIS) に作成されます。

  - ユーザーがアドレス帳サービスからファイルをダウンロードできるようにする。

  - クライアントが更新を取得できるようにする。

  - 会議を有効にする。

  - ユーザーが会議コンテンツをダウンロードできるようにする。

  - ユーザーが配布グループを拡張できるようにする。

  - 電話会議を有効にする。

  - 応答グループ機能を有効にする。

さらに、 Lync Server 2010 の累積的な更新プログラム: 2011 年 11 月のインストーラーは、次の目的のために、IIS に仮想ディレクトリを作成します。

  - フロント エンド サーバー または Standard Edition サーバーで、インスタント メッセージング (IM)、プレゼンスなどのモビリティ機能をモバイル デバイス上でサポートするため

  - フロント エンド サーバー、Standard Edition サーバー、およびディレクターで、モバイル デバイスが自動的にモビリティ リソースを検出できるようにするため

> [!NOTE]
> モビリティを展開する場合は、IIS 7.5 を使用することをお勧めします。 Lync Server Mobility Service のインストーラーは、いくつかの ASP.NET フラグを設定しパフォーマンスを向上させます。既定では、IIS 7.5 が Windows Server 2008 R2 にインストールされ、Mobility Service インストーラーによって ASP.NET 設定が自動的に変更されます。Windows Server 2008 で IIS 7.0 を使用する場合は、これらの設定を手動で変更する必要があります。


Lync Server に次の IIS モジュールをインストールする必要があります。


> [!IMPORTANT]
> 組織で IIS およびすべての Web サービスをシステム ドライブ以外のドライブに配置する必要がある場合、[セットアップ] ダイアログ ボックスで Lync Server ファイルのインストール先パスを変更できます。OCSCore.msi などセットアップ ファイルをこのパスにインストールすると、残りの Lync Server ファイルもこのドライブに展開されます。IIS のインストール時に Windows サーバー マネージャーによって展開された INETPUB を再配置する方法の詳細については、 <A class=uri href="http://go.microsoft.com/fwlink/?linkid=216888%26clcid=0x411">http://go.microsoft.com/fwlink/?linkid=216888&amp;clcid=0x411</A> を参照してください。



  - 静的コンテンツ

  - 既定のドキュメント

  - HTTP エラー

  - ASP.NET

  - .NET 拡張機能

  - Internet Server API (ISAPI) 拡張機能

  - ISAPI フィルター

  - HTTP ロギング機能

  - ログ ツール

  - 追跡

  - Windows 認証

  - 要求のフィルタリング

  - 静的コンテンツ圧縮

  - 動的コンテンツ圧縮

  - IIS 管理コンソール

  - IIS 管理スクリプトおよびツール

  - 匿名認証 (IIS のインストール時に既定でインストールされる)

  - クライアント証明書マッピング認証

次の表では、内部アクセス用の仮想ディレクトリの URI とそれらが参照しているファイル システム リソースの一覧を示します。

### 内部アクセス用の仮想ディレクトリ

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>機能</th>
<th>仮想ディレクトリの URI</th>
<th>参照先</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>アドレス帳サーバー</p></td>
<td><p>https:// <em>&lt;Internal FQDN&gt;</em>/ABS/int/Handler</p></td>
<td><p>内部ユーザー用のアドレス帳サーバー ダウンロード ファイルの場所。</p></td>
</tr>
<tr class="even">
<td><p>自動検出サービス</p></td>
<td><p>https:// &lt;Internal FQDN&gt;/Autodiscover</p></td>
<td><p>内部モバイル デバイス ユーザー用のモビリティ リソースを探す Lync Server 自動検出サービスの場所。</p></td>
</tr>
<tr class="odd">
<td><p>クライアント更新</p></td>
<td><p>http:// <em>&lt;Internal FQDN&gt;</em>/AutoUpdate/Int</p></td>
<td><p>内部のコンピューターベース クライアント用の更新ファイルの場所。</p></td>
</tr>
<tr class="even">
<td><p>会議</p></td>
<td><p>http:// <em>&lt;Internal FQDN&gt;</em>/Conf/Int</p></td>
<td><p>内部ユーザー用会議リソースの場所。</p></td>
</tr>
<tr class="odd">
<td><p>デバイス更新</p></td>
<td><p>http:// <em>&lt;Internal FQDN&gt;</em>/DeviceUpdateFiles_Int</p></td>
<td><p>内部統合コミュニケーション (UC) デバイス用の UC デバイス更新ファイルの場所。</p></td>
</tr>
<tr class="even">
<td><p>ミーティング</p></td>
<td><p>http:// <em>&lt;Internal FQDN&gt;</em>/etc/place/null</p></td>
<td><p>内部ユーザー用のミーティング コンテンツの場所。</p></td>
</tr>
<tr class="odd">
<td><p>Mobility Service</p></td>
<td><p>https:// &lt;Internal FQDN&gt;/Mcx</p></td>
<td><p>内部モバイル デバイス ユーザー用の Mobility Service リソースの場所。</p></td>
</tr>
<tr class="even">
<td><p>グループ拡張およびアドレス帳 Web クエリ サービス</p></td>
<td><p>http:// <em>&lt;Internal FQDN&gt;</em>/GroupExpansion/int/service.asmx</p></td>
<td><p>内部ユーザーのグループ拡張を有効にする Web サービスの場所。また、内部 Lync MobileMicrosoft Lync 2010 Mobile クライアントにグローバル アドレス一覧情報を提供するアドレス帳 Web クエリ サービスの場所。</p></td>
</tr>
<tr class="odd">
<td><p>電話会議</p></td>
<td><p>http:// <em>&lt;Internal FQDN&gt;</em>/PhoneConferencing/Int</p></td>
<td><p>内部ユーザー用の電話会議データの場所。</p></td>
</tr>
<tr class="even">
<td><p>デバイス更新</p></td>
<td><p>http:// <em>&lt;Internal FQDN&gt;</em>/RequestHandler</p></td>
<td><p>内部 UC デバイスによるログのアップロードと更新の確認を可能にするデバイス更新 Web サービス要求ハンドラーの場所。</p></td>
</tr>
<tr class="odd">
<td><p>応答グループ アプリケーション</p></td>
<td><p>http:// <em>&lt;Internal FQDN&gt;</em>/RgsConfig</p>
<p>http:// <em>&lt;Internal FQDN&gt;</em>/RgsClients</p></td>
<td><p>応答グループ構成ツールの場所。</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> 集中構成での フロント エンド プールの場合は、IIS を展開してから、プールにサーバーを追加する必要があります。


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="security" alt="security" />セキュリティ 注:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>IIS 管理用スナップインを使用して、IIS Web コンポーネント サーバーで使用される証明書を割り当てる必要があります。</td>
</tr>
</tbody>
</table>

