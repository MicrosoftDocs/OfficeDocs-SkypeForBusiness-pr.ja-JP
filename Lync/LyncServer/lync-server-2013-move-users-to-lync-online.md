---
title: 'Lync Server 2013: Lync Online へのユーザーの移動'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6cad11937fc2f975030e0d90b152f43707e7c36
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a>Lync Server 2013 でユーザーを Lync Online に移動する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-05-29_

ユーザーの Lync Online への移行を開始する前に、移動するアカウントに関連付けられているユーザーデータをバックアップする必要があります。 ユーザーアカウントを使用して、一部のユーザーデータが移動されるわけではありません。 詳細については、「 [Lync Server 2013: data」の「バックアップと復元の要件](lync-server-2013-backup-and-restoration-requirements-data.md)」を参照してください。

<div>

## <a name="migrate-user-settings-to-lync-online"></a>ユーザー設定を Lync Online に移行する

ユーザー設定は、ユーザー アカウントと共に移動されます。 オンプレミスの設定の中には、ユーザーアカウントを使用して移動しないものがあります。

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a>パイロットユーザーを Lync Online に移行する

Lync Online へのユーザーの移動を開始する前に、いくつかのパイロットユーザーを移動して、環境が正しく構成されていることを確認することをお勧めします。 その後、追加のユーザーの移動を試みる前に、Lync の機能とサービスが期待どおりに機能することを確認できます。

オンプレミスのユーザーを Lync Online テナントに移動するには、Microsoft Office 365 テナントの管理者の資格情報を使用して、Lync Server 管理シェルで次のコマンドレットを実行します。 "Username@contoso.com" を、移動するユーザーの情報に置き換えます。

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

**HostedMigrationOverrideUrl**パラメーターに指定する url の形式は、次の形式で、Hosted Migration service が実行されているプールへの url である必要\<があり\>ます。 Https://pool FQDN/hostedmigration/hostedmigrationservice.svc

Office 365 テナントアカウントの Lync Online コントロールパネルの URL を表示することによって、ホストされた移行サービスへの URL を確認できます。

**Office 365 テナントのホスト型移行サービスの URL を確認するには**

1.  Office 365 テナントに管理者としてログインします。

2.  **Lync 管理センター**を開きます。

3.  **Lync 管理センター**が表示されたら、アドレスバーの URL を選択して、 **lync.com**までコピーします。 URL の例は、次のようになります。
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  URL 内の**webdir**を**管理者**に置き換えます。結果は次のようになります。
    
    `https://admin0a.online.lync.com`

5.  次の文字列を URL: **/HostedMigration/hostedmigrationservice.svc**に追加します。
    
    生成される URL は**HostedMigrationOverrideUrl**の値で、次のようになります。
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a>Lync Online へのユーザーの移動

-Filter パラメーターを指定して RegistrarPool[コマンドレット](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)を使用して、ユーザーアカウントに割り当てられた特定のプロパティを持つユーザーを選択することで、複数のユーザーを移動することができます。 その後、次の例に示すように、返されたユーザーを[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)コマンドレットにパイプ処理できます。

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

また、次の例に示すように、-OU パラメーターを使用して、指定した OU 内のすべてのユーザーを取得することもできます。

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a>Lync Online のユーザー設定と機能を確認する

ユーザーの移動が正常に完了したことは、次の方法で確認できます。

  - Lync Online コントロール パネルでユーザーの状態を表示します。社内ユーザーとオンライン ユーザーでは視覚的なインジケーターが異なります。

  - 次のコマンドレットを実行します。
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

