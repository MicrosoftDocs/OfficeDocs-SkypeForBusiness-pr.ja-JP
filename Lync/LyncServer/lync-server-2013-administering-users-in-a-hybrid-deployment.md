---
title: 'Lync Server 2013: ハイブリッド展開でのユーザーの管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c6cfa255eddc998047f5b404d59b7e6622fbaae
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a>ハイブリッド Lync Server 2013 展開でユーザーを管理する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-05-29_

Microsoft Office 365 Online ポータルで使用可能なユーザー管理機能を使用して、Lync Online に移行したユーザーのユーザー設定とポリシーを管理できます。 管理タスクを実行するには、テナント管理者アカウントを使用してサインインする必要があります。

<div>

## <a name="moving-users-back-to-on-premises"></a>ユーザーを社内に戻す

<div class="">


> [!IMPORTANT]  
> このセクションは、Lync オンプレミスに対して作成および有効化された後、オンプレミス展開から Lync Online に移動したユーザーに対してのみ適用されます。 Lync Online で作成されたユーザーを移動する必要があり、オンプレミス展開で Lync が有効になっていない場合は、「lync <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">online から Lync Server 2013 の lync オンプレミスへのユーザーの移動</A>」を参照してください。



</div>

  - 次のコマンドレットを実行して、ユーザーを Lync Online から Lync オンプレミスに戻します。
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

**HostedMigrationOverrideUrl**パラメーターに指定する url の形式は、次の形式で、Hosted Migration service が実行されているプールへの url である必要があります。

Https://\<プールの\>FQDN/hostedmigration/hostedmigrationservice.svc Office 365 テナントアカウントの Lync Online コントロールパネルの URL を表示することによって、ホストされた移行サービスへの URL を確認できます。

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

</div>

<span> </span>

</div>

</div>

</div>

