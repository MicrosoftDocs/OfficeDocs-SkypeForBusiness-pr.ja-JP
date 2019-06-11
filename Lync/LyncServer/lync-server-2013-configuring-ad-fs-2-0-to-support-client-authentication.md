---
title: 'Lync Server 2013: クライアント認証をサポートするように AD FS 2.0 を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12f7cad4b36eb96f7b36925aa91e6363b8cdd264
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a>Lync Server 2013 でのクライアント認証をサポートするように AD FS 2.0 を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-07-03_

AD FS 2.0 でスマート カードを使用した認証をサポートできるように構成可能な認証の種類が 2 つあります。

  - フォーム ベース認証 (FBA)

  - トランスポート層セキュリティ クライアント認証

フォーム ベース認証を使用すると、ユーザー名/パスワードを使用した認証またはスマート カードと PIN を使用した認証をユーザーに許可できる Web ページを開発できます。 このトピックでは、AD FS 2.0 でトランスポート層セキュリティ クライアント認証を実装する方法を説明します。 AD FS 2.0 認証の種類の詳細については、「AD FS 2.0: で[http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384)ローカル認証の種類を変更する方法」を参照してください。

<div>


**クライアント認証をサポートするように AD FS 2.0 を構成するには**

1.  ドメイン管理者のアカウントを使用して AD FS 2.0 コンピューターにログインします。

2.  エクスプローラーを起動します。

3.  C: inetpub\\\\adfs\\ls を参照してください

4.  既存の web.config ファイルのバックアップ コピーを作成します。

5.  メモ帳を使用して既存の web.config ファイルを開きます。

6.  メニュー バーの [**編集**] をクリックし、[**検索**] をクリックします。

7.  ** \<Localauthenticationtypes\>** を検索します。
    
    4 つの認証の種類が 1 行に 1 つずつ表示されます。

8.  TLSClient 認証の種類を含む行をセクションの一覧の一番上に移動します。

9.  web.config ファイルを保存して閉じます。

10. 管理者特権でコマンド プロンプトを起動します。

11. 次のコマンドを実行して IIS を再起動します。
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

