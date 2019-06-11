---
title: 'Lync Server 2013: 常設チャット サーバーのフェールオーバー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over Persistent Chat Server
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204772(v=OCS.15)
ms:contentKeyID: 48183726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 021b34cafd91397cc36da1dbc22f91b8665aea96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 での常設チャット サーバーのフェールオーバー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-02-05_

常設チャットサーバーのフェールオーバーは、主に手動で行うように設計されています。

フェイルオーバー手順は、セカンダリデータセンターが稼働していることを前提としていますが、プライマリ常設チャットデータベースが配置されている常設チャットサーバーサービスは、次のように完全には使用できません。

  - 常設チャットサーバーのプライマリデータベースと常設チャットサーバーのミラーデータベースがダウンしています。

  - Lync Server フロントエンドサーバーがダウンしています。

この操作は次の 2 つの基本手順に基づいています。

  - プライマリ常設チャットデータベース (行う) を回復します。

  - 新しいプライマリ データベースのミラーリングを確立する。

常設チャットのコンプライアンスデータベース (会社間) は、フェールオーバーされません。 このデータベースの内容は一時的なものであり、コンプライアンス アダプターがデータを処理するときに削除されます。 データの損失を防ぐために、アダプターの出力を適切に管理することは、常設チャット管理者の責任となります。

<div>

## <a name="to-fail-over-persistent-chat-server"></a>常設チャットサーバーをフェイルオーバーするには

1.  常設チャットサーバーバックアップログ配布データベースからログ配布を削除します。
    
    1.  SQL Server Management Studio を使用して、常設チャットサーバーバックアップ行うデータベースが配置されているデータベースインスタンスに接続します。
    
    2.  マスター データベースに対するクエリ ウィンドウを開きます。
    
    3.  次のコマンドを使用して、ログ配布を削除します。
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  バックアップ共有から、バックアップ サーバーのコピー先フォルダーへ、コピーしていないバックアップ ファイルをコピーします。

3.  セカンダリ データベースに、適用していないトランザクション ログ バックアップを順番に適用します。 詳細については、「[方法: トランザクションログバックアップ (Transact-sql) を適用する方法http://go.microsoft.com/fwlink/p/?linkid=247428」を参照してください。

4.  バックアップ mgc データベースをオンラインにします。手順 1b. で開いたクエリ ウィンドウを使用して、次の手順を実行します。
    
    1.  mgc データベースへのすべての接続を終了します (接続がある場合)。
        
        1.  行うデータベースへの接続を確認するには、 **who2 sp\_** を実行します。
        
        2.  spid を終了してこれらの接続を終了します。 ** \<\> **
    
    2.  データベースをオンラインにします。
        
        1.  **restore database mgc with recovery** を実行します。

5.  Lync Server 管理シェルで、コマンド**セット CsPersistentChatState-Identity "service: 001.litwareinc.com" – PoolState FailedOver**を使用して、行う backup データベースにフェールオーバーします。 atl-cs-001.litwareinc.com の部分には、常設チャット プールの完全修飾ドメイン名を指定します。
    
    mgc バックアップ データベースがプライマリ データベースとして動作するようになります。

6.  Lync Server 管理シェルで、 **CsMirrorDatabase**コマンドレットを使用して、プライマリデータベースとして機能するバックアップデータベースに対して高可用性ミラーを確立します。 バックアップ データベース インスタンスをプライマリ データベースとして使用し、バックアップ ミラー データベース インスタンスをミラー インスタンスとして使用します。 これは、セットアップ時にプライマリ データベースに対して最初に構成したミラーと同じものではありません。 詳細については、「 [lync server 2013 でのバックエンドサーバーの高可用性のための SQL ミラーリングの展開](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)」の「Lync Server 管理シェルコマンドレットの使用」セクションを参照してください。

7.  常設チャットサーバーのアクティブなサーバーを設定します。 Lync Server コマンドシェルで、 **CsPersistentChatActiveServer**コマンドレットを使用してアクティブなサーバーの一覧を設定します。
    
    <div>
    

    > [!IMPORTANT]  
    > すべてのアクティブ サーバーは、新しいプライマリ データベースと同じデータ センター内、またはデータベースへの接続が低待機時間/高帯域幅であるデータ センター内に配置する必要があります。

    
    </div>
    
    この時点で、常設チャットサーバーのプライマリデータベースから永続的なチャットサーバーバックアップデータベースへのフェールオーバーが正常に完了します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

