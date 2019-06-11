---
title: Lync Server 2013 コアファイルと RTCLocal データベースのインストール
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing the Lync Server 2013 core files and the RTCLocal database
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48183591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99eccdd8d6473c25c6096c370f616975c7da141f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a>Lync Server 2013 コアファイルと RTCLocal データベースのインストール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-20_

Lync Server 2013 コアファイルをコンピューターにインストールするには、次の手順を実行します。 RTCLocal データベースは、コアファイルのインストール時に自動的にインストールされます。 監視ノードに SQL Server をインストールする必要はないことに注意してください。 代わりに、SQL Server Express が自動的にインストールされます。

Lync Server 2013 コアファイルと RTCLocal データベースをインストールするには、次の操作を行います。

1.  ウォッチャーノードのコンピューターで、[**スタート**] をクリックし、[**すべてのプログラム**]、[**アクセサリ**]、[**コマンドプロンプト**] を右クリックして、[**管理者として実行**] をクリックします。

2.  [コンソール] ウィンドウで、次のコマンドを入力し、ENTER キーを押します。 Lync Server セットアップファイルへの適切なパスを使用します。
    
        D:\Setup.exe /BootstrapLocalMgmt

主要な Lync Server コンポーネントが正常にインストールされたことを確認するには、[**スタート**] をクリックし、[**すべてのプログラム**]、[ **lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。 Lync Server 2013 管理シェルで、次の Windows PowerShell コマンドを入力し、enter キーを押します。

    Get-CsWatcherNodeConfiguration

このコマンドを初めて実行したときに、ウォッチャーノードのコンピューターをまだ構成していないため、データは返されません。 コマンドを実行してもエラーが返されない限り、Lync Server のセットアップが正常に完了したと見なすことができます。

ウォッチャーノードのコンピューターが境界ネットワーク内にある場合は、次のコマンドを実行して、Lync Server 2013 のインストールを確認できます。

    Get-CsPinPolicy

組織で使用するために構成されている暗証番号 (PIN) ポリシーの数に応じて、次のような情報が表示されます。

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

PIN ポリシーに関する情報が表示される場合は、コアコンポーネントが正常にインストールされていることを意味します。

</div>

<span> </span>

</div>

</div>

</div>

