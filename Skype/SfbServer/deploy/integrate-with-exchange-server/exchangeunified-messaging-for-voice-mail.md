---
title: Skype for Business Server 2015 ボイス メールに対する Exchange Server ユニファイド メッセージングの構成
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/19/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: '概要: Exchange Server ユニファイド メッセージングの構成 Skype ビジネス サーバーのボイス メールをします。'
ms.openlocfilehash: 9f4cb3dcd43d8f6300a5fbe38bd37c40d48e8273
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-2015-voice-mail"></a>Skype for Business Server 2015 ボイス メールに対する Exchange Server ユニファイド メッセージングの構成
 
**の概要:**Exchange Server ユニファイド メッセージングの構成 Skype ビジネス サーバーのボイス メールにします。
  
ビジネス サーバー 2015 の Skype を使用すると、ボイスメールのメッセージを Exchange Server 2016 または Exchange Server 2013 に格納されています。ボイスメール メッセージは、ユーザーの受信トレイの電子メール メッセージとして表示されます。 
  
ビジネス サーバー 2015 2016 の Exchange Server や Exchange Server 2013 の Skype 間でサーバーからサーバーへの認証を既に構成した場合は、ユニファイド メッセージングを設定する準備がします。 これを行うには、最初に作成し、新しいユニファイド メッセージング ダイヤル プランを Exchange Server に割り当てる必要があります。 などのこれら 2 つのコマンド (Exchange 管理シェル内から実行) は、Exchange の新しい 3 桁のダイヤル プランを構成します。
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

例の最初のコマンドで、VoIPSecurity パラメーターおよびパラメーター値 "Secured" は、信号チャネルがトランスポート層セキュリティ (TLS) を使用して暗号化されることを指定します。URIType "SipName" は、SIP プロトコルを使用してメッセージが送受信されることを指定し、CountryOrRegionCode の 1 は、ダイヤル プランが米国に適用されることを指定します。
  
2 番目のコマンドで、ConfiguredInCountryOrRegionGroups パラメーターに渡されるパラメーター値は、このダイヤル プランで使用できる国内のグループを指定します。 パラメーターの値"任意の場所、\*、\*、\*"次の設定。
  
- グループ名 ("Anywhere")
    
- AllowedNumberString (\*、任意の数値の文字列を許可することを示すワイルドカード文字)
    
- DialNumberString (\*、すべてのダイヤルの番号を許可することを示すワイルドカード文字)
    
- TextComment (\*、任意のテキスト コマンドを許可することを示すワイルドカード文字)
    
> [!NOTE]
> 新しいダイヤル プランを作成すると、既定のメールボックス ポリシーも作成されます。 
  
作成し、新しいダイヤル プランを構成した後、新しいダイヤル プランにユニファイド メッセージング サーバーとそのサーバーのスタートアップ モードを変更しを追加する必要があります。具体的には、「デュアル」のスタートアップ モードを設定する必要があります。 Exchange 管理シェル内からこれらのタスクの両方を行うことができます。
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

ユニファイド メッセージング サーバーの構成が完了したら次に Exchange 証明書がユニファイド メッセージング サービスに適用されることを確認するのには有効にする ExchangeCertificate コマンドレットを実行する必要があります。
  
```
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

証明書の割り当てが適切に行われた後、ユニファイド メッセージング サーバー上の MsExchangeUM サービスを停止して、再起動する必要があります。このサービスは、スタートアップ モードを変更した場合はいつでも、停止して再起動する必要があります。
  
ユニファイド メッセージング サーバーの構成が終了すると、UM Call Router を構成できます。
  
```
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

スタートアップ モードが変更されているため、UM Call Router をホストしているコンピューター上で MsExchangeUMCR サービスを停止および再起動する必要があります。
  
ユニファイド メッセージングのセットアップを完了するには、UM メールボックス ポリシーを作成し、そのポリシーを使用して、ユーザーのユニファイド メッセージングを有効にする必要があります。次のようなコマンドを使用して、メールボックス ポリシーを作成できます。
  
```
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

また、次のようなコマンドを使用して、ユーザーのユニファイド メッセージングを有効にできます。
  
```
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

上のコマンドで、Extensions パラメーターはユーザーの内線番号を表します。この例の場合、ユーザーの内線番号は 100 です。
  
メールボックスを有効にすると、ユーザー kenmyer@litwareinc.com は Exchange ユニファイド メッセージングを使用できるようになります。 コマンドレットを実行して、[テスト CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps)から、Skype のビジネス サーバー管理シェルのユーザーを Exchange UM に接続できることを確認することができます。
  
```
$credential = Get-Credential "litwareinc\kenmyer"

Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

ユニファイド メッセージングに対して有効になっている 2 番目のユーザーがある場合は、この 2 番目のユーザーは最初のユーザーのボイス メール メッセージのままにしていることを確認する[テスト CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps)コマンドレットを使用することができます。
  
```
$credential = Get-Credential "litwareinc\pilar"

Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```


