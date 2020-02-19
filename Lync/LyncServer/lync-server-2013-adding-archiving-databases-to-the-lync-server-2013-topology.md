---
title: 'Lync Server 2013: Lync Server 2013 トポロジへのアーカイブデータベースの追加'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding Archiving databases to the Lync Server 2013 topology
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204654(v=OCS.15)
ms:contentKeyID: 48183338
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8bed8e9fa8b15bd4e9e7fb1f72b102ed223edd9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a>Lync Server 2013 トポロジへのアーカイブデータベースの追加

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-10_

アーカイブをサポートするために展開を構成する前に、トポロジにアーカイブを組み込む必要があります。 このトピックの情報では、トポロジビルダーを使用して既存のトポロジにアーカイブを追加する方法について説明します。

<div>


> [!NOTE]  
> Microsoft Exchange 統合を使用して、展開内のすべてのユーザーの Exchange 2013 サーバーにアーカイブデータとファイルを保存する場合は、<STRONG>アーカイブ Sql server ストア</STRONG>を指定しないか、 <STRONG>sql server ストアミラーリング</STRONG>情報を使用してください。



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a>トポロジにアーカイブデータベースのサポートを追加するには

1.  Lync Server 2013 を実行しているコンピューター、または Lync Server 管理ツールがインストールされているコンピューターで、ローカルユーザーグループのメンバーであるアカウント (または同等のユーザー権限を持つアカウント) を使用してログオンします。
    
    <div>
    

    > [!NOTE]  
    > トポロジを定義するには、ローカルユーザーグループのメンバーであるアカウントを使用しますが、トポロジを公開するには、サーバーをトポロジに追加する必要があります。 <STRONG>Domain Admins</STRONG>グループおよび<STRONG>RTCUniversalServerAdmins</STRONG>グループのメンバーであり、かつ、Lync server 2013 ファイルストアに使用しているファイル共有のフルコントロールのアクセス許可 (つまり、読み取り、書き込み、および変更) を持つアカウントを使用する必要があります (つまり、トポロジビルダーが必要な随意アクセス制御リスト (dacl) を構成できるようにする必要があります。、またはそれと同等の権限を持つアカウント。

    
    </div>

2.  トポロジ ビルダーを開始します。

3.  コンソールツリーで、アーカイブを展開するフロントエンドプールに移動してから、アーカイブを展開するフロントエンドプールの名前をクリックします。

4.  [**操作**] メニューの [**プロパティの編集**] をクリックします。

5.  [**プロパティの編集 **] ダイアログ ボックスで、[**全般**] をクリックします。

6.  [**アーカイブ**] まで下方向にスクロールします。

7.  [**アーカイブ**] チェックボックスをオンにします。

8.  [**アーカイブ SQL Server ストア**] で、次のいずれかの手順を実行します。
    
      - 既存の SQL Server ストアを使用するには、ドロップダウン リスト ボックスで、使用する SQL Server ストアの名前をクリックします。 すべてのユーザーが Microsoft Exchange Server 2013 以降に所属している場合は、Exchange のすべてのユーザーの Lync communications をアーカイブすることができます。 この場合、SQL Server アーカイブストアを構成する必要はありません。
    
      - 新しい SQL Server ストアを指定するには、[**新規**] をクリックし、[**新しい sql Server ストアの定義**] ダイアログボックスで次の操作を行います。
        
          - [ **Sql server の fqdn**] で、新しい SQL server ストアを作成するサーバーの fqdn を指定します。
        
          - 既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。
        
          - 指定した SQL Server インスタンスがミラーリング関係にある場合は、[**この sql インスタンスはミラーリングの関係に**ある] チェックボックスをオンにし、[**ミラーポート番号**] でポート番号を指定します。

9.  SQL Server ストアミラーリングを使用する場合は、[ **Sql Server ストアミラーリングの有効化**] を選択し、次の操作を行います。
    
      - 既存の SQL Server ストアをミラーリングに使用するには、[**アーカイブ SQL server ストアミラー** ] ドロップダウンリストボックスで、ミラーリングに使用する sql server ストアの名前をクリックします。
    
      - ミラーリング用の新しい SQL Server ストアを指定するには、[**新規**] をクリックし、[**新しい sql Server ストアの定義**] ダイアログボックスで、次のいずれかの操作を行います。
        
        1.  [ **Sql server の fqdn**] で、新しい sql server ストアを作成する対象の sql SERVER の fqdn を指定します。
        
        2.  既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。
        
        3.  指定した SQL Server インスタンスがミラーリング関係にある場合は、[**この sql インスタンスはミラーリングの関係に**ある] チェックボックスをオンにし、[**ミラーポート番号**] でポート番号を指定します。
    
      - Sql Server のミラーリングを有効にし、SQL Server ミラーリング監視 (プライマリの SQL Server サーバーとミラーインスタンスの正常性を検出できる3つの独立した SQL Server インスタンス) を含める場合は、[ **Sql server ミラーリング監視を使用して自動フェールオーバーを有効**にする] チェックボックスをオンにして、次のいずれかの操作を行います。
        
        1.  [ **Sql server の fqdn**] で、新しい SQL server ミラーリング監視を作成するサーバーの fqdn を指定します。
        
        2.  既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、ミラーリング監視で使用するインスタンスを指定します。
        
        3.  指定した SQL Server インスタンスがミラーリング関係にある場合は、[**この sql インスタンスはミラーリングの関係に**ある] チェックボックスをオンにし、[**ミラーポート番号**] でポート番号を指定します。

10. 構成を保存するには、[**OK**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

