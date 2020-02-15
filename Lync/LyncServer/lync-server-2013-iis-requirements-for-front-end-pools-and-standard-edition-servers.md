---
title: フロントエンドプールおよび Standard Edition サーバーの IIS 要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS requirements for Front End pools and Standard Edition servers
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399038(v=OCS.15)
ms:contentKeyID: 48185888
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc92cc4c27f7af395a8e41bec26679a27010562d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a>Lync Server 2013 のフロントエンドプールおよび Standard Edition サーバーの IIS 要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-19_

Standard Edition サーバーとフロントエンドサーバーおよびディレクターの場合、Lync Server 2013 インストーラーは次の目的のためにインターネットインフォメーションサービス (IIS) に仮想ディレクトリを作成します。

  - ユーザーがアドレス帳サービスからファイルをダウンロードできるようにする。

  - クライアントが更新を取得できるようにするには

  - 会議を有効にする。

  - ユーザーが会議コンテンツをダウンロードできるようにする。

  - ユーザーが配布グループを拡張できるようにする。

  - 電話会議を有効にする。

  - 応答グループ機能を有効にする。

さらに、Lync Server 2010:11 月2011インストーラーの累積的な更新プログラムにより、次の目的のために IIS で仮想ディレクトリが作成されます。

  - インスタントメッセージング (IM) やプレゼンスなど、モバイルデバイスでのモビリティ機能をサポートするフロントエンドサーバーまたは Standard Edition サーバー上

  - フロントエンドサーバーまたは Standard Edition サーバーとディレクターで、モバイルデバイスがモビリティリソースを自動的に検出できるようにする



> [!NOTE]
> モビリティを展開する場合は、IIS 7.5 を使用することをお勧めします。 Lync Server Mobility Service installer は、パフォーマンスを向上させるためにいくつかの ASP.NET フラグを設定します。 既定では、IIS 7.5 が Windows Server 2008 R2 にインストールされ、Mobility Service インストーラーによって ASP.NET 設定が自動的に変更されます。 Windows Server 2008 で IIS 7.0 を使用する場合は、この設定を手動で変更する必要があります。



Lync Server には、次の IIS モジュールがインストールされている必要があります。


> [!IMPORTANT]
> IIS およびすべての Web サービスをシステムドライブ以外のドライブに配置する必要がある組織では、[セットアップ] ダイアログボックスで Lync Server ファイルのインストール場所のパスを変更できます。 このパスに対して、OCSCore を含むセットアップファイルをインストールすると、残りの Lync Server ファイルもこのドライブに展開されます。 IIS のインストール時に Windows Server Manager によって展開された INETPUB の再<A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>配置方法の詳細については、「」を参照してください。


  - 静的コンテンツ

  - 既定のドキュメント

  - HTTP エラー

  - ASP.NET

  - .NET 拡張機能

  - Internet Server API (ISAPI) 拡張機能

  - ISAPI フィルター

  - HTTP ロギング機能

  - ログ ツール

  - ・

  - Windows 認証

  - 要求のフィルタリング

  - 静的コンテンツ圧縮

  - 動的コンテンツ圧縮

  - IIS 管理コンソール

  - IIS 管理スクリプトおよびツール

  - 匿名認証 (IIS のインストール時に既定でインストールされる)

  - クライアント証明書マッピング認証

次の表では、内部アクセス用の仮想ディレクトリの URI とそれらが参照しているファイル システム リソースの一覧を示します。

### <a name="virtual-directories-for-internal-access"></a>内部アクセス用の仮想ディレクトリ

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
<td><p>https://&lt;内部 FQDN&gt;/ABS/int/Handler</p></td>
<td><p>内部ユーザー用のアドレス帳サーバー ダウンロード ファイルの場所。</p></td>
</tr>
<tr class="even">
<td><p>自動検出サービス</p></td>
<td><p>https://&lt;内部 FQDN&gt;/自動検出</p></td>
<td><p>内部モバイルデバイスユーザーのモビリティリソースを検索する Lync Server 自動検出サービスの場所。</p></td>
</tr>
<tr class="odd">
<td><p>クライアントの更新</p></td>
<td><p>http://&lt;内部 FQDN&gt;/AutoUpdate/Int</p></td>
<td><p>内部のコンピューターベース クライアント用の更新ファイルの場所。</p></td>
</tr>
<tr class="even">
<td><p>Conf</p></td>
<td><p>http://&lt;内部 FQDN&gt;/conf/Int</p></td>
<td><p>内部ユーザー用会議リソースの場所。</p></td>
</tr>
<tr class="odd">
<td><p>デバイス更新</p></td>
<td><p>http://&lt;内部 FQDN&gt;/DeviceUpdateFiles_Int</p></td>
<td><p>内部統合コミュニケーション (UC) デバイス用の UC デバイス更新ファイルの場所。</p></td>
</tr>
<tr class="even">
<td><p>会議</p></td>
<td><p>http://&lt;内部 FQDN&gt;/etc/place/null</p></td>
<td><p>内部ユーザー用のミーティング コンテンツの場所。</p></td>
</tr>
<tr class="odd">
<td><p>Mobility Service</p></td>
<td><p>https://&lt;内部 FQDN&gt;/mcx</p></td>
<td><p>内部モバイル デバイス ユーザー用の Mobility Service リソースの場所。</p></td>
</tr>
<tr class="even">
<td><p>グループ拡張およびアドレス帳 Web クエリ サービス</p></td>
<td><p>http://&lt;内部 FQDN&gt;/グループの内部 FQDN</p></td>
<td><p>内部ユーザーのグループ拡張を有効にする Web サービスの場所。 また、内部 Lync Mobile Microsoft Lync 2010 モバイルクライアントにグローバルアドレス一覧情報を提供する、アドレス帳 Web クエリサービスの場所についても説明します。</p></td>
</tr>
<tr class="odd">
<td><p>電話会議</p></td>
<td><p>http://&lt;内部 FQDN&gt;/PhoneConferencing/Int</p></td>
<td><p>内部ユーザー用の電話会議データの場所。</p></td>
</tr>
<tr class="even">
<td><p>デバイス更新</p></td>
<td><p>http://&lt;内部 FQDN&gt;/RequestHandler</p></td>
<td><p>内部 UC デバイスによるログのアップロードと更新の確認を可能にするデバイス更新 Web サービス要求ハンドラーの場所。</p></td>
</tr>
<tr class="odd">
<td><p>応答グループ アプリケーション</p></td>
<td><p>http://&lt;内部 FQDN&gt;/RgsConfig</p>
<p>http://&lt;内部 FQDN&gt;/RgsClients</p></td>
<td><p>応答グループ構成ツールの場所。</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> 統合構成のフロントエンドプールの場合は、サーバーをプールに追加する前に IIS を展開する必要があります。


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="security" alt="security" />セキュリティに関する注意事項:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>IIS 管理用スナップインを使用して、IIS Web コンポーネント サーバーで使用される証明書を割り当てる必要があります。</td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

