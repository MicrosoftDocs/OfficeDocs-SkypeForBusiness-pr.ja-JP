---
title: 'Lync Server 2013: SQL Server Reporting Services のインストール'
description: 'Lync Server 2013: SQL Server Reporting Services のインストール。'
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
ms.openlocfilehash: 70da5e3845d18057b3362fa39953dee6cdc3d9f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573883"
---
# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a>Lync Server 2013 での SQL Server Reporting Services のインストール

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-20_

Microsoft Lync Server 2013 の監視レポートを使用する場合 (詳細については、このドキュメントの次のセクションを参照してください)、最初に SQL Server Reporting Services をインストールする必要があります。Reporting Services は、Microsoft SQL Server をインストールするとき、または SQL Server をインストールした後で、いつでもインストールできます。 SQL Server をインストールしていない場合は、このドキュメントで前述した手順に従ってください。 SQL Server をインストールするときは、[機能の選択] ページで [Reporting Services] を選択していることを確認してください。 SQL Server Reporting Services がインストールされます。

SQL Server はインストールしたが、SQL Server Reporting Services はインストールしていない場合は、SQL Server 2008 R2 または SQL Server 2012 に適した指示に従って、この機能を追加できます。

Reporting Services が正常にインストールされたことを確認するには、次の手順に従います。

1.  Microsoft SQL Server 2008 R2 を実行中の場合は、[**スタート**]、[**すべてのプログラム**]、[**Microsoft SQL Server 2008 R2**]、[**構成ツール**] の順にクリックし、[**Reporting Services 構成マネージャー**] をクリックします。
    
    Microsoft SQL Server 2012 を実行中の場合は、[**スタート**]、[**すべてのプログラム**]、[**Microsoft SQL Server 2012**]、[**構成ツール**] の順にクリックし、[**Reporting Services 構成マネージャー**] をクリックします。

2.  [**Reporting Services 構成の接続**] ダイアログ ボックスで、サーバーの名前が [**サーバー名**] ボックスに、および監視データを保存する SQL Server インスタンスの名前が [**レポート サーバー インスタンス**] ボックスに表示されることを確認します。[**接続**] をクリックします。

Reporting Service 構成マネージャーで、[レポートサーバーの状態] ウィンドウに、SQL Server Reporting Services がインストールされており、Reporting Services が現在実行中であることを示す必要があります。レポートサーバーの状態は [ **開始** ] と表示され、[ **開始** ] ボタンは淡色表示され、使用できません。 Reporting Services が実行されていない場合は、[ **開始** ] をクリックしてサービスを開始します。

[レポート サーバー データベース名] ラベルの横にデータベースが表示されない場合は、次の操作を行います。

1.  Reporting Services 構成マネージャーで、[**データベース**] をクリックします。

2.  [レポート サーバー データベース] ウィンドウで、[**データベースの変更**] をクリックします。

3.  レポート サーバー データベース構成ウィザードで、[**新しいレポート サーバー データベースを作成する**] を選択し、[**次へ**] をクリックします。

4.  レポート サーバー データベース構成ウィザードの [データベース サーバー] ウィンドウで、[**サーバー名**] ボックス、[**認証の種類**] ボックス、および [**ユーザー名**] ボックスに表示される情報が正しいことを確認します。[**接続テスト**] をクリックしてデータベース サーバーに接続できることを確認し、[**次へ**] をクリックします。

5.  レポート サーバー データベース構成ウィザードの [データベース] ウィンドウで、[**データベース名**]、[**言語**]、および [**レポート サーバー モード**] の既定値をそのまま使用し、[**次へ**] をクリックします。

6.  レポート サーバー データベース構成ウィザードの [資格情報] ウィンドウで、[**認証の種類**] ドロップダウン リスト、[**ユーザー名**] ボックス、および [**パスワード**] ボックスに正しい情報が表示されていることを確認し、[**次へ**] をクリックします。

7.  レポート サーバー データベース構成ウィザードの [概要] ウィンドウで、[**次へ**] をクリックします。

8.  レポート サーバー データベース構成ウィザードの [続行して完了する] ウィンドウで、[**完了**] をクリックします。

Reporting Services の URL が構成されていることを確認するには、[**Web サービスの URL**] をクリックします。[**レポート サーバー Web サービスの URL**] 見出しの下に、1 つまたは複数の URL が表示されることを確認します。これらの各 URL をクリックすることで、SQL Server Reporting Services のローカル インストール用のホーム ページにアクセスできることを確認できます。

</div>

<span> </span>

</div>

</div>

</div>

