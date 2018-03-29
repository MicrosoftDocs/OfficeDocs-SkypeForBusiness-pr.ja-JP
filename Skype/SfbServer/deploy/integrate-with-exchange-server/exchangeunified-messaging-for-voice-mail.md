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
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-2015-voice-mail"></a><span data-ttu-id="e88bb-103">Skype for Business Server 2015 ボイス メールに対する Exchange Server ユニファイド メッセージングの構成</span><span class="sxs-lookup"><span data-stu-id="e88bb-103">Configure Exchange Server Unified Messaging for Skype for Business Server 2015 voice mail</span></span>
 
<span data-ttu-id="e88bb-104">**の概要:**Exchange Server ユニファイド メッセージングの構成 Skype ビジネス サーバーのボイス メールにします。</span><span class="sxs-lookup"><span data-stu-id="e88bb-104">**Summary:** Configure Exchange Server Unified Messaging for Skype for Business Server voice mail.</span></span>
  
<span data-ttu-id="e88bb-105">ビジネス サーバー 2015 の Skype を使用すると、ボイスメールのメッセージを Exchange Server 2016 または Exchange Server 2013 に格納されています。ボイスメール メッセージは、ユーザーの受信トレイの電子メール メッセージとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="e88bb-105">Skype for Business Server 2015 enables you to have voicemail messages stored in Exchange Server 2016 or Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> 
  
<span data-ttu-id="e88bb-106">ビジネス サーバー 2015 2016 の Exchange Server や Exchange Server 2013 の Skype 間でサーバーからサーバーへの認証を既に構成した場合は、ユニファイド メッセージングを設定する準備がします。</span><span class="sxs-lookup"><span data-stu-id="e88bb-106">If you have already configured server-to-server authentication between Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you are ready to setup unified messaging.</span></span> <span data-ttu-id="e88bb-107">これを行うには、最初に作成し、新しいユニファイド メッセージング ダイヤル プランを Exchange Server に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e88bb-107">To do so, you must first create and assign a new unified messaging dial plan on your Exchange Server.</span></span> <span data-ttu-id="e88bb-108">などのこれら 2 つのコマンド (Exchange 管理シェル内から実行) は、Exchange の新しい 3 桁のダイヤル プランを構成します。</span><span class="sxs-lookup"><span data-stu-id="e88bb-108">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="e88bb-p102">例の最初のコマンドで、VoIPSecurity パラメーターおよびパラメーター値 "Secured" は、信号チャネルがトランスポート層セキュリティ (TLS) を使用して暗号化されることを指定します。URIType "SipName" は、SIP プロトコルを使用してメッセージが送受信されることを指定し、CountryOrRegionCode の 1 は、ダイヤル プランが米国に適用されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="e88bb-p102">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicate that the signaling channel is encrypted by using Transport Layer Security (TLS). The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>
  
<span data-ttu-id="e88bb-111">2 番目のコマンドで、ConfiguredInCountryOrRegionGroups パラメーターに渡されるパラメーター値は、このダイヤル プランで使用できる国内のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="e88bb-111">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="e88bb-112">パラメーターの値"任意の場所、\*、\*、\*"次の設定。</span><span class="sxs-lookup"><span data-stu-id="e88bb-112">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>
  
- <span data-ttu-id="e88bb-113">グループ名 ("Anywhere")</span><span class="sxs-lookup"><span data-stu-id="e88bb-113">Group name ("Anywhere")</span></span>
    
- <span data-ttu-id="e88bb-114">AllowedNumberString (\*、任意の数値の文字列を許可することを示すワイルドカード文字)</span><span class="sxs-lookup"><span data-stu-id="e88bb-114">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>
    
- <span data-ttu-id="e88bb-115">DialNumberString (\*、すべてのダイヤルの番号を許可することを示すワイルドカード文字)</span><span class="sxs-lookup"><span data-stu-id="e88bb-115">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>
    
- <span data-ttu-id="e88bb-116">TextComment (\*、任意のテキスト コマンドを許可することを示すワイルドカード文字)</span><span class="sxs-lookup"><span data-stu-id="e88bb-116">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>
    
> [!NOTE]
> <span data-ttu-id="e88bb-117">新しいダイヤル プランを作成すると、既定のメールボックス ポリシーも作成されます。</span><span class="sxs-lookup"><span data-stu-id="e88bb-117">Creating a new dial plan will also create a Default Mailbox Policy.</span></span> 
  
<span data-ttu-id="e88bb-118">作成し、新しいダイヤル プランを構成した後、新しいダイヤル プランにユニファイド メッセージング サーバーとそのサーバーのスタートアップ モードを変更しを追加する必要があります。具体的には、「デュアル」のスタートアップ モードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e88bb-118">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="e88bb-119">Exchange 管理シェル内からこれらのタスクの両方を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e88bb-119">You can perform both of these tasks from within the Exchange Management Shell:</span></span>
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

<span data-ttu-id="e88bb-120">ユニファイド メッセージング サーバーの構成が完了したら次に Exchange 証明書がユニファイド メッセージング サービスに適用されることを確認するのには有効にする ExchangeCertificate コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e88bb-120">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>
  
```
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

<span data-ttu-id="e88bb-p105">証明書の割り当てが適切に行われた後、ユニファイド メッセージング サーバー上の MsExchangeUM サービスを停止して、再起動する必要があります。このサービスは、スタートアップ モードを変更した場合はいつでも、停止して再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e88bb-p105">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server. This service must be stopped and restarted any time you change the startup mode.</span></span>
  
<span data-ttu-id="e88bb-123">ユニファイド メッセージング サーバーの構成が終了すると、UM Call Router を構成できます。</span><span class="sxs-lookup"><span data-stu-id="e88bb-123">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>
  
```
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

<span data-ttu-id="e88bb-124">スタートアップ モードが変更されているため、UM Call Router をホストしているコンピューター上で MsExchangeUMCR サービスを停止および再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e88bb-124">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>
  
<span data-ttu-id="e88bb-p106">ユニファイド メッセージングのセットアップを完了するには、UM メールボックス ポリシーを作成し、そのポリシーを使用して、ユーザーのユニファイド メッセージングを有効にする必要があります。次のようなコマンドを使用して、メールボックス ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e88bb-p106">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging. You can create a mailbox policy by using a command similar to this:</span></span>
  
```
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="e88bb-127">また、次のようなコマンドを使用して、ユーザーのユニファイド メッセージングを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="e88bb-127">And you can enable a user for unified messaging by using a command similar to this:</span></span>
  
```
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

<span data-ttu-id="e88bb-p107">上のコマンドで、Extensions パラメーターはユーザーの内線番号を表します。この例の場合、ユーザーの内線番号は 100 です。</span><span class="sxs-lookup"><span data-stu-id="e88bb-p107">In the preceding command, the Extensions parameter represents the telephone extension number for the user. In this example, the user has the extension number 100.</span></span>
  
<span data-ttu-id="e88bb-130">メールボックスを有効にすると、ユーザー kenmyer@litwareinc.com は Exchange ユニファイド メッセージングを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e88bb-130">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="e88bb-131">コマンドレットを実行して、[テスト CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps)から、Skype のビジネス サーバー管理シェルのユーザーを Exchange UM に接続できることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="e88bb-131">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) cmdlet from within the Skype for Business Server Management Shell:</span></span>
  
```
$credential = Get-Credential "litwareinc\kenmyer"

Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

<span data-ttu-id="e88bb-132">ユニファイド メッセージングに対して有効になっている 2 番目のユーザーがある場合は、この 2 番目のユーザーは最初のユーザーのボイス メール メッセージのままにしていることを確認する[テスト CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps)コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e88bb-132">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>
  
```
$credential = Get-Credential "litwareinc\pilar"

Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```


