---
title: Skype for Business Server ボイス メールに対する Exchange Server ユニファイド メッセージングの構成
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
ms.openlocfilehash: 21664f50b657324b4e70e86da83a4abbe1c14239
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20979312"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a><span data-ttu-id="a21cc-103">Skype for Business Server ボイス メールに対する Exchange Server ユニファイド メッセージングの構成</span><span class="sxs-lookup"><span data-stu-id="a21cc-103">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>
 
<span data-ttu-id="a21cc-104">**の概要:** Exchange Server ユニファイド メッセージングの構成 Skype ビジネス サーバーのボイス メールにします。</span><span class="sxs-lookup"><span data-stu-id="a21cc-104">**Summary:** Configure Exchange Server Unified Messaging for Skype for Business Server voice mail.</span></span>
  
<span data-ttu-id="a21cc-105">ビジネス サーバー用の Skype を使用すると、ボイスメールのメッセージを Exchange Server 2016 または Exchange Server 2013 に格納されています。ボイスメール メッセージは、ユーザーの受信トレイの電子メール メッセージとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="a21cc-105">Skype for Business Server enables you to have voicemail messages stored in Exchange Server 2016 or Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> 

> [!NOTE]
> <span data-ttu-id="a21cc-106">として以前に Exchange ユニファイド メッセージングは、不要になった使用可能な Exchange 2019 が、電話システムを使用してレコードのボイス メール メッセージと、ユーザーの Exchange メールボックスに記録を残すことができます。</span><span class="sxs-lookup"><span data-stu-id="a21cc-106">Exchange Unified Messaging as previously known is no longer available in Exchange 2019, but you can still use Phone System to record voicemail messages and then leave the recording in a user's Exchange mailbox.</span></span> <span data-ttu-id="a21cc-107">詳細については、[クラウドのボイスメールの計画サービス](../../../SfBServer2019/hybrid/plan-cloud-voicemail.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a21cc-107">See [Plan Cloud Voicemail service](../../../SfBServer2019/hybrid/plan-cloud-voicemail.md) for more information.</span></span>
  
<span data-ttu-id="a21cc-108">ビジネス サーバーと Exchange Server 2016 または Exchange Server 2013 の Skype 間でサーバーからサーバーへの認証を既に構成した場合は、ユニファイド メッセージングを設定する準備がします。</span><span class="sxs-lookup"><span data-stu-id="a21cc-108">If you have already configured server-to-server authentication between Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, then you are ready to setup unified messaging.</span></span> <span data-ttu-id="a21cc-109">これを行うには、最初に作成し、新しいユニファイド メッセージング ダイヤル プランを Exchange Server に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a21cc-109">To do so, you must first create and assign a new unified messaging dial plan on your Exchange Server.</span></span> <span data-ttu-id="a21cc-110">などのこれら 2 つのコマンド (Exchange 管理シェル内から実行) は、Exchange の新しい 3 桁のダイヤル プランを構成します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-110">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="a21cc-111">最初では、例、VoIPSecurity パラメーター、およびパラメーター値の [セキュリティで保護された"のコマンドは、トランスポート層セキュリティ (TLS) を使用して信号チャネルが暗号化されているを示しています。</span><span class="sxs-lookup"><span data-stu-id="a21cc-111">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicates that the signaling channel is encrypted by using Transport Layer Security (TLS).</span></span> <span data-ttu-id="a21cc-112">URIType "SipName" は、SIP プロトコルを使用してメッセージが送受信されることを指定し、CountryOrRegionCode の 1 は、ダイヤル プランが米国に適用されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-112">The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>
  
<span data-ttu-id="a21cc-113">2 番目のコマンドで、ConfiguredInCountryOrRegionGroups パラメーターに渡されるパラメーター値は、このダイヤル プランで使用できる国内のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-113">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="a21cc-114">パラメーターの値"任意の場所、\*、\*、\*"次の設定。</span><span class="sxs-lookup"><span data-stu-id="a21cc-114">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>
  
- <span data-ttu-id="a21cc-115">グループ名 ("Anywhere")</span><span class="sxs-lookup"><span data-stu-id="a21cc-115">Group name ("Anywhere")</span></span>
    
- <span data-ttu-id="a21cc-116">AllowedNumberString (\*、任意の数値の文字列を許可することを示すワイルドカード文字)</span><span class="sxs-lookup"><span data-stu-id="a21cc-116">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>
    
- <span data-ttu-id="a21cc-117">DialNumberString (\*、すべてのダイヤルの番号を許可することを示すワイルドカード文字)</span><span class="sxs-lookup"><span data-stu-id="a21cc-117">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>
    
- <span data-ttu-id="a21cc-118">TextComment (\*、任意のテキスト コマンドを許可することを示すワイルドカード文字)</span><span class="sxs-lookup"><span data-stu-id="a21cc-118">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>
    
> [!NOTE]
> <span data-ttu-id="a21cc-119">新しいダイヤル プランを作成すると、既定のメールボックス ポリシーも作成されます。</span><span class="sxs-lookup"><span data-stu-id="a21cc-119">Creating a new dial plan will also create a Default Mailbox Policy.</span></span> 
  
<span data-ttu-id="a21cc-120">作成し、新しいダイヤル プランを構成した後、新しいダイヤル プランにユニファイド メッセージング サーバーとそのサーバーのスタートアップ モードを変更しを追加する必要があります。具体的には、「デュアル」のスタートアップ モードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a21cc-120">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="a21cc-121">Exchange 管理シェル内からこれらのタスクの両方を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a21cc-121">You can perform both of these tasks from within the Exchange Management Shell:</span></span>
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

<span data-ttu-id="a21cc-122">ユニファイド メッセージング サーバーの構成が完了したら次に Exchange 証明書がユニファイド メッセージング サービスに適用されることを確認するのには有効にする ExchangeCertificate コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a21cc-122">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>
  
```
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

<span data-ttu-id="a21cc-p106">証明書の割り当てが適切に行われた後、ユニファイド メッセージング サーバー上の MsExchangeUM サービスを停止して、再起動する必要があります。このサービスは、スタートアップ モードを変更した場合はいつでも、停止して再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a21cc-p106">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server. This service must be stopped and restarted any time you change the startup mode.</span></span>
  
<span data-ttu-id="a21cc-125">ユニファイド メッセージング サーバーの構成が終了すると、UM Call Router を構成できます。</span><span class="sxs-lookup"><span data-stu-id="a21cc-125">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>
  
```
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

<span data-ttu-id="a21cc-126">スタートアップ モードが変更されているため、UM Call Router をホストしているコンピューター上で MsExchangeUMCR サービスを停止および再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a21cc-126">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>
  
<span data-ttu-id="a21cc-p107">ユニファイド メッセージングのセットアップを完了するには、UM メールボックス ポリシーを作成し、そのポリシーを使用して、ユーザーのユニファイド メッセージングを有効にする必要があります。次のようなコマンドを使用して、メールボックス ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a21cc-p107">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging. You can create a mailbox policy by using a command similar to this:</span></span>
  
```
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="a21cc-129">また、次のようなコマンドを使用して、ユーザーのユニファイド メッセージングを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="a21cc-129">And you can enable a user for unified messaging by using a command similar to this:</span></span>
  
```
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

<span data-ttu-id="a21cc-p108">上のコマンドで、Extensions パラメーターはユーザーの内線番号を表します。この例の場合、ユーザーの内線番号は 100 です。</span><span class="sxs-lookup"><span data-stu-id="a21cc-p108">In the preceding command, the Extensions parameter represents the telephone extension number for the user. In this example, the user has the extension number 100.</span></span>
  
<span data-ttu-id="a21cc-132">メールボックスを有効にすると、ユーザー kenmyer@litwareinc.com は Exchange ユニファイド メッセージングを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a21cc-132">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="a21cc-133">コマンドレットを実行して、[テスト CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps)から、Skype のビジネス サーバー管理シェルのユーザーを Exchange UM に接続できることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="a21cc-133">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) cmdlet from within the Skype for Business Server Management Shell:</span></span>
  
```
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

<span data-ttu-id="a21cc-134">ユニファイド メッセージングに対して有効になっている 2 番目のユーザーがある場合は、この 2 番目のユーザーは最初のユーザーのボイス メール メッセージのままにしていることを確認する[テスト CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps)コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="a21cc-134">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>
  
```
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a><span data-ttu-id="a21cc-135">Microsoft Exchange Server 上のユニファイド メッセージングを構成します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-135">Configuring Unified Messaging on Microsoft Exchange Server</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="a21cc-136">呼び出しへの応答、Outlook Voice Access、またはエンタープライズ VoIP ユーザー向けの自動応答サービスを提供する Exchange ユニファイド メッセージング (UM) を使用する場合は、[ビジネスの Skype での Exchange ユニファイド メッセージング統合の計画](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)を、読み書きし、このセクションの手順です。</span><span class="sxs-lookup"><span data-stu-id="a21cc-136">If you want to use Exchange Unified Messaging (UM) to provide call answering, Outlook Voice Access, or auto-attendant services for Enterprise Voice users, read [Plan for Exchange Unified Messaging integration in Skype for Business](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md), and then follow the instructions in this section.</span></span> 

<span data-ttu-id="a21cc-137">Exchange ユニファイド メッセージング (UM) エンタープライズ VoIP を使用するを構成するには、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a21cc-137">To configure Exchange Unified Messaging (UM) to work with Enterprise Voice, you’ll need to perform the following tasks:</span></span>

- <span data-ttu-id="a21cc-138">Exchange ユニファイド メッセージング (UM) サービスを実行するサーバーに証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-138">Configure certificates on the server running Exchange Unified Messaging (UM) services</span></span>
> [!NOTE]
> <span data-ttu-id="a21cc-139">UM SIP URI ダイヤル プランのすべてに、すべてのクライアント アクセス、メールボックス サーバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-139">Add all Client Access and Mailbox servers to all UM SIP URI dial plans.</span></span> <span data-ttu-id="a21cc-140">、発信通話ルーティングされませんが機能しない場合とが必要です。</span><span class="sxs-lookup"><span data-stu-id="a21cc-140">If not, outbound call routing won’t work as expected.</span></span> 
- <span data-ttu-id="a21cc-141">、必要に応じて 1 つまたは複数 UM SIP URI ダイヤル プラン、およびサブスクライバー アクセスの電話番号を作成し、対応する L のダイヤル プランを作成します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-141">Create one or more UM SIP URI dial plans, along with the subscriber access phone numbers, as needed, and then create corresponding L dial plans.</span></span>

- <span data-ttu-id="a21cc-142">Exchucutil.ps1 スクリプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-142">Use the exchucutil.ps1 script to:</span></span>
    - <span data-ttu-id="a21cc-143">UM IP ゲートウェイを作成します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-143">Create UM IP gateways.</span></span>
    - <span data-ttu-id="a21cc-144">UM ハント グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-144">Create UM hunt groups.</span></span>
    - <span data-ttu-id="a21cc-145">UM の Active Directory ドメイン サービス オブジェクトを読み取るアクセス許可をビジネスのサーバー用の Skype を付与します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-145">Grant Skype for Business Server permission to read UM Active Directory Domain Services objects.</span></span>
- <span data-ttu-id="a21cc-146">UM 自動アテンダント オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-146">Create a UM auto-attendant object.</span></span>
- <span data-ttu-id="a21cc-147">サブスクライバー アクセス オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-147">Create a subscriber access object.</span></span>
- <span data-ttu-id="a21cc-148">UM SIP URI ダイヤル プランには、各ユーザーと関連付けられたユーザーの SIP URI を作成します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-148">Create a SIP URI for each user and associating users with a UM SIP URI dial plan.</span></span>

### <a name="requirements-and-recommendations"></a><span data-ttu-id="a21cc-149">要件と推奨事項</span><span class="sxs-lookup"><span data-stu-id="a21cc-149">Requirements and Recommendations</span></span>

<span data-ttu-id="a21cc-150">このセクションのドキュメントは、次の Exchange の役割を展開している作業を開始する前に: クライアント アクセス、およびメールボックスです。</span><span class="sxs-lookup"><span data-stu-id="a21cc-150">Before you begin, the documentation in this section assumes that you have deployed the following Exchange roles: Client Access and Mailbox.</span></span> <span data-ttu-id="a21cc-151">Microsoft Exchange Server、Exchange UM サービスとして実行これらのサーバーにします。</span><span class="sxs-lookup"><span data-stu-id="a21cc-151">In Microsoft Exchange Server, Exchange UM runs as a service on these servers.</span></span>

<span data-ttu-id="a21cc-152">また、次の点を注意してください。</span><span class="sxs-lookup"><span data-stu-id="a21cc-152">Also note the following:</span></span>
- <span data-ttu-id="a21cc-153">Exchange UM がインストールされている場合複数のフォレストで、各 UM のフォレストの Exchange Server の統合の手順を実行しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="a21cc-153">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest.</span></span> <span data-ttu-id="a21cc-154">さらに、各 UM フォレストは、Skype のビジネス サーバーを展開すると、し、フォレストでは、whichSkype ビジネス サーバーの展開を構成する必要が各 UM のフォレストを信頼するフォレストを信頼するように構成しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="a21cc-154">In addition, each UM forest must be configured to trust the forest in which Skype for Business Server is deployed, and the forest in whichSkype for Business Server is deployed must be configured to trust each UM forest.</span></span>
- <span data-ttu-id="a21cc-155">統合の手順は、ユニファイド メッセージング サービスが実行されている、両方の Exchange Server の役割および Skype ビジネス サーバーを実行しているサーバー上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="a21cc-155">Integration steps are performed on both the Exchange Server roles where Unified Messaging services are running, and on the server running Skype for Business Server.</span></span> <span data-ttu-id="a21cc-156">Lync Server 2013 の統合の手順を実行する前に Exchange Server ユニファイド メッセージング統合の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a21cc-156">You should perform the Exchange Server Unified Messaging integration steps before you perform the Lync Server 2013 integration steps.</span></span>
> [!NOTE]
> <span data-ttu-id="a21cc-157">統合手順が、管理者ロールで、どのサーバーで実行されるを参照してください[と統合するための展開プロセスの概要、設置型ユニファイド メッセージングおよびビジネス用の Skype](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a21cc-157">To see which integration steps are performed on which servers and by which administrator roles, see  [Deployment process overview for integrating on-premises Unified Messaging and Skype for Business](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md).</span></span> 

<span data-ttu-id="a21cc-158">次のツールは、Exchange UM を実行している各サーバーで使用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a21cc-158">The following tools must be available on each server running Exchange UM:</span></span>
- <span data-ttu-id="a21cc-159">Exchange 管理シェル</span><span class="sxs-lookup"><span data-stu-id="a21cc-159">Exchange Management Shell</span></span>
- <span data-ttu-id="a21cc-160">スクリプト exchucutil.ps1、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-160">The script exchucutil.ps1, which performs the following tasks:</span></span>
    - <span data-ttu-id="a21cc-161">各 Skype のビジネス サーバー、UM IP ゲートウェイを作成します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-161">Creates a UM IP gateway for each Skype for Business Server.</span></span>
    - <span data-ttu-id="a21cc-162">各ゲートウェイのハント グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-162">Creates a hunt group for each gateway.</span></span> <span data-ttu-id="a21cc-163">各ハント グループのパイロット id は、フロント エンド プールまたは Standard Edition サーバー、ゲートウェイに関連付けられているで使用される UM SIP URI ダイヤル プランを指定します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-163">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Front End pool or Standard Edition server that is associated with the gateway.</span></span>
    - <span data-ttu-id="a21cc-164">Skype ビジネス サーバー Exchange UM Active Directory ドメイン サービス内のオブジェクトを読み取るアクセス許可を与えられます。</span><span class="sxs-lookup"><span data-stu-id="a21cc-164">Grants Skype for Business Server permission to read Exchange UM objects in Active Directory Domain Services.</span></span>



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a><span data-ttu-id="a21cc-165">ExchUCUtil.ps1 を持つ Microsoft Exchange ユニファイド メッセージングを構成します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-165">Configure Unified Messaging on Microsoft Exchange with ExchUCUtil.ps1</span></span> 

<span data-ttu-id="a21cc-166">ビジネス サーバー Exchange ユニファイド メッセージング (UM) での Microsoft Skype を統合していると、は、シェルでは、ExchUcUtil.ps1 スクリプトを実行する必要が。</span><span class="sxs-lookup"><span data-stu-id="a21cc-166">When you’re integrating Microsoft Skype for Business Server with Exchange Unified Messaging (UM), you have to run the ExchUcUtil.ps1 script in the Shell.</span></span> <span data-ttu-id="a21cc-167">ExchUcUtil.ps1 スクリプトは、次のこと。</span><span class="sxs-lookup"><span data-stu-id="a21cc-167">The ExchUcUtil.ps1 script does the following:</span></span>

- <span data-ttu-id="a21cc-168">ビジネス サーバー プールの各 Skype の UM IP ゲートウェイを作成します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-168">Creates a UM IP gateway for each Skype for Business Server pool.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a21cc-169">ExchUcUtil.ps1 スクリプトでは、1 つまたは複数の UM IP ゲートウェイを作成します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-169">The ExchUcUtil.ps1 script creates one or more UM IP gateways.</span></span> <span data-ttu-id="a21cc-170">スクリプトを作成する 1 つのゲートウェイを除くすべての UM IP ゲートウェイで発信呼び出しを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a21cc-170">You must disable outgoing calls on all UM IP gateways except one gateway that the script created.</span></span> <span data-ttu-id="a21cc-171">これには、スクリプトを実行する前に作成された UM IP ゲートウェイに送信呼び出しを無効にすることが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a21cc-171">This includes disabling outgoing calls on UM IP gateways that were created before you ran the script.</span></span> 

- <span data-ttu-id="a21cc-172">各 UM IP ゲートウェイの UM ハント グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-172">Creates a UM hunt group for each UM IP gateway.</span></span> <span data-ttu-id="a21cc-173">各ハント グループのパイロット id は、ビジネス サーバーのフロント エンド プールまたは Standard Edition サーバー、UM IP ゲートウェイに関連付けられているため、Skype で使用する UM SIP URI ダイヤル プランを指定します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-173">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Skype for Business Server Front End pool or Standard Edition server that’s associated with the UM IP gateway.</span></span>
- <span data-ttu-id="a21cc-174">UM などコンテナー オブジェクトを Active Directory の UM のダイヤル プラン、自動応答、UM IP ゲートウェイ、UM ハント グループを読むビジネス サーバーのアクセス許可の付与 Skype。</span><span class="sxs-lookup"><span data-stu-id="a21cc-174">Grants Skype for Business Server permission to read Active Directory UM container objects such as UM dial plans, auto attendants, UM IP gateways, and UM hunt groups.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="a21cc-175">Skype のビジネス サーバーが配置され、各 UM のフォレストを信頼するようにビジネス Server 2013 の Skype を配置するフォレストを構成する必要があります、フォレストを信頼するには、各 UM のフォレストを構成しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="a21cc-175">Each UM forest must be configured to trust the forest in which Skype for Business Server is deployed, and the forest in which Skype for Business Server 2013 is deployed must be configured to trust each UM forest.</span></span> <span data-ttu-id="a21cc-176">Exchange UM がインストールされている場合複数のフォレストで、各 UM のフォレストの Exchange Server の統合の手順を行う必要があります。 またはビジネス サーバー ドメインの Skype を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a21cc-176">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest or you’ll have to specify the Skype for Business Server domain.</span></span> <span data-ttu-id="a21cc-177">たとえば、ExchUcUtil.ps1 – フォレスト: < lync のドメイン ・ コント ローラーの fqdn >。</span><span class="sxs-lookup"><span data-stu-id="a21cc-177">For example, ExchUcUtil.ps1 –Forest:<lync-domain-controller-fqdn>.</span></span> 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a><span data-ttu-id="a21cc-178">ExchUcUtil.ps1 スクリプトを実行するのにシェルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-178">Use the Shell to run the ExchUcUtil.ps1 script</span></span>

<span data-ttu-id="a21cc-179">Skype ビジネス サーバーとして同じトポロジでは、組織内のすべての Exchange サーバー上には、ExchUcUtil.ps1 スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-179">Run the ExchUcUtil.ps1 script on any Exchange server in your organization that’s in the same topology as Skype for Business Server.</span></span> <span data-ttu-id="a21cc-180">シェルを使用して、メールボックス サーバーからスクリプトを実行するか、クライアント アクセス サーバーでリモートの Windows PowerShell を使用してスクリプトを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="a21cc-180">You can run the script from a Mailbox server using the Shell or you can run the script using Remote Windows PowerShell on a Client Access server.</span></span> <span data-ttu-id="a21cc-181">組織内のクライアント アクセス サーバー上でスクリプトを実行するクライアント アクセス サーバーは、組織内のメールボックス サーバーへのリモートの Windows PowerShell セッションをプロキシになります。</span><span class="sxs-lookup"><span data-stu-id="a21cc-181">If you run the script on a Client Access server in your organization, the Client Access server will proxy the Remote Windows PowerShell session to a Mailbox server in the organization.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="a21cc-182">ExchUcUtil.ps1 スクリプトでは、1 つまたは複数の UM IP ゲートウェイを作成します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-182">The ExchUcUtil.ps1 script creates one or more UM IP gateways.</span></span> <span data-ttu-id="a21cc-183">スクリプトを作成する 1 つのゲートウェイを除くすべての UM IP ゲートウェイで発信呼び出しを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a21cc-183">You must disable outgoing calls on all UM IP gateways except one gateway that the script created.</span></span> <span data-ttu-id="a21cc-184">これには、スクリプトを実行する前に作成された UM IP ゲートウェイに送信呼び出しを無効にすることが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a21cc-184">This includes disabling outgoing calls on UM IP gateways that were created before you ran the script.</span></span> <span data-ttu-id="a21cc-185">UM IP ゲートウェイで発信呼び出しを無効にするには、発信呼び出しを UM IP ゲートウェイを無効にするを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a21cc-185">To disable outgoing calls on a UM IP gateway, see Disable outgoing calls on UM IP gateways.</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="a21cc-186">Exchange 組織の管理役割のアクセス許可があるか、スクリプトを実行する Exchange 組織管理者のセキュリティ グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a21cc-186">You must have the permissions of the Exchange Organization Management role or be a member of the Exchange Organization Administrators security group to run the script.</span></span> 

1. <span data-ttu-id="a21cc-187">Exchange 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a21cc-187">Open the Exchange Management Shell.</span></span>
2. <span data-ttu-id="a21cc-188">C:\Windows\System32 プロンプトで、入力の**cd\<ドライブ文字 >: \Program Files\Microsoft\Exchange Server\V15\Scripts >。ExchUcUtil.ps1**、し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-188">At the C:\Windows\System32 prompt, type **cd \<drive letter>:\Program Files\Microsoft\Exchange Server\V15\Scripts>.ExchUcUtil.ps1**, and then press Enter.</span></span>

#### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="a21cc-189">どうやってこの方法でしょうか。</span><span class="sxs-lookup"><span data-stu-id="a21cc-189">How do you know this worked?</span></span>

<span data-ttu-id="a21cc-190">ExchUcUtul.ps1 スクリプトが正常に完了したことを確認するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a21cc-190">To verify that the ExchUcUtul.ps1 script completed successfully, do the following:</span></span>
- <span data-ttu-id="a21cc-191">Get UMIPGateway コマンドレット、または、EAC を使用すると、新しい UM IP ゲートウェイまたは作成されたゲートウェイを表示します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-191">Use the Get-UMIPGateway cmdlet or the EAC to view the new UM IP gateway or gateways that were created.</span></span>
- <span data-ttu-id="a21cc-192">Get UMHuntGroup コマンドレット、または、EAC を使用すると、新しい UM ハント グループまたは作成されたグループを表示します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-192">Use the Get-UMHuntGroup cmdlet or the EAC to view the new UM hunt group or groups that were created.</span></span>

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a><span data-ttu-id="a21cc-193">Exchange Server ユニファイド メッセージングを実行するサーバーに証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-193">Configure certificates on the server running Exchange Server Unified Messaging</span></span>
 
<span data-ttu-id="a21cc-194">ビジネスのサーバー計画のドキュメントでの Skype での Exchange ユニファイド メッセージング統合のための計画で説明するように Exchange ユニファイド メッセージング (UM) を展開しているし、エンタープライズ VoIP ユーザーに Exchange UM の機能を提供する場合、組織で Exchange UM を実行するサーバーに証明書を構成するのには次の手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a21cc-194">If you have deployed Exchange Unified Messaging (UM), as described in Planning for Exchange Unified Messaging integration in Skype for Business Server in the Planning documentation, and you want to provide Exchange UM features to Enterprise Voice users in your organization, you can use the following procedures to configure the certificate on the server running Exchange UM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a21cc-195">内部証明書は、ビジネス サーバーの Skype を実行しているサーバーと Microsoft Exchange を実行しているサーバーの両方する必要があります信頼性のない、相互に信頼されたルート機関の証明書。</span><span class="sxs-lookup"><span data-stu-id="a21cc-195">For internal certificates, both the servers running Skype for Business Server and the servers running Microsoft Exchange must have trusted root authority certificates that are mutually trusted.</span></span> <span data-ttu-id="a21cc-196">証明機関 (CA) できます、同じまたは別の証明機関を信頼されたルート機関の証明書ストアに登録されている証明機関のルートの証明書がサーバーにある限り。</span><span class="sxs-lookup"><span data-stu-id="a21cc-196">The certification authority (CA) can either be the same, or a different certification authority, as long as the servers have the certification authority’s root certificate registered in their trusted root authority certificate store.</span></span> 

<span data-ttu-id="a21cc-197">Skype ビジネス サーバーに接続するためにサーバー証明書を Exchange Server を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a21cc-197">The Exchange Server must be configured with a server certificate in order to connect to Skype for Business Server:</span></span>
1. <span data-ttu-id="a21cc-198">Exchange Server 用の CA 証明書をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="a21cc-198">Download the CA certificate for the Exchange Server.</span></span>
2. <span data-ttu-id="a21cc-199">Exchange Server 用には、CA 証明書をインストールします。</span><span class="sxs-lookup"><span data-stu-id="a21cc-199">Install the CA certificate for the Exchange Server.</span></span>
3. <span data-ttu-id="a21cc-200">CA が、Exchange Server の Ca の信頼されたルートのリストにあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-200">Verify that the CA is in the list of trusted root CAs of the Exchange Server.</span></span>
4. <span data-ttu-id="a21cc-201">Exchange Server の証明書の要求を作成し、証明書をインストールします。</span><span class="sxs-lookup"><span data-stu-id="a21cc-201">Create a certificate request for the Exchange Server and install the certificate.</span></span> 
5. <span data-ttu-id="a21cc-202">Exchange Server の証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a21cc-202">Assign the certificate for the Exchange Server.</span></span>


<span data-ttu-id="a21cc-203">**CA 証明書をダウンロードするには。**</span><span class="sxs-lookup"><span data-stu-id="a21cc-203">**To download the CA certificate:**</span></span>

1. <span data-ttu-id="a21cc-204">Exchange UM を実行するサーバー、[**スタート] ボタン**、[**実行**] をクリック、タイプ**http://\<、発行 CA 用サーバーの名前 >/certsrv**、し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a21cc-204">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<name of your Issuing CA Server>/certsrv**, and then click **OK**.</span></span>
2. <span data-ttu-id="a21cc-205">[タスクを選択して、[ **CA 証明書、証明書チェーン、または CRL のダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a21cc-205">Under Select a task, click **Download a CA certificate, certificate chain, or CRL**.</span></span>
3. <span data-ttu-id="a21cc-206">[ **CA 証明書、証明書チェーン、または CRL のダウンロード**の**Base 64 エンコード方法**を選択し、**ダウンロードする CA 証明書**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a21cc-206">Under **Download a CA Certificate, Certificate Chain, or CRL**, select **Encoding Method to Base 64**, and then click**Download CA certificate**.</span></span>
> [!NOTE]
> <span data-ttu-id="a21cc-207">この段階での識別のエンコード規則 (DER) エンコーディングを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a21cc-207">You can also specify Distinguished Encoding Rules (DER) encoding at this step.</span></span> <span data-ttu-id="a21cc-208">DER は、この手順の次の手順でファイルの種類のエンコードを選択し、手順 10 の**証明書の CA をインストールする**場合は、.cer ではなく、.p7b です。</span><span class="sxs-lookup"><span data-stu-id="a21cc-208">If you select DER encoding, the file type in the next step of this procedure and in step 10 of **To Install the CA certificate** is .p7b rather than .cer.</span></span> 
4. <span data-ttu-id="a21cc-209">**ファイルのダウンロード**] ダイアログ ボックスで**を保存**] をクリックし、サーバー上のハード ディスクにファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-209">In the **File Download** dialog box, click **Save**, and then save the file to the hard disk on the server.</span></span> <span data-ttu-id="a21cc-210">(ファイルは、.cer またはファイルの拡張子は .p7b、エンコード前の手順で選択したことによってのいずれかです。)</span><span class="sxs-lookup"><span data-stu-id="a21cc-210">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in the previous step.)</span></span>

<span data-ttu-id="a21cc-211">**CA 証明書をインストールするには。**</span><span class="sxs-lookup"><span data-stu-id="a21cc-211">**To install the CA certificate:**</span></span>

1. <span data-ttu-id="a21cc-212">Exchange UM を実行するサーバー上で **[スタート] ボタン**、**実行**をクリックすると、[名前] ボックスに「 **mmc**と入力して、 **[ok]** をクリックし、Microsoft 管理コンソール (MMC) を開きます。</span><span class="sxs-lookup"><span data-stu-id="a21cc-212">On the server running Exchange UM, open Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the Open box, and then clicking **OK**.</span></span>
2. <span data-ttu-id="a21cc-213">[**ファイル**] メニュー **[スナップインの追加と削除]** をクリックし、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a21cc-213">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>
3. <span data-ttu-id="a21cc-214">[**スタンドアロン スナップインの追加**] ボックスで、**証明書**をクリックし、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a21cc-214">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>
4. <span data-ttu-id="a21cc-215">[**証明書スナップイン**] ダイアログ ボックスの [**コンピューター アカウント**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a21cc-215">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>
5. <span data-ttu-id="a21cc-216">**[コンピューターの選択**] ダイアログ ボックスであることを確認、**ローカル コンピューター: (このコンソールを実行しているコンピューター)** ] チェック ボックスをオンにして、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a21cc-216">In the **Select Computer** dialog box, verify that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>
6. <span data-ttu-id="a21cc-217">**[閉じる**] をクリックし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a21cc-217">Click **Close**, and then click **OK**.</span></span> 
7. <span data-ttu-id="a21cc-218">コンソール ツリーで、[**証明書 (ローカル コンピューター)** を展開を選択し、**信頼されたルート証明機関**] を展開し、[**証明書**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a21cc-218">In the console tree, expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>
8. <span data-ttu-id="a21cc-219">**証明書**を右クリックし、**すべてのタスク**] をクリックし、[**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a21cc-219">Right-click **Certificates**, click **All Tasks**, and click **Import**.</span></span>
9. <span data-ttu-id="a21cc-220">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a21cc-220">Click **Next**.</span></span> 
10. <span data-ttu-id="a21cc-221">**参照**ファイルを検索する] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a21cc-221">Click **Browse** to locate the file, and then click **Next**.</span></span> <span data-ttu-id="a21cc-222">(ファイルは、.cer またはファイルの拡張子は .p7b、 **CA 証明書をダウンロードする**は、手順 3 で選択したエンコード方法によってがあります。</span><span class="sxs-lookup"><span data-stu-id="a21cc-222">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in step 3 of **To download the CA certificate**.</span></span>
11. <span data-ttu-id="a21cc-223">次のストアに**証明書をすべての場所**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a21cc-223">Click **Place All Certificates** in the following store.</span></span>
12. <span data-ttu-id="a21cc-224">**[参照**] をクリックし、**信頼されたルート証明機関**を選択します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-224">Click **Browse**, and then select **Trusted Root Certification Authorities**.</span></span> 
13. <span data-ttu-id="a21cc-225">**次**の設定を確認する] をクリックし、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a21cc-225">Click **Next** to verify the settings, and then click **Finish**.</span></span> 


<span data-ttu-id="a21cc-226">**CA が、信頼されたルート Ca の一覧にあることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="a21cc-226">**To verify that the CA is in the list of trusted root CAs:**</span></span>

1. <span data-ttu-id="a21cc-227">サーバーで Exchange UM を実行して、[証明書 (ローカル コンピューター) を展開 MMC で信頼されたルート証明機関を展開し、[証明書] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a21cc-227">On the server running Exchange UM, in MMC expand Certificates (Local Computer), expand Trusted Root Certification Authorities, and then click Certificates.</span></span>
2. <span data-ttu-id="a21cc-228">詳細ウィンドウで、CA が信頼された Ca のリストであるを確認します。</span><span class="sxs-lookup"><span data-stu-id="a21cc-228">In the details pane, verify that your CA is on the list of trusted CAs.</span></span>


