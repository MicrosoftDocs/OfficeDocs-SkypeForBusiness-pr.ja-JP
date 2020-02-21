---
title: 新しい Lync Server 2013 仲介サーバーを使用するように音声ルートを変更する
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
ms.openlocfilehash: b4998057543f6695104ecbe759135b6735160c23
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a>新しい Lync Server 2013 仲介サーバーを使用するように音声ルートを変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-28_

この手順では、従来の Office Communications Server 2007 R2 仲介サーバーではなく、Lync Server 2013 仲介サーバーを使用するように音声ルートを変更します。

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a>新しい仲介サーバーを使用するように音声ルートを変更するには

1.  Lync Server 2013 コントロール パネル

2.  左ウィンドウで、[**音声のルーティング**]、[**ルート**] の順に選択します。

3.  [**新規**] をクリックして、新しい音声ルートを作成します。

4.  次のフィールドに入力します。
    
      - [**名前**]: 音声ルートのわかりやすい名前を入力します。このドキュメントでは、**W15PSTNRoute** を使用します。
    
      - [**説明**]: 音声ルートの簡単な説明を入力します。

5.  [**関連付けられているゲートウェイ**] より前の残りのすべてのセクションをスキップします。[**追加**] をクリックします。新しいデフォルト ゲートウェイを選択し、[**OK**] をクリックします。

6.  [**関連付けられている PSTN 使用法**] で、[**選択**] をクリックします。

7.  [**PSTN 使用法レコードの選択**] ページで、レコードの名前を選択し、[**OK**] をクリックします。

8.  [**新規音声ルート**] ページで、[**OK**] をクリックして [**音声ルート**] を作成します。

9.  [**音声のルーティング**] ページで、[**ルート**] を選択します。

10. 新しく作成されたルートを一覧の先頭に移動し、[**コミット**] を選択します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

