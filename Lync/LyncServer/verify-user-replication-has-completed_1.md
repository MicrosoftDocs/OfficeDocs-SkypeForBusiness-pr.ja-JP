---
title: ユーザー レプリケーションの完了の確認
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31bed57b6e24db0ba6f75e323fe311aa4aaf262c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755521"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a>ユーザー レプリケーションの完了の確認

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

6.  Enter キーを押して **\<All Event IDs\>** **30024**と入力し、[ **OK]** をクリックします。

7.  フィルターが適用されたイベントの一覧の [**全般**] タブで、ユーザーのレプリケーションが正常に完了したことを示す項目を探します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

