---
title: 'Lync Server 2013: 常設チャット サーバーのフェールバック'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back Persistent Chat Server
ms:assetid: 67b91de4-6ddc-43e6-9812-5e1aa84a7980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204970(v=OCS.15)
ms:contentKeyID: 48184396
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d79c25d153de81906fcaf9355a543d31cb8fe0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 常設チャット サーバーのフェールバック

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-02-05_

この手順では、常設チャットサーバーの障害から回復するために必要な手順と、プライマリデータセンターからの操作を再確立するために必要な手順について説明します。

常設チャットサーバーの障害時に、プライマリデータセンターには完全な停止が発生し、プライマリデータベースとミラーデータベースは利用できなくなります。 プライマリ データ センターはバックアップ サーバーにフェールオーバーします。

以下の手順では、プライマリ データ センターがバックアップされ、サーバーが再構築された後、通常の動作を回復します。 この手順では、プライマリデータセンターが全体の停止から回復され、トポロジビルダーを使用して行うデータベースと、使い方が再構築されていることを前提としています。

この手順では、フェイルオーバー期間中に新しいミラーサーバーとバックアップサーバーが展開されていないこと、および、展開されている唯一のサーバーが、 [Lync server 2013 での常設チャットサーバーのフェイルオーバー](lync-server-2013-failing-over-persistent-chat-server.md)によって定義されたものであることを前提としています。

この手順の意図は、プライマリ サーバーからバックアップ サーバーへのフェールオーバーの原因となった障害が発生する前の状態に構成を復旧することにあります。

<div>

## <a name="to-fail-back-persistent-chat-server"></a>常設チャットサーバーをフェイルバックするには

1.  Lync Server 管理シェルの`Set-CsPersistentChatActiveServer`コマンドレットを使用して、常設チャットサーバーの Active Server リストからすべてのサーバーをクリアします。 これにより、すべての常設チャットサーバーが、フェイルバック中に行うデータベースとデータベースに接続できなくなります。
    
    <div>
    

    > [!IMPORTANT]  
    > セカンダリ常設チャットサーバーのバックエンドサーバー上の SQL Server エージェントは、特権を持つアカウントで実行されている必要があります。 このアカウントには、次のアクセス許可が与えられている必要があります。 
    > <UL>
    > <LI>
    > <P>バックアップが置かれるネットワーク共有に対する読み取りアクセス</P>
    > <LI>
    > <P>バックアップのコピー先となるローカル ディレクトリに対する書き込みアクセス</P></LI></UL>

    
    </div>

2.  バックアップ mgc データベースでのミラーリングを無効にします。
    
    1.  SQL Server Management Studio を使用して、backup 行うインスタンスに接続します。
    
    2.  mgc データベースを右クリックし、[**タスク**] をポイントしてから、[**ミラー**] をクリックします。
    
    3.  [**ミラーリングの削除**] をクリックします。
    
    4.  [**OK**] をクリックします。
    
    5.  mgccomp データベースに対しても同じ手順を実行します。

3.  mgc データベースをバックアップして、新しいプライマリ データベースに復元できるようにします。
    
    1.  SQL Server Management Studio を使用して、backup 行うインスタンスに接続します。
    
    2.  mgc データベースを右クリックし、[**タスク**] をポイントしてから、[**バックアップ**] をクリックします。[**データベースのバックアップ**] ダイアログ ボックスが表示されます。
    
    3.  [**バックアップの種類**] で、[**完全**] を選択します。
    
    4.  [**バックアップ コンポーネント**] として、[**データベース**] をクリックします。
    
    5.  [**名前**] に表示される既定のバックアップ セット名をそのまま使用するか、バックアップ セット名として別の名前を入力します。
    
    6.  * \<オプション\> *[**説明**] にバックアップセットの説明を入力します。
    
    7.  バックアップ先の一覧から既定のバックアップ場所を削除します。
    
    8.  ログ配布用に設定した共有の場所へのパスを使用して、この一覧にファイルを追加します。このパスはプライマリ データベースとバックアップ データベースの両方に使用できます。
    
    9.  [**OK**] をクリックします。ダイアログ ボックスが閉じられ、バックアップ プロセスが開始されます。

4.  上記のステップで作成されたバックアップ データベースを使用して、プライマリ データベースを復元します。
    
    1.  SQL Server Management Studio を使用して、プライマリ行うインスタンスに接続します。
    
    2.  mgc データベースを右クリックし、[**タスク**]、[**復元**] の順にポイントしてから、[**データベース**] をクリックします。[**データベースの復元**] ダイアログ ボックスが表示されます。
    
    3.  [**復元元デバイス**] を選択します。
    
    4.  [参照] ボタンをクリックします。[**バックアップの指定**] ダイアログ ボックスが表示されます。[**バックアップ メディア**] で、[**ファイル**] を選択します。[**追加**] をクリックし、ステップ 3 で作成したバックアップ ファイルを選択し、[**OK**] をクリックします。
    
    5.  [**復元するバックアップ セットの選択**] で、バックアップを選択します。
    
    6.  [**ページの選択**] ウィンドウで、[**オプション**] をクリックします。
    
    7.  [**復元オプション**] で、[**既存のデータベースを上書きする**] を選択します。
    
    8.  [**復旧状態**] で、[**データベースを使用可能な状態にする**] を選択します。
    
    9.  [**OK**] をクリックします。復元プロセスが開始されます。

5.  プライマリデータベースの SQL Server ログの配布を構成します。 「 [Lync server 2013 で高可用性と障害復旧のために常設チャットサーバーを構成](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)する」の手順に従って、プライマリ行うデータベースのログの配布を確立します。

6.  常設チャットサーバーのアクティブなサーバーを設定します。 Lync Server 管理シェルで、 **CsPersistentChatActiveServer**コマンドレットを使用してアクティブなサーバーの一覧を設定します。
    
    <div>
    

    > [!IMPORTANT]  
    > すべてのアクティブ サーバーは、新しいプライマリ データベースと同じデータ センター内、またはデータベースへの接続が低待機時間/高帯域幅であるデータ センター内に配置する必要があります。

    
    </div>

プールを通常の状態に復元します。次の Windows PowerShell コマンドを実行します。

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

詳細については、 [CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState)コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

