---
title: 'Lync Server 2013: Lync Server 2013 ボイスメールに対する Microsoft Exchange Server 2013 ユニファイドメッセージングの構成'
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
ms.openlocfilehash: 33c506e8b9f1201ad9382e361afc376590c6feca
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a>Microsoft Lync Server 2013 ボイスメール用の Microsoft Exchange Server 2013 ユニファイドメッセージングの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-04_

Microsoft Lync Server 2013 を使用すると、ボイスメールメッセージを Microsoft Exchange Server 2013 に保存できます。このようなボイスメールメッセージは、ユーザーの受信トレイに電子メールメッセージとして表示されます。 この機能は、Lync Server および Exchange の2010エディションでも参照されています。しかし、この「ユニファイドメッセージング」を構成するプロセスは、UM 呼び出しルーターコンポーネントの導入により、2013エディションでは簡略化されています。 このコンポーネントは、Exchange 2013 クライアントアクセスサーバーにインストールされ、Exchange ユニファイドメッセージング (ボイスメールなど) へのすべての呼び出しは、最初に呼び出しルーターを経由してルーティングされ、適切なメールボックスサーバーにリダイレクトされます。

Lync Server 2013 と Exchange 2013 の間のサーバー間認証を既に構成している場合は、ユニファイドメッセージングをセットアップする準備ができています。 そのためには、まず、Exchange サーバーで新しいユニファイドメッセージングダイヤルプランを作成して割り当てる必要があります。 たとえば、次の2つのコマンド (Exchange 管理シェルから実行) は、Exchange 用の新しい3桁のダイヤルプランを構成します。

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

例の最初のコマンドで、VoIPSecurity パラメーターおよびパラメーター値 "Secured" は、信号チャネルがトランスポート層セキュリティ (TLS) を使用して暗号化されることを指定します。URIType "SipName" は、SIP プロトコルを使用してメッセージが送受信されることを指定し、CountryOrRegionCode の 1 は、ダイヤル プランが US に適用されることを指定します。

2 番目のコマンドで、ConfiguredInCountryOrRegionGroups パラメーターに渡されるパラメーター値は、このダイヤル プランで使用できる国内のグループを指定します。 パラメーターの値を "Anywhere\*,\*,\*," に設定すると、次のようになります。

  - グループ名 ("Anywhere")

  - Allowednumber 文字列 (\*つまり、任意の数字文字列を使用できることを示すワイルドカード文字)

  - [ダイヤル番号]\*文字列 (つまり、任意のダイヤル番号が許可されていることを示すワイルドカード文字)

  - TextComment (\*、任意のテキストコマンドを使用できることを示すワイルドカード文字)

<div>


> [!NOTE]  
> 新しいダイヤルプランを作成すると、既定のメールボックスポリシーも作成されます。



</div>

新しいダイヤルプランを作成して構成した後、新しいダイヤルプランをユニファイドメッセージングサーバーに追加して、そのサーバーのスタートアップモードを変更する必要があります。特に、スタートアップモードを "Dual" に設定する必要があります。 Exchange 管理シェルでは、次のどちらのタスクも実行できます。

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

ユニファイドメッセージングサーバーを構成したら、次に、Get-exchangecertificate コマンドレットを実行して、Exchange 証明書がユニファイドメッセージングサービスに適用されていることを確認する必要があります。

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

証明書の割り当てが適切に行われた後、ユニファイド メッセージング サーバー上の MsExchangeUM サービスを停止し、再起動する必要があります。このサービスは、スタートアップ モードを変更した場合はいつでも、停止して再起動する必要があります。

ユニファイド メッセージング サーバーの構成が終了すると、UM Call Router を構成できます。

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

スタートアップ モードが変更されているため、UM Call Router をホストしているコンピューター上で MsExchangeUMCR サービスを停止および再起動する必要があります。

ユニファイド メッセージングのセットアップを完了するには、UM メールボックス ポリシーを作成し、そのポリシーを使用して、ユーザーに対してユニファイド メッセージングを有効にする必要があります。次のようなコマンドを使用して、メールボックス ポリシーを作成できます。

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

また、次のようなコマンドを使用して、ユーザーに対してユニファイド メッセージングを有効にできます。

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

上のコマンドで、Extensions パラメーターはユーザーの内線番号を表します。この例の場合、ユーザーの内線番号は 100 です。

メールボックスを有効にすると、ユーザー kenmyer@litwareinc.com は Exchange ユニファイド メッセージングを使用できるようになります。 Lync Server 管理シェルから、 [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity)コマンドレットを実行することによって、ユーザーが Exchange UM に接続できることを確認できます。

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

ユニファイド メッセージングが有効化されている 2 番目のユーザーがいる場合は、[Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) コマンドレットを使用して、この 2 番目のユーザーが最初のユーザーにボイスメール メッセージを残すことができるかを確認できます。

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

</div>

<span> </span>

</div>

</div>

</div>

