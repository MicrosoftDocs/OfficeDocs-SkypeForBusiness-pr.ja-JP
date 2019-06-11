---
title: 信頼済みアプリケーション サーバーの構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a27dbab3e954c96a07739f8a214ae7d1ec87ace
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>信頼済みアプリケーション サーバーの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-11_

混在環境では、新しい信頼できるアプリケーションサーバーを作成する場合は、次ホッププールを Lync Server 2013 プールとして設定する必要があります。 混在環境では、従来の Lync Server 2010 プールと Lync Server 2013 プールの両方がドロップダウンリストに表示されます。 従来のプールの選択はサポートされていません。

**信頼できるアプリケーションサーバーを作成するときに、[Lync Server 2013 (次ホップ)] を選択します。**

1.  トポロジビルダーを開きます。

2.  左側のウィンドウで、[**信頼されたアプリケーションサーバー** ] を右クリックし、[**新しい信頼できるアプリケーションプール**] をクリックします。

3.  信頼されているアプリケーションプールの**プール FQDN**を入力し、それが単一サーバーか複数サーバーかを選択します。

4.  [ **次へ**] をクリックします。

5.  **[次ホップの選択**] ページで、一覧から Lync Server 2013 フロントエンドプールを選びます。

6.  [**完了**] をクリックします。

7.  トップノードの**Lync サーバー**を選択し、[**操作**] メニューの [**発行**] を選択します。
    
    信頼された**アプリケーションプール**が正常に作成され、正しいフロントエンドプールに関連付けられていることを確認します。

</div>

<span> </span>

</div>

</div>

</div>

