---
title: 'Lync Server 2013: 集中ログサービスの使用'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Centralized Logging Service
ms:assetid: 7b05aaef-f0ea-4649-ba8a-02e68b0cdf23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688101(v=OCS.15)
ms:contentKeyID: 49733700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03b5e4e2582c7b1738f0a6072197643f4df99238
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a>Lync Server 2013 での一元管理ログサービスの使用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

一元管理のログサービスは、Lync Server 2013 の新機能です。 これは、以前のリリースで提供された**Ocslogger**と**ocslogger**のツールの拡張機能です。 一元ログサービスを使用して、次のタスクを実行することができます。

  - 1つまたは複数のコンピューターとプールで、1つの場所とコマンドからのログの記録を開始します。

  - 1つまたは複数のコンピューターとプールのログの記録を1つの場所とコマンドから停止します。

  - 1つまたは複数のコンピューターとプールでログを検索し、1つの場所とコマンドを特定します。 [検索] コマンドをカスタマイズして、すべてのコンピューターに保存されているログの総計を返すことも、特定のデータをキャプチャするトリムダウン結果を返すこともできます。

  - ログ セッションの構成は次のとおりです。
    
      - **シナリオ**を定義するか、既定のシナリオを使用します。 一元管理サービスの*シナリオ*は、スコープ (グローバルまたはサイト) で構成されています。シナリオ名は、そのシナリオの目的と1つ以上のプロバイダーを識別するために用意されています。 コンピューターでは、いつでも2つのシナリオを実行できます。
    
      - 既存のプロバイダー** を使用するか、新しいプロバイダーを作成します。プロバイダー** では、ログ セッションが収集するもの、詳細さのレベル、追跡するコンポーネント、適用されるフラグを定義します。
        
        <div>
        

        > [!TIP]  
        > OCSLogger を使用したことがあれば、プロバイダー<EM></EM>は、<STRONG>コンポーネント</STRONG>のコレクション (S4、SIPStack など)、<STRONG>ログ タイプ</STRONG> (WPP、EventLog、IIS ログファイルなど)、<STRONG>トレース レベル</STRONG> (すべて、詳細、デバッグなど)、<STRONG>フラグ</STRONG> (TF_COMPONENT、TF_DIAG など) に相当します。 これらの項目は、プロバイダー (Windows PowerShell 変数) で定義され、中央の [ログサービス] コマンドに渡されます。

        
        </div>
    
      - ログを収集するコンピューターとプールを構成します。
    
      - [オプション]**サイト**(そのサイト内のコンピューター上のログキャプチャの実行) または [**グローバル**] (展開のすべてのコンピューターでログのキャプチャを実行する) のログセッションのスコープを定義します。

一元的なログサービスは非常に強力であり、問題のトラブルシューティングを行うために、大規模または小規模のニーズをすべて満たすことができます。 根本原因の分析からパフォーマンスの問題を解決するために、一元管理サービスは、どの管理者にとっても重要なツールである場合があります。 すべての例は、Lync Server 管理シェルを使用して表示されます。 一元管理されたログサービスのコマンドラインコンポーネントが、" **Clscontroller .exe**" と呼ばれています。 ツール自体を通じてコマンドラインツールのヘルプが提供されます。 ただし、コマンドラインから実行できる関数のセットは限られています。 Lync Server 管理シェルを使用すると、より広範で構成可能な機能セットにアクセスできます。 一元管理サービスを使用する場合は、常に Lync Server 管理シェルを最初に考慮する方法として検討する必要があります。

このセクションのトピックでは、一元管理サービスの使用方法と、さまざまな機能の使い方の例について説明します。

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 の一元管理されたログサービスの概要](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [Lync Server 2013 で中央集中ログサービスの構成設定を管理する](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [Lync Server 2013 の一元ログサービスの構成設定について](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [Lync Server 2013 でログをキャプチャするために、一元ログサービスの開始を使用する](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [Lync Server 2013 の中央集中ログサービスに対して Stop を使用する](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [Lync Server 2013 の中央集中ログサービスで作成されたキャプチャログでの検索の使用](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [Lync Server 2013 の一元ログサービスからのキャプチャログの読み取り](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

