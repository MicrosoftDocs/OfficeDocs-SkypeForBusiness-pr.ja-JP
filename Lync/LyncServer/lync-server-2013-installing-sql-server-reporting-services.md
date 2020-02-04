---
title: 'Lync Server 2013: SQL Server Reporting Services のインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204957(v=OCS.15)
ms:contentKeyID: 48184345
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6342743486e3a3261e297d602ceb994d421dc13c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a>Lync Server 2013 で SQL Server Reporting Services をインストールする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-06-20_

Microsoft Lync Server 2013 監視レポートを使用する場合 (詳細については、このドキュメントの次のセクションを参照してください)、まず SQL Server Reporting Services をインストールする必要があります。Reporting Services は、Microsoft SQL Server のインストール時に、または SQL Server をインストールした後であれば、いつでもインストールできます。 SQL Server がインストールされていない場合は、このドキュメントで前に説明した指示に従ってください。 SQL Server をインストールするときに、[機能の選択] ページで [Reporting Services] を選択していることを確認します。 これにより、SQL Server Reporting Services がインストールされます。

Sql server が既にインストールされているが、SQL Server Reporting Services をインストールしていない場合は、SQL Server 2008 R2 または SQL Server 2012 の適切な手順に従って、その機能を追加できます。

レポートサービスが正常にインストールされたことを確認するには、次の手順を実行します。

1.  Microsoft SQL Server 2008 R2 を実行している場合は、[**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft SQL Server 2008 R2**]、[**構成ツール**]、[ **Reporting Services 構成マネージャー**] の順にクリックします。
    
    Microsoft SQL Server 2012 を実行している場合は、[**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft SQL Server 2012**]、[**構成ツール**]、[ **Reporting Services 構成マネージャー**] の順にクリックします。

2.  [ **Reporting Services の構成接続**] ダイアログボックスで、[**サーバー名**] ボックスにサーバー名が表示され、監視データを格納する SQL server インスタンスの名前が [**レポートサーバーインスタンス**] ボックスに表示されていることを確認します。 [**接続**] をクリックします。

Reporting Service 構成マネージャーの [レポートサーバーの状態] ウィンドウには、SQL Server Reporting Services がインストールされていて、Reporting Services が現在実行されていることが表示されます。レポートサーバーの状態は [**開始**] と表示され、[**スタート**] ボタンは淡色表示され、使用できなくなります。 レポートサービスが実行されていない場合は、[**開始**] をクリックしてサービスを開始します。

[レポートサーバーデータベース名] ラベルの横にデータベースが表示されない場合は、次の操作を行います。

1.  Reporting Services 構成マネージャーで [**データベース**] をクリックします。

2.  [レポートサーバーデータベース] ウィンドウで、[**データベースの変更**] をクリックします。

3.  レポートサーバーデータベース構成ウィザードの [操作] ウィンドウで、[**新しいレポートサーバーデータベースの作成**] を選択し、[**次へ**] をクリックします。

4.  [レポートサーバーデータベース構成ウィザード] の [データベースサーバー] ウィンドウで、[**サーバー名**]、[**認証の種類**]、[**ユーザー名**] ボックスに表示されている情報が正しいことを確認します。 [**接続テスト**] をクリックしてデータベースサーバーへの接続を確立できることを確認し、[**次へ**] をクリックします。

5.  レポートサーバーデータベース構成ウィザードの [データベース] ウィンドウで、**データベース名**、**言語**、および**レポートサーバーモード**の既定値をそのまま使用し、[**次へ**] をクリックします。

6.  [レポートサーバーデータベースの構成ウィザード] の [資格情報] ウィンドウで、[**認証の種類**] ドロップダウンリストと [**ユーザー名**] ボックスと [**パスワード**] ボックスに正しい情報が表示されていることを確認し、[**次へ**] をクリックします。

7.  レポートサーバーデータベース構成ウィザードの [概要] ウィンドウで、[**次へ**] をクリックします。

8.  [レポートサーバーデータベースの構成ウィザード] の [進行状況] と [完了] ウィンドウで、[**完了**] をクリックします。

レポートサービスの Url が構成されていることを確認するには、[ **Web サービスの url**] をクリックします。 [見出し**レポートサーバー] Web サービスの url**の下に、1つ以上の url が表示されます。 これらの各 Url をクリックして、SQL Server Reporting Services のローカルインストールのホームページにアクセスできることを確認します。

</div>

<span> </span>

</div>

</div>

</div>

