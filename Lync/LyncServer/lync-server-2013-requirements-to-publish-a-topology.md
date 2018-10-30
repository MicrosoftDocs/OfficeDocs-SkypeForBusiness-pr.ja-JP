---
title: 'Lync Server 2013: トポロジを公開する場合の要件'
TOCTitle: トポロジを公開する場合の要件
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg195733(v=OCS.15)
ms:contentKeyID: 48272755
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でトポロジを公開する場合の要件

 

_**トピックの最終更新日:** 2013-02-21_

このトピックでは、トポロジ ビルダーまたは Lync Server 2013 管理シェル コマンドライン インターフェイスを使用してトポロジを公開する場合に限って適用されるインフラストラクチャおよびソフトウェアの要件について説明します。Lync Server 2013 のすべての管理ツールは、オペレーティング システム、ソフトウェア、およびアクセス許可の一般的な要件に加えて、これらの要件も満たす必要があります。トポロジを公開する前に、管理ツールのすべての要件を満たしていることを確認してください。

  - トポロジ ビルダーは、作成する Lync Server 2013 展開と同じドメインまたはフォレストに参加するコンピューター上で実行する必要があります。このように実行すると、 Active Directory ドメイン サービス の準備が完了し、そのコンピューター上で管理ツールを実行してトポロジを適切に公開できます。

  - トポロジに定義されているコンピューターは、ドメイン (エッジ サーバーを除く)、および AD DS に参加する必要があります。ただし、トポロジを公開するときにコンピューターがオンラインである必要はありません。

  - プールのファイル共有を作成し、リモート ユーザーが使用できるようにする必要があります。

  - Enterprise Edition フロント エンド プールを公開するには、SQL Server ベースのバックエンド サーバーが、サーバーを展開するドメインに参加し、オンラインであり、リモート ユーザーが使用できるように適切なファイアウォール ルールで構成する必要があります。ファイアウォール例外の指定の詳細については、「[Lync Server 2013 での SQL Server のファイアウォール要件について](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)」を参照してください。SQL Server の構成のその他の詳細については、「[Lync Server 2013 用 SQL Server の構成](lync-server-2013-configure-sql-server-for-lync-server.md)」を参照してください。
    
    > [!NOTE]
    > Standard Edition サーバーには、公開される構成を受け入れる併置されたデータベースがあります。最初に、 Lync Server 展開ウィザードで [<strong>最初の Standard Edition サーバーの準備</strong>] 設定タスクを実行する必要があります。


## 関連項目

#### タスク

[Lync Server 2013 でトポロジを公開する](lync-server-2013-publish-the-topology.md)  
[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)  

#### 概念

[Lync Server 2013 の管理ツールのソフトウェア要件](lync-server-2013-administrative-tools-software-requirements.md)  
[Lync Server 2013 でのサーバーおよびツールのオペレーティング システムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)  

#### その他のリソース

[Lync Server 2013 のセットアップと管理に必要な管理者権限およびアクセス許可](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

