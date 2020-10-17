---
title: 'Lync Server 2013: レジストラー構成設定の作成'
description: 'Lync Server 2013: レジストラーの構成設定を作成します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Registrar configuration settings
ms:assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182601(v=OCS.15)
ms:contentKeyID: 48185758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ada10302b3c2319e0f713ce2d3bea00b6fed126
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548703"
---
# <a name="create-registrar-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 でレジストラーの構成設定を作成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-17_

レジストラーを使用してプロキシ サーバーの認証方式を構成できます。 指定する認証プロトコルにより、プール内のサーバーがクライアントに発行するチャレンジの種類が決まります。 使用可能なプロトコルは以下のとおりです。

  - **Kerberos**    これは、クライアントが使用できる最強のパスワードベースの認証スキームですが、通常は、キー配布センター (Kerberos ドメインコントローラー) へのクライアント接続を必要とするため、通常はエンタープライズクライアントのみで使用できます。 この設定は、サーバーでエンタープライズのクライアントのみを認証する場合に適しています。

  - **NTLM**    これは、パスワードでチャレンジ応答ハッシュスキームを使用するクライアントが使用できるパスワードベースの認証です。 これは、リモート ユーザーなど、キー配布センター (Kerberos ドメイン コントローラ) に接続できないクライアントの認証で使用できる唯一のクライアント認証方式です。 サーバーでリモート ユーザーのみの認証処理を行う場合は、NTLM を選択してください。

  - **証明書認証**    これは、サーバーが Lync Phone Edition クライアント、共通領域電話、Lync 2013、lync Windows ストアアプリから証明書を取得する必要がある場合の新しい認証方法です。 Lync Phone Edition クライアントでは、ユーザーがサインインして、暗証番号 (PIN) を提供することによって正常に認証されると、Lync Server 2013 は電話に対して SIP URI をプロビジョニングし、Lync Server 署名入りの証明書または Joe (Ex: SN=joe@contoso.com) を識別するユーザー証明書を電話にプロビジョニングします。 この証明書は、レジストラー サービスと Web サービスでの認証に使用されます。

<div>


> [!NOTE]  
> サーバーがリモートとエンタープライズ両方のクライアント認証をサポートする場合は、Kerberos と NTLM の両方を有効にすることをお勧めします。 エッジ サーバーと内部サーバーは通信して、NTLM 認証のみがリモート クライアントに提供されるようにします。 これらのサーバーで Kerberos のみが有効な場合、リモート ユーザーを認証できません。 エンタープライズ ユーザーはサーバーに対しても認証を行い、Kerberos が使用されます。<BR>Lync Windows ストアアプリクライアントを使用する場合は、証明書認証を有効にする必要があります。



</div>

以下の手順に従って新しいレジストラーを作成します。

<div>

## <a name="to-create-new-registrar-configuration-settings"></a>新しいレジストラーの構成設定を作成するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**レジストラー**] をクリックします。

4.  [**レジストラー**] ページで [**新規作成**] をクリックします。

5.  [**サービスの選択**] で、レジストラーを適用するサービスをクリックし、[**OK**] をクリックします。

6.  [**新規レジストラー設定**] で、クライアントの機能および環境のサポート状況に応じて、次の中から 1 つ以上選択します。
    
      - [**Kerberos 認証を有効にする**]。プール内のサーバーは、Kerberos 認証を使用してチャレンジを発行します。
    
      - [**NTLM 認証を有効にする**]。プール内のサーバーは、NTLM 認証を使用してチャレンジを発行します。
    
      - [**証明書認証を有効にする**]。プール内のサーバーは、クライアントに対して証明書を発行します。

7.  [**確定**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

