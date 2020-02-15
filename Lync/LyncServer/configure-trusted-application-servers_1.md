---
title: 信頼されたアプリケーション サーバーを構成する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204865(v=OCS.15)
ms:contentKeyID: 48184056
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7e74cba866a7353890bb47de745e5e525d43963
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>信頼されたアプリケーション サーバーを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-04_

混在環境では、従来の Office Communications Server トポロジと Lync Server 2013 をマージした後で、新しい信頼されたアプリケーションサーバーを作成し、トポロジビルダーを使用して新しい信頼されたアプリケーションサーバーを定義する場合は、次ホッププールをに設定する必要があります。Lync Server 2013 プール。 マージされた環境では、従来の Office Communications Server プールと Lync Server 2013 プールの両方がドロップダウンリストに表示されます。 従来のプールの選択はサポートされていません**。

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a>信頼されたアプリケーションサーバーの作成時に Lync Server 2013 を次ホップとして選択するには

1.  トポロジ ビルダーで既存のトポロジを開きます。

2.  左側のウィンドウで、[**信頼済みアプリケーション サーバー**] を右クリックし、[**新しい信頼済みアプリケーション プール**] をクリックします。

3.  信頼済みアプリケーション プールの [**プールの FQDN**] を入力し、単一サーバーの展開にするか複数サーバーの展開にするかを選択します。

4.  [**次へ**] をクリックします。

5.  [**次ホップの選択**] ページで、リストから Lync Server 2013 フロントエンドプールを選択します。
    
    ![[信頼されたアプリケーションプールの新規定義] ダイアログ](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "[信頼されたアプリケーションプールの新規定義] ダイアログ")  

6.  [**完了**] をクリックします。

7.  上位ノードの [**Lync Server**] を選択し、[**操作**] ウィンドウで [**公開**] を選択します。

8.  [**信頼済みアプリケーション プール**] が正常に作成され、適切なフロントエンド プールに関連付けられたことを確認します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

