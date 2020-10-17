---
title: 'Lync Server 2013: クライアント認証をサポートするように AD FS 2.0 を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d2b713d109a72431e78e966258a84c084523a7a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517644"
---
# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a>Lync Server 2013 でクライアント認証をサポートするように AD FS 2.0 を構成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-07-03_

AD FS 2.0 がスマートカードを使用した認証をサポートするように構成できる認証の種類には、次の2つがあります。

  - フォームベース認証 (FBA)

  - トランスポート層セキュリティクライアント認証

フォームベース認証を使用すると、ユーザーのユーザー名またはパスワードを使用するか、スマートカードと PIN を使用して認証を行う web ページを開発できます。 このトピックでは、AD FS 2.0 を使用してトランスポート層セキュリティクライアント認証を実装する方法に焦点を当てます。 AD FS 2.0 認証の種類の詳細については、「AD FS 2.0: でローカル認証の種類を変更する方法」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=313384](https://go.microsoft.com/fwlink/p/?linkid=313384) 。

<div>


**クライアント認証をサポートするように AD FS 2.0 を構成するには**

1.  ドメイン管理者アカウントを使用して、AD FS 2.0 コンピューターにログインします。

2.  Windows エクスプローラーを起動します。

3.  C: \\ inetpub \\ adfs \\ ls を参照します。

4.  既存の web.config ファイルのバックアップコピーを作成します。

5.  メモ帳を使用して既存の web.config ファイルを開きます。

6.  メニューバーから [ **編集** ] を選択し、[ **検索**] を選択します。

7.  検索 **\<localAuthenticationTypes\>** します。
    
    一覧には、1行に1つずつ、4つの認証の種類があることに注意してください。

8.  TLSClient 認証の種類を含む行をセクションの一覧の先頭に移動します。

9.  web.config ファイルを保存して閉じます。

10. 昇格された特権を使用してコマンドプロンプトを起動します。

11. 次のコマンドを実行して IIS を再起動します。
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

