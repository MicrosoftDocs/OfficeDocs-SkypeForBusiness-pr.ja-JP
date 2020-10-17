---
title: 併置された仲介サーバーをスタンドアロンの仲介サーバーに移行する (オプション)
description: 併置された仲介サーバーをスタンドアロンの仲介サーバーに移行します (オプション)。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e99eb445e8377a52901f54f52ca3933babe15571
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559423"
---
# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a>併置された仲介サーバーをスタンドアロンの仲介サーバーに移行する (オプション)

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-19_

次の手順を使用して、Standard Edition サーバーまたはフロントエンド プールに併置された仲介サーバーを単一サイト展開用のスタンドアロン仲介サーバーへ移行します。

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a>併置された仲介サーバーをスタンドアロンの仲介サーバーに移行するには

1.  トポロジ ビルダーで既存のトポロジを開きます。

2.  左側のウィンドウで、[**仲介プール**] に移動します。

3.  [**仲介プール**] を右クリックし、[**新しい仲介サーバー**] を選択します。

4.  [**新しい仲介プールの定義**] ページで、新しい仲介サーバー プールの FQDN を提供します。さらに、このプールを単一サーバー プールまたは複数サーバー プールとするかを選択し、[**次へ**] をクリックします。

5.  新しい仲介サーバーによる着信通話のルーティング先となる次ホップ フロントエンド サーバー プールを選択し、[**次へ**] をクリックします。

6.  仲介サーバーで使用されるエッジ プールを選択し、[**次へ**] をクリックします。

7.  [**PSTN ゲートウェイの指定**] ページで、以前の PSTN ゲートウェイを仲介サーバーと関連付けます。ゲートウェイを選択し、[**追加**] をクリックします。

8.  [**完了**] をクリックして、**新しい仲介プールの定義**ウィザードを閉じます。

9.  [ **トポロジビルダー**] で、最上位ノードの [ **Lync Server 2013**] を選択します。

10. [**操作**] ウィンドウで、[**トポロジの公開**] を選択してウィザードを完了します。

11. 「展開」のドキュメントの「 [install The 仲介 server For Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) 」の手順に従って、新しい仲介サーバーにファイルをインストールします。

12. 仲介サーバーにファイルをインストールした後、トポロジ ビルダーに戻り、左側のウィンドウでプールに移動します。

13. プールを右クリックし、[**プロパティの編集**] を選択します。

14. [**仲介サーバー**] で、[**併置された仲介サーバーが有効**] チェック ボックスをオフにし、[**OK**] をクリックします。

15. [ **トポロジビルダー**] で、最上位ノードの [ **Lync Server 2013**] を選択します。

16. [**操作**] メニューで、[**トポロジの公開**] を選択してウィザードを完了します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

