---
title: Lync Server 2013 での集中ログ サービスの使用
TOCTitle: Lync Server 2013 での集中ログ サービスの使用
ms:assetid: 7b05aaef-f0ea-4649-ba8a-02e68b0cdf23
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688101(v=OCS.15)
ms:contentKeyID: 49887011
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での集中ログ サービスの使用

 

_**トピックの最終更新日:** 2012-11-01_

集中ログ サービス は Lync Server 2013 での新機能です。以前のリリースで提供されていた **OCSLogger** および **OCSTracer** ツールを拡張したものです。集中ログ サービス を使用すると次のタスクを実行できます。

  - 1 つの場所とコマンドから、1 つ以上のコンピューターおよびプールでログを開始します。

  - 1 つの場所とコマンドから、1 つ以上のコンピューターおよびプールのログを停止します。

  - 1 つ以上のコンピューターおよびプールで、1 つの場所とコマンドを検索します。検索コマンドを変更して、すべてのコンピューターで取得および格納されたログの集約全体を取得することも、特定のデータに絞り込んだ結果を取得することもできます。

  - ログ セッションの構成は次のとおりです。
    
      - **シナリオ**を定義するか、既定のシナリオを使用します。集中ログ サービス のシナリオは、対象範囲 (グローバルまたはサイト)、シナリオの目的を識別するためのシナリオ名、および 1 つ以上のプロバイダーで構成されています。1 台のコンピューターで同時に 2 つのシナリオを実行できます。
    
      - 既存のプロバイダーを使用するか、新しいプロバイダーを作成します。プロバイダーでは、ログ セッションが収集するもの、詳細さのレベル、追跡するコンポーネント、適用されるフラグを定義します。
        

        > [!TIP]
        > OCSLogger を使用したことがあれば、プロバイダーは、<STRONG>コンポーネント</STRONG>のコレクション (S4、SIPStack など)、<STRONG>ログ タイプ</STRONG> (WPP、EventLog、IIS ログファイルなど)、<STRONG>トレース レベル</STRONG> (すべて、詳細、デバッグなど)、<STRONG>フラグ</STRONG> (TF_COMPONENT、TF_DIAG など) に相当します。これらの項目はプロバイダーで定義されており (Windows PowerShell 変数)、集中ログ サービス コマンドに渡されます。

    
      - ログを収集するコンピューターおよびプールを構成します。
    
      - ログ セッションの対象範囲を、**サイト** (そのサイトのコンピューターだけでログ キャプチャを実行します) または**グローバル** (展開のすべてのコンピューターでログ キャプチャを実行します) から定義します。

集中ログ サービス は非常に強力であり、問題の大小にかかわらずほとんどすべてのトラブルシューティングのニーズを満たすことができます。根本原因の分析からパフォーマンスの問題まで、集中ログ サービス はすべての管理者にとって重要なツールになる可能性があります。すべての例は Lync Server 管理シェルを使用して示されています。**CLSController.exe** と呼ばれる 集中ログ サービス 用のコマンドライン コンポーネントがあります。ヘルプはコマンドライン ツール自体で提供されています。ただし、コマンド ラインから実行できる限られた機能のセットがあります。Lync Server 管理シェルを使用することで、さらに豊富で構成可能な機能のセットにアクセスできます。集中ログ サービス を使用するときは、Lync Server 管理シェルを最初に検討する必要があります。

このセクションのトピックでは、集中ログ サービス の使用方法を説明し、多くの機能の使用例を示します。

## このセクション中

  - [集中ログサービスの概要](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [PowerShell を使用する集中ログ サービス構成設定の管理](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [集中ログ サービスの構成設定について](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [集中ログ サービスの Start を使用したログのキャプチャー](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [集中ログ サービスの Stop の使用](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [集中ログ サービスが作成したキャプチャ ログ検索の使用](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [集中ログサービスからキャプチャしたログの閲覧](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

