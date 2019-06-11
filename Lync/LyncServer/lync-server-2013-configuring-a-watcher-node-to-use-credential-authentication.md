---
title: 'Lync Server 2013: 資格情報認証を使用するようにウォッチャーノードを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to use credential authentication
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204632(v=OCS.15)
ms:contentKeyID: 48183255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3746042e0fbf6c7342dd19085f563440b26bb0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840299"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a>Lync Server 2013 での資格情報認証を使用するためのウォッチャーノードの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-20_

ウォッチャーノードのコンピューターが境界ネットワークの外側にある場合は、別の手順に従って、そのウォッチャーノードが代理トランザクションを実行するように構成する必要があります。 具体的には、信頼されたアプリケーションプールと信頼されたアプリケーションを作成しないようにする必要があります。また、監視ノードが、境界ネットワーク内のコンピューターに通知を送信できるようにする証明書をインストールする必要があります。 これは、次の2つの個別のタスクを完了する必要があることを意味します。

  - コンピューターの RTC ローカルの読み取り専用管理者グループのメンバーシップを更新する

  - ウォッチャーノード構成ファイルをインストールする

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a>RTC ローカルの読み取り専用管理者グループのメンバーシップを更新しています

ウォッチャーノードが境界ネットワークの外側にある場合は、ネットワークサービスアカウントを、ウォッチャーノードコンピューターの RTC ローカルの読み取り専用管理者グループに追加する必要があります。 これを行うには、ウォッチャーノードで次の手順を実行します。

1.  [**スタート**] をクリックし、[**コンピューター**] を右クリックして、[**管理**] をクリックします。

2.  サーバーマネージャーで、[**構成**] を展開し、[**ローカルユーザーとグループ**] を展開して、[**グループ**] をクリックします。

3.  [グループ] ウィンドウで、[ **RTC ローカル読み取り専用管理者**] をダブルクリックします。

4.  [ **RTC のローカルの読み取り専用管理者のプロパティ**] ダイアログボックスで、[**追加**] をクリックします。

5.  [**ユーザー、コンピューター、サービスアカウント、またはグループの選択**] ダイアログボックスで、[**場所**] をクリックします。

6.  [**場所**] ダイアログボックスで、ウォッチャーノードのコンピューターの名前を選び、[ **OK]** をクリックします。

7.  [**選択するオブジェクト名を入力してください**] ボックスに「**ネットワークサービス**」と入力し、[ **OK**] をクリックします。

8.  [ **RTC のローカルの読み取り専用管理者のプロパティ**] ダイアログボックスで、[ **OK**] をクリックし、[**サーバーマネージャー**] を閉じます。

監視ノード コンピューターを再起動します。

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a>ウォッチャーノード構成ファイルのインストール

ウォッチャーノードのコンピューターが再起動したら、次の手順として、Watchernode ファイルを実行します。 このファイルを実行するには、[**スタート**]、[**すべてのプログラム**]、[ **lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックして、lync server 2013 管理シェルを開きます。 Lync Server 管理シェルで、次のコマンドを入力し、enter キーを押します (Watchernode のコピーの実際のパスを確認してください)。

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> 前に説明したように、Watchernode はコマンドウィンドウから実行することもできます。 コマンド ウィンドウを開くには、[<STRONG>スタート</STRONG>] メニューをクリックし、[<STRONG>コマンド プロンプト</STRONG>] を右クリックして、[<STRONG>管理者として実行</STRONG>] をクリックします。 コマンドウィンドウが開いたら、前に示したのと同じコマンドを入力します。



</div>

監視ノードを信頼されたアプリケーション プールとしてセットアップできない場合はいつでも、ネゴシエート モードが使用されます。このモードでは、管理者が監視ノードのテスト ユーザー パスワードを管理する必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

