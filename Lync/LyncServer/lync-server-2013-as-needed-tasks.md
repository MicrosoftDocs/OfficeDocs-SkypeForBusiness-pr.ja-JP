---
title: 'Lync Server 2013: 必要に応じてタスク'
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
ms.openlocfilehash: 344512a1dd4db44b8290efdcc726275b4a6898de
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="as-needed-tasks-in-lync-server-2013"></a>Lync Server 2013 での必要なタスク

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-08-18_

必要に応じて、次のタスクを実行します。 通常、標準の手順でもカバーされています。

  - **完全なセキュリティ監査   **この監査は、メッセージングシステムのアップグレードまたは再設計、または試行された (または成功した) セキュリティ違反に対応して、定期的に行うことができます。 この手順では、サーバーやファイアウォールでのポートスキャン、セキュリティ修正プログラムの監査、サードパーティのペネトレーションテストなどを行うことができます。

  - **証明書に関する情報を期限切れ**   にするには Lync Server 証明書は通常の週間タスクの1つであり、管理者はすべての証明書の有効期限を記録する必要があります。 このレコードを使用すると、特定の証明書が期限切れになり、必要に応じて置き換えられるときに、管理者が通知を作成できます。

  - **パフォーマンスの基準計画**   を更新するアップグレードまたは構成の変更後にパフォーマンスベースラインを更新します。 組織では、ベースラインを使用してパフォーマンスの変化を測定し、システムのパフォーマンスに影響する問題を検出することができます。

  - **エンタープライズプール**   、標準エディションサーバー、および組織内の他のすべてのサーバーのエンタープライズプールの初期構成を管理するには、個々のサーバーを展開するときに行いました。 Standard Edition server とエンタープライズプールの展開後のサーバーとプールの管理には、次のタスクが含まれます。
    
      - フロントエンドサーバーの管理
    
      - Web 会議を管理する
    
      - 会議を管理する
    
      - サービスアカウントの資格情報を変更する
    
      - データベースの管理
    
      - サービスを開始および停止し、サーバーの役割を非アクティブ化する
    
      - サーバーとサーバーの役割の削除、プールの削除、サーバーとプールの無効化

  - **利用状況**   の管理 Lync Server 2013 を構成して、組織に最も適した機能を提供できます。 これには、次のポリシーが含まれます。
    
      - オンプレミスの Web 会議会議のサポートを管理する
    
      - インスタントメッセージを送信するための配布グループの使用を管理する
    
      - 連絡先、プレゼンス、およびクエリを管理する
    
      - クライアントのバージョンのフィルター処理を構成する
    
      - インテリジェント IM フィルターの設定
    
      - アーカイブ、通話の詳細の記録、会議のコンプライアンスを構成する

  - **エッジサーバー**   への接続の管理外部接続を提供するために必要なサーバーと設定の進行状況には、次のものが含まれます。
    
      - 内部サーバーとエッジサーバー間の接続の管理
    
      - エッジサーバーの内部および外部インターフェイスと証明書の構成
    
      - フェデレーションパートナーへのアクセスを管理する

  - ****   アドレス帳の管理アドレス帳サーバーを管理するには、次のものが含まれます。
    
      - アドレス帳のサーバー電話の正規化を構成する
    
      - コマンドラインからアドレス帳サーバーを管理する

  - ****   ユーザーアカウントの管理を管理するには、次のものが含まれます。
    
      - Lync Server のユーザーアカウントを有効にする
    
      - ウィザードを使用して Lync Server ユーザーを構成する
    
      - Lync Server の個々のユーザーアカウントのプロパティを構成する
    
      - Lync Server ユーザーを検索する
    
      - Lync Server ユーザーを移動する
    
      - Lync Server ユーザーを削除する

  - **Lync server 2013 ログファイル**   の分析一般的なトラブルシューティングに使用される便利なツールの1つについては、「lync server [2013 logging ツールの使用](http://technet.microsoft.com/en-us/library/gg558599.aspx)について詳しく説明されている lync server 2013 ログツール」をご覧ください。

ログツールによって (サーバーごとに) ログファイルが生成されるため、Microsoft Office Server 12 リソースキットツールがコンピューターにインストールされている場合は、Snooper ツールを使用してこれらのログファイルを表示および分析することができます。 そうしないと、ログもテキストエディターを使って分析することができます。これは、Snooper ユーティリティを使用する場合よりも透明で、より複雑なものになります。

プロトコルメッセージの表示と分析を行うには

ログツールで、デバッグセッションを終了したら、[ログファイルの分析] をクリックし、Snooper ツールを使用してログファイルを表示します。 次のコンポーネントのプロトコルログを分析できます。

  - Lync Server SipStack (SIP)

  - Lync Server S4 (SIP)

  - MCU インフラストラクチャ C3P とフォーカス C3P を含む Lync Server 会議のシグナリングトラフィック (C3P)

  - Lync Server Web 会議トラフィック (PSOM)

  - Lync Server ユニファイドコミュニケーションクライアントプラットフォームクライアント (UCCP)

  - アーカイブデータベースからのエラーレポート

必要なタスクのパフォーマンスを整理するために、必要に応じて操作のチェックリストを確認します。

<div>


> [!IMPORTANT]  
> 詳細な管理手順と管理手順については、「Microsoft Lync Server 2013 管理者ガイド」を参照してください。



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a>バックアップ (および復元) ポリシーまたは構成設定

Lync Server 2013 を使用すると、システム全体のバックアップと復元を行うことができます。 1つのポリシーまたは構成設定の単一のコレクションをバックアップして、適切なポリシーを取得し、そのオブジェクトを Clixml コマンドレットにパイプして、ポリシー情報を XML ファイルとして保存します。

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

これで、RedmondClientPolicy を試して、設定を変更することができます。 以前のポリシーを復元する場合は、次のように入力します。

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

この方法はほとんどのポリシーと設定で動作しますが、より複雑な項目 (ルーティング構成設定など、複数の異なる音声ルートを含むアイテム) では動作しません。

</div>

</div>

<span> </span>

</div>

</div>

</div>

