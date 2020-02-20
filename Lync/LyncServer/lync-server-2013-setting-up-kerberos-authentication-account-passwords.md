---
title: 'Lync Server 2013: Kerberos 認証アカウントのパスワードの設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication account passwords
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48185167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bef30a82479c876dbb4b4e6e6e9b55b3c2b37dc3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a>Lync Server 2013 での Kerberos 認証アカウントパスワードの設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2010-11-03_

Kerberos 認証アカウントのコンピューター オブジェクトを作成したら、そのアカウント用のパスワードを設定できます。 Windows PowerShell コマンドレットを実行して、1台のサーバーで Kerberos アカウントのパスワードを設定します。 Kerberos 認証のために作成したオブジェクトにパスワードを設定できます。 このパスワードは既知の値に設定することができますが、既定値はランダムなパスワードです。 このパスワードは、このアカウントを使用するすべての Kerberos 認証ソースを利用できます。 Kerberos アカウントのパスワードを設定して管理するには、Windows PowerShell コマンドレットを使用します。

<div>


> [!NOTE]  
> Kerberos アカウントオブジェクトはコンピューターオブジェクトですが、参照されている Windows PowerShell コマンドレットの操作には UserAccount パラメーターを使用します。 これは間違いではなく、このコマンドレットを Kerberos のアカウントの作成および管理に使用するときの、意図的な動作です。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 のサーバーで Kerberos 認証アカウントのパスワードを設定する](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [Lync Server 2013 で Kerberos 認証アカウントのパスワードを IIS に同期させる](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

