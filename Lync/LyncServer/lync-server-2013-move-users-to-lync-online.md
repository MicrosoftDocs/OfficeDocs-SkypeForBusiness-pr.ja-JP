---
title: 'Lync Server 2013: ユーザーを Lync Online に移動する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 410fd1fe521bd8d4750b290a54db26adb630a8be
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a>Lync Server 2013 でユーザーを Lync Online に移動する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-05-29_

Lync Online へのユーザーの移行を開始する前に、移動するアカウントに関連付けられたユーザーデータをバックアップする必要があります。 ユーザー アカウントと共にすべてのユーザー データが移動されるわけではありません。 詳細については、「 [Lync Server 2013: データのバックアップと復元の要件](lync-server-2013-backup-and-restoration-requirements-data.md)」を参照してください。

<div>

## <a name="migrate-user-settings-to-lync-online"></a>ユーザー設定を Lync Online に移行する

ユーザー設定は、ユーザー アカウントと共に移動されます。 いくつかのオンプレミス設定は、ユーザー アカウントと共に移動されることはありません。

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a>パイロットユーザーを Lync Online に移動する

ユーザーを Lync Online に移行する前に、いくつかのパイロットユーザーを移動して、環境が正しく構成されていることを確認することをお勧めします。 追加のユーザーを移行する前に、Lync 機能とサービスが期待どおりに機能することを確認することができます。

オンプレミスのユーザーを Lync Online テナントに移動するには、Microsoft Office 365 テナントの管理者資格情報を使用して、Lync Server 管理シェルで次のコマンドレットを実行します。 "username@contoso.com" を、移動するユーザーの情報で置換します。

   ```
    $creds=Get-Credential
   ```

   ```
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

**HostedMigrationOverrideUrl**パラメーターに指定する url の形式は、次の形式で、ホステッド移行サービスが実行されているプールへの url である必要\<があり\>ます。 Https://pool FQDN/HostedMigration/hostedmigrationService。

ホスティング型移行サービスへの URL は、ご使用の Office 365 テナント アカウント用の Lync Online コントロール パネルの URL を表示することで確認できます。

**Office 365 テナントのホスティング型移行サービスの URL を確認するには**

1.  管理者として Office 365 テナントにログインします。

2.  **Lync 管理センター**を開きます。

3.  **Lync 管理センター**が表示されたら、アドレスバーの URL を選択して**lync.com**にコピーします。 URL は、次のような書式です。
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  URL の **webdir** を **admin** に置き換えると、次のようになります。
    
    `https://admin0a.online.lync.com`

5.  URL に以下の文字列を付加します。**/HostedMigration/hostedmigrationservice.svc**
    
    以上の手順によって、**HostedMigrationOverrideUrl** の値を持った URL は次のようになります。
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a>ユーザーを Lync Online に移動する

複数のユーザーを移動するには[](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) 、– Filter パラメーターを指定して RegistrarPool のユーザーアカウントに割り当てられている特定のプロパティを持つユーザーを選択します。 次の例に示すように、返されたユーザーを[移動-csuser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)コマンドレットにパイプします。

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

また、以下のサンプルに示すように、-OU パラメーターを使用して、指定した OU 内のすべてのユーザーを取得できます。

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a>Lync Online のユーザー設定と機能を確認する

ユーザーの移動が正常に完了したことは、次の方法で確認できます。

  - Lync Online のコントロールパネルでユーザーの状態を表示します。 オンプレミス ユーザーとオンライン ユーザーでは視覚的なインジケーターが異なります。

  - 次のコマンドレットを実行します。
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

