---
title: 'Lync Server 2013: Lync Server 2013 ボイスメール用に Microsoft Exchange Server 2013 ユニファイドメッセージングを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Exchange Server 2013 Unified Messaging for Lync Server 2013 voice mail
ms:assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687983(v=OCS.15)
ms:contentKeyID: 49733573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 367f4cc517771f51d7a1452293ad9803075d285f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a>Microsoft Lync Server 2013 用 Microsoft Exchange Server 2013 ユニファイドメッセージングの構成ボイスメール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-04_

Microsoft Lync Server 2013 を使用すると、ボイスメールメッセージを Microsoft Exchange Server 2013 に保存することができます。これらのボイスメールメッセージは、ユーザーの受信トレイにメールメッセージとして表示されます。 この機能は、2010エディションの Lync Server と Exchange にも含まれていました。ただし、この "ユニファイドメッセージング" を構成するプロセスは、UM Call Router コンポーネントの導入により、2013エディションで簡素化されています。 このコンポーネントは Exchange 2013 クライアントアクセスサーバーにインストールされ、Exchange ユニファイドメッセージング (ボイスメールなど) へのすべての呼び出しは、まず通話ルーター経由でルーティングされ、適切なメールボックスサーバーにリダイレクトされます。

Lync Server 2013 と Exchange 2013 間のサーバー間認証を既に構成している場合は、ユニファイドメッセージングを設定することができます。 そのためには、まず Exchange server で新しいユニファイドメッセージングダイヤルプランを作成して割り当てる必要があります。 たとえば、次の2つのコマンド (Exchange 管理シェル内から実行) では、Exchange 用の新しい3桁のダイヤルプランを構成します。

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

例の最初のコマンドで、VoIPSecurity パラメーターおよびパラメーター値 "Secured" は、信号チャネルがトランスポート層セキュリティ (TLS) を使用して暗号化されることを指定します。URIType "SipName" は、SIP プロトコルを使用してメッセージが送受信されることを指定し、CountryOrRegionCode の 1 は、ダイヤル プランが米国に適用されることを指定します。

2 番目のコマンドで、ConfiguredInCountryOrRegionGroups パラメーターに渡されるパラメーター値は、このダイヤル プランで使用できる国内のグループを指定します。 "Anywhere、\*,\*\*" というパラメーター値は、次のように設定します。

  - グループ名 ("Anywhere")

  - Allowed連番文字列 (\*任意の数字文字列が許可されていることを示すワイルドカード文字)

  - [ダイヤル番号]\*文字列 (およびダイヤルされた番号が許可されていることを示すワイルドカード文字)

  - TextComment (\*任意のテキストコマンドが許可されていることを示すワイルドカード文字)

<div>


> [!NOTE]  
> 新しいダイヤル プランを作成すると、既定のメールボックス ポリシーも作成されます。



</div>

新しいダイヤルプランを作成して構成した後、新しいダイヤルプランをユニファイドメッセージングサーバーに追加し、そのサーバーのスタートアップモードを変更する必要があります。特に、スタートアップモードを "デュアル" に設定する必要があります。 Exchange 管理シェルでは、次の2つのタスクを実行できます。

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

ユニファイドメッセージングサーバーの構成が完了したら、次に、Import-exchangecertificate コマンドレットを実行して、Exchange 証明書がユニファイドメッセージングサービスに適用されていることを確認します。

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

証明書の割り当てが適切に行われた後、ユニファイド メッセージング サーバー上の MsExchangeUM サービスを停止して、再起動する必要があります。このサービスは、スタートアップ モードを変更した場合はいつでも、停止して再起動する必要があります。

ユニファイド メッセージング サーバーの構成が終了すると、UM Call Router を構成できます。

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

スタートアップ モードが変更されているため、UM Call Router をホストしているコンピューター上で MsExchangeUMCR サービスを停止および再起動する必要があります。

ユニファイド メッセージングのセットアップを完了するには、UM メールボックス ポリシーを作成し、そのポリシーを使用して、ユーザーのユニファイド メッセージングを有効にする必要があります。次のようなコマンドを使用して、メールボックス ポリシーを作成できます。

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

また、次のようなコマンドを使用して、ユーザーのユニファイド メッセージングを有効にできます。

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

上のコマンドで、Extensions パラメーターはユーザーの内線番号を表します。この例の場合、ユーザーの内線番号は 100 です。

メールボックスを有効にすると、ユーザー kenmyer@litwareinc.com は Exchange ユニファイド メッセージングを使用できるようになります。 Lync Server 管理シェル内から[テスト用の CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity)コマンドレットを実行することで、ユーザーが Exchange UM に接続できることを確認できます。

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

ユニファイド メッセージングが有効化されている 2 番目のユーザーがいる場合は、[Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) コマンドレットを使用して、この 2 番目のユーザーが最初のユーザーにボイスメール メッセージを残せることを確認できます。

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

</div>

<span> </span>

</div>

</div>

</div>

