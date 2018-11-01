---
title: 'Lync Server 2013: ユーザーを Lync Online に移動する'
TOCTitle: ユーザーを Lync Online に移動する
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48272402
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でユーザーを Lync Online に移動する

 

_**トピックの最終更新日:** 2014-05-29_

Lync Online へのユーザーの移行を開始する前に、移動するアカウントに関連付けられているユーザー データのバックアップを実行する必要があります。ユーザー アカウントと共にすべてのユーザー データが移動されるわけではありません。詳細については、「[Lync Server 2013 でのバックアップと復元の要件: データ](lync-server-2013-backup-and-restoration-requirements-data.md)」を参照してください。

## ユーザー設定を Lync Online に移行する

ユーザー設定は、ユーザー アカウントと共に移動されます。いくつかの社内設定は、ユーザー アカウントと共に移動されることはありません。

## パイロット ユーザーを Lync Online に移動する

Lync Online にユーザーを移動する前に、現在の環境が適切に構成されていることを確認する目的で、少数のユーザーを試験的に移動する必要があります。その他のユーザーを移動する前に、Lync 機能とサービス機能が予想どおりであることを確認できます。

Skype for Business Online テナントに社内ユーザーを移動するには、Microsoft Office 365 テナントの管理者資格情報を使用して、Lync Server 管理シェルで以下のコマンドレットを実行します。"username@contoso.com" を、移動するユーザーの情報で置換します。

    $creds=Get-Credential

   &nbsp;

    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

**HostedMigrationOverrideUrl** パラメーターの URL には、ホスティング型移行サービスが実行されているプールへの URL を次の形式で指定する必要があります。 *Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc*

ホスティング型移行サービスへの URL は、ご使用の Office 365 テナント アカウントの Lync Online コントロール パネルの URL を表示することで確認できます。

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

## ユーザーを Lync Online に移動する

[Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) コマンドレットに –Filter パラメーターを指定して、複数のユーザーを移動することができます。このパラメーターにより、RegistrarPool のような、ユーザー アカウントに割り当てられた特定のプロパティを持つユーザーを選択できます。次に、返されたユーザーを、以下のサンプルに示すように、パイプを使用して [Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Move-CsUser) コマンドレットに渡すことができます。

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

また、以下のサンプルに示すように、-OU パラメーターを使用して、指定した OU 内のすべてのユーザーを取得できます。

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

## Lync Online のユーザー設定と機能を確認する

ユーザーの移動が正常に完了したことは、次の方法で確認できます。

  - Lync Online コントロール パネルでユーザーの状態を表示します。社内ユーザーとオンライン ユーザーでは視覚的なインジケーターが異なります。

  - 次のコマンドレットを実行します。
    
        Get-CsUser -Identity

