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
ms.openlocfilehash: 3f32ca61178d6bf15791f81e64279e7f1076828e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530204"
---
# <a name="user-and-client-authentication-for-lync-server-2013"></a>Lync Server 2013 のユーザーとクライアントの認証

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-11-11_

信頼されたユーザーとは、Microsoft Lync Server 2013 の信頼されたサーバーによって認証された資格情報を持つユーザーのことです。 このサーバーは、通常、Standard Edition サーバー、Enterprise Edition フロント エンド サーバー、またはディレクターです。 Lync Server 2013 は、Active Directory ドメインサービスを、ユーザー資格情報の単一の信頼されたバックエンドリポジトリとして利用します。

認証では、ユーザーの資格情報が信頼されたサーバーに渡されます。 Lync Server 2013 は、ユーザーの状態と場所に応じて、次の認証プロトコルを使用します。

  - **MIT Kerberos Version 5 セキュリティ プロトコル**: Active Directory の資格情報を持つ内部ユーザーに対して使用されます。Kerberos では、クライアントが Active Directory ドメイン サービスに接続できる状態であることが必要です。このため、Kerberos は企業のファイアウォールの外側にいるクライアントの認証には使用できません。

  - **NTLM プロトコル**: Active Directory の資格情報を持ち、企業のファイアウォールの外側にあるエンドポイントから接続しているユーザーに対して使用されます。アクセス エッジ サービスによってログオン要求がディレクター (ある場合) またはフロントエンド サーバーに渡され、そこで認証が行われます。アクセス エッジ サービス自体では認証は行われません。
    
    <div>
    

    > [!NOTE]  
    > NTLM プロトコルは Kerberos ほど攻撃に対して強くないので、NTLM の使用を最小限にしている組織もあります。 そのため、Lync Server 2013 へのアクセスは、VPN または DirectAccess 接続を介して接続された内部またはクライアントに制限される場合があります。

    
    </div>

  - **ダイジェスト プロトコル**: いわゆる匿名ユーザーに対して使用されます。匿名ユーザーは、有効な Active Directory の資格情報は持たないが、社内会議に招待され、有効な会議キーを持つ外部ユーザーです。ダイジェスト認証は、他のクライアント操作には使用されません。

Lync Server 2013 認証は、次の2つのフェーズで構成されます。

1.  クライアントとサーバーの間に、セキュリティ アソシエーションが確立されます。

2.  クライアントとサーバーは、既存のセキュリティ アソシエーションを使用して、送信するメッセージに署名し、受信するメッセージを検証します。サーバーで認証が有効になっている場合、クライアントからの認証されていないメッセージは受信されません。

ユーザーの信用情報は、ユーザー ID 自体ではなく、ユーザーから送信される各メッセージに添付されます。サーバーは、各メッセージについて、送信元ユーザーの資格情報が有効であるかどうか確認します。ユーザーの資格情報が有効な場合、そのメッセージを受け取る最初のサーバーだけでなく、信頼済みサーバー クラウドに属する他のすべてのサーバーで、そのメッセージが受信できるようになります。

フェデレーション パートナーが発行した有効な資格情報を持つユーザーは信頼されますが、これらのユーザーに対しては、内部ユーザーに与えられる権限のうち一部の使用を、必要に応じて制限できます。

ICE プロトコルおよび TURN プロトコルでも、IETF TURN RFC に記載されているとおり、ダイジェスト認証が使用されます。

クライアント証明書は、Lync Server 2013 によってユーザーを認証するための代替方法を提供します。 ユーザー名とパスワードを指定する代わりに、ユーザーは、証明書と、暗号化のチャレンジを解決するために必要な証明書に対応する秘密キーを持っています。 (この証明書には、ユーザーを識別し、Lync Server 2013 を実行しているサーバーによって信頼されていて、失効されていないルート CA によって発行される必要があります)。認証のためには、ユーザーは暗証番号 (PIN) だけを入力する必要があります。 証明書は、ユーザー名やパスワードの入力が困難な Microsoft Lync 2013 Phone Edition を実行している電話機やその他のデバイスに特に役立ちます。

</div>

<span> </span>

</div>

</div>

</div>

