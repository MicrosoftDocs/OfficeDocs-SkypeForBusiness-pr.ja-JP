---
title: "Lync Server 2013 ボイスメールに対する Exchange Server 2013 ユニファイド メッセージングの構成"
TOCTitle: "Lync Server 2013 ボイスメールに対する Exchange Server 2013 ユニファイド メッセージングの構成"
ms:assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ687983(v=OCS.15)
ms:contentKeyID: 49886862
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Microsoft Lync Server 2013 ボイスメールに対する Microsoft Exchange Server 2013 ユニファイド メッセージングの構成

 

_**トピックの最終更新日:** 2013-02-04_

Microsoft Lync Server 2013 を使用すると、ボイスメール メッセージを Microsoft Exchange Server 2013 に格納できます。そのボイスメール メッセージは、ユーザーの受信トレイ内の電子メール メッセージとして表示されます。この機能は 2010 Edition の Lync Server および Exchange にもありましたが、2013 Edition で UM Call Router コンポーネントが導入されたことで、この "ユニファイド メッセージング" を構成するプロセスが簡単になりました。このコンポーネントは Exchange 2013 クライアント アクセス サーバーにインストールされます。Exchange ユニファイド メッセージングへのすべての呼び出し (ボイスメールなど) は、最初に Call Router を介してルーティングされ、次に適切なメールボックス サーバーへとリダイレクトされます。

Lync Server 2013 と Exchange 2013 の間で既にサーバー間認証が構成されている場合は、すぐにユニファイド メッセージングをセットアップできます。そのためには、まず、Exchange サーバー上で新しいユニファイド メッセージング ダイヤル プランを作成し、割り当てる必要があります。たとえば、次の 2 つのコマンド (Exchange 管理シェルから実行) では、Exchange の新しい 3 桁のダイヤル プランを構成しています。

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

例の最初のコマンドで、VoIPSecurity パラメーターおよびパラメーター値 "Secured" は、信号チャネルがトランスポート層セキュリティ (TLS) を使用して暗号化されることを指定します。URIType "SipName" は、SIP プロトコルを使用してメッセージが送受信されることを指定し、CountryOrRegionCode の 1 は、ダイヤル プランが US に適用されることを指定します。

2 番目のコマンドで、ConfiguredInCountryOrRegionGroups パラメーターに渡されるパラメーター値は、このダイヤル プランで使用できる国内のグループを指定します。パラメーター値 "Anywhere,\*,\*,\*" によって、次の内容が設定されます。

  - グループ名 ("Anywhere")

  - AllowedNumberString (\*、ワイルドカード文字は任意の番号文字列を使用できることを表します)

  - DialNumberString (\*、ワイルドカード文字は任意のダイヤル番号を使用できることを表します)

  - TextComment (\*、ワイルドカード文字は任意のテキスト コマンドを使用できることを表します)

新しいダイヤル プランを作成および構成した後、その新しいダイヤル プランをユニファイド メッセージング サーバーに追加し、そのサーバーのスタートアップ モードを変更する必要があります。具体的には、スタートアップ モードを "Dual" に設定する必要があります。この両方のタスクは、Exchange 管理シェルから実行できます。

    Set-UmServer -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

ユニファイド メッセージング サーバーを構成した後、次に、Enable-ExchangeCertificate コマンドレットを実行して、Exchange 証明書をユニファイド メッセージング サービスに適用する必要があります。

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

証明書の割り当てが適切に行われた後、ユニファイド メッセージング サーバー上の MsExchangeUM サービスを停止し、再起動する必要があります。このサービスは、スタートアップ モードを変更した場合はいつでも、停止して再起動する必要があります。

ユニファイド メッセージング サーバーの構成が終了すると、UM Call Router を構成できます。

    Set-CsUMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

スタートアップ モードが変更されているため、UM Call Router をホストしているコンピューター上で MsExchangeUMCR サービスを停止および再起動する必要があります。

ユニファイド メッセージングのセットアップを完了するには、UM メールボックス ポリシーを作成し、そのポリシーを使用して、ユーザーに対してユニファイド メッセージングを有効にする必要があります。次のようなコマンドを使用して、メールボックス ポリシーを作成できます。

    New-UMMailboxPolicy -ID "RedmondMailboxPolicy" -AllowedCountryOrRegionGroups "Anywhere"

また、次のようなコマンドを使用して、ユーザーに対してユニファイド メッセージングを有効にできます。

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

上のコマンドで、Extensions パラメーターはユーザーの内線番号を表します。この例の場合、ユーザーの内線番号は 100 です。

メールボックスを有効にすると、ユーザー kenmyer@litwareinc.com は Exchange ユニファイド メッセージングを使用できるようになります。Lync Server 管理シェルから [Test-CsExUMConnectivity](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsExUMConnectivity) コマンドレットを実行することで、ユーザーが Exchange UM に接続できるかを確認できます。

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

ユニファイド メッセージングが有効化されている 2 番目のユーザーがいる場合は、[Test-CsExUMVoiceMail](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsExUMVoiceMail) コマンドレットを使用して、この 2 番目のユーザーが最初のユーザーにボイスメール メッセージを残すことができるかを確認できます。

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

