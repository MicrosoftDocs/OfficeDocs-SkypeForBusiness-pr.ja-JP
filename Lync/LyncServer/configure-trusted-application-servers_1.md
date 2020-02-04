---
title: 信頼済みアプリケーション サーバーの構成
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
ms.openlocfilehash: 92e7f2c808e9ea5a3e8dfbf3010715c86e02596e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>信頼済みアプリケーション サーバーの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-04_

混在環境では、従来の Office Communications Server トポロジを Lync Server 2013 と統合した後に新しい信頼できるアプリケーションサーバーを作成し、トポロジビルダーを使用して新しい信頼されたアプリケーションサーバーを定義する場合は、次のホッププールをに設定する必要があります。Lync Server 2013 プール。 統合された環境では、従来の Office Communications Server プールと Lync Server 2013 プールの両方がドロップダウンリストに表示されます。 従来のプールの選択はサポートされて*いません*。

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a>信頼されているアプリケーションサーバーを作成するときに、次ホップとして Lync Server 2013 を選ぶには

1.  トポロジビルダーで既存のトポロジを開きます。

2.  左側のウィンドウで、[**信頼されたアプリケーションサーバー** ] を右クリックし、[**新しい信頼できるアプリケーションプール**] をクリックします。

3.  信頼されているアプリケーションプールの**プール FQDN**を入力し、単一サーバー展開と複数サーバーのどちらの展開にするかを選択します。

4.  [ **次へ**] をクリックします。

5.  **[次ホップの選択**] ページで、一覧から Lync Server 2013 フロントエンドプールを選びます。
    
    ![[新しい信頼されたアプリケーションプールの定義] ダイアログ](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "[新しい信頼されたアプリケーションプールの定義] ダイアログ")  

6.  [**完了**] をクリックします。

7.  トップノードの**Lync サーバー**を選択し、[**操作**] ウィンドウで [**発行**] を選択します。

8.  信頼された**アプリケーションプール**が正常に作成され、正しいフロントエンドプールに関連付けられていることを確認します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

