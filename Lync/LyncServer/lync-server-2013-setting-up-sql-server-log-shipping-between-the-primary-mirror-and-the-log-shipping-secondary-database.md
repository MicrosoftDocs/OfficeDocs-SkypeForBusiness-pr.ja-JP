---
title: 'Lync Server 2013: プライマリ ミラーとログ配布セカンダリ データベース間での SQL Server ログ配布のセットアップ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database
ms:assetid: 4e8e9ce9-4301-47f2-a0c3-669afeb53295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204887(v=OCS.15)
ms:contentKeyID: 48184119
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3758e654826de42f6bf6bed8ead29ce03adb6ca5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database-in-lync-server-2013"></a>Lync Server 2013 でのプライマリ ミラーとログ配布セカンダリ データベース間での SQL Server ログ配布のセットアップ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-21_

プライマリ常設チャットデータベースがミラーデータベースにフェールオーバーされた場合は、次の手順に従ってログの配布を続行します。

1.  プライマリ永続的チャットデータベースをミラーに手動でフェールオーバーします。 これを行うには、Lync Server 管理シェルと**Invoke-CsDatabaseFailover**コマンドレットを使用します。 詳細については、「 [lync server 2013 でバックエンドサーバーの高可用性を実現するために SQL ミラーリングを展開](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)する」の「Lync Server 管理シェルコマンドレットの使用」を参照してください。

2.  SQL Server Management Studio を使用して、プライマリ常設チャットサーバーのミラーインスタンスに接続します。

3.  SQL Server エージェントが実行されていることを確認します。

4.  mgc データベースを右クリックし、[**プロパティ**] をクリックします。

5.  [**ページの選択**] で、[**トランザクション ログの配布**] をクリックします。

6.  [**ログ配布構成のプライマリ データベースとして有効にする**] チェック ボックスをオンにします。

7.  [**トランザクション ログのバックアップ**] で、[**バックアップの設定**] をクリックします。

8.  [**バックアップ フォルダーのネットワーク パスを指定する**] ボックスに、トランザクション ログのバックアップ フォルダーとして作成した共有場所へのネットワーク パスを入力します。

9.  バックアップ フォルダーがプライマリ サーバーに存在する場合は、[**バックアップ フォルダーがプライマリ サーバーに存在する場合は、バックアップ フォルダーのローカル パスを入力**] ボックスにバックアップ フォルダーのローカル パスを入力します (バックアップ フォルダーがプライマリ サーバーに存在しない場合は、このボックスを空のままにします)。
    
    <div>
    

    > [!IMPORTANT]  
    > プライマリサーバーの SQL Server サービスアカウントがローカルシステムアカウントで実行されている場合は、プライマリサーバー上にバックアップフォルダーを作成し、そのフォルダーへのローカルパスを指定する必要があります。

    
    </div>

10. [**次の期間を経過したファイルを削除する**] パラメーターと [**バックアップが次の期間内に行われない場合は警告する**] パラメーターを構成します。

11. [**バックアップ ジョブ**] の [**スケジュール**] ボックスに一覧表示されるバックアップ スケジュールを確認してください。 インストールのスケジュールをカスタマイズするには、[**スケジュール**] をクリックし、必要に応じて SQL Server エージェントのスケジュールを調整します。
    
    <div>
    

    > [!IMPORTANT]  
    > プライマリ データベースと同じ設定を使用します。

    
    </div>

12. [**圧縮**] で、[**既定のサーバー設定を使用する**] をクリックし、[**OK**] をクリックします。

13. [**セカンダリ サーバー インスタンスとデータベース**] で、[**追加**] をクリックします。

14. [**接続**] をクリックして、セカンダリ サーバーとして構成した SQL Server のインスタンスに接続します。

15. [**セカンダリ データベース**] ボックスで、一覧から [**mgc**] データベースを選択します。

16. [**セカンダリ データベースの初期化**] タブで、[**いいえ、セカンダリ データベースは初期化されています**] オプションをクリックします。

17. [**ファイルのコピー**] タブの [**ファイルのコピー先フォルダー**] に、トランザクション ログのバックアップをコピーするフォルダーのパスを入力して、[**OK**] をクリックします。多くの場合、このフォルダーは、セカンダリ サーバー上にあります。

18. [**スクリプトの構成**] ボックスの一覧を開き、[**スクリプト構成を新規クエリ ウィンドウに保存**] をクリックします。

19. [**データベースのプロパティ**] に表示された新規クエリ ウィンドウで [**OK**] をクリックして、構成プロセスを開始します。

20. クエリの最初の半分 (手順18を参照) を選んで実行します。--- \* \* \* \* \* \* --------- \* \* \* \* \* \*---------------------------
    
    <div>
    

    > [!IMPORTANT]  
    > Sql Server Management Studio では、SQL Server のログ配布構成で複数のプライマリデータベースがサポートされていないため、このスクリプトを手動で実行する必要があります。

    
    </div>

21. [**キャンセル**] をクリックして、ログ配布構成パネルを閉じ、プライマリ データベースとミラー化されたデータベース (フェールオーバー時) の両方でログ ファイルの配布を適切に実装する実用的なセットアップを確立します。 

22. プライマリ常設チャットデータベースを手動でプライマリにフェールバックします。 この操作を行うには、Lync Server 管理シェルと、または「 **CsDatabaseFailover** 」コマンドレットを使用します。 詳細については、「 [lync server 2013 でバックエンドサーバーの高可用性を実現するために SQL ミラーリングを展開](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)する」の「Lync Server 管理シェルコマンドレットの使用」を参照してください。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのバックエンド サーバーの高可用性を実現するための SQL ミラーリングの展開](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
[Lync Server 2013 でのバックエンド サーバーの高可用性を実現するための SQL ミラーリングの展開](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

