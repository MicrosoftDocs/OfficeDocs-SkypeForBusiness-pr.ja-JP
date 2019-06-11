---
title: フロントエンド プールおよび Standard Edition サーバーの IIS 要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IIS requirements for Front End pools and Standard Edition servers
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399038(v=OCS.15)
ms:contentKeyID: 48185888
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d804df614eab49eeabe82cca9d304e082d9ced3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a>Lync Server 2013 のフロントエンド プールおよび Standard Edition サーバーの IIS 要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-06-19_

Standard Edition サーバー、フロントエンドサーバー、およびディレクターの場合、Lync Server 2013 installer では、次の目的でインターネットインフォメーションサービス (IIS) で仮想ディレクトリが作成されます。

  - ユーザーがアドレス帳サービスからファイルをダウンロードできるようにするには

  - クライアントが更新プログラムを取得できるようにするには

  - 会議を有効にするには

  - ユーザーが会議コンテンツをダウンロードできるようにするには

  - ユーザーが配布グループを展開できるようにするには

  - 電話会議を有効にするには

  - 応答グループの機能を有効にするには

さらに、Lync Server 2010: 2011 年11月の累積更新プログラムでは、次の目的で IIS で仮想ディレクトリが作成されます。

  - モバイルデバイスでのインスタントメッセージング (IM) やプレゼンスなどの機動性機能をサポートするフロントエンドサーバーまたは Standard Edition サーバーの場合

  - フロントエンドサーバーまたは標準エディションのサーバーおよびディレクターで、モバイルデバイスでモビリティリソースを自動的に検出できるようにする



> [!NOTE]
> モバイル機能を導入する場合は、IIS 7.5 を使用することをお勧めします。 Lync Server Mobility Service installer は、パフォーマンスを向上させるためにいくつかの ASP.NET フラグを設定します。 既定では、Windows Server 2008 R2 に IIS 7.5 がインストールされ、モビリティサービスのインストーラーによって ASP.NET の設定が自動的に変更されます。 Windows Server 2008 で IIS 7.0 を使っている場合は、これらの設定を手動で変更する必要があります。



Lync Server では、次の IIS モジュールをインストールする必要があります。


> [!IMPORTANT]
> 組織で IIS およびすべての Web サービスをシステムドライブ以外のドライブに配置する必要がある場合、[セットアップ] ダイアログボックスで Lync Server ファイルのインストール場所のパスを変更することができます。 このパス (OCSCore など) にセットアップファイルをインストールすると、その他の Lync Server ファイルもこのドライブに展開されます。 IIS をインストールするときに、Windows Server Manager によって展開された INETPUB <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>を再配置する方法の詳細については、を参照してください。


  - 静的コンテンツ

  - 既定のドキュメント

  - HTTP エラー

  - ASP.NET

  - .NET の拡張性

  - Internet Server API (ISAPI) の拡張機能

  - ISAPI フィルター

  - HTTP ログ

  - ログ ツール

  - トレース

  - Windows 認証

  - 要求のフィルタリング

  - 静的コンテンツ圧縮

  - 動的コンテンツ圧縮

  - IIS 管理コンソール

  - IIS 管理スクリプトおよびツール

  - 匿名認証 (IIS がインストールされている場合に既定でインストールされます)

  - クライアント証明書マッピング認証

次の表は、内部アクセス用の仮想ディレクトリと、それらが参照するファイルシステムリソースの Uri を示しています。

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
<td><p>https://&lt;の内部&gt;FQDN/ABS/int/Handler</p></td>
<td><p>内部ユーザーのアドレス帳サーバーのダウンロードファイルの場所。</p></td>
</tr>
<tr class="even">
<td><p>自動検出サービス</p></td>
<td><p>https://&lt;内部 FQDN&gt;/自動検出</p></td>
<td><p>内部のモバイルデバイスユーザーのモビリティリソースを検索する、Lync Server 自動検出サービスの場所。</p></td>
</tr>
<tr class="odd">
<td><p>クライアントの更新</p></td>
<td><p>http://&lt;の内部&gt;FQDN/AutoUpdate/Int</p></td>
<td><p>内部コンピューターベースのクライアントの更新ファイルの場所。</p></td>
</tr>
<tr class="even">
<td><p>会議</p></td>
<td><p>http://&lt;内部 FQDN&gt;/conf/Int</p></td>
<td><p>内部ユーザーの会議リソースの場所。</p></td>
</tr>
<tr class="odd">
<td><p>デバイスの更新</p></td>
<td><p>http://&lt;内部 FQDN&gt;/deviceupdatefiles_ Int</p></td>
<td><p>内部 UC デバイスの統合通信 (UC) デバイス更新ファイルの場所。</p></td>
</tr>
<tr class="even">
<td><p>会議</p></td>
<td><p>http://&lt;の内部&gt;FQDN/etc/place/null</p></td>
<td><p>内部ユーザー向けの会議コンテンツの場所。</p></td>
</tr>
<tr class="odd">
<td><p>モバイルサービス</p></td>
<td><p>https://&lt;内部 FQDN&gt;/mcx</p></td>
<td><p>内部モバイルデバイスユーザー向けのモビリティサービスリソースの場所。</p></td>
</tr>
<tr class="even">
<td><p>グループの展開とアドレス帳 Web クエリサービス</p></td>
<td><p>http://&lt;の内部&gt;FQDN またはグループの無効化</p></td>
<td><p>内部ユーザーに対してグループの拡張を可能にする Web サービスの場所。 また、内部の Lync Mobile Microsoft Lync 2010 モバイルクライアントにグローバルアドレス一覧の情報を提供するアドレス帳 Web クエリサービスの場所。</p></td>
</tr>
<tr class="odd">
<td><p>電話会議</p></td>
<td><p>http://&lt;の内部&gt;FQDN/PhoneConferencing/Int</p></td>
<td><p>内部ユーザー向けの電話会議データの場所。</p></td>
</tr>
<tr class="even">
<td><p>デバイスの更新</p></td>
<td><p>http://&lt;の内部&gt;FQDN/RequestHandler</p></td>
<td><p>内部の UC デバイスでログをアップロードし、更新プログラムを確認できるようにする、デバイス更新 Web サービス要求ハンドラーの場所。</p></td>
</tr>
<tr class="odd">
<td><p>応答グループ アプリケーション</p></td>
<td><p>http://&lt;の内部&gt;FQDN/RgsConfig</p>
<p>http://&lt;の内部&gt;FQDN/RgsClients</p></td>
<td><p>応答グループ構成ツールの場所。</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> 統合された構成のフロントエンドプールの場合は、プールにサーバーを追加する前に、IIS を展開する必要があります。


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="証券" alt="security" />セキュリティメモ:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Iis 管理スナップインを使用して、IIS web コンポーネントサーバーで使用する証明書を割り当てる必要があります。</td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

