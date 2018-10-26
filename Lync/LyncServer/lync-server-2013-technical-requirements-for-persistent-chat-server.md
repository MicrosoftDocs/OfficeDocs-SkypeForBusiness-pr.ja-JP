---
title: 'Lync Server 2013: 常設チャット サーバーの技術要件'
TOCTitle: 常設チャット サーバーの技術要件
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398495(v=OCS.15)
ms:contentKeyID: 48272356
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 常設チャット サーバーの技術要件

 

_**トピックの最終更新日:** 2016-12-08_

常設チャット サーバーをホストする各コンピューターには、次のコンポーネントの既存の Lync Server 2013 トポロジへのアクセス権が必要です。

  - **Lync Server 2013、フロント エンド サーバー。**  フロント エンド サーバーはセッション開始プロトコル (SIP) ルーティングの基盤であり、常設チャット機能と 常設チャット サーバーを実行しているコンピューター間の通信が可能になります。常設チャット サーバーを展開する前に、Lync Server 2013 Standard Edition または Lync Serverフロント エンド プールと Lync Server を実行する他の社内コンピューターが組織に適切に展開されていることを確認してください。

以下のセクションでは、常設チャット サーバーと 常設チャットデータを格納するデータベースの固有の要件について説明します。

## 常設チャット サーバーの要件

Lync Server および最新バージョンの 常設チャット サーバーを展開するハードウェア要件の詳細については、「サポート」のドキュメントの「[Lync Server 2013　用のサーバー ハードウェア プラットフォーム](lync-server-2013-server-hardware-platforms.md)」を参照してください。

Lync Server および 常設チャット サーバーに対するサーバーおよびツールのオペレーションシステム サポートの詳細については、「サポート」ドキュメントの「[Lync Server 2013 でのサーバーおよびツールのオペレーティング システムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。

常設チャット サーバー の展開に必要となる追加ソフトウェアの詳細については、次の表を参照してください。

### 常設チャット サーバーのソフトウェア要件

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
<td><p>常設チャット サーバーと 常設チャット コンプライアンス サービスで使用されます (展開されている場合)。</p></td>
</tr>
</tbody>
</table>


## 常設チャット サーバーのデータベース要件

常設チャット サーバーでは、常設チャット データベースを使用して、チャット履歴、構成、ユーザー プロビジョニング データを保存します。必要に応じて、常設チャット コンプライアンス データベースを使用して、コンプライアンス データを保存します。


> [!IMPORTANT]
> 常設チャット データベース (mgc) とコンプライアンス データベース (mgccomp) は、同じ SQL Server インスタンスに置くことも、別の SQL Server に置くこともきます。



データベース サーバー プラットフォームを準備するには、各コンピューターがハードウェア要件を満たしていることを確認した後、必要なソフトウェアをインストールします。

常設チャット データベース サーバー用のサーバー プラットフォームには、Lync Server バックエンド データベース サーバーと同じハードウェアが必要です。詳細については、「サポート」のドキュメントの「[Lync Server 2013　用のサーバー ハードウェア プラットフォーム](lync-server-2013-server-hardware-platforms.md)」を参照してください。

次のどちらかのソフトウェア アプリケーションがデータベース サーバーにインストールされていることを確認してください。

  - Microsoft SQL Server 2012。Microsoft SQL Server 2012 のインストール方法の詳細については、「SQL Server 2012 のインストール」(<http://go.microsoft.com/fwlink/?linkid=248559>) を参照してください。

  - Microsoft SQL Server 2008 R2。Microsoft SQL Server 2008 R2 をインストールする方法については、<http://go.microsoft.com/fwlink/?linkid=275702> で「SQL Server Installation (SQL Server 2008 R2)」を参照してください。

## 常設チャット サーバー の証明書の要件

証明書の取得、SQL Server データベースの作成、およびファイル ストアの作成の詳細については、展開ドキュメントの「[Lync Server 2013 の展開](lync-server-2013-deploying-lync-server.md)」を参照してください。

