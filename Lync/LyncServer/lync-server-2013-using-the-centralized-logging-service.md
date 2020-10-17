---
title: 'Lync Server 2013: 集中ログサービスの使用'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Centralized Logging Service
ms:assetid: 7b05aaef-f0ea-4649-ba8a-02e68b0cdf23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688101(v=OCS.15)
ms:contentKeyID: 49733700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 276cc87d6ec943332fc30dc21c0906a03703382d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529954"
---
# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a>Lync Server 2013 での集中ログサービスの使用

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

集中ログサービスは、Lync Server 2013 の新機能です。 以前のリリースで提供されていた **OCSLogger** および **OCSTracer** ツールを拡張したものです。 集中ログサービスを使用して、次のタスクを実行できます。

  - 1 つの場所とコマンドから、1 つ以上のコンピューターおよびプールでログを開始します。

  - 1 つの場所とコマンドから、1 つ以上のコンピューターおよびプールのログを停止します。

  - 1 つ以上のコンピューターおよびプールで、1 つの場所とコマンドを検索します。検索コマンドを変更して、すべてのコンピューターで取得および格納されたログの集約全体を取得することも、特定のデータに絞り込んだ結果を取得することもできます。

  - ログ セッションの構成は次のとおりです。
    
      - **シナリオ**を定義するか、既定のシナリオを使用します。 集中ログサービスの *シナリオ* は、範囲 (グローバルまたはサイト)、シナリオ名、および1つ以上のプロバイダーで構成されます。 1 台のコンピューターで同時に 2 つのシナリオを実行できます。
    
      - 既存のプロバイダー** を使用するか、新しいプロバイダーを作成します。プロバイダー** では、ログ セッションが収集するもの、詳細さのレベル、追跡するコンポーネント、適用されるフラグを定義します。
        
        <div>
        

        > [!TIP]  
        > OCSLogger を使用したことがあれば、プロバイダー<EM></EM>は、<STRONG>コンポーネント</STRONG>のコレクション (S4、SIPStack など)、<STRONG>ログ タイプ</STRONG> (WPP、EventLog、IIS ログファイルなど)、<STRONG>トレース レベル</STRONG> (すべて、詳細、デバッグなど)、<STRONG>フラグ</STRONG> (TF_COMPONENT、TF_DIAG など) に相当します。 これらのアイテムは、プロバイダー (Windows PowerShell 変数) で定義され、集中ログサービスコマンドに渡されます。

        
        </div>
    
      - ログを収集するコンピューターおよびプールを構成します。
    
      - ログ セッションの対象範囲を、**サイト** (そのサイトのコンピューターだけでログ キャプチャを実行します) または**グローバル** (展開のすべてのコンピューターでログ キャプチャを実行します) から定義します。

集中ログサービスは非常に強力であり、問題のトラブルシューティングに関するほぼすべてのニーズを満たすことができます (大規模または小規模)。 根本原因の分析からパフォーマンスの問題まで、集中ログサービスは任意の管理者にとって重要なツールとなります。 すべての例は、Lync Server 管理シェルを使用して表示されます。 **CLSController.exe**と呼ばれる集中ログサービス用のコマンドラインコンポーネントがあります。 ヘルプはコマンドライン ツール自体で提供されています。 ただし、コマンド ラインから実行できる限られた機能のセットがあります。 Lync Server 管理シェルを使用すると、はるかに多くの構成可能な機能セットにアクセスできます。 集中ログサービスを使用する場合は、常に Lync Server 管理シェルを最初に検討する方法として考慮する必要があります。

このセクションのトピックでは、集中ログサービスを使用する方法と、さまざまな機能の使用方法の例について説明します。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 の集中ログサービスの概要](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [Lync Server 2013 での集中ログサービスの構成設定の管理](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [Lync Server 2013 での集中ログサービスの構成設定について](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [Lync Server 2013 でログをキャプチャするための集中ログサービスの Start の使用](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [Lync Server 2013 での集中ログサービスの Stop の使用](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [Lync Server 2013 での集中ログサービスによって作成されたキャプチャログでの検索の使用](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [Lync Server 2013 の集中ログサービスからキャプチャログを読み取る](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

