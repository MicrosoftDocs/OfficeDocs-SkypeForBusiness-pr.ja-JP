---
title: Lync Server 2013 コアファイルおよび RTCLocal データベースのインストール
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Server 2013 core files and the RTCLocal database
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48183591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17b3b1925607a80f143c57e6185c7a709b19ee0c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a>Lync Server 2013 コアファイルおよび RTCLocal データベースのインストール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-20_

Lync Server 2013 のコアファイルをコンピューターにインストールするには、次の手順を実行します。 RTCLocal データベースは、コア ファイルをインストールするときに自動的にインストールされます。 監視ノードに SQL Server をインストールする必要はないことに注意してください。 代わりに、SQL Server Express が自動的にインストールされます。

Lync Server 2013 コアファイルおよび RTCLocal データベースをインストールするには、次のようにします。

1.  ウォッチャー ノード コンピューターで、[**スタート**] ボタンをクリックし、[**すべてのプログラム**]、[**アクセサリ**] の順にクリックします。次に、[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックします。

2.  コンソールウィンドウで、次のコマンドを入力し、ENTER キーを押して、Lync Server セットアップファイルへの適切なパスを指定します。
    
        D:\Setup.exe /BootstrapLocalMgmt

コア Lync Server コンポーネントが正常にインストールされたことを確認するには、[**スタート**]、[**すべてのプログラム**]、[ **lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。 Lync Server 2013 管理シェルで、次の Windows PowerShell コマンドを入力し、enter キーを押します。

    Get-CsWatcherNodeConfiguration

最初にこのコマンドを実行したときは、まだウォッチャー ノード コンピューターを構成していないので何もデータが表示されません。 エラーが返されずにコマンドが実行されている限り、Lync Server のセットアップが正常に完了したと見なすことができます。

監視ノードコンピューターが境界ネットワーク内にある場合は、次のコマンドを実行して Lync Server 2013 のインストールを確認できます。

    Get-CsPinPolicy

組織で構成されている暗証番号 (PIN) ポリシーの数に応じて、次のような情報が表示されます。

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

PIN ポリシーに関する情報が表示された場合は、コア コンポーネントが正常にインストールされています。

</div>

<span> </span>

</div>

</div>

</div>

