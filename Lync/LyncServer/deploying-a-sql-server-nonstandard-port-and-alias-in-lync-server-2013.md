---
title: Lync Server 2013 で SQL Server の非標準ポートおよびエイリアスを展開する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a SQL Server nonstandard port and alias in Lync Server 2013
ms:assetid: 2da92c1f-250e-407a-8651-fb2aec76aeb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn776290(v=OCS.15)
ms:contentKeyID: 62634609
ms.date: 09/17/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fffa3502b04a9d05387cd94e157ed183e1fe32ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a>Lync Server 2013 で SQL Server の非標準ポートおよびエイリアスを展開する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2015-09-16_

Microsoft Lync Server 2013 は、SQL Server で標準以外のポートとエイリアスを使用することをサポートしています。 SQL Server の標準以外のポートとエイリアスを使用すると、セキュリティが強化され、Lync の展開により柔軟な環境が作成されます。 以下の手順は、Lync Server 2013 環境を適切にセキュリティで保護する手順の1つにすぎません。 Lync Server 2013 の実装で攻撃を受ける可能性を減らすために、追加の手順を実行する必要があります。

次の記事では、Lync Server 2013 で SQL Server 標準以外のポートとエイリアスを設定するために必要な手順について説明します。

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a>Lync Server 2013 で SQL Server 標準以外のポートと別名を展開する

Lync Server 2013 トポロジビルダーは、Lync Server 2013 を構成するときに、実際の SQL Server FQDN ではなく、完全修飾ドメイン名 (FQDN) として SQL Server のエイリアスを使用することをサポートしています。 これにより、実際の SQL Server FQDN を悪意のある攻撃者から非表示にすることができます。 また、次の図に示すように、標準ポート以外のポートを使用すると、攻撃者が標準ポート1433でデータベースを攻撃しようとしている場合に、そのポートの実際のポートが不明瞭になります。

![ハッカーには、攻撃するポート番号がわかりません。](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "ハッカーには、攻撃するポート番号がわかりません。")

Lync Server 2013 が SQL Server と通信するために使用しているポートを正しく判断するために、攻撃者はすべてのポートをスキャンしてポート情報を取得する必要があります。 攻撃者によるポートスキャンにより、セキュリティが命令を検出して停止する可能性が高まります。 SQL Server の別名を使って、標準以外のポートで強化されたセキュリティを追加することに加えて、展開の柔軟性を高めることもできます。 これは、SQL Server 名の変更が必要な状況で構成の変更を削減するために役立ちます。

<div>


> [!NOTE]  
> SQL Server には、2つのフォールトトレランスメソッド (フェールオーバークラスタリングとミラーリング) が用意されています。 Sql Server のフォールトトレランスメソッドは、いずれも SQL Server の標準以外のポートと、Lync Server 2013 でエイリアスを使用してサポートされています。 プールで使用される SQL Server バックエンドがミラー化された構成にある場合、SQL Server バックエンドサーバー上の SQL browser サービスが実行されていて、データベースがミラーリングされた SQL にフェールオーバーしたときに、ミラーデータベースに接続する必要があります。Server.



</div>

トポロジビルダー内から SQL Server データベースの接続を構成している場合、または、CsDatabase コマンドレットを使用している場合、SQL Server 標準以外のポート番号を明示的に定義して SQL インスタンスに関連付けることはできません。 標準以外のポートを設定するには、SQL Server および Windows Server ユーティリティを使用する必要があります。

Lync Server 2013 で使用するために SQL Server の標準以外のポートとエイリアスを設定するには、3つの主要な手順を実行する必要があります。 手順は次のとおりです。

  - Lync Server 2013 に最新の更新プログラムが適用されていることを確認します。

  - SQL Server の標準以外のポートと別名を設定します。

  - "トポロジビルダー" を使用して、SQL Server の別名で Lync Server 2013 を構成します。

  - トポロジを公開し、データベースを確認します。

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a>Lync Server 2013 に最新の更新プログラムが適用されていることを確認する

Lync Server 2013 を最新の状態に維持することが重要です。 最新の更新プログラムとその適用方法に関する情報を確認するには、「 [Lync Server 2013 の更新プログラム](http://support.microsoft.com/kb/2809243)」を参照してください。

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a>SQL Server の標準以外のポートと別名を設定する

Lync Server 2013 トポロジビルダーから参照できるようにするには、データベースインスタンスで SQL Server 以外の標準ポートと別名を設定する必要があります。 SQL Server の標準以外のポートと別名を設定するには、3つの主な手順を実行する必要があります。 手順は次のとおりです。

  - 既定の TCP/IP プロトコルの値を変更します。

  - SQL Server のエイリアスを作成して構成します。

  - ドメインネームシステム (DNS) の正規名 (CNAME) リソースレコードを作成します。

**既定の TCP/IP プロトコルの値を変更する**

1.  次の図に示すように、[**開始**] を選択し、[ **SQL Server 構成マネージャー**] を選択します。
    
    ![SQL Server Management Studio アイコン](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "SQL Server Management Studio アイコン")

2.  次の図に示すように、ナビゲーションウィンドウで、 **sql server インスタンス**を展開し、[ **sql server ネットワーク構成**] を展開して、[**インスタンス\<名\>のプロトコル**] を選びます。
    
    ![TCP/IP プロパティへの移動](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "TCP/IP プロパティへの移動")

3.  右側のウィンドウで、[ **tcp/ip**] を右クリックし、[**プロパティ**] を選択します。 [TCP/IP のプロパティ] ダイアログボックスが表示されます。

4.  [ **IP アドレス**] タブを選択します。[IP アドレス] タブには、サーバー上のすべてのアクティブ IP アドレスが表示されます。 これらは、次の図に示すように、IP1、IP2、および IPAll の形式になっています。
    
    ![TCP/IP プロパティを開く](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "TCP/IP プロパティを開く")

5.  すべての IP アドレスの [ **TCP 動的ポート**] フィールドをオフにします。 フィールドにゼロの文字が含まれている場合は、SQL Server が動的なポートをリッスンしていることを意味します。 これらのフィールドが消去され、ゼロが含まれていないことを確認します。

6.  Lync Server でデータベースへの接続に使用する IP アドレスについては、次の図に示すように、[**有効** **] が [はい**] に設定されていることを確認します。
    
    ![適切な IP に [Yes] を設定して有効にします。](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "適切な IP に [Yes] を設定して有効にします。")

7.  ダイアログボックスの下部にある [ **Ipall** ] セクションで、次の図に示すように、[ **TCP port** ] フィールドに必要なポートを入力します。 この例では、ポート50062を使用していますが、49152と65535の間の任意のポートを使うことができます。 これらのポートは動的使用とプライベート機能に割り当てられているため、Lync Server 2013 の展開で使用されている他のポートと競合しないようにします。
    
    ![IPAll セクションでポートを設定します。](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "IPAll セクションでポートを設定します。")

8.  [ **OK]** を選択して、[Tcp/ip のプロパティ] ダイアログボックスを閉じます。

9.  Sql server 構成マネージャーの左側のウィンドウで sql **Server サービス**を選択して、sql server インスタンスを再起動します。 次に、次の図に示すように、右側のウィンドウで [ **SQL Server \<インスタンス\>名**] を右クリックし、[**再起動**] を選択します。
    
    ![インスタンス用の SQL Server サービスをリセットする。](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "インスタンス用の SQL Server サービスをリセットする。")

<div>


> [!IMPORTANT]  
> 新しい SQL Server ポートに対応するように、ファイアウォールの設定が更新されていることを確認してください。



</div>

**SQL Server の別名を作成および構成する**

1.  次の図に示すように、[**開始**] を選択し、[ **SQL Server 構成マネージャー**] を選択します。
    
    ![SQL Server Management Studio アイコン](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "SQL Server Management Studio アイコン")

2.  左側のウィンドウで [ **Sql Server インスタンス**] を展開し、[ **sql Native Client \<\> version Configuration**] を展開して、次の図に示すように [**エイリアス**] を選びます。
    
    ![SQL Server 構成マネージャーのエイリアス。](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "SQL Server 構成マネージャーのエイリアス。")

3.  [**エイリアス**] を右クリックし、[**新しいエイリアス**] を選択します。

4.  次の図に示すように、**エイリアス名**、**ポート番号**、**プロトコル**、**サーバー**を入力します。
    
    ![新しいエイリアスを作成する](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "新しいエイリアスを作成する")
    
    <div>
    

    > [!CAUTION]  
    > SQL Server がリッスンするポートであるため、前の手順で使ったものと同じ標準以外のポートを入力してください。 構成されたエイリアスが間違った SQL Server FQDN またはインスタンスに接続している場合は、関連付けられたネットワークプロトコルを無効にしてから再度有効にします。 この操作を実行すると、キャッシュされた接続情報がクリアされ、クライアントが正常に接続できるようになります。

    
    </div>

**DNS CNAME リソースレコードを作成する**

1.  DNS を管理するコンピューターにサインインします。

2.  [**スタート**] を選択し、次の図に示すように [**サーバーマネージャー**] を選択します。
    
    ![サーバーマネージャーを開く](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "サーバーマネージャーを開く")

3.  次の図に示すように、[**ツール**] ドロップダウンを選び、[ **DNS**] を選びます。
    
    ![サーバーマネージャーから DNS を開いています。](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "サーバーマネージャーから DNS を開いています。")

4.  左側のウィンドウで、[サーバー名] ノードを展開し、[前方参照ゾーン] ノードを展開して、関連するドメインを選びます。

5.  次の図に示すように、ドメインを右クリックし、[**新しいエイリアス (CNAME)**] を選びます。
    
    ![新しいエイリアスを作成するためのオプションの選択](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "新しいエイリアスを作成するためのオプションの選択")

6.  次の図に示すように、**エイリアス名**と**SQL Server の FQDN**を入力します。
    
    ![[New alias CNAME] ダイアログボックスに入力します。](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "[New alias CNAME] ダイアログボックスに入力します。")

7.  **[OK]** を選択して CNAME を保存し、DNS マネージャーで表示します。

</div>

<div>

## <a name="validate-database-connectivity"></a>データベース接続を検証する

機能しているかどうかを確認するには、さまざまな方法があります。 エイリアスを使用して、指定したポートで SQL Server データベースがリッスンしていることを確認します。 **Netstat**コマンドと**telnet**コマンドを使用して、クイックチェックを完了することができます。

<div>


> [!NOTE]  
> Telnet クライアントは Windows Server に付属しているが、インストールが必要な機能です。 Windows Server の機能をインストールするには、サーバーマネージャーを開き、[管理] メニューの [役割と機能の追加] を選択します。



</div>

**Netstat と telnet を使ってデータベース接続を確認する**

1.  [**スタート**] を選択し、「 **cmd** 」と入力してコマンドプロンプトを開きます。

2.  次の図に示すように、「 **netstat-a-f**」と入力し、SQL Server が正しいポートで実行されていることを確認します。
    
    ![Netstat を使ってポートを確認します。](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Netstat を使ってポートを確認します。")

3.  SQL Server インスタンスへの接続を確認するには、「 ** \<telnet\> \<alias name port \# ** 」と入力します。 接続に成功すると、telnet が接続され、エラーが表示されなくなります。 これは、SQL Server インスタンスが正しいエイリアスで正しいポートをリッスンしていることを示します。 SQL Server データベースへの接続に問題がある場合は、telnet に接続できないというエラーが表示されます。 データベースサーバーでデータベース接続を確認しましたが、Lync Server (ネットワーク経由) から同じことを行うことができます。また、ファイアウォールによってアクセスがブロックされていないことを確認してください。

</div>

<div>

## <a name="conclusion"></a>終わりに

SQL Server のエイリアスを構成したら、それを使って、トポロジビルダーツールで Lync Server 2013 トポロジを作成できます。 トポロジの詳細については、「 [Lync Server 2013 でトポロジを定義して構成する](lync-server-2013-defining-and-configuring-the-topology.md)」を参照してください。

</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Microsoft lync server 2013](microsoft-lync-server-2013.md) 
[lync server 2013 のセキュリティの計画](lync-server-2013-planning-for-security.md)  
[Lync Server 2013 でのトポロジの定義と構成](lync-server-2013-defining-and-configuring-the-topology.md)  
[Lync Server 2013 の展開](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

