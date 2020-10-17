---
title: 'Lync Server 2013: 新しい Web サービス構成設定の作成'
description: 'Lync Server 2013: 新しい Web サービス構成設定を作成します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create new Web Service configuration settings
ms:assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182605(v=OCS.15)
ms:contentKeyID: 48185801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc66b0c8f394260fbe30e444f800640c774b6bcf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553963"
---
# <a name="create-new-web-service-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 で新しい Web サービス構成設定を作成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

[ **Web サービス** ] ページを使用して、Lync Server 2013 に関連する web サーバーと web サービスにアクセスするための認証方法を構成できます。

以下の手順に従って新しい Web サービス ポリシーを作成します。

<div>

## <a name="to-create-new-web-service-configuration-settings"></a>新しい web サービス構成設定を作成するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**Web サービス**] をクリックします。

4.  [**Web サービス**] ページで、[**新規作成**] をクリックし、次のいずれかを実行します。
    
      - サイトの Web サービスを構成するには、[**サイト構成**] をクリックします。 [**サイトの選択**] で、Web サービス ポリシーを適用するサイトをクリックし、[**OK**] をクリックします。
    
      - プールの Web サービスを構成するには、[**プール構成**] をクリックします。 [**サービスの選択**] で、Web サービス ポリシーを適用するサービスをクリックし、[**OK**] をクリックします。

5.  [**新規 Web サービス設定**] の [**統合 Windows 認証**] で、[**ネゴシエート**]、[**統合 Windows 認証**]、または [**なし**] を選択します。

6.  クライアントの機能および環境のサポート状況に応じて、次の中から 1 つ以上選択します。
    
      - [**PIN 認証を有効にする**]。PIN 番号を使用してクライアントが承認されるようにします。
    
      - [**証明書認証を有効にする**]。プール内のサーバーは、クライアントに対して証明書を発行します。
    
      - [**証明書チェーンのダウンロードを有効にする**]。認証証明書を与えられたサーバーがその証明書の証明書チェーンをダウンロードできるようにします。

7.  [**確定**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

