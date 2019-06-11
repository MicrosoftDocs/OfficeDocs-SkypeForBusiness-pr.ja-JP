---
title: 'Lync Server 2013: レジストラー構成の設定を作成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create Registrar configuration settings
ms:assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182601(v=OCS.15)
ms:contentKeyID: 48185758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 624dc1cfcc8ba8de1f749d6a1a50de9989783070
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-registrar-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 でレジストラー構成設定を作成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-03-17_

レジストラーを使用してプロキシ サーバーの認証方式を構成できます。指定する認証プロトコルにより、プール内のサーバーがクライアントに発行するチャレンジの種類が決まります。使用可能なプロトコルは以下のとおりです。

  - **Kerberos**   パスワードベースの最強の認証スキームはクライアントで利用できますが、通常は、キー配布センター (Kerberos ドメインコントローラー) へのクライアント接続が必要なため、エンタープライズクライアントでのみ利用できます。 この設定は、サーバーでエンタープライズのクライアントのみを認証する場合に適しています。

  - **NTLM**   このパスワードベースの認証は、パスワードに対するチャレンジ応答ハッシュスキームを使用するクライアントで利用できます。 これは、リモート ユーザーなど、キー配布センター (Kerberos ドメイン コントローラー) に接続できないクライアントの認証で使用できる唯一のクライアント認証方式です。 サーバーでリモート ユーザーのみの認証処理を行う場合は、NTLM を選択してください。

  - **証明書の認証**   サーバーが lync Phone Edition クライアント、一般的なエリア電話、lync 2013、lync Windows ストアアプリから証明書を取得する必要がある場合の、新しい認証方法です。 Lync Phone Edition クライアントでは、ユーザーがサインインして、暗証番号 (PIN) を指定して正常に認証されると、Lync Server 2013 は電話に対して SIP URI をプロビジョニングし、Lync Server の署名された証明書またはユーザー証明書をプロビジョニングします。これにより、Joe (Ex: SN=joe@contoso.com) が電話に対して識別されます。 この証明書は、レジストラー サービスと Web サービスでの認証に使用されます。

<div>


> [!NOTE]  
> サーバーがリモートとエンタープライズ両方のクライアント認証をサポートする場合は、Kerberos と NTLM の両方を有効にすることをお勧めします。エッジ サーバーと内部サーバーは通信して、NTLM 認証のみがリモート クライアントに提供されるようにします。これらのサーバーで Kerberos のみが有効な場合、リモート ユーザーを認証できません。エンタープライズ ユーザーはサーバーに対しても認証を行い、Kerberos が使用されます。<BR>Lync Windows ストアアプリクライアントを使用する場合は、証明書の認証を有効にする必要があります。



</div>

以下の手順に従って新しいレジストラーを作成します。

<div>

## <a name="to-create-new-registrar-configuration-settings"></a>レジストラー構成設定を作成するには

1.  RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Lync Server 2013 を展開したネットワーク上のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

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

