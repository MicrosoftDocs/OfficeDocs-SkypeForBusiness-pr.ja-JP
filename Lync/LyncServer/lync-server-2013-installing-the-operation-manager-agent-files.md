---
title: 'Lync Server 2013: Operation Manager エージェントファイルのインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Operation Manager agent files
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205345(v=OCS.15)
ms:contentKeyID: 48185692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7b658475e911d300d4ec8f6c15320e69ab71e15
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42118850"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a>Lync Server 2013 での Operation Manager エージェントファイルのインストール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-20_

Operations Manager エージェントファイルをコンピューターにインストールするには、次の手順を実行します。

1.  System Center セットアップメディアで、 **setupom.exe**をダブルクリックします。

2.  System Center Operation Manager セットアップで、[ **Operations Manager エージェントのインストール**] をクリックします。

3.  System Center Setup ウィザードの [ **System Center Operations Manager セットアップウィザードへようこそ**] ページで、[**次へ**] をクリックします。

4.  [インストール**先フォルダー** ] ページで、Operations Manager エージェントファイルをインストールするフォルダーを選択し、[**次へ**] をクリックします。

5.  [**管理グループの構成**] ページで、[**管理グループ情報の指定**] を選択し、[**次へ**] をクリックします。

6.  [管理**グループの構成**] ページで、[管理**グループ名**] ボックスに operations manager 管理グループの名前を入力し、[**管理サーバー** ] ボックスに、operations manager サーバーのホスト名 (たとえば、「atl-scom-001」) を入力します。 Operations Manager で使用されるポート番号を変更した場合は、[管理サーバーのポート] ボックスに新しいポート番号を入力します。 それ以外の場合は、ポートを既定値の5723のままにして、[**次へ**] をクリックします。

7.  [**エージェントアクションアカウント**] ページで、[**ローカルシステム**] を選択し、[**次へ**] をクリックします。

8.  [ **Microsoft update** ] ページで、[ **microsoft update を使用しない**] を選択し、[**次へ**] をクリックします。

9.  [**インストールの準備完了**] ページで、[**インストール**] をクリックします。

10. [ **System Center Operations Manager セットアップウィザードを完了**しています] ページで、[**完了**] をクリックします。

11. **[終了]** をクリックします。

System Center 2007 R2 を使用している場合は、[**スタート**]、[**すべてのプログラム**]、[ **System Center Operations manager 2007 R2**]、[ **operations manager シェル**] の順にクリックして、エージェントが作成されたことを確認できます。 Operations Manager シェルで、次の Windows PowerShell コマンドを入力し、enter キーを押します。

    Get-Agent 

すべての Operations Manager エージェントの一覧が画面に表示されます。

System Center 2012 を使用している場合は、Operations 2012 Manager シェルから次のコマンドを実行します。

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

