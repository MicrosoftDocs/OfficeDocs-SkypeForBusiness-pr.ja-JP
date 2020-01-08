---
title: 'Lync Server 2013: ハイブリッド展開でユーザーを管理する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7804aacb226d06fbf239939658b6592d438a84f9
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971129"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a>ハイブリッド Lync Server 2013 展開でユーザーを管理する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-05-29_

Microsoft Office 365 Online ポータルで利用可能なユーザー管理機能を使って、Lync Online に移行したユーザーのユーザー設定とポリシーを管理できます。 管理タスクを実行するには、テナント管理者アカウントを使用してサインインする必要があります。

<div>

## <a name="moving-users-back-to-on-premises"></a>ユーザーをオンプレミスに戻す

<div class="">


> [!IMPORTANT]  
> このセクションは、Lync をオンプレミスで作成して有効にし、オンプレミスの展開から Lync Online に移行したユーザーにのみ適用されます。 Lync Online で作成されたユーザーを移動する場合 (オンプレミスの展開で Lync に対して有効にしていない場合) は、「lync <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Online のユーザーを Lync Server 2013 で社内の lync に移動</A>する」を参照してください。



</div>

  - Lync Online からオンプレミスの Lync にユーザーを戻すには、次のコマンドレットを実行します。
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

**HostedMigrationOverrideUrl** パラメーターの URL には、ホスティング型移行サービスが実行されているプールへの URL を次の形式で指定する必要があります。

Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc. ホスティング型移行サービスへの URL は、ご使用の Office 365 テナント アカウント用の Lync Online コントロール パネルの URL を表示することで確認できます。

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

</div>

<span> </span>

</div>

</div>

</div>

