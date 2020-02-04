---
title: 'Lync Server 2013: 既存の Web サービスの構成設定を変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify existing Web Service configuration settings
ms:assetid: bd9c7aa5-d31c-4fab-b31d-8baae26b1296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182580(v=OCS.15)
ms:contentKeyID: 48185272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11bd7f4629d4a3cf0f356a47760810e380af7deb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737137"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-existing-web-service-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 で既存の Web サービス構成の設定を変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

**Web サービス**ページを使用して、Lync Server 2013 関連の web サーバーと web サービスにアクセスするための認証方法を構成することができます。

既存の Web サービス ポリシーを変更するには、次の手順を実行します。

<div>

## <a name="to-modify-existing-web-service-configuration-settings"></a>既存の Web サービス構成設定を変更するには

1.  RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Lync Server 2013 を展開したネットワーク上のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**Web サービス**] をクリックします。

4.  [**Web サービス**] ページで、構成をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。

5.  [**Web サービス設定の編集**] の [**統合 Windows 認証**] で、[**ネゴシエート**]、[**統合 Windows 認証**]、または [**なし**] を選択します。

6.  クライアントの機能および環境のサポート状況に応じて、次の中から 1 つ以上選択します。
    
      - [**PIN 認証を有効にする**]。PIN 番号を使用してクライアントが承認されるようにします。
    
      - [**証明書認証を有効にする**]。プール内のサーバーは、クライアントに対して証明書を発行します。
    
      - [**証明書チェーンのダウンロードを有効にする**]。認証証明書を与えられたサーバーがその証明書の証明書チェーンをダウンロードできるようにします。

7.  [**確定**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 コントロールパネルで認証を構成する](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

