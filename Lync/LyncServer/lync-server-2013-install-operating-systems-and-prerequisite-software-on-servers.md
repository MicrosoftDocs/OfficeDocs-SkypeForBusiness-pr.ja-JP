---
title: オペレーティングシステムと必要なソフトウェアをサーバーにインストールする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install operating systems and prerequisite software on servers
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48183288
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37cfbf02d379a3003338d4eabc7a5ca3c4b49f15
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498694"
---
# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a>Lync Server 2013 のサーバーにオペレーティングシステムと必要なソフトウェアをインストールする

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-07-24_

ハードウェアおよびシステム インフラストラクチャを設定したら、展開する各サーバーに適切な Windows オペレーティング システム、更新プログラム、および他の必要なソフトウェアをすべてインストールする必要があります。 これには、各 Lync Server 2013 のサーバーの役割、および展開に必要な SQL Server を実行している追加のインフラストラクチャサーバーまたはサーバーが含まれます。

<div>


> [!NOTE]
> ここでは、オペレーティング システムと内部サーバーに必要なソフトウェアのインストールについて説明します。 エッジサーバーを展開して外部ユーザーアクセスをサポートする場合は、エッジサーバーやリバースプロキシサーバーを含む、これらのサーバーのオペレーティングシステムと前提条件となるソフトウェアもインストールする必要があります。 外部ユーザーアクセスをサポートするサーバーの準備の詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">境界ネットワークでのサーバーのインストールの準備 (Lync Server 2013 の</A> 場合)」を参照してください。



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a>サーバーへの Windows オペレーティング システムのインストール

展開する各サーバーで、次のようにして適切な Windows オペレーティングシステムをインストールします。

  - **Lync Server 2013**     を実行しているサーバーLync Server 2013 を実行しているサーバーのオペレーティングシステム要件の詳細については、「サポート」のドキュメントの「 [Lync server 2013 のサーバーおよびツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。

  - **データベースサーバー**    データベースサーバーのオペレーティングシステム要件 (バックエンドデータベース、アーカイブデータベース、監視データベースなど) の詳細については、SQL Server のドキュメントを参照してください。 SQL Server 2012 については、SQL Server 2012 オンラインブック () を参照してください [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) 。

<div>


> [!NOTE]
> Windows Server 2008 R2 SP1 に Lync Server 2013 をインストールしている場合は、 &nbsp; &nbsp; まず、マイクロソフトサポート技術情報の記事2646886「修正: モジュールが IIS 7.5 で InsertEntityBody メソッドを呼び出すときにヒープの破損が発生する」 ( <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp kbid = 2646886</A>) に記載されている更新プログラムをインストールする必要があります。<BR>また、KB 記事「 <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">イベント id 32402, 61045 は、Windows Server 2012 にインストールされている Lync Server 2013 フロントエンドサーバーに記録さ</A>れています」の説明に従って、レジストリを変更する必要があります。



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a>サーバーへの Windows 更新プログラムのインストール

各サーバーで、Windows Update から次の更新プログラムをインストールします。

  - **Lync Server 2013 を実行しているサーバーの Windows Update**    Lync Server 2013 を実行しているサーバーで必要とされる Windows Update からの更新プログラムの詳細については、「計画」のドキュメントの「 [Lync server 2013 の追加ソフトウェア要件](lync-server-2013-additional-software-requirements.md)」を参照してください。

  - **データベースサーバー**    バックエンドデータベース、アーカイブデータベース、監視データベースなど、データベースサーバーに必要な更新プログラムの詳細については、SQL Server 2012 のドキュメントを参照してください。 SQL Server 2012 については、SQL Server 2012 オンラインブック () を参照してください [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) 。

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a>他の必要なソフトウェアのサーバーへのインストール

Lync Server 2013 には、サーバーに次の追加ソフトウェアがインストールされている必要があります。

  - **Lync Server 2013 を実行しているサーバーの前提条件となるソフトウェア**    Lync Server 2013 を実行しているサーバーの追加ソフトウェアの前提条件は、展開されるサーバーの役割によって異なります。 各サーバーの特定のソフトウェア要件の詳細については、「計画」のドキュメントの「 [Lync server 2013 の追加ソフトウェア要件](lync-server-2013-additional-software-requirements.md) 」を参照してください。

  - **Windows Identity Foundation**    Lync Server 2013 では、サーバー間認証のシナリオをサポートするために、Windows Identity Foundation をインストールする必要があります。 コンピューターに既にインストールされていることを確認するには、[コントロールパネル] の [ **プログラムと機能**] をクリックし、 **インストールされた更新プログラムを表示**して、[ **Microsoft Windows**] の下に表示します。 Windows Identity Foundation のインストールの詳細については、「」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) 。

  - **Microsoft .Net Framework 4.5**    Lync Server 2013 では、64ビット版の Microsoft .NET Framework 4.5 が必要です。

  - **データベースサーバー**     の前提条件となるソフトウェアデータベースサーバーに必要な Windows Update (バックエンドデータベース、アーカイブデータベース、監視データベースなど) の詳細については、SQL Server 2012 のドキュメントを参照してください [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) 。
    
    <div>
    

    > [!NOTE]
    > Lync Server 2013 は、各 Standard Edition サーバーと、ローカル構成ストアが配置されている Lync Server 2013 を実行している各サーバーに、Microsoft SQL Server 2012 Express を自動的にインストールします。

    
    </div>

  - **Windows Media フォーマットランタイム**    会議を展開するすべてのフロントエンドサーバーおよび Standard Edition サーバーには、Windows Media フォーマットランタイムがインストールされている必要があります。 コール パーク、アナウンス、応答グループの各アプリケーションがアナウンスと音楽を再生する Windows Media オーディオ (.wma) ファイルを実行するには、Windows Media フォーマット ランタイムが必要です。
    
    <div>
    

    > [!NOTE]
    > Windows Server 2012 および Windows Server 2012 R2 では、Windows Media フォーマットランタイムが Microsoft Media Foundation と共にインストールされます。

    
    </div>
    
    <div>
    

    > [!NOTE]
    > Windows Server &nbsp; 2008 および Windows server &nbsp; 2008 R2 の場合、Windows &nbsp; Media フォーマットランタイムは windows デスクトップ環境の一部としてインストールされます。 Lync Server 2013 をインストールする前に、Windows デスクトップ環境をインストールすることをお勧めします。 Lync Server 2013 がサーバー上でこのソフトウェアを見つけられない場合は、インストールを求めるメッセージが表示され、インストールを完了するためにサーバーを再起動する必要があります。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

