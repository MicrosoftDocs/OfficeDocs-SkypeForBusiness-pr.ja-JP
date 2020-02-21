---
title: ユーザーのレプリケーションが完了したことを確認する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48183441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96e8df3cb77e6b53596ae17e15fed6b05243a99a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a>ユーザーのレプリケーションが完了したことを確認する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-17_

最初のレプリケーションが完了していないため、Active Directory ドメインサービス (AD DS) と Lync Server 2013 データベース間のユーザー情報が同期されていないために、 **csuser**コマンドレットを実行しているときにエラーが発生することがあります。 Lync Server 2013 のユーザーレプリケーターサービスの初期同期が正常に完了するまでにかかる時間は、Lync Server 2013 プールをホストしている Active Directory フォレスト内でホストされているドメインコントローラーの数によって異なります。 Lync Server 2013 のユーザーレプリケーターサービスの初期同期処理は、Lync Server 2013 フロントエンドサーバーが初めて起動されたときに発生します。 その後、この同期はユーザー レプリケーターの間隔に基づいて行われます。 **Move-CsUser** コマンドレットを実行する前に、次の手順を実行して、ユーザーのレプリケーションが完了していることを確認してください。

<div>

## <a name="to-verify-user-replication-has-completed"></a>ユーザーのレプリケーションが完了したことを確認するには

1.  トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  [**スタート**] メニューをクリックし、[**ファイル名を指定して実行**] をクリックします。

3.  「**eventvwr.exe**」と入力し、[**OK**] をクリックします。

4.  イベント ビューアーで、[**アプリケーションとサービス ログ**] をクリックして展開し、[Lync Server] を選択します。

5.  [**操作**] ウィンドウで [**現在のログをフィルター**] をクリックします。

6.  [**イベント ソース**] ボックスの一覧の [**LS User Replicator**] をクリックします。

7.  ** \<すべてのイベント id\> **に**30024**と入力し、[ **OK]** をクリックします。

8.  フィルターが適用されたイベントの一覧の [**全般**] タブで、ユーザーのレプリケーションが正常に完了したことを示す項目を探します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

