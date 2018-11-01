---
title: 'Lync Server 2013: オペレーティング システムと必要なソフトウェアのサーバーへのインストール'
TOCTitle: オペレーティング システムと必要なソフトウェアのサーバーへのインストール
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48271115
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のオペレーティング システムと必要なソフトウェアのサーバーへのインストール

 

_**トピックの最終更新日:** 2016-12-08_

ハードウェアおよびシステム インフラストラクチャのセットアップ後は、展開する各サーバーに適切な Windows オペレーティング システム、更新プログラム、およびその他の必要なソフトウェアをすべてインストールする必要があります。これには、展開に必要な、各 Lync Server 2013 サーバーの役割と、追加のインフラストラクチャ サーバーまたは SQL Server 実行サーバーが含まれます。

> [!NOTE]
> ここでは、オペレーティング システムと内部サーバーに必要なソフトウェアのインストールについて説明します。外部ユーザー アクセスをサポートするために エッジ サーバーを展開する場合は、そうしたサーバーに必要なオペレーティング システムやソフトウェア (エッジ サーバー、リバース プロキシ サーバーなど) もインストールする必要があります。外部ユーザー アクセスをサポートするためのサーバーの準備の詳細については、「展開」のドキュメントの「<a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Lync Server 2013 の境界ネットワークへのサーバーのインストールの準備</a>」を参照してください。


## サーバーへの Windows オペレーティング システムのインストール

展開するサーバーごとに適切な Windows オペレーティング システムをインストールします。

  - **Lync Server 2013 を実行するサーバー**Lync Server 2013 を実行するサーバーのオペレーティング システム要件の詳細については、「サポート」のドキュメントの「[Lync Server 2013 でのサーバーおよびツールのオペレーティング システムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。

  - **データベース サーバー**   データベース サーバー (バック エンド データベース、アーカイブ データベース、監視データベースなど) のオペレーティング システム要件の詳細については、SQL Server のドキュメントを参照してください。 SQL Server 2012 の場合は、「SQL Server 2012 のインストール」([http://go.microsoft.com/fwlink/?linkid=218015\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=218015%26clcid=0x411)) を参照してください。

> [!NOTE]
> Lync Server 2013 を Windows Server 2008 R2 にインストールする場合は、Microsoft サポート技術情報の記事 2646886「FIX: Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5 (英語)」(<a href="http://go.microsoft.com/fwlink/?linkid=3052%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=3052&amp;clcid=0x411</a>) に記載されている更新プログラムを最初にインストールする必要があります。<br />
> さらに、サポート技術情報の記事「<a href="http://go.microsoft.com/fwlink/p/?linkid=506893">Windows Server 2012 の R2 に取り付けられている Lync Server 2013 のフロント エンド サーバーでログに記録はイベント Id 32402、61045</a>」に従って、レジストリも変更する必要があります。


## サーバーへの Windows Updateのインストール

Windows Update で提供されている次の更新プログラムを各サーバーにインストールします。

  - **Lync Server 2013 を実行するサーバー用の Windows 更新プログラム**   Lync Server 2013 を実行するサーバーに必要な、Windows Updateの更新プログラムの詳細については、「計画」のドキュメントの「[Lync Server 2013 の追加ソフトウェア要件](lync-server-2013-additional-software-requirements.md)」を参照してください。

  - **データベース サーバー**   データベース サーバー (バックエンド データベース、アーカイブ データベース、監視データベースなど) に必要な、Windows Update の更新プログラムの詳細については、SQL Server 2012 のドキュメントを参照してください。 SQL Server 2012 の場合は、「SQL Server 2012 のインストール」([http://go.microsoft.com/fwlink/?linkid=218015\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=218015%26clcid=0x411)) を参照してください。

## 他の必要なソフトウェアのサーバーへのインストール

Lync Server 2013 では、以下の追加ソフトウェアをサーバーにインストールする必要があります。

  - **Lync Server 2013 を実行するサーバーに必要なソフトウェア**    Lync Server 2013 を実行するサーバーに必要な追加ソフトウェアは、展開するサーバーの役割によって異なります。各サーバー特有のソフトウェア要件の詳細については、「計画」のドキュメントの「[Lync Server 2013 の追加ソフトウェア要件](lync-server-2013-additional-software-requirements.md)」を参照してください。

  - **Windows Identity Foundation**    Lync Server 2013 では、サーバー間認証のシナリオをサポートするために、Windows Identity Foundation のインストールが必要です。既に Windows Identity Foundation がコンピューターにインストールされているかどうかを確認するには、コントロール パネルを開き、\[**プログラムと機能**\]、\[**インストールされている更新プログラムを表示**\] の順にクリックして、\[**Microsoft Windows**\] の下を探します。Windows Identity Foundation のインストールの詳細については、([http://go.microsoft.com/fwlink/?linkid=204657\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=204657%26clcid=0x411)) を参照してください。

  - **Microsoft .NET Framework 4.5**    Lync Server 2013 には、64 ビット版の Microsoft .NET Framework 4.5 が必要です。

  - **データベース サーバーに必要なソフトウェア**   データベース サーバー (バックエンド データベース、アーカイブ データベース、監視データベースなど) に必要な Windows 更新プログラムの詳細については、SQL Server 2012 のドキュメント ([http://go.microsoft.com/fwlink/?linkid=218015\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=218015%26clcid=0x411)) を参照してください。
    
    > [!NOTE]
    > Lync Server 2013 では、各 Standard Edition サーバーと、ローカル構成ストアが配置される Lync Server 2013 実行サーバーのそれぞれに、Microsoft SQL Server 2012 Express が自動的にインストールされます。


  - **Windows Media フォーマット ランタイム**   会議が展開される フロント エンド サーバーおよび Standard Edition サーバーのすべてに Windows Media フォーマット ランタイムをインストールする必要があります。Windows Media フォーマット ランタイムは、コール パーク、アナウンス、および応答グループ アプリケーションのアナウンスや音楽で再生される Windows Media オーディオ (.wma) ファイルを実行するために必要です。
    
    > [!NOTE]
    > Windows Server 2012 および Windows Server 2012 R2 では、Windows Media フォーマット ランタイムが Microsoft Media Foundation と共にインストールされます。
    
    > [!NOTE]
    > Windows Server 2008 および Windows Server 2008 R2 では、Windows Media フォーマット ランタイムが Windows デスクトップ エクスペリエンスの一部としてインストールされます。 Lync Server 2013 をインストールする前に、Windows デスクトップ エクスペリエンスをインストールすることをお勧めします。このソフトウェアが Lync Server 2013 によってサーバーから検出されない場合は、このソフトウェアのインストールを指示するメッセージが表示されます。このメッセージが表示されたら、サーバーを再起動してインストールを完了する必要があります。

