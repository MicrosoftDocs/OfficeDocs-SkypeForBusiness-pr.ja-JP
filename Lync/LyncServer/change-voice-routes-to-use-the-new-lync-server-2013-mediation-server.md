---
title: 新しい Lync Server 2013 仲介サーバーを使用するようにボイスルートを変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change voice routes to use the new Lync Server 2013 Mediation Server
ms:assetid: acd487b3-377c-46bf-9f71-fe6152002664
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205162(v=OCS.15)
ms:contentKeyID: 48185069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40f9bed4262adcabdb23e5b5b85e7de43292d18b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a>新しい Lync Server 2013 仲介サーバーを使用するようにボイスルートを変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-28_

この手順では、従来の Office Communications Server 2007 R2 仲介サーバーではなく、Lync Server 2013 仲介サーバーを使用するように、ボイスルートを変更します。

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a>新しい仲介サーバーを使用するようにボイスルートを変更するには

1.  Lync Server 2013 コントロール パネル

2.  左側のウィンドウで、[**音声ルーティング**]、[Route] の**順**に選択します。

3.  [**新規**] をクリックして、新しいボイスルートを作成します。

4.  次のフィールドに入力します。
    
      - **名前**: ボイスルートのわかりやすい名前を入力します。 このドキュメントでは、 **W15PSTNRoute**を使用します。
    
      - [ **Description (説明**): ボイスルートの短い説明を入力します。

5.  **関連するゲートウェイ**に到達するまで、残りのすべてのセクションをスキップします。 [**追加**] をクリックします。 新しいデフォルトゲートウェイを選択して、[ **OK]** をクリックします。

6.  [**関連する PSTN 使用**] で、[**選択**] をクリックします。

7.  **[PSTN 使用状況レコードの選択**] ページからレコード名を選び、[ **OK]** をクリックします。

8.  [**新しいボイスルーティング**] ページで [ **OK** ] をクリックして、**ボイスルート**を作成します。

9.  [**音声ルーティング**] ページで、[**ルーティング**] を選びます。

10. 新しく作成されたルートを一覧の一番上に移動して、[**コミット**] を選びます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

