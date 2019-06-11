---
title: 'Lync Server 2013: Operation Manager エージェントファイルのインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing the Operation Manager agent files
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205345(v=OCS.15)
ms:contentKeyID: 48185692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb8675e6c75c288e6594e45ecdcc2f65497a047a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a>Lync Server 2013 での Operation Manager エージェントファイルのインストール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-20_

Operations Manager エージェントファイルをコンピューターにインストールするには、次の手順を実行します。

1.  System Center セットアップメディアで、 **SetupOM**をダブルクリックします。

2.  System Center Operation Manager のセットアップで、[ **Operations Manager エージェントのインストール**] をクリックします。

3.  System Center セットアップウィザードの [ **System Center Operations Manager セットアップウィザードへようこそ**] ページで、[**次へ**] をクリックします。

4.  [**インポート先のフォルダー** ] ページで、Operations Manager エージェントファイルをインストールするフォルダーを選び、[**次へ**] をクリックします。

5.  [**管理グループの構成**] ページで、[**管理グループ情報の指定**] を選び、[**次へ**] をクリックします。

6.  [**管理グループの構成**] ページで、[**管理グループ名**] ボックスに operations manager 管理グループの名前を入力し、次に、 **operations manager サーバーのホスト名 (例: atl-scom-001) を入力します。管理サーバー**ボックス。 Operations Manager で使用されているポート番号を変更した場合は、[管理サーバーのポート] ボックスに新しいポート番号を入力します。 それ以外の場合は、ポートを既定値の5723のままにして、[**次へ**] をクリックします。

7.  [**エージェントアクションアカウント**] ページで、[**ローカルシステム**] を選択し、[**次へ**] をクリックします。

8.  [ **Microsoft update** ] ページで、[ **microsoft update を使用しない**] を選び、[**次へ**] をクリックします。

9.  [**インストールの準備ができ**ました] ページで、[**インストール**] をクリックします。

10. **System Center Operations Manager のセットアップウィザードの完了**ページで、[**完了**] をクリックします。

11. [**終了**] をクリックします。

System Center 2007 R2 を使用している場合は、[**スタート**]、[**すべてのプログラム**]、[ **System center Operations manager 2007 R2**]、[ **operations manager Shell**] の順にクリックして、エージェントが作成されていることを確認できます。 In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:

    Get-Agent 

すべての Operations Manager エージェントの一覧が画面に表示されます。

System Center 2012 を使っている場合は、次のコマンドを Operations 2012 Manager シェルから実行します。

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

