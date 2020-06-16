---
title: 信頼されたアプリケーション サーバーを構成する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb71833e782378f0d959fcbfcf5647235252e594
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>信頼されたアプリケーション サーバーを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-11_

混在環境では、信頼されたアプリケーションサーバーを新たに作成する場合は、次ホッププールを Lync Server 2013 プールに設定する必要があります。 混在環境では、ドロップダウンリストに従来の Lync Server 2010 プールと Lync Server 2013 プールの両方が表示されます。 従来のプールを選択することはできません。

**信頼されたアプリケーションサーバーを作成するときに、次ホップとして Lync Server 2013 を選択する**

1.  トポロジ ビルダーを開きます。

2.  左側のウィンドウで、[**信頼済みアプリケーション サーバー**] を右クリックし、[**新しい信頼済みアプリケーション プール**] をクリックします。

3.  信頼済みアプリケーション プールの [**プールの FQDN**] を入力し、単一サーバーにするか複数サーバーにするかを選択します。

4.  [**次へ**] をクリックします。

5.  [**次ホップの選択**] ページで、リストから Lync Server 2013 フロントエンドプールを選択します。

6.  [**完了**] をクリックします。

7.  最上位の [**Lync Server**] ノードを選択し、[**操作**] メニューの [**公開**] を選択します。
    
    **信頼済みアプリケーション プール**が正しく作成されていることと、適切なフロントエンド プールに関連付けられていることを確認します。

</div>

<span> </span>

</div>

</div>

</div>

