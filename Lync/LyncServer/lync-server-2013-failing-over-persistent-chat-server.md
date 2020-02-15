---
title: 'Lync Server 2013: 常設チャットサーバーのフェールオーバー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over Persistent Chat Server
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204772(v=OCS.15)
ms:contentKeyID: 48183726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0d5ac758c1e4c87fd5559da1c2a9cf388dc8834
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 での常設チャットサーバーのフェールオーバー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-02-05_

常設チャットサーバーのフェールオーバーは、主に手動プロセスとして設計されています。

フェールオーバーの手順は、セカンダリデータセンターが稼働していることを前提としていますが、プライマリ常設チャットデータベースが配置されている常設チャットサーバーサービスは完全には使用できません (次のようなものがあります)。

  - 常設チャットサーバーのプライマリデータベースと常設チャットサーバーのミラーデータベースがダウンしています。

  - Lync Server フロントエンドサーバーがダウンしています。

操作は 2 つの基本手順に基づいて行われます。

  - プライマリ常設チャットデータベース (mgc) を復元します。

  - 新しいプライマリ データベースのミラーリングを確立する。

常設チャットコンプライアンスデータベース (メンバー) がフェールオーバーしていません。 このデータベースの内容は一時的なものであり、コンプライアンス アダプターがデータを処理するときに削除されます。 データ損失を防ぐためにアダプター出力を適切に管理するには、常設チャット管理者としての責任があります。

<div>

## <a name="to-fail-over-persistent-chat-server"></a>常設チャットサーバーをフェールオーバーするには

1.  常設チャットサーバーのバックアップログ配布データベースからログ配布を削除します。
    
    1.  SQL Server Management Studio を使用して、常設チャットサーバーバックアップ mgc データベースが配置されているデータベースインスタンスに接続します。
    
    2.  マスター データベースに対するクエリ ウィンドウを開きます。
    
    3.  次のコマンドを使用して、ログ配布を削除します。
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  バックアップ共有から、バックアップ サーバーのコピー先フォルダーへ、コピーしていないバックアップ ファイルをコピーします。

3.  セカンダリ データベースに、適用していないトランザクション ログ バックアップを順番に適用します。 詳細については、「方法: トランザクションログバックアップを適用する (Transact-sql)」をhttp://go.microsoft.com/fwlink/p/?linkid=247428参照してください。

4.  バックアップ mgc データベースをオンラインにします。手順 1b. で開いたクエリ ウィンドウを使用して、次の手順を実行します。
    
    1.  mgc データベースへのすべての接続を終了します (接続がある場合)。
        
        1.  mgc データベースへの接続を識別するために、 **exec sp\_who2** 。
        
        2.  ** \<spid\>を切断**してこれらの接続を終了します。
    
    2.  データベースをオンラインにします。
        
        1.  **restore database mgc with recovery**。

5.  Lync Server 管理シェルで、コマンド**set-cspersistentchatstate-Identity "service: 001.litwareinc.com" – PoolState FailedOver**を使用して、mgc バックアップデータベースにフェールオーバーします。 Atl-cs-001.litwareinc.com の常設チャットプールの完全修飾ドメイン名に置き換えてください。
    
    mgc バックアップ データベースがプライマリ データベースとして動作するようになります。

6.  Lync Server 管理シェルで、 **install-csmirrordatabase**コマンドレットを使用して、プライマリデータベースとして機能するバックアップデータベースの高可用性ミラーを確立します。 バックアップ データベース インスタンスをプライマリ データベースとして使用し、バックアップ ミラー データベース インスタンスをミラー インスタンスとして使用します。 これは、セットアップ時にプライマリ データベースに対して最初に構成したミラーと同じものではありません。 詳細については、「 [Lync server 2013 でバックエンドサーバーの高可用性を実現するための SQL ミラーリングを展開](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)する」の「Lync Server 管理シェルコマンドレットを使用する」を参照してください。

7.  常設チャットサーバーのアクティブなサーバーを設定します。 Lync Server コマンドシェルから、 **set-cspersistentchatactiveserver**コマンドレットを使用してアクティブなサーバーの一覧を設定します。
    
    <div>
    

    > [!IMPORTANT]  
    > すべてのアクティブ サーバーが新しいプライマリ データベースと同じデータ センター内に置かれているか、このデータベースへの接続が低待機時間/高帯域幅であるデータセンター内に置かれている必要があります。

    
    </div>
    
    この時点で、常設チャットサーバーのプライマリデータベースから常設チャットサーバーのバックアップデータベースへのフェールオーバーは正常に完了します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

