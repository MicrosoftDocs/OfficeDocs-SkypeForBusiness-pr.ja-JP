---
title: 'Lync Server 2013: 常設チャットサーバーの技術要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Persistent Chat Server
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398495(v=OCS.15)
ms:contentKeyID: 48184383
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b84f1a2932b76c8030c907463e8f0f2e93bedda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 の常設チャットサーバーの技術要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-01-06_

常設チャットサーバーをホストする各コンピューターは、次のコンポーネントを使用して、既存の Lync Server 2013 トポロジにアクセスする必要があります。

  - **Lync Server 2013、フロントエンドサーバー。** フロントエンドサーバーは、セッション開始プロトコル (SIP) ルーティングの基盤です。これにより、常設チャットサーバーを実行しているコンピューターと常設チャット機能を実行しているコンピューター間の通信が可能になります。 常設チャットサーバーの展開を開始する前に、組織に合わせて、lync server 2013、Standard Edition、または lync server のフロントエンドプールと lync server が実行されているその他の内部コンピューターの展開を確認します。

以下のセクションでは、常設チャットサーバーと永続的なチャットデータを格納するデータベースの固有の要件について説明します。

<div>

## <a name="persistent-chat-server-requirements"></a>常設チャットサーバーの要件

Lync Server および最新バージョンの常設チャットサーバーの展開に推奨されるハードウェアの詳細については、サポートドキュメントの「 [Lync server 2013 用のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)」を参照してください。

Lync Server および常設チャットサーバー向けのサーバーとツールのオペレーティングシステムサポートの詳細については、サポートドキュメントの「 [Lync server 2013 でのサーバーとツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。

常設チャットサーバーの展開に必要なその他のソフトウェアの詳細については、次の表を参照してください。

### <a name="persistent-chat-server-software-prerequisites"></a>常設チャットサーバーソフトウェアの前提条件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>ソフトウェア</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>メッセージキュー</p></td>
<td><p>常設チャットサーバーと常設チャットコンプライアンスサービス (展開されている場合)。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a>常設チャットサーバーのデータベース要件

常設チャットサーバーは、常設チャットデータベースを使って、チャット履歴、構成、ユーザープロビジョニングデータを保存します。 必要に応じて、常設チャットのコンプライアンスデータベースを使ってコンプライアンスデータを保存します。

<div>


> [!IMPORTANT]  
> 常設チャットデータベース (行う) とコンプライアンスデータベース () は、SQL Server の同じインスタンスまたは別の SQL server に配置できます。



</div>

データベース サーバー プラットフォームを準備するには、各コンピューターがハードウェア要件を満たしていることを確認した後、必要なソフトウェアをインストールします。

常設チャットデータベースサーバーのサーバープラットフォームには、Lync Server バックエンドデータベースサーバーと同じハードウェアが必要です。 詳細については、サポートドキュメントの「 [Lync server 2013 用のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)」を参照してください。

次のどちらかのソフトウェア アプリケーションがデータベース サーバーにインストールされていることを確認してください。

  - Microsoft SQL Server 2012 Microsoft SQL Server 2012 のインストール方法の詳細については、「SQL Server 2012 を[http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559)インストールする」を参照してください。

  - Microsoft SQL Server 2008 R2 Microsoft SQL Server 2008 R2 のインストール方法の詳細については、「SQL Server のインストール (SQL Server 2008 R2 [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702))」を参照してください。

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a>常設チャットサーバー証明書の要件

証明書の取得、SQL Server データベースの作成、ファイルストアの作成の詳細については、「展開ドキュメントに[Lync Server 2013 を展開](lync-server-2013-deploying-lync-server.md)する」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

