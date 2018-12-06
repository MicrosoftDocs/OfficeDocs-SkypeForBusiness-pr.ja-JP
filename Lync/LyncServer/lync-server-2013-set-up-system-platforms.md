---
title: 'Lync Server 2013: システム プラットフォームを設定する'
TOCTitle: システム プラットフォームを設定する
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48271606
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でシステム プラットフォームを設定する

 

_**トピックの最終更新日:** 2013-02-21_

常設チャット サーバーの展開を開始する前に、サーバー上でシステム要件を満たすハードウェアに必要なオペレーティング システムをインストールする必要があります。

Lync Server 2013 を実行するサーバー、データベース サーバー、およびファイル サーバーのサポートされるハードウェアの詳細については、「サポート」のドキュメントの「[Lync Server 2013 でサポートされるハードウェア](lync-server-2013-supported-hardware.md)」を参照してください。サポートされるオペレーティング システムおよびデータベース ソフトウェアの詳細については、「サポート」のドキュメントの「[Lync Server 2013 でのサーバーのソフトウェアおよびインフラストラクチャ サポート](lync-server-2013-server-software-and-infrastructure-support.md)」を参照してください。Windows 更新プログラム要件の詳細については、「サポート」のドキュメントの「[Lync Server 2013 の追加サーバー サポートおよび要件](lync-server-2013-additional-server-support-and-requirements.md)」を参照してください。

常設チャット サーバーのフロント エンド サーバー**PersistentChatService** は、Lync Server 2013Enterprise Edition プールの 1 台以上のスタンドアロン コンピューターに展開できます。Lync ServerEnterprise Editionフロント エンド サーバーに共存することはできません。常設チャット サーバーは、他の Lync Server の役割と同様にブートストラップによって展開できます。**ファイルのアップロード/ダウンロード用の常設チャット Web サービス**および**チャット ルーム管理用の常設チャット Web サービス**は、Lync Server 2013フロント エンド サーバーに展開される Web コンポーネントです。

常設チャット サーバーの 1 つの フロント エンド サーバーで 20,000 のアクティブ ユーザーをサポートできます。常設チャット サーバー プールには最大 4 つのアクティブなフロントエンドを展開できるため、合計で 80,000 の同時ユーザーをサポートできます。常設チャットの バック エンド サーバー**PersistentChatStore** には、チャット ルームおよびカテゴリが格納されます。同じ SQL Server インスタンスに Lync Server 2013バック エンド サーバーと **PersistentChatStore** を共存することもできますが、**PersistentChatStore** は Enterprise Edition プールの専用の SQL Serverバック エンド サーバーにインストールすることをお勧めします。

組織がコンプライアンスのサポートを必要とする場合は、トポロジ ビルダーを使用してインストールできます。常設チャット サーバーの フロント エンド サーバーと同一のコンピューター上に、常設チャット サーバー コンプライアンス サービスがインストールされます。コンプライアンスには別のデータベースが必要です。常設チャット サーバーのコンプライアンス要件の詳細については、「計画」のドキュメントの「[Lync Server 2013 での常設チャット サーバーの計画](lync-server-2013-planning-for-persistent-chat-server.md)」を参照してください。

各トポロジには、少なくとも Lync Server 2013 がインストールされたサーバー、および SQL Server データベース ソフトウェアがインストールされたサーバーが必要です。トポロジ ビルダーでは、複数の 常設チャット サーバー プールをサポートしています。複数の 常設チャット サーバー プールを展開する場合は、「展開」のドキュメントの「[Lync Server 2013 の展開](lync-server-2013-deploying-lync-server.md)」に説明されている、任意のプールの展開時と同じ展開手順に従います。

また、常設チャット サーバーを Lync Server 2013Standard Edition に展開することもできます。この場合は、**PersistentChatService**フロント エンド サーバーは Standard Edition サーバーと共存し、**PersistentChatStore**バック エンド サーバーをローカルの SQL Server Express インスタンスに展開できます。


> [!IMPORTANT]
> 常設チャット サーバーStandard Edition では高可用性はサポートされません。パフォーマンスとスケーラビリティには制限があります。さらに、新規の 常設チャット サーバー&nbsp; Standard Edition サーバーの展開のみがサポートされます。Lync Server 2010グループ チャット サーバーの Lync Server 2013常設チャット サーバーStandard Edition へのアップグレードはサポートされていません。



## 関連項目

#### 概念

[Lync Server 2013 の追加サーバー サポートおよび要件](lync-server-2013-additional-server-support-and-requirements.md)  

#### その他のリソース

[Lync Server 2013 でサポートされるハードウェア](lync-server-2013-supported-hardware.md)  
[Lync Server 2013 でのサーバーのソフトウェアおよびインフラストラクチャ サポート](lync-server-2013-server-software-and-infrastructure-support.md)  
[Lync Server 2013 での常設チャット サーバーの計画](lync-server-2013-planning-for-persistent-chat-server.md)  
[Lync Server 2013 の展開](lync-server-2013-deploying-lync-server.md)

