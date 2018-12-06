---
title: 'Lync Server 2013: Lync Online とのフェデレーションを構成する'
TOCTitle: Lync Online とのフェデレーションを構成する
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205126(v=OCS.15)
ms:contentKeyID: 48273027
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 と Lync Online とのフェデレーションを構成する

 

_**トピックの最終更新日:** 2016-12-08_

このセクションの手順に従って、社内の展開と Skype for Business Online の間の相互運用性を構成します。

## Skype for Business Online によってフェデレーションに対する社内エッジ サービスを構成する

フェデレーションにより、内部設置型展開のユーザーが組織の Office 365 ユーザーと通信できるようになります。フェデレーションを構成するには、次のコマンドレットを実行します。

    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting

   &nbsp;

    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root

## 共有 SIP アドレス空間に対して Skype for Business Online テナントを構成する

セッション開始プロトコル (SIP) アドレスは、電話番号や電子メール アドレスに似た、ネットワーク上の各ユーザーの一意の識別子です。Lync ユーザーを内部設置型から Skype for Business Online に移動する前に、セッション開始プロトコル (SIP) アドレス スペースを内部設置型展開と共有するように Office 365 テナントを構成する必要があります。これが構成されていないと、次のエラー メッセージが表示されることがあります。

Move-CsUser : HostedMigration エラー: エラー=(510), 説明=(このユーザーのテナントは共有 SIP アドレス スペース用に有効化されていません。)

共有 SIP アドレス空間を構成するには、 Skype for Business Online とリモート PowerShell セッションを確立して、次のコマンドレットを実行します。

    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true

Skype for Business Online とのリモート PowerShell セッションを確立するには、最初に Windows PowerShell の Skype for Business Online モジュール ( [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911) にあります) をインストールします。

そのモジュールをインストールしたら、次のコマンドレットによってリモート セッションを確立します。

    Import-Module LyncOnlineConnector

   &nbsp;

    $cred = Get-Credential

   &nbsp;

    $CSSession = New-CsOnlineSession -Credential $cred

   &nbsp;

    Import-PSSession $CSSession -AllowClobber

Skype for Business Online とのリモート PowerShell セッションを確立する方法について詳しくは、「 [Windows PowerShell を使用した Lync Online への接続](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」をご覧ください。

Skype for Business Online PowerShell モジュールの使用方法について詳しくは、「 [Windows PowerShell による Lync Online の管理](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」をご覧ください。

## 関連項目

#### その他のリソース

[New-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider)

