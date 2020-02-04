---
title: 'Lync Server 2013: アーカイブデータベースの Lync Server 2013 トポロジへの追加'
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
ms.openlocfilehash: 7476107b064b45dbef74b03ff9d54e02fc9eee52
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a>Lync Server 2013 トポロジへのアーカイブデータベースの追加

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-10_

アーカイブをサポートするように展開を構成する前に、トポロジにアーカイブを組み込む必要があります。 このトピックでは、トポロジビルダーを使用して既存のトポロジにアーカイブを追加する方法について説明します。

<div>


> [!NOTE]  
> Microsoft Exchange 統合を使用して、展開するすべてのユーザーの Exchange 2013 サーバーにアーカイブデータとファイルを保存する場合は、<STRONG>アーカイブ Sql server ストア</STRONG>を指定しないか、 <STRONG>sql server ストアのミラーリング</STRONG>情報を使用します。



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a>トポロジにアーカイブデータベースのサポートを追加するには

1.  Lync Server 2013 を実行しているコンピューター、または Lync Server 管理ツールがインストールされているコンピューターで、ローカルユーザーグループのメンバーであるアカウント (または同等のユーザー権限を持つアカウント) を使用してログオンします。
    
    <div>
    

    > [!NOTE]  
    > トポロジを定義するには、ローカルユーザーグループのメンバーであるアカウントを使用しますが、トポロジを公開するには、サーバーをトポロジに追加するために必要なトポロジを指定します。<STRONG>ドメイン管理者</STRONG>グループと<STRONG>RTCUniversalServerAdmins</STRONG>グループのメンバーであり、Lync server 2013 ファイルストアで使用しているファイル共有に対してフルコントロールのアクセス許可 (つまり読み取り、書き込み、変更) を持ち、そのアカウントを使用する必要があります。そのため、トポロジビルダーは、必要な随意アクセス制御リスト (dacl) を構成できます。または、同等の権限を持つアカウント。

    
    </div>

2.  トポロジビルダーを起動します。

3.  コンソールツリーで、アーカイブ展開の対象となるフロントエンドプールに移動し、アーカイブを展開するフロントエンドプールの名前をクリックします。

4.  [**操作**] メニューの [**プロパティの編集**] をクリックします。

5.  [**プロパティの編集**] ダイアログ ボックスで、[**全般**] をクリックします。

6.  [**アーカイブ**] まで下方向にスクロールします。

7.  [**アーカイブ**] チェック ボックスをオンにします。

8.  [**アーカイブ SQL Server ストア**] で、次のいずれかの操作を行います。
    
      - 既存の SQL Server ストアを使用するには、ドロップダウン リスト ボックスで、使用する SQL Server ストアの名前をクリックします。 すべてのユーザーが Microsoft Exchange Server 2013 以降を使用している場合は、Exchange のすべてのユーザーに対して Lync の通信をアーカイブすることができます。 この場合、SQL Server アーカイブストアを構成する必要はありません。
    
      - 新しい SQL Server ストアを指定するには、[**新規**作成] をクリックし、[**新しい sql Server ストアの定義**] ダイアログボックスで、次の操作を行います。
        
          - [ **Sql SERVER fqdn**] で、新しい SQL Server ストアを作成するサーバーの fqdn を指定します。
        
          - 既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。
        
          - 指定した SQL Server インスタンスがミラーリング関係にある場合は、[**この sql インスタンスがミラーリング**関係] チェックボックスをオンにし、[**ミラーポート番号**] でポート番号を指定します。

9.  SQL Server ストアのミラーリングを使用する場合は、[ **Sql Server ストアのミラーリングを有効**にする] を選択し、次の操作を行います。
    
      - ミラーリング用の既存の SQL Server ストアを使用するには、[**アーカイブ SQL server ストアミラー** ] ドロップダウンリストボックスで、ミラーリングに使用する sql server ストアの名前をクリックします。
    
      - ミラーリング用の新しい SQL Server ストアを指定するには、[**新規**作成] をクリックし、[**新しい sql Server ストアの定義**] ダイアログボックスで、次のいずれかの操作を行います。
        
        1.  [ **Sql SERVER fqdn**] で、新しい sql server ストアを作成する sql SERVER の fqdn を指定します。
        
        2.  既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、使用するインスタンスを指定します。
        
        3.  指定した SQL Server インスタンスがミラーリング関係にある場合は、[**この sql インスタンスがミラーリング**関係] チェックボックスをオンにし、[**ミラーポート番号**] でポート番号を指定します。
    
      - Sql server のミラーリングを有効にして、SQL Server ミラーリング監視 (プライマリ SQL Server サーバーの正常性を検出できる別の SQL Server インスタンス) を含める場合は、[ **Sql server ミラーリング監視を使用して自動フェールオーバーを有効に**する] チェックボックスをオンにして、次のいずれかの操作を行います。
        
        1.  [ **Sql SERVER fqdn**] で、新しい SQL server ミラーリング監視を作成するサーバーの fqdn を指定します。
        
        2.  既定のインスタンスを使用するには [**既定のインスタンス**] をクリックし、別のインスタンスを指定するには [**名前付きインスタンス**] をクリックして、ミラーリング監視で使用するインスタンスを指定します。
        
        3.  指定した SQL Server インスタンスがミラーリング関係にある場合は、[**この sql インスタンスがミラーリング**関係] チェックボックスをオンにし、[**ミラーポート番号**] でポート番号を指定します。

10. 構成を保存するには、[**OK**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

