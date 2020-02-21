---
title: 'Lync Server 2013: アーカイブデータベースオプションの変更'
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
ms.openlocfilehash: a820ca891ceb8196f8b4e0d2e023799f36e9e9ca
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changing-archiving-database-options-in-lync-server-2013"></a>Lync Server 2013 でのアーカイブデータベースオプションの変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

SQL Server ストレージを使用して、ユーザーのためにアーカイブストレージ用にアーカイブを展開する場合は、次のデータベース記憶域の変更を行うことができます。

  - 別の SQL Server データベースをアーカイブストレージとして使用します。 これには、プライマリアーカイブデータベースと、SQL Server ミラーリングに使用する任意のデータベースが含まれます。

  - Exchange 2013 サーバーにアーカイブデータおよびファイルを保存するには、Microsoft Exchange 統合に切り替えます。 すべてのユーザーが Exchange 2013 サーバーに所属しており、展開内のすべてのユーザーに対して Microsoft Exchange ストレージを使用する場合は、SQL Server ストアデータベースをトポロジから削除する必要があります。

これらの変更を行うには、トポロジビルダーを実行し、変更を行ってからトポロジを再度公開する必要があります。 これを行うには、トポロジビルダーを使用します。 Exchange 2013 サーバーに所属していない Lync ユーザーがいない場合は、[ **Sql server ストアのアーカイブ**] または [ **sql server ストアミラーリングの有効化**] の情報を指定しないでください。

<div>

## <a name="to-change-your-archiving-database-option"></a>アーカイブ データベース オプションを変更するには

1.  Lync Server 2013 を実行しているコンピューター、または Lync Server 管理ツールがインストールされているコンピューターで、ローカルユーザーグループのメンバーであるアカウント (または同等のユーザー権限を持つアカウント) を使用してログオンします。
    
    <div>
    

    > [!NOTE]  
    > トポロジを定義するには、ローカルユーザーグループのメンバーであるアカウントを使用しますが、トポロジにコンポーネントを追加するために必要なトポロジを公開するには、 <STRONG>Domain Admins</STRONG>グループおよび<STRONG>RTCUniversalServerAdmins</STRONG>グループのメンバーであり、かつ、Lync Server 2013 ファイルストアに使用しているファイル共有のフルコントロールのアクセス許可 (つまり、読み取り、書き込み、および変更) を持つアカウントを使用する必要があります (つまり、トポロジビルダーが必要な随意アクセス制御リストを構成できるようにします。Dacl)、またはそれと同等の権限を持つアカウント。

    
    </div>

2.  トポロジ ビルダーを開始します。

3.  コンソール プールで、アーカイブを展開したフロントエンド プールに移動し、データベース オプションを変更するフロントエンド プールの名前をクリックします。

4.  [**操作**] メニューの [**プロパティの編集**] をクリックします。

5.  [**プロパティの編集 **] ダイアログ ボックスで、[**全般**] をクリックします。

6.  [**アーカイブ**] まで下方向にスクロールします。

7.  [**アーカイブ**] で、次の操作を実行します。
    
      - 別の既存の SQL Server ストアに変更するには、[**アーカイブ SQL Server ストア**] ドロップダウン リスト ボックスで、次の操作を実行します。
        
          - 既存の SQL Server ストアを使用するには、ドロップダウン リスト ボックスで、使用する SQL Server ストアの名前をクリックします。
        
          - 新しい SQL Server ストアを定義するには、[**新規作成**] をクリックし、[**新しい SQL Server ストアの定義**] ダイアログ ボックスで次の操作を実行します。
            
              - 既存の SQL Server ストアを使用するには、ドロップダウン リスト ボックスで、使用する SQL Server ストアの名前をクリックします。
            
              - 新しい SQL Server ストアを指定するには、[**新規**] をクリックし、[**新しい sql Server ストアの定義**] ダイアログボックスで次の操作を行います。
                
                  - [ **Sql server の fqdn**] で、新しい SQL server ストアを作成するサーバーの fqdn を指定します。
                
                  - 既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。
                
                  - 指定した SQL Server インスタンスがミラーリング関係にある場合は、[**この sql インスタンスはミラーリングの関係に**ある] チェックボックスをオンにし、[**ミラーポート番号**] でポート番号を指定します。
    
      - ミラーリング用に SQL Server ストアを追加するか、SQL Server ストア ミラーリングとして別の既存の SQL Server ストアに変更するには、[**SQL Server ストア ミラーリングを有効にする**] を選択して、以下の作業をします。
        
          - 既存の SQL Server ストアをミラーリングに使用するには、[**アーカイブ SQL server ストアミラー** ] ドロップダウンリストボックスで、ミラーリングに使用する sql server ストアの名前をクリックします。
        
          - ミラーリング用の新しい SQL Server ストアを指定するには、[**新規**] をクリックし、[**新しい sql Server ストアの定義**] ダイアログボックスで、次のいずれかの操作を行います。
            
            1.  [ **Sql server の fqdn**] で、新しい sql server ストアを作成する対象の sql SERVER の fqdn を指定します。
            
            2.  既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。
            
            3.  指定した SQL Server インスタンスがミラーリング関係にある場合は、[**この sql インスタンスはミラーリングの関係に**ある] チェックボックスをオンにし、[**ミラーポート番号**] でポート番号を指定します。
        
          - Sql Server ミラーリングを有効にし、SQL Server ミラーリング監視 (プライマリの SQL Server サーバーとミラーインスタンスの正常性を検出できる別の SQL Server インスタンス) を追加または変更する場合は、[ **sql server ミラーリング監視を使用して自動フェールオーバーを有効**にする] チェックボックスをオンにして、次のいずれかの操作を行います。
            
            1.  [ **Sql server の fqdn**] で、新しい SQL server ミラーリング監視を作成するサーバーの fqdn を指定します。
            
            2.  既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、ミラーリング監視で使用するインスタンスを指定します。
            
            3.  指定した SQL Server インスタンスがミラーリング関係にある場合は、[**この sql インスタンスはミラーリングの関係に**ある] チェックボックスをオンにし、[**ミラーポート番号**] でポート番号を指定します。
    
      - Exchange 2013 サーバーにアーカイブデータおよびファイルを格納するために Microsoft Exchange 統合に切り替えるには (展開内のすべてのユーザーが Exchange 2013 サーバーに所属している場合)、アーカイブデータベースに関するすべての情報を削除します。
    
    <div>
    

    > [!IMPORTANT]  
    > Exchange 2013 サーバーに所属していない Lync ユーザーがいる場合は、SQL Server ストアの情報を削除しないでください。

    
    </div>

8.  構成を保存するには、[**OK**] をクリックします。
    
    <div>
    

    > [!IMPORTANT]  
    > トポロジビルダーで行った変更は、新しいトポロジを公開するまで有効になりません。 詳細については、「展開」のドキュメントの「<A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">更新されたトポロジを公開して Lync Server 2013 にアーカイブデータベースを追加する</A>」を参照してください。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

