---
title: 'Lync Server 2013: Kerberos 認証アカウント パスワードの設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Kerberos authentication account passwords
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48185167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06ca8bf5d1b3dc90b1ceacbe581e0426b5c0aaa9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848772"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a>Lync Server 2013 での Kerberos 認証アカウント パスワードの設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2010-11-03_

Kerberos 認証アカウントのコンピューターオブジェクトを作成したら、アカウントのパスワードを設定できます。 1つのサーバーで Kerberos アカウントのパスワードを設定するための Windows PowerShell コマンドレットを実行します。 Kerberos 認証用に作成したオブジェクトに対してパスワードを設定することができます。 パスワードは既知の値に設定できますが、既定ではランダムなパスワードになります。 パスワードは、そのアカウントを使用するすべての Kerberos 認証ソースで利用できます。 Kerberos アカウントのパスワードをセットアップして管理するには、Windows PowerShell コマンドレットを使用します。

<div>


> [!NOTE]  
> Kerberos アカウントオブジェクトはコンピューターオブジェクトですが、参照されている Windows PowerShell コマンドレットの操作には UserAccount パラメーターを使います。 これは間違いではありませんが、Kerberos アカウントの作成とメンテナンスで使用する場合のコマンドレットの動作です。



</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 でのサーバーへの Kerberos 認証アカウント パスワードの設定](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [Lync Server 2013 での Kerberos 認証アカウント パスワードと IIS との同期](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

