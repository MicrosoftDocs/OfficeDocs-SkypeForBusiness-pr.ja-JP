---
title: 'Lync Server 2013: 常設チャットサーバーの技術要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Persistent Chat Server
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398495(v=OCS.15)
ms:contentKeyID: 48184383
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c99493a2d6921214f91c36fb62e7a75a7279f646
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 の常設チャットサーバーの技術要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-01-06_

常設チャットサーバーをホストする各コンピューターは、以下のコンポーネントを使用して、既存の Lync Server 2013 トポロジにアクセスできる必要があります。

  - **Lync Server 2013、フロントエンドサーバー。** フロントエンドサーバーは、セッション開始プロトコル (SIP) ルーティングの基盤であり、常設チャットサーバーと常設チャット機能を実行しているコンピューター間の通信を可能にします。 常設チャットサーバーの展開を開始する前に、組織に合わせて lync server 2013、Standard Edition、lync Server フロントエンドプール、および Lync server を実行している他の内部コンピューターの展開を確認します。

次のセクションでは、常設チャットサーバーおよび常設チャットデータを格納するデータベースの特定の要件について説明します。

<div>

## <a name="persistent-chat-server-requirements"></a>常設チャットサーバーの要件

Lync Server および常設チャットサーバーの最新バージョンを展開するために推奨されるハードウェアの詳細については、「サポート」のドキュメントの「 [Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)」を参照してください。

Lync Server および常設チャットサーバーのサーバーおよびツールのオペレーティングシステムのサポートの詳細については、「サポート」のドキュメントの「 [Lync server 2013 でのサーバーとツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。

常設チャットサーバーの展開に必要な追加ソフトウェアの詳細については、次の表を参照してください。

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
<td><p>メッセージ キュー</p></td>
<td><p>常設チャットサーバーおよび常設チャットコンプライアンスサービス (展開されている場合) によって使用されます。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a>常設チャットサーバーのデータベースの要件

常設チャットサーバーは、常設チャットデータベースを使用して、チャットの履歴、構成、およびユーザープロビジョニングデータを保存します。 必要に応じて、常設チャットコンプライアンスデータベースを使用してコンプライアンスデータを保存します。

<div>


> [!IMPORTANT]  
> 常設チャットデータベース (mgc) とコンプライアンスデータベース (メンバーサーバー) は、SQL Server の同じインスタンスまたは別の SQL Server に配置できます。



</div>

データベースサーバープラットフォームを準備するには、各コンピューターがハードウェア要件を満たしていることを確認してから、前提条件となるソフトウェアをインストールします。

常設チャットデータベースサーバーのサーバープラットフォームには、Lync Server バックエンドデータベースサーバーと同じハードウェアが必要です。 詳細については、「サポート」のドキュメントの「 [Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)」を参照してください。

データベースサーバーで、次のいずれかのソフトウェアアプリケーションがインストールされていることを確認します。

  - Microsoft SQL Server 2012。 Microsoft SQL Server 2012 をインストールする方法の詳細については、「SQL Server 2012 [https://go.microsoft.com/fwlink/p/?LinkID=248559](https://go.microsoft.com/fwlink/p/?linkid=248559)をインストールする」を参照してください。

  - Microsoft SQL Server 2008 R2 Microsoft SQL Server 2008 R2 のインストール方法の詳細については、「」の「SQL Server のインストール (SQL [https://go.microsoft.com/fwlink/?LinkId=275702](https://go.microsoft.com/fwlink/?linkid=275702)Server 2008 R2)」を参照してください。

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a>常設チャットサーバーの証明書の要件

証明書の取得、SQL Server データベースの作成、およびファイルストアの作成の詳細については、「展開」のドキュメントの「[展開 Lync Server 2013](lync-server-2013-deploying-lync-server.md) 」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

