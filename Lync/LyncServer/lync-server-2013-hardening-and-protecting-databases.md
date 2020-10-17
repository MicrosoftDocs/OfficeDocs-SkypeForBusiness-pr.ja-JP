---
title: 'Lync Server 2013: データベースのセキュリティ強化および保護'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting the databases of Lync Server 2013
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518330(v=OCS.15)
ms:contentKeyID: 62625490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0254c77bb276add6f55ccff623c1fc2bec590102
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536914"
---
# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a>Lync Server 2013 のデータベースの強化と保護

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-12-05_

また、Microsoft Lync Server 2013 は、ユーザー情報、会議の状態、アーカイブデータ、および通話詳細レコード (Cdr) を格納するための SQL Server データベースに依存しています。 Lync Server のバックエンドデータベースで Lync Server 2013 データを最大限に利用できるようにするには、フォールトトレランスを向上させてトラブルシューティングを簡略化する方法でアプリケーションデータをパーティション分割します。 アプリケーション データを分割する方法は、次のとおりです。

  - **サーバーパーティション分割のベストプラクティス**     の使用オペレーティングシステム、アプリケーション、およびプログラムファイルをデータファイルから分離します。

  - **トランザクションログファイルとデータベースファイル**     の保存これらのファイルを別々に保存して、フォールトトレランスを向上させ、回復を最適化し、暗号化されたディスクまたはボリュームに保存します。

  - **サーバーのクラスター化**     を使用するバックエンドサーバーをクラスター化して、Lync Server 2013 のシステム可用性を最適化します。

  - **すべてのデータバックアップが暗号化され、適切に処理**     されることを確認する紛失、破棄、または紛失したバックアップメディアは、Lync Server 2013 の展開のデータセキュリティに大きな脅威をもたらす可能性があります。

Standard Edition サーバー以外の Lync Server 2013 サーバーでは、SQL Server Express インスタンス (RTCLOCAL インスタンス) はリモートでアクセスできず、ローカルファイアウォールの例外は作成されません。ただし、Standard Edition サーバー上の SQL Server Express を除きます。 Standard Edition サーバーでは、バックエンドデータベースと中央管理ストア (CMS) の両方がリモートでアクセスできるように設定されています。 SQL Server データベースを強化するには、次の操作を行います。

  - Standard Edition サーバー上の SQL Server Express ファイアウォールをカスタマイズして、データベースにリモートからアクセスできるサーバーのスコープを制限します。既定では、すべての IP アドレスがデータベースにリモートからアクセスできます。

  - SQL Server 構成マネージャーを使用して、SQL Server リモート アクセス用のプロトコル、IP アドレス、およびポートを指定します。
    
      - Lync Server 2013 は TCP/IP プロトコルを使用します。 IP version 4 (IPv4) をサポートし、IP version 6 (IPv6) はサポートしません。
        
        <div>
        

        > [!NOTE]  
        > Lync Server 2013 は、デュアル IP スタックが有効になっているネットワークで機能します。

        
        </div>
    
      - Lync Server 2013 では、複数の IP アドレス (マルチホームネットワークアドレスカード) をサポートしています。 SQL Server が特定の IP アドレス (個別のアドレスまたはサブネット単位) のみをリッスンすることや、特定のプロトコルのみを使用することを指定できます。
    
      - Lync Server 2013 は、静的および動的な SQL Server ポートをサポートしています。

  - 既定でない静的ポートで SQL Server を実行し、SQL Server ブラウザーを実行しません (この結果、クライアントにリッスン ポートをレポートできません)。 これには、フロントエンドサーバー、監視サーバー、アーカイブサーバー、管理コンソール (Lync Server 管理シェル、Lync Server コントロールパネル、またはトポロジビルダーを実行している)、および Lync Server データベースを実行している他のすべてのサーバーを含む、各 SQL Server クライアントのカスタム構成が必要です。

<div>


> [!NOTE]  
> データベースへのアクセスは、信頼できるデータベース管理者に制限する必要があります。 悪意のあるデータベース管理者は、データベース管理者が Lync Server 2013 サーバーの直接のアクセスや制御を許可されていない場合でも、Lync Server 2013 サーバーでの権限を取得するか、またはサービスから機密情報を取得するために、データベースにデータを挿入または変更することができます。



</div>

カスタム構成の詳細と SQL Server データベースのセキュリティ強化については、NextHop の記事「カスタム SQL Server ネットワーク構成での Lync Server 2010 の使用」、「」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008) 。

<div>


> [!NOTE]  
> また、オペレーティングシステムとアプリケーションサーバーを強化することもできます。また、グループポリシーを使用して、Lync Server 展開のセキュリティロックダウンを実装することもできます。 詳細については、「 <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Lync Server 2013 のサーバーとアプリケーションのセキュリティ強化と保護</A>」を参照してください。



</div>

</div>

<span> </span>

</div>

</div>

</div>

