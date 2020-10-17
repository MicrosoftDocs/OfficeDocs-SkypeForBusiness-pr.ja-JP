---
title: Lync Server 2013 での SQL Server の標準以外のポートとエイリアスの展開
description: Lync Server 2013 で SQL Server の標準以外のポートとエイリアスを展開します。
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
ms.openlocfilehash: da76db2b946a47e13fe3549d7184b0b12894a83a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551233"
---
# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a>Lync Server 2013 での SQL Server の標準以外のポートとエイリアスの展開

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2015-09-16_

Microsoft Lync Server 2013 は、SQL Server で標準以外のポートとエイリアスを使用することをサポートしています。 SQL Server の非標準ポートとエイリアスを使用すると、セキュリティが向上し、Lync 展開により柔軟な環境が作成されます。 これらの手順は、Lync Server 2013 環境を適切にセキュリティで保護する手順の1つにすぎません。 Lync Server 2013 実装の攻撃対象を減らすには、追加の手順を実行する必要があります。

次の記事では、Lync Server 2013 で標準以外の SQL Server のポートとエイリアスをセットアップするために必要な手順について説明します。

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a>Lync Server 2013 に SQL Server の非標準ポートとエイリアスを展開する

Lync Server 2013 トポロジビルダーでは、Lync Server 2013 を構成する際に、実際の SQL Server の FQDN ではなく、完全修飾ドメイン名 (FQDN) として SQL Server のエイリアスを使用することができます。 これにより、実際の SQL Server の FQDN を悪意のある攻撃者に対して非表示にすることができます。 また、次の図に示されているように、標準ポート1433上のデータベースを攻撃しようとしている場合に、非標準ポートを使用して、次の図に示すように、実際のポートを不明瞭にします。

![ハッカーは、攻撃対象のポート番号を認識していません。](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "ハッカーは、攻撃対象のポート番号を認識していません。")

SQL Server との通信に使用している Lync Server 2013 のポートを正しく判断するには、攻撃者はすべてのポートをスキャンしてポート情報を取得する必要があります。 攻撃者によるポートスキャンでは、セキュリティが命令を検出して停止する可能性が高くなります。 拡張セキュリティを標準以外のポートで追加することに加えて、SQL Server の別名を使用して展開の柔軟性を提供することもできます。 これは、SQL Server の名前の変更が必要になる状況での構成変更を減らすために役立ちます。

<div>


> [!NOTE]  
> SQL Server には、2つのフォールトトレランス方法 (フェールオーバークラスタリングとミラーリング) が用意されています。 Sql Server のフォールトトレランス方式は、SQL Server の非標準ポートと、Lync Server 2013 でエイリアスを使用してサポートされています。 プールによって使用される SQL Server バックエンドがミラーリングされた構成にある場合は、データベースがミラーリングされた SQL Server にフェールオーバーするときに、SQL Server バックエンドサーバー上の SQL browser サービスが、ミラーリングされたデータベースに接続するために実行されている必要があります。



</div>

トポロジビルダー内から SQL Server データベース接続を構成する場合、または Install-CsDatabase コマンドレットを使用する場合は、SQL Server の非標準ポート番号を明示的に定義して SQL インスタンスに関連付けることはできません。 非標準ポートを設定するには、SQL Server および Windows Server ユーティリティを使用する必要があります。

Lync Server 2013 で使用するために SQL Server の非標準ポートとエイリアスをセットアップするには、3つの主要な手順を実行する必要があります。 その手順は、次のとおりです。

  - Lync Server 2013 に最新の更新プログラムが適用されていることを確認します。

  - SQL Server の非標準ポートとエイリアスをセットアップします。

  - トポロジビルダーを使用して、SQL Server エイリアスを使用して Lync Server 2013 を構成します。

  - トポロジを公開し、データベースを確認します。

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a>Lync Server 2013 に最新の更新プログラムが適用されていることを確認する

Lync Server 2013 を最新の状態に保つことが重要です。 最新の更新プログラムとその適用方法に関する情報を確認するには、「 [Lync Server 2013 の更新プログラム](https://support.microsoft.com/kb/2809243)」を参照してください。

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a>SQL Server の非標準ポートとエイリアスをセットアップする

Lync Server 2013 トポロジビルダーから参照できるようにするには、SQL Server の非標準ポートとエイリアスをデータベースインスタンスで設定する必要があります。 SQL Server の非標準ポートとエイリアスをセットアップするには、3つの主要な手順を実行する必要があります。 これらの手順は次のとおりです。

  - 既定の TCP/IP プロトコルの値を変更します。

  - SQL Server エイリアスを作成して構成します。

  - ドメインネームシステム (DNS) 正規名 (CNAME) リソースレコードを作成します。

**既定の TCP/IP プロトコル値を変更する**

1.  次の図に示すように、[ **スタート**] を選択し、[ **SQL Server 構成マネージャー**] を選択します。
    
    ![SQL Server Management Studio アイコン](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "SQL Server Management Studio アイコン")

2.  次の図に示すように、ナビゲーションウィンドウで、 **Sql server インスタンス**を選択し、[ **Sql server ネットワーク構成**] を展開して、[**プロトコル \<instance name\> **] を選択します。
    
    ![[TCP/IP のプロパティ] に移動します。](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "[TCP/IP のプロパティ] に移動します。")

3.  右側のウィンドウで、[ **tcp/ip**] を右クリックし、[ **プロパティ**] を選択します。 [TCP/IP のプロパティ] ダイアログボックスが表示されます。

4.  [ **IP アドレス** ] タブを選択します。[IP アドレス] タブには、サーバー上のすべてのアクティブな IP アドレスが表示されます。 次の図に示すように、これらは IP1, IP2 の形式になっています。
    
    ![TCP/IP のプロパティを開きます。](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "TCP/IP のプロパティを開きます。")

5.  すべての IP アドレスの [ **TCP 動的ポート** ] フィールドをオフにします。 フィールドにゼロ文字が含まれている場合は、SQL Server が動的ポートをリッスンしていることを意味します。 これらのフィールドがクリアされていて、ゼロが含まれていないことを確認してください。

6.  Lync Server がデータベースへの接続に使用する IP アドレスについては、次の図に示すように、[ **有効** **] が [はい]** に設定されていることを確認してください。
    
    ![正しい IP に対して [はい] として有効に設定します。](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "正しい IP に対して [はい] として有効に設定します。")

7.  ダイアログの下部にある [ **Ipall** ] セクションで、次の図に示すように、[ **TCP ポート** ] フィールドに目的のポートを入力します。 この例ではポート50062を使用していますが、49152と65535の間で任意のポートを使用できます。 これらは動的およびプライベートの使用に割り当てられているポートであり、これにより、Lync Server 2013 の展開で使用されている他のポートと競合することはありません。
    
    ![IPAll セクションのポートを設定します。](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "IPAll セクションのポートを設定します。")

8.  [ **OK]** を選択して、[Tcp/ip のプロパティ] ダイアログを閉じます。

9.  Sql server 構成マネージャーの左側のウィンドウで、[ **Sql Server サービス** ] を選択して、sql server インスタンスを再起動します。 次の図に示すように、右側のウィンドウで [ **SQL Server \<instance name\> ** ] を右クリックし、[**再起動**] を選択します。
    
    ![インスタンスの SQL Server サービスをリセットします。](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "インスタンスの SQL Server サービスをリセットします。")

<div>


> [!IMPORTANT]  
> 新しい SQL Server ポートに対応するように、ファイアウォールの設定を更新してください。



</div>

**SQL Server のエイリアスを作成して構成する**

1.  次の図に示すように、[ **スタート**] を選択し、[ **SQL Server 構成マネージャー**] を選択します。
    
    ![SQL Server Management Studio アイコン](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "SQL Server Management Studio アイコン")

2.  次の図に示すように、左側のウィンドウで、[ **Sql Server インスタンス**] を選択し、[ **sql Native Client \<version\> 構成**] を選択してから、[ **エイリアス**] を選択します。
    
    ![SQL Server 構成マネージャーのエイリアス。](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "SQL Server 構成マネージャーのエイリアス。")

3.  [ **エイリアス**] を右クリックし、[ **新しいエイリアス...**] を選択します。

4.  次の図に示すように、 **エイリアス名**、 **ポート番号**、 **プロトコル**、および **サーバー**を入力します。
    
    ![新しいエイリアスを作成する](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "新しいエイリアスを作成する")
    
    <div>
    

    > [!CAUTION]  
    > 前の手順で使用したのと同じ非標準ポートを入力してください。これは、SQL Server がリッスンするポートです。 構成されたエイリアスが正しくない SQL Server の FQDN またはインスタンスに接続している場合は、関連付けられているネットワークプロトコルを無効にしてから再び有効にします。 これにより、キャッシュされた接続情報がクリアされ、クライアントが正常に接続できるようになります。

    
    </div>

**DNS CNAME リソースレコードを作成する**

1.  DNS を管理しているコンピューターにサインインします。

2.  次の図に示すように、[ **スタート**] を選択し、[ **サーバーマネージャー**] を選択します。
    
    ![サーバーマネージャーを開く](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "サーバーマネージャーを開く")

3.  次の図に示すように、[ **ツール** ] ドロップダウンを選択し、[ **DNS**] を選択します。
    
    ![サーバーマネージャーから DNS を開く。](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "サーバーマネージャーから DNS を開く。")

4.  左側のウィンドウで、[サーバー名] ノードを展開し、[前方参照ゾーン] ノードを展開して、該当するドメインを選択します。

5.  次の図に示すように、ドメインを右クリックし、[ **新しいエイリアス (CNAME)**] を選択します。
    
    ![新しいエイリアス CNAME を作成するためのオプションの選択](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "新しいエイリアス CNAME を作成するためのオプションの選択")

6.  次の図に示すように、 **SQL Server の****エイリアス名**と FQDN を入力します。
    
    ![[新しいエイリアスの CNAME] ダイアログに記入します。](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "[新しいエイリアスの CNAME] ダイアログに記入します。")

7.  **[OK]** を選択して CNAME を保存し、DNS マネージャーで表示します。

</div>

<div>

## <a name="validate-database-connectivity"></a>データベース接続を検証する

動作していることを確認するには、さまざまな方法があります。 SQL Server データベースが、エイリアスを使用して指定されたポートでリッスンしていることを確認します。 クイックチェックは、 **netstat** コマンドと **telnet** コマンドを使用して完了できます。

<div>


> [!NOTE]  
> Telnet クライアントは Windows Server に付属している機能ですが、インストールする必要があります。 Windows Server の機能をインストールするには、サーバーマネージャーを開き、[管理] メニューの [役割と機能の追加] を選択します。



</div>

**Netstat および telnet を使用してデータベース接続を確認する**

1.  [ **スタート**] を選択し、コマンドプロンプトを開くために「 **cmd** 」と入力します。

2.  「 **Netstat-a-f**」と入力し、次の図に示すように、SQL Server が正しいポートを使用して実行されていることを確認します。
    
    ![Netstat を使用してポートを確認する。](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Netstat を使用してポートを確認する。")

3.  「 **Telnet \<alias name\> \<port \#\> ** 」と入力して、SQL Server インスタンスへの接続を確認します。 接続に成功すると、telnet が接続され、エラーは表示されません。 これは、SQL Server インスタンスが正しいエイリアスで適切なポートをリッスンしていることを示しています。 SQL Server データベースへの接続で問題が発生した場合は、接続を確立できないというエラーが telnet に表示されます。 データベースサーバーでデータベース接続を確認したので、Lync Server (ネットワーク経由) から同じことを行うことができます。また、アクセスをブロックしているファイアウォールがないことを確認してください。

</div>

<div>

## <a name="conclusion"></a>まとめ

SQL Server のエイリアスを構成したら、それを使用して、トポロジビルダーツールで Lync Server 2013 トポロジを作成できます。 トポロジの詳細については、「 [Lync Server 2013 でのトポロジの定義と構成](lync-server-2013-defining-and-configuring-the-topology.md)」を参照してください。

</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Microsoft Lync Server 2013](microsoft-lync-server-2013.md)  
[Lync Server 2013 でのセキュリティの計画](lync-server-2013-planning-for-security.md)  
[Lync Server 2013 でのトポロジの定義と構成](lync-server-2013-defining-and-configuring-the-topology.md)  
[Lync Server 2013 の展開 ](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

