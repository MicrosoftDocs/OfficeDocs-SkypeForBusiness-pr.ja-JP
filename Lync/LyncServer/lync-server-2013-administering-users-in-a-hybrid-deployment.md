---
title: 'Lync Server 2013: ハイブリッド展開でユーザーを管理する'
TOCTitle: ハイブリッド展開でユーザーを管理する
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48272387
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ハイブリッド Lync Server 2013 展開でユーザーを管理する

 

_**トピックの最終更新日:** 2014-05-29_

Microsoft Office 365 のオンライン ポータルにあるユーザー管理機能を使用すると、Lync Online に移行されたユーザーのユーザー設定とユーザー ポリシーを管理できます。管理タスクを実行するには、テナント管理者アカウントを使用してサインインする必要があります。

## ユーザーを社内に戻す


> [!IMPORTANT]
> このセクションは、内部設置型 Lync 用に作成および有効化された後で内部設置型展開から Lync Online に移動されたユーザーに対してのみ適用されます。内部設置型展開の Lync 用に有効化されていない、Lync Online で作成されたユーザーを移動する場合は、「<A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Lync Server 2013 での Lync Online から内部設置型 Lync へのユーザーの移動</A>」を参照してください。



  - Lync Online から内部設置型 Lync にユーザーを移動するには、次のコマンドレットを実行します。
    
        $cred=Get-Credential

       &nbsp;
    
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>

**HostedMigrationOverrideUrl** パラメーターの URL には、ホスティング型移行サービスが実行されているプールへの URL を次の形式で指定する必要があります。

*Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc* 。ホスティング型移行サービスへの URL は、ご使用の Office 365 テナント アカウント用の Lync Online コントロール パネルの URL を表示することで確認できます。

**Office 365 テナントのホスティング型移行サービスの URL を確認するには**

1.  管理者として Office 365 テナントにログインします。

2.  \[ **Lync 管理センター** \] を開きます。

3.  \[ **Lync 管理センター** \] が表示されたら、**lync.com** の近くのアドレス バーの URL を選択してコピーします。URL は、次のような書式です。
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  URL の **webdir** を **admin** に置き換えると、次のようになります。
    
    `https://admin0a.online.lync.com`

5.  URL に以下の文字列を付加します。 **/HostedMigration/hostedmigrationservice.svc**
    
    以上の手順によって、**HostedMigrationOverrideUrl** の値を持った URL は次のようになります。
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

