---
title: 'Lync Server 2013: 必要に応じたタスク'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: As-needed tasks
ms:assetid: b66bc6fe-f138-4cf4-ba7f-aee9a3e0497e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722431(v=OCS.15)
ms:contentKeyID: 63969643
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58abaf251bf479a9e892d019bd086a10b2300afc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="as-needed-tasks-in-lync-server-2013"></a>Lync Server 2013 で必要になるタスク

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-08-18_

必要に応じて、次のタスクを実行します。 多くの場合、標準の手順でも説明されています。

  - **完全なセキュリティ監査   **この監査は、メッセージングシステムのアップグレードまたは再設計に対応して、または試行された (または成功した) セキュリティ違反に応答して、定期的に実行できます。 この手順には、サーバーとファイアウォールのポートスキャン、セキュリティ修正プログラムの監査、およびサードパーティの侵入テストが含まれる場合があります。

  - **[証明書を置き換えて、期限切れ**   になるようにする] Lync Server 証明書は、通常の週次のタスクの1つであり、管理者がすべての証明書の有効期限を記録する必要があります。 このレコードを使用すると、管理者は特定の証明書が期限切れになり、必要に応じて置き換えられたときに通知を作成できます。

  - **パフォーマンスベースライン**   の更新アップグレードまたは構成の変更後のパフォーマンスベースラインを更新します。 組織はベースラインを使用して、パフォーマンスの変化を測定し、システムのパフォーマンスに影響する問題を検出することができます。

  - **エンタープライズプール**   、Standard Edition サーバー、および組織の環境内の他のサーバーのエンタープライズプールの初期構成の管理は、個々のサーバーの展開中に実行されました。 Standard Edition サーバーおよびエンタープライズプールのサーバーとプールの展開後の管理には、次のタスクが含まれます。
    
      - フロントエンドサーバーの管理
    
      - Web 会議の管理
    
      - 会議の管理
    
      - サービスアカウントの資格情報の変更
    
      - データベースを管理する
    
      - サービスの開始と停止、およびサーバーの役割の非アクティブ化
    
      - サーバーとサーバーの役割の削除、プールの削除、およびサーバーとプールの使用停止

  - **利用状況**   の管理 Lync Server 2013 を構成して、組織にとって最も適切な機能を提供できます。 エクスポートできるものには、次のようなものがあります。
    
      - オンプレミス Web 会議会議のサポートの管理
    
      - 配布グループの使用を管理してインスタントメッセージを送信する
    
      - 連絡先、プレゼンス、およびクエリを管理する
    
      - クライアントバージョンフィルターを構成する
    
      - インテリジェント IM フィルターの構成
    
      - アーカイブ、通話詳細記録、会議のコンプライアンスの構成

  - **エッジサーバー接続**   の管理サーバーの継続的な管理と、外部接続を提供するために必要な設定には、次のものが含まれます。
    
      - 内部サーバーとエッジサーバー間の接続の管理
    
      - エッジサーバーの内部および外部インターフェイスと証明書の構成
    
      - フェデレーションパートナーアクセスの管理

  - ****   アドレス帳の管理アドレス帳サーバーの管理には、以下が含まれます。
    
      - アドレス帳サーバーの電話の正規化を構成する
    
      - コマンドラインからアドレス帳サーバーを管理する

  - **ユーザーアカウント**   の管理ユーザーアカウントの管理には、次のようなものがあります。
    
      - Lync Server でユーザーアカウントを有効にする
    
      - ウィザードを使用して Lync Server ユーザーを構成する
    
      - 個々の Lync Server ユーザーアカウントのプロパティを構成する
    
      - Lync Server ユーザーの検索
    
      - Lync Server ユーザーの移動
    
      - Lync Server ユーザーの削除

  - **Lync server 2013 ログファイル**   の分析トラブルシューティングに一般的に使用される便利なツールの1つは、「 [lync server 2013 logging tool の使用](https://technet.microsoft.com/library/gg558599.aspx)」で詳しく説明されている lync server 2013 ログツールです。

ログツールはログファイル (サーバー単位) を生成するため、これらのログファイルは、Microsoft Office Server 12 リソースキットツールがコンピューターにインストールされている場合、Snooper ツールを使用して表示および分析できます。 それ以外の場合、ログはテキストエディターを使用して分析することができます。これは、Snooper ユーティリティを使用するよりも透過的で複雑です。

プロトコルメッセージを表示および分析するには

ログツールで、デバッグセッションを終了した後、Snooper ツールを使用してログファイルを表示するには、[ログファイルの分析] をクリックします。 次のコンポーネントのプロトコルログを分析することができます。

  - Lync Server SipStack (SIP)

  - Lync Server S4 (SIP)

  - Lync Server 会議信号トラフィック (C3P) (MCU インフラストラクチャ C3P およびフォーカス C3P を含む)

  - Lync Server Web 会議トラフィック (PSOM)

  - Lync Server 統合コミュニケーションクライアントプラットフォームクライアント (UCCP)

  - アーカイブデータベースからのエラーレポート

必要なタスクのパフォーマンスを整理するには、必要に応じた操作チェックリストを参照してください。

<div>


> [!IMPORTANT]  
> 管理および管理手順の詳細については、「Microsoft Lync Server 2013 Administration Guide」を参照してください。



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a>バックアップ (および復元) ポリシーまたは構成設定

Lync Server 2013 では、システム全体をバックアップおよび復元できます。 Iif をバックアップして、構成設定の単一のポリシーまたは単一のコレクションを取得し、適切なポリシーを取得してから、そのオブジェクトを Export-clixml コマンドレットにパイプ処理して、ポリシー情報を XML ファイルとして保存します。

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

これで、RedmondClientPolicy を試して、設定の多くを変更することができるようになります。 以前のポリシーを復元するのではなく、次のように入力します。

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

この方法は、ほとんどのポリシーと設定で機能しますが、複雑なアイテム (複数のサブオブジェクトを含むアイテムなど) では機能しません (多数の異なる音声ルートを含むルーティング構成設定など)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

