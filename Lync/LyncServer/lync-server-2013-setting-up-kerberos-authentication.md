---
title: 'Lync Server 2013: Kerberos 認証の設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398976(v=OCS.15)
ms:contentKeyID: 48185601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8ae852be13ee1ca7780ed89bf710e64fe5a2902
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a>Lync Server 2013 での Kerberos 認証のセットアップ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

Lync Server 2013 は、Web サービスの NTLM および Kerberos 認証をサポートしています。 Office Communications Server 2007 および Office Communications Server 2007 R2 Web サービスアプリケーションプールを実行するためのユーザーアカウントとして、既定の RTCComponentService および RTCService を使用して、サービスプリンシパル名 (SPN) をユーザーに割り当てることができます。アカウントを選択し、認証プリンシパルとして機能します。 Lync Server は NetworkService を使用して Web サービスを実行し、NetworkService に Spn を割り当てられません。

Active Directory オブジェクトに Spn を保持する必要がないという問題を解決するために、Lync Server コントロールパネルでこの目的のためにコンピューターアカウントオブジェクトを使用することができます。 コンピューターアカウントオブジェクトは、Spn を保持することができ、パスワードの有効期限の対象にはなりません。これは、以前のバージョンでユーザーアカウントを使用する場合の問題でした。

Windows PowerShell コマンドレットを使用して、Kerberos 認証を提供するようにコンピューターオブジェクトを構成します。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 で Kerberos 認証を有効にするための前提条件](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [Lync Server 2013 で Kerberos 認証アカウントを作成する](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [Lync Server 2013 のサイトへの Kerberos 認証アカウントの割り当て](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [Lync Server 2013 での Kerberos 認証アカウントパスワードの設定](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [Lync Server 2013 の他のサイトへの Kerberos 認証の追加](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [Lync Server 2013 で、サイトから Kerberos 認証を削除する](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [Lync Server 2013 での Kerberos 認証の状態と割り当てのテストおよびレポート](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

