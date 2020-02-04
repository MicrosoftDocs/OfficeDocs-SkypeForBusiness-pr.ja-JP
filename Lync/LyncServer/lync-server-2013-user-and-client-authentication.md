---
title: 'Lync Server 2013: ユーザーとクライアントの認証'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User and client authentication for Lync Server 2013
ms:assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481132(v=OCS.15)
ms:contentKeyID: 59893868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c9c91f1b8355c95ceb3deae5f07e5c95710d036
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-and-client-authentication-for-lync-server-2013"></a>Lync Server 2013 のユーザーとクライアントの認証

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-11-11_

信頼されたユーザーとは、Microsoft Lync Server 2013 の信頼できるサーバーによって資格情報が認証されたユーザーのことです。 通常、このサーバーは Standard Edition server、Enterprise Edition のフロントエンドサーバー、またはディレクターです。 Lync Server 2013 は、ユーザー資格情報の単一の信頼できるバックエンドリポジトリとして Active Directory ドメインサービスに依存します。

認証では、ユーザーの資格情報が信頼されたサーバーに渡されます。 Lync Server 2013 では、ユーザーの状態と場所に応じて、次の認証プロトコルが使用されます。

  - Active Directory 資格情報を持つ内部ユーザー用の**MIT Kerberos バージョン5セキュリティプロトコル**。 Kerberos には Active Directory ドメインサービスへのクライアント接続が必要です。このため、会社のファイアウォール以外のクライアントを認証するために使用することはできません。

  - 企業ファイアウォール外のエンドポイントから接続している Active Directory 資格情報を持つユーザーの**NTLM プロトコル**。 アクセスエッジサービスは、ログイン要求をディレクター (存在する場合) または認証用のフロントエンドサーバーに渡します。 アクセスエッジサービス自体では、認証は実行されません。
    
    <div>
    

    > [!NOTE]  
    > NTLM プロトコルは Kerberos ほど攻撃に対して強くないので、NTLM の使用を最小限にしている組織もあります。 その結果、Lync Server 2013 へのアクセスは、VPN または DirectAccess 接続経由で接続されている内部またはクライアントに制限されることがあります。

    
    </div>

  - **ダイジェスト プロトコル**: いわゆる匿名ユーザーに対して使用されます。匿名ユーザーは、有効な Active Directory の資格情報は持たないが、社内会議に招待され、有効な会議キーを持つ外部ユーザーです。ダイジェスト認証は、他のクライアント操作には使用されません。

Lync Server 2013 認証は、次の2つのフェーズで構成されます。

1.  クライアントとサーバーの間に、セキュリティ アソシエーションが確立されます。

2.  クライアントとサーバーは、既存のセキュリティ アソシエーションを使用して、送信するメッセージに署名し、受信するメッセージを検証します。サーバーで認証が有効になっている場合、クライアントからの認証されていないメッセージは受信されません。

ユーザーの信用情報は、ユーザー ID 自体ではなく、ユーザーから送信される各メッセージに添付されます。サーバーは、各メッセージについて、送信元ユーザーの資格情報が有効であるかどうか確認します。ユーザーの資格情報が有効な場合、そのメッセージを受け取る最初のサーバーだけでなく、信頼済みサーバー クラウドに属する他のすべてのサーバーで、そのメッセージが受信できるようになります。

フェデレーション パートナーが発行した有効な資格情報を持つユーザーは信頼されますが、これらのユーザーに対しては、内部ユーザーに与えられる権限のうち一部の使用を、必要に応じて制限できます。

ICE プロトコルおよび TURN プロトコルでも、IETF TURN RFC に記載されているとおり、ダイジェスト認証が使用されます。

クライアント証明書は、ユーザーが Lync Server 2013 による認証を行うための代替手段を提供します。 ユーザー名とパスワードを提供する代わりに、ユーザーは証明書と、暗号化認証の解決に必要な証明書に対応する秘密キーを持ちます。 (この証明書には、ユーザーを識別するサブジェクト名またはサブジェクトの別名が必要です。また、Lync Server 2013 を実行しているサーバーによって信頼されているルート CA によって発行され、失効していない場合は、証明書の有効期間内に存在する必要があります)。認証するには、個人識別番号 (PIN) を入力する必要があります。 証明書は、Microsoft Lync 2013 Phone Edition を実行している電話やその他のデバイスで、ユーザー名やパスワードの入力が困難な場合に特に便利です。

</div>

<span> </span>

</div>

</div>

</div>

