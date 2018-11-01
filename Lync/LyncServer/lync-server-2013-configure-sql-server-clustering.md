---
title: Lync Server 2013 での SQL Server クラスタリングの構成
TOCTitle: Lync Server 2013 での SQL Server クラスタリングの構成
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56558968
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での SQL Server クラスタリングの構成

 

_**トピックの最終更新日:** 2016-12-08_

Microsoft Lync Server 2013 では、SQL Server 2012 と SQL Server 2008 R2 のクラスタリングをサポートしています。サポート内容について詳しくは、「[Lync Server 2013 でのデータベース ソフトウェアのサポート](lync-server-2013-database-software-support.md)」をご覧ください。

Enterprise Edition のフロントエンド サーバーとバックエンド データベースのインストールと展開の前に、SQL Server クラスターの設定と構成が必要です。SQL Server 2012 のフェールオーバー クラスタリングのベスト プラクティスと設定手順については、<http://technet.microsoft.com/ja-jp/library/hh231721.aspx> をご覧ください。SQL Server 2008 のフェールオーバー クラスタリングについては、<http://technet.microsoft.com/ja-jp/library/ms189134(v=sql.105).aspx> をご覧ください。

SQL Server をインストールする際は、SQL Server Management Studio をインストールしてデータベースとログ ファイルの場所を管理する必要があります。SQL Server Management Studio は、SQL Server のインストール時にオプション コンポーネントとしてインストールされます。


> [!IMPORTANT]
> SQL Server ベースのサーバーにデータベースをインストールして展開するには、データベース ファイルのインストール先である SQL Server ベースのサーバーの、SQL Server sysadmin グループのメンバーである必要があります。SQL Server sysadmin グループのメンバーでない場合は、データベース ファイルの展開前にグループへの追加を要求する必要があります。sysadmin グループのメンバーになれない場合は、SQL Server のデータベース管理者にスクリプトを提供して、データベースの構成と展開を依頼する必要があります。この手順の実行に必要なユーザー権限とアクセス許可について詳しくは、「<A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync Server 2013 の SQL Server の展開のアクセス許可</A>」をご覧ください。



## SQL Server クラスタリングを構成するには

1.  SQL Server クラスタリングのインストールと構成を完了したら、SQL Server インスタンスの仮想クラスタ名 (SQL Server クラスタリングの設定時に構成) と SQL Server データベースのインスタンス名を使用して、トポロジ ビルダーで SQL Server ストアを定義する必要があります。クラスタ化された SQL Server ベースのサーバーの場合、単独の SQL Server ベースのサーバーとは異なり、仮想ノードの完全修飾ドメイン名 (FQDN) を使用します。
    
    > [!NOTE]
    > トポロジ ビルダーで、Windows Server クラスタ ノードを個別に構成する必要はありません。SQL Server の仮想クラスタ名だけを使用します。


2.  トポロジ ビルダーを使用してデータベースを展開している場合は、SQL Server sysadmin グループのメンバーである必要があります。SQL Server sysadmin グループのメンバーではあるがドメインでの特権 (SQL Server のデータベース管理者の役割など) がない場合、データベースを作成する権限はありますが、Lync Server で必要な情報を読み取る権限はありません。Lync Server の展開に必要なユーザー権限とアクセス許可について詳しくは、「[Lync Server 2013 の SQL Server の展開のアクセス許可](lync-server-2013-deployment-permissions-for-sql-server.md)」をご覧ください。

3.  SQL Server Management Studio を使用して、データベース フォルダーとログ ファイル フォルダーが SQL Server クラスタの共有ディスクに既定で正しくマッピングされていることを確認します。これは、トポロジ ビルダーを使用してデータベースを作成する場合に必要な手順です。
    
    > [!NOTE]
    > SQL Server Management Studio をインストールしなかった場合は、SQL Server のインストールを再実行し、既存の SQL Server 展開の追加機能として管理ツールを選ぶとインストールできます。


4.  トポロジ ビルダーか Windows PowerShell コマンドレットを使用して、SQL Server ベースのサーバーのデータベースをインストールします。トポロジ ビルダーを使用するには、次の手順を使用します。Windows PowerShell コマンドレットの使用については、「[Lync Server 2013 での Lync Server 管理シェルを使用したデータベースのインストール](lync-server-2013-database-installation-using-lync-server-management-shell.md)」をご覧ください。

## トポロジ ビルダーを使用してデータベースを作成するには

1.  トポロジ ビルダーを以下の手順で起動します。\[ **スタート** \]、\[ **すべてのプログラム** \]、\[ **Microsoft Lync Server 2013** \]、\[ **Lync Server トポロジ ビルダー** \] の順にクリックします。
    

    > [!WARNING]
    > 次の手順は、トポロジ ビルダーでトポロジを定義し、構成してあることを前提とします。トポロジの定義について詳しくは、「<A href="lync-server-2013-defining-and-configuring-the-topology.md">Lync Server 2013 でのトポロジの定義と構成</A>」をご覧ください。トポロジ ビルダーを使用してトポロジを公開しデータベースを構成するには、正しいユーザー権限とグループ メンバーシップを持つユーザーとしてログオンする必要があります。必要な権限とグループ メンバーシップについて詳しくは、「<A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync Server 2013 の SQL Server の展開のアクセス許可</A>」をご覧ください。



2.  トポロジ ビルダーで、トポロジの公開時に、\[**データベースの作成**\] ページの \[**詳細設定**\] をクリックします。

3.  \[**データベース ファイルの場所の選択**\] ページには、SQL Server クラスタにデータベース ファイルを展開する方法を指定する 2 つのオプションがあります。次のいずれかを選びます。
    
      - \[**データベース ファイルの場所を自動的に判断する**\] - このオプションを選ぶと、SQL Server ベースのサーバー上のドライブ構成に基づいてデータベース ログとデータ ファイルの場所を決定するアルゴリズムが使用されます。ファイルは、最適なパフォーマンスが出るように分散されます。
    
      - \[SQL Server インスタンスの既定値を使用する\] - このオプションを選ぶと、SQL Server のインスタンス設定に従ってログ ファイルとデータ ファイルがインストールされます。データベース ファイルを SQL Server に展開した後、SQL Server データベース管理者がファイルを再配置して特定の SQL Server 構成要件向けにパフォーマンスを最適化したい場合があるかもしれません。

4.  トポロジの公開を完了して操作中にエラーがなかったことを確認します。

