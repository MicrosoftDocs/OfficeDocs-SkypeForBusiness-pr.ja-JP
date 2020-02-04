---
title: 'Lync Server 2013: アーカイブデータベースのオプションを変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing Archiving database options
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204814(v=OCS.15)
ms:contentKeyID: 48183879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 198e2abff6118197167f0f017ace22fc2ad76381
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-archiving-database-options-in-lync-server-2013"></a>Lync Server 2013 でアーカイブデータベースのオプションを変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

いずれかのユーザーのために SQL Server ストレージを使用してアーカイブを展開している場合は、次のデータベース記憶域を変更することができます。

  - アーカイブストレージとして別の SQL Server データベースを使用します。 これには、プライマリアーカイブデータベースと、SQL Server ミラーリングで使用するデータベースが含まれます。

  - Exchange 2013 サーバーにアーカイブデータとファイルを保存するには、Microsoft Exchange 統合に切り替えます。 すべてのユーザーが Exchange 2013 サーバーを使用していて、展開内のすべてのユーザーに対して Microsoft Exchange ストレージを使用する場合は、SQL Server ストアデータベースをトポロジから削除する必要があります。

これらの変更を行うには、トポロジビルダーを実行し、変更を行ってから、トポロジをもう一度公開する必要があります。 トポロジービルダーを使用して、この操作を行うことができます。 Exchange 2013 サーバーを使っていない Lync ユーザーがいる場合を除き、**アーカイブ Sql server ストア**または**sql server ストアのミラーリング**情報を有効にしないようにします。

<div>

## <a name="to-change-your-archiving-database-option"></a>[アーカイブデータベース] オプションを変更するには

1.  Lync Server 2013 を実行しているコンピューター、または Lync Server 管理ツールがインストールされているコンピューターで、ローカルユーザーグループのメンバーであるアカウント (または同等のユーザー権限を持つアカウント) を使用してログオンします。
    
    <div>
    

    > [!NOTE]  
    > トポロジを定義するには、[ローカルユーザー] グループのメンバーであるアカウントを使用します。ただし、トポロジを公開するには、トポロジにコンポーネントを追加するために必要なトポロジを指定します。<STRONG>ドメイン管理者</STRONG>グループと<STRONG>RTCUniversalServerAdmins</STRONG>グループのメンバーであり、Lync Server 2013 ファイルストアで使用しているファイル共有に対してフルコントロールのアクセス許可 (つまり、読み取り、書き込み、変更) を持つアカウントを使用する必要があります (つまり、トポロジビルダーは必要な随意アクセス制御リストを構成できます。Dacl)、または同等の権限を持つアカウント。

    
    </div>

2.  トポロジビルダーを起動します。

3.  コンソール プールで、アーカイブを展開したフロントエンド プールに移動し、データベース オプションを変更するフロントエンド プールの名前をクリックします。

4.  [**アクション**] メニューの [**プロパティの編集**] をクリックします。

5.  [**プロパティの編集**] ダイアログ ボックスで、[**全般**] をクリックします。

6.  [**アーカイブ**] まで下方向にスクロールします。

7.  [**アーカイブ**] で、次の操作を実行します。
    
      - 別の既存の SQL Server ストアに変更するには、[**SQL Server ストアのアーカイブ**] ドロップダウン リスト ボックスで、次の操作を実行します。
        
          - 既存の SQL Server ストアを使用するには、ドロップダウン リスト ボックスで、使用する SQL Server ストアの名前をクリックします。
        
          - 新しい SQL Server ストアを定義するには、[**新規**] をクリックし、[**新しい SQL Server ストアの定義**] ダイアログ ボックスで次の操作を実行します。
            
              - 既存の SQL Server ストアを使用するには、ドロップダウン リスト ボックスで、使用する SQL Server ストアの名前をクリックします。
            
              - 新しい SQL Server ストアを指定するには、[**新規**作成] をクリックし、[**新しい sql Server ストアの定義**] ダイアログボックスで、次の操作を行います。
                
                  - [ **Sql SERVER fqdn**] で、新しい SQL Server ストアを作成するサーバーの fqdn を指定します。
                
                  - 既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。
                
                  - 指定した SQL Server インスタンスがミラーリング関係にある場合は、[**この sql インスタンスがミラーリング**関係] チェックボックスをオンにし、[**ミラーポート番号**] でポート番号を指定します。
    
      - ミラーリング用に SQL Server ストアを追加するか、SQL Server ストア ミラーリングとして別の既存の SQL Server ストアに変更するには、[**SQL Server ストア ミラーリングの有効化**] を選択して、以下の操作を実行します。
        
          - ミラーリング用の既存の SQL Server ストアを使用するには、[**アーカイブ SQL server ストアミラー** ] ドロップダウンリストボックスで、ミラーリングに使用する sql server ストアの名前をクリックします。
        
          - ミラーリング用の新しい SQL Server ストアを指定するには、[**新規**作成] をクリックし、[**新しい sql Server ストアの定義**] ダイアログボックスで、次のいずれかの操作を行います。
            
            1.  [ **Sql SERVER fqdn**] で、新しい sql server ストアを作成する sql SERVER の fqdn を指定します。
            
            2.  既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。
            
            3.  指定した SQL Server インスタンスがミラーリング関係にある場合は、[**この sql インスタンスがミラーリング**関係] チェックボックスをオンにし、[**ミラーポート番号**] でポート番号を指定します。
        
          - Sql server のミラーリングを有効にし、SQL Server ミラーリング監視 (プライマリ SQL Server サーバーの正常性を検出できる別の SQL Server インスタンス) を追加または変更する場合は、[ **Sql server ミラーリング監視を使用して自動フェールオーバーを有効**にする] チェックボックスをオンにして、次のいずれかの操作を行います。
            
            1.  [ **Sql SERVER fqdn**] で、新しい SQL server ミラーリング監視を作成するサーバーの fqdn を指定します。
            
            2.  既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、ミラーリング監視で使用するインスタンスを指定します。
            
            3.  指定した SQL Server インスタンスがミラーリング関係にある場合は、[**この sql インスタンスがミラーリング**関係] チェックボックスをオンにし、[**ミラーポート番号**] でポート番号を指定します。
    
      - Exchange 2013 サーバーにアーカイブデータとファイルを保存するために Microsoft Exchange の統合に切り替えるには (展開のすべてのユーザーが Exchange 2013 サーバーに所属している場合)、アーカイブデータベースのすべての情報を削除します。
    
    <div>
    

    > [!IMPORTANT]  
    > Exchange 2013 サーバーを使っていない Lync ユーザーがいる場合は、SQL Server ストアの情報を削除しないでください。

    
    </div>

8.  構成を保存するには、[**OK**] をクリックします。
    
    <div>
    

    > [!IMPORTANT]  
    > トポロジビルダーで行った変更は、新しいトポロジを公開するまで有効になりません。 詳細については、「更新されたトポロジを公開して、展開ドキュメントの<A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Lync Server 2013 でアーカイブデータベースを追加する」を</A>参照してください。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

