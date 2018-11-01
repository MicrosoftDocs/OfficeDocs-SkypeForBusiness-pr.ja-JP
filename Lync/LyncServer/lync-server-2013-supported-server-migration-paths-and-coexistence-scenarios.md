---
title: 'Lync Server 2013: サポートされるサーバー移行パスと共存のシナリオ'
TOCTitle: サポートされるサーバー移行パスと共存のシナリオ
ms:assetid: 2a6a730f-7f80-45f9-9540-3edfdaa265fb
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425764(v=OCS.15)
ms:contentKeyID: 48271638
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でサポートされるサーバー移行パスと共存のシナリオ

 

_**トピックの最終更新日:** 2012-10-16_

Lync Server 2013 では、次のどちらかの製品からの移行がサポートされています。

  - Microsoft Lync Server 2010

  - Microsoft Office Communications Server 2007 R2

上記の両方のバージョンを実行する環境からの移行はサポートされません。Microsoft Office Communications Server 2007 や Live Communications Server 2005 など、これより前のバージョンからの移行はサポートされません。以前の展開に グループ チャットが含まれる場合は、別途移行する必要があります。

## 移行方法

すべての Lync Server トポロジとサーバーの役割の移行がサポートされています。Standard Edition サーバーから Enterprise Edition サーバーへの移行など、あるトポロジから別のトポロジに移行できます。

Lync Server 2013 では、次の移行方法のみがサポートされています。

  - **サイド バイ サイド移行 :** サイド バイ サイド移行では、Lync Server 2013 が既存の Microsoft Lync Server 2010 または Office Communications Server 2007 R2 展開と並行して展開されます。その後、手動で、運用を新しいサーバーに移行し、ユーザーを Lync Server 2013 に移動します。この方法では、移行中に、ハードウェアとソフトウェアを含む、追加サーバー プラットフォームが必要であり、新しい構成ではシステム名とプール名が異なります。以前のバージョンにロールバックする必要がある場合は、以前のサーバーに運用を戻すことができます。

Active Directory ドメイン サービス フォレスト間での移行は、サポートされません。

推奨される移行パスは、段階的な方法です。コンポーネント展開の適切な段階実行など、以前のリリースからの移行の詳細については、「移行」のドキュメントの以下のトピックを参照してください。

  - [Lync Server 2010 から Lync Server 2013 への移行](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [Office Communications Server 2007 R2 から Lync Server 2013 への移行](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [Lync Server 2010、グループ チャットまたは Office Communicatins Server 2007 R2 グループ チャットから Lync Server 2013、常設チャット サーバーへの移行](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

## 共存シナリオ

Lync Server 2013 は、Lync Server 2010 展開または Office Communications Server 2007 R2 展開のどちらかのコンポーネントと共存できます。Lync Server 2013 の Lync Server 2010 および Office Communications Server 2007 R2 の両方との同時展開、つまり 3 つのバージョンの同時展開はサポートされません。

以前の Lync Server 2010 または Office Communications Server 2007 R2 展開が新しい Lync Server 2013 展開と一時的に共存する段階的移行の進行中は、混在バージョンのルーティングのサポートは制限されます。詳細については、「移行」のドキュメントを参照してください。

Lync Server 2013 のデータベース インスタンスには、Microsoft SQL Server 2008 R2 または Microsoft SQL Server 2012 を実行する別のコンピューターを使用する必要があります。Lync Server 2010 または Office Communications Server 2007 R2 のフロントエンド プールに使用しているものと同じ SQL Server のインスタンスを Lync Server 2013 のフロントエンド プールに使用することはできません。Lync Server 2010 または Office Communications Server 2007 R2 が既に展開されている環境において トポロジ ビルダーで Lync Server 2013 を定義および構成する場合、トポロジ ビルダーでは、既にトポロジ内で使用されている Lync Server 2013 のインスタンスを定義することはできません。

トポロジ ビルダーでは、この問題について知らせるために、"SQL Server '\[サーバーの FQDN\]' には、役割 'ユーザー ストア' をホストする SQL インスタンスが既に存在します。" というメッセージが表示されます。

> [!NOTE]
> Lync Server 2013 展開に新しいサーバー役割を展開する予定がある場合は、最初に「移行」のドキュメントおよび「展開」のドキュメントの説明に従って既存の展開をアップグレードしてから、「計画」のドキュメントおよび「展開」のドキュメントの説明に従って新しいサーバー役割を展開します。以前のバージョンのグループ チャットを移行する場合は、Lync Server 2010 または Office Communications Server 2007 R2 から他のすべてのコンポーネントを移行する作業が完了した後で、最後に移行してください。


Lync Server 2010 または Office Communications Server 2007 R2 と Lync Server 2013 のコンポーネントの共存と移行に関する具体的な共存の要件やその他の詳細については、「移行」のドキュメントの「[Lync Server 2010 から Lync Server 2013 への移行](migration-from-lync-server-2010-to-lync-server-2013.md)」および「[Office Communications Server 2007 R2 から Lync Server 2013 への移行](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)」を参照してください。クライアントの混在バージョン サポートの詳細については、「[Lync Server 2013 で以前の展開からサポートされるクライアント](lync-server-2013-supported-clients-from-previous-deployments.md)」を参照してください。

