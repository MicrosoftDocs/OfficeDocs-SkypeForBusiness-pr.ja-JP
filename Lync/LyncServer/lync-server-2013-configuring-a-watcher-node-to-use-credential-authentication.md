---
title: 'Lync Server 2013: 資格情報認証を使用するように監視ノードを構成する'
description: 'Lync Server 2013: 資格情報認証を使用するように監視ノードを構成する。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use credential authentication
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204632(v=OCS.15)
ms:contentKeyID: 48183255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b65d4e3f90b27aac69b8569472ac9896766e093e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576323"
---
# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a>Lync Server 2013 で資格情報認証を使用するように監視ノードを構成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-20_

ウォッチャー ノードのコンピューターが境界ネットワークの外側にある場合は、代理トランザクションを実行するようにウォッチャー ノードを構成するために、少し異なる手順に従う必要があります。具体的には、信頼されたアプリケーション プールや信頼されたアプリケーションを作成せずに、境界ネットワークの内側にあるコンピューターにウォッチャー ノードが通知を送信できるようにする証明書をインストールする必要があります。つまり、次に示す個別の 2 つのタスクを完了する必要があります。

  - コンピューターの RTC Local Read-only Administrators グループのメンバーシップを更新する

  - ウォッチャー ノード構成ファイルをインストールする

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a>RTC Local Read-Only Administrators グループのメンバーシップの更新

ウォッチャー ノードが境界ネットワークの外側にある場合は、Network Service アカウントをウォッチャー ノード コンピューターの RTC Local Read-only Administrators グループに追加する必要があります。そのためには、ウォッチャー ノードで以下の手順を完了します。

1.  [**スタート**] メニューの [**コンピューター**] を右クリックし、[**管理**] をクリックします。

2.  サーバー マネージャーで、[**構成**]、[**ローカル ユーザーとグループ**] の順に展開し、[**グループ**] をクリックします。

3.  [グループ] ウィンドウで、[**RTC Local Read-only Administrators**] をダブルクリックします。

4.  [**RTC Local Read-only Administrators のプロパティ**] ダイアログ ボックスで、[**追加**] をクリックします。

5.  [**ユーザー、コンピューター、サービス アカウント、またはグループの選択**] ダイアログで、[**場所**] をクリックします。

6.  [**場所**] ダイアログ ボックスで、ウォッチャー ノード コンピューターの名前を選択し、[**OK**] をクリックします。

7.  [**選択するオブジェクト名を入力してください**] ボックスに、「**Network Service**」と入力し、[**OK**] をクリックします。

8.  [**RTC Local Read-only Administrators のプロパティ**] ダイアログ ボックスで、[**OK**] をクリックし、[**サーバー マネージャー**] を閉じます。

ウォッチャー ノード コンピューターを再起動します。

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a>ウォッチャー ノード構成ファイルのインストール

ウォッチャー ノード コンピューターの再起動後、次の手順は Watchernode.msi ファイルの実行です。 このファイルを実行するには、[ **スタート**]、[ **すべてのプログラム**]、[ **lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックして、Lync server 2013 管理シェルを開きます。 Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します (Watchernode.msi のコピーへの実際のパスを確認してください)。

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> 前述のように、Watchernode.msi はコマンド ウィンドウから実行することもできます。コマンド ウィンドウを開くには、[<STRONG>スタート</STRONG>] メニューをクリックし、[<STRONG>コマンド プロンプト</STRONG>] を右クリックして、[<STRONG>管理者として実行</STRONG>] をクリックします。コマンド ウィンドウが開いたら、先ほどと同じコマンドを入力します。



</div>

ウォッチャー ノードを信頼されたアプリケーション プールとしてセットアップできない場合はいつでも、ネゴシエート モードが使用されます。 このモードでは、管理者がウォッチャー ノードのテスト ユーザー パスワードを管理する必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

