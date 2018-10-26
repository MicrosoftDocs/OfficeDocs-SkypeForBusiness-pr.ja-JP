---
title: Lync Online から内部設置型 Lync にユーザーを移行する前の最初の手順
TOCTitle: Lync Online から内部設置型 Lync にユーザーを移行する前の最初の手順
ms:assetid: 98245b04-ded4-4186-8da3-ba1c554b5c39
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn689118(v=OCS.15)
ms:contentKeyID: 62247342
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Online から内部設置型 Lync にユーザーを移行する前の最初の手順

 

_**トピックの最終更新日:** 2016-12-08_

Lync Online ユーザーを内部設置型の環境に移動する前に、次のすべての条件が満たされていることを確認します。

  - 内部設置型 Lync Server 環境は、完全に展開および検証されている必要があります。詳細については、「[Lync Server 2013 の展開](lync-server-2013-deploying-lync-server.md)」を参照してください。

  - Lync Online テナントは、リモート PowerShell アクセス用に構成されている必要があります。
    
    そのためには、最初に Windows PowerShell の Skype for Business Online モジュール ([http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911) にあります) をインストールします。
    
    モジュールをインストールしたら、Lync Server 管理シェルに次のコマンドレットを入力してリモート セッションを確立します。
    
        Import-Module LyncOnlineConnector

       &nbsp;
    
        $cred = Get-Credential

       &nbsp;
    
        $CSSession = New-CsOnlineSession -Credential $cred

       &nbsp;
    
        Import-PSSession $CSSession -AllowClobber
    
  Skype for Business Online とのリモート PowerShell セッションを確立する方法について詳しくは、「[Windows PowerShell を使用した Lync Online への接続](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」をご覧ください。
  
  Skype for Business Online PowerShell モジュールの使用方法について詳しくは、「[Windows PowerShell による Lync Online の管理](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」をご覧ください。

  - Lync Online は、共有 SIP アドレス スペース用に構成する必要があります。そのためには、最初に Lync Online とリモート PowerShell セッションを確立します。次に、次のコマンドレットを実行します。
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

これらの手順を実行した後で、「[Lync Online ユーザーの内部設置型 Lync への移行](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md)」に進むことができます。

