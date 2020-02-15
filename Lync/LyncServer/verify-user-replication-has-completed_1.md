---
title: ユーザーのレプリケーションが完了したことを確認する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6433c1e88edf69b957047b9dc405df392e5ec104
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036195"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a>ユーザーのレプリケーションが完了したことを確認する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-28_

**Move-cslegacyuser**コマンドレットを実行しているときに、最初のレプリケーションが完了していないため、Active Directory ドメインサービス (AD DS) と Lync Server 2013 データベースの間のユーザー情報が同期されていないために障害が発生することがあります。 Lync Server 2013 のユーザーレプリケーターサービスの初期同期が正常に完了するまでにかかる時間は、Lync Server 2013 プールをホストしている Active Directory フォレスト内でホストされているドメインコントローラーの数によって異なります。 Lync Server 2013 のユーザーレプリケーターサービスの初期同期処理は、Lync Server 2013 フロントエンドサーバーが初めて起動されたときに発生します。 それ以降は、ユーザー レプリケーターの間隔に基づいて同期が行われます。 **Move-CsLegacyUser** コマンドレットを実行する前に次の手順を実行し、ユーザーのレプリケーションが完了していることを確認します。

<div>

## <a name="to-verify-that-user-replication-has-completed"></a>ユーザーのレプリケーションが完了していることを確認するには

1.  Lync Server 2013 フロントエンドサーバーから、[**スタート**] メニューをクリックし、[**実行**] をクリックします。

2.  「**eventvwr.exe**」と入力し、[**OK**] をクリックします。

3.  イベント ビューアーで、[**アプリケーションとサービス ログ**] をクリックして展開し、[Lync Server] を選択します。

4.  [**操作**] ウィンドウで [**現在のログをフィルター**] をクリックします。

5.  [**イベント ソース**] ボックスの一覧の [**LS User Replicator**] をクリックします。

6.  ** \<すべてのイベント id\> **に**30024**と入力し、[ **OK]** をクリックします。

7.  フィルターが適用されたイベントの一覧の [**全般**] タブで、ユーザーのレプリケーションが正常に完了したことを示す項目を探します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

