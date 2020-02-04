---
title: ユーザー レプリケーションの完了の確認
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
ms.openlocfilehash: bc6d8100a7bd0d348c3414da627584bae8697a1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a>ユーザー レプリケーションの完了の確認

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-28_

**CsLegacyUser**コマンドレットを実行しているときに、最初のレプリケーションが完了していないため、Active Directory ドメインサービス (AD DS) と Lync Server 2013 データベースの同期が無効になっているために、エラーが発生する可能性があります。 Lync Server 2013 ユーザーレプリケーターサービスの初回の同期が正常に完了するまでにかかる時間は、Lync Server 2013 プールをホストしている Active Directory フォレストでホストされているドメインコントローラーの数によって異なります。 Lync server 2013 ユーザーレプリケーターサービスの初期同期処理は、Lync Server 2013 フロントエンドサーバーが初めて起動されたときに発生します。 その後、同期はユーザーレプリケーターの間隔に基づいています。 次の手順を実行して、 **CsLegacyUser**コマンドレットを実行する前にユーザーレプリケーションが完了していることを確認します。

<div>

## <a name="to-verify-that-user-replication-has-completed"></a>ユーザーの複製が完了したことを確認するには

1.  Lync Server 2013 フロントエンドサーバーから、[**スタート**] メニューをクリックし、[**実行**] をクリックします。

2.  **Eventvwr.exe**と入力して、[ **OK]** をクリックします。

3.  イベントビューアーで [**アプリケーションとサービスログ**] をクリックして展開し、[Lync Server] を選択します。

4.  **操作**ウィンドウで、[**現在のログをフィルター**] をクリックします。

5.  [**イベントソース**] ボックスの一覧の [ **LS ユーザーレプリケーター**] をクリックします。

6.  ** \<すべてのイベント id\> **に**30024**と入力し、[ **OK]** をクリックします。

7.  [フィルター処理されたイベント] ボックスの一覧の **[全般**] タブで、ユーザーの複製が正常に完了したことを示すエントリを探します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

