---
title: Skype for Business Server Exchange Serverユニファイド メッセージングの構成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: '概要: Skype for Business Server Exchange Serverユニファイド メッセージングを構成します。'
ms.openlocfilehash: 68cf4a11deccac9ad71bdb6216c4126362787498
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834037"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a><span data-ttu-id="1caba-103">Skype for Business Server Exchange Serverユニファイド メッセージングの構成</span><span class="sxs-lookup"><span data-stu-id="1caba-103">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>
 
<span data-ttu-id="1caba-104">**概要:** Skype for Business Server Exchange Serverユニファイド メッセージングを構成します。</span><span class="sxs-lookup"><span data-stu-id="1caba-104">**Summary:** Configure Exchange Server Unified Messaging for Skype for Business Server voice mail.</span></span>
  
<span data-ttu-id="1caba-105">Skype for Business Server では、ボイスメール メッセージを Exchange Server 2016 または Exchange Server 2013 に保存できます。これらのボイスメール メッセージは、ユーザーの受信トレイに電子メール メッセージとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="1caba-105">Skype for Business Server enables you to have voicemail messages stored in Exchange Server 2016 or Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> 

> [!NOTE]
> <span data-ttu-id="1caba-106">Exchange 2019 では、以前に知られている Exchange ユニファイド メッセージングは使用できなくなりましたが、引き続き電話システムを使用してボイスメール メッセージを録音し、その録音をユーザーの Exchange メールボックスに残しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="1caba-106">Exchange Unified Messaging as previously known is no longer available in Exchange 2019, but you can still use Phone System to record voicemail messages and then leave the recording in a user's Exchange mailbox.</span></span> <span data-ttu-id="1caba-107">詳細 [については、「クラウド ボイスメール サービスを計画](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1caba-107">See [Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) for more information.</span></span>
  
<span data-ttu-id="1caba-108">Skype for Business Server と Exchange Server 2016 または Exchange Server 2013 の間でサーバー間認証を既に構成している場合は、ユニファイド メッセージングをセットアップする準備が整っています。</span><span class="sxs-lookup"><span data-stu-id="1caba-108">If you have already configured server-to-server authentication between Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, then you are ready to setup unified messaging.</span></span> <span data-ttu-id="1caba-109">これを行うには、最初に新しいユニファイド メッセージング ダイヤル プランを作成し、そのダイヤル プランに割り当Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="1caba-109">To do so, you must first create and assign a new unified messaging dial plan on your Exchange Server.</span></span> <span data-ttu-id="1caba-110">たとえば、次の 2 つのコマンド (Exchange 管理シェル 内から実行) は、Exchange の新しい 3 桁のダイヤル プランを構成します。</span><span class="sxs-lookup"><span data-stu-id="1caba-110">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>
  
```powershell
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="1caba-111">例の最初のコマンドで、VoIPSecurity パラメーターとパラメーター値 "Secured" は、信号チャネルがトランスポート層セキュリティ (TLS) を使用して暗号化されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="1caba-111">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicates that the signaling channel is encrypted by using Transport Layer Security (TLS).</span></span> <span data-ttu-id="1caba-112">URIType "SipName" は、SIP プロトコルを使用してメッセージが送受信されることを指定し、CountryOrRegionCode の 1 は、ダイヤル プランが US に適用されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="1caba-112">The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>
  
<span data-ttu-id="1caba-113">2 番目のコマンドで、ConfiguredInCountryOrRegionGroups パラメーターに渡されるパラメーター値は、このダイヤル プランで使用できる国内のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="1caba-113">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="1caba-114">パラメーター値 "Anywhere, \* \* , , " \* は、以下を設定します。</span><span class="sxs-lookup"><span data-stu-id="1caba-114">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>
  
- <span data-ttu-id="1caba-115">グループ名 ("Anywhere")</span><span class="sxs-lookup"><span data-stu-id="1caba-115">Group name ("Anywhere")</span></span>
    
- <span data-ttu-id="1caba-116">AllowedNumberString ( \* , a wildcard character indicating that any number string is allowed)</span><span class="sxs-lookup"><span data-stu-id="1caba-116">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>
    
- <span data-ttu-id="1caba-117">DialNumberString ( \* , a wildcard character indicating that any dialed number is allowed number is allowed)</span><span class="sxs-lookup"><span data-stu-id="1caba-117">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>
    
- <span data-ttu-id="1caba-118">TextComment ( \* , a wildcard character indicating that any text command is allowed)</span><span class="sxs-lookup"><span data-stu-id="1caba-118">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>
    
> [!NOTE]
> <span data-ttu-id="1caba-119">新しいダイヤル プランを作成すると、既定のメールボックス ポリシーも作成されます。</span><span class="sxs-lookup"><span data-stu-id="1caba-119">Creating a new dial plan will also create a Default Mailbox Policy.</span></span> 
  
<span data-ttu-id="1caba-120">新しいダイヤル プランを作成して構成した後、新しいダイヤル プランをユニファイド メッセージング サーバーに追加し、そのサーバーのスタートアップ モードを変更する必要があります。特に、スタートアップ モードを "デュアル" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1caba-120">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="1caba-121">これらの両方のタスクは、Exchange 管理シェル 内から実行できます。</span><span class="sxs-lookup"><span data-stu-id="1caba-121">You can perform both of these tasks from within the Exchange Management Shell:</span></span>
  
```powershell
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

<span data-ttu-id="1caba-122">ユニファイド メッセージング サーバーを構成した後、次に Enable-ExchangeCertificate コマンドレットを実行して、Exchange 証明書がユニファイド メッセージング サービスに適用されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1caba-122">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>
  
```powershell
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

<span data-ttu-id="1caba-p106">証明書の割り当てが適切に行われた後、ユニファイド メッセージング サーバー上の MsExchangeUM サービスを停止し、再起動する必要があります。このサービスは、スタートアップ モードを変更した場合はいつでも、停止して再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1caba-p106">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server. This service must be stopped and restarted any time you change the startup mode.</span></span>
  
<span data-ttu-id="1caba-125">ユニファイド メッセージング サーバーの構成が終了すると、UM Call Router を構成できます。</span><span class="sxs-lookup"><span data-stu-id="1caba-125">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>
  
```powershell
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

<span data-ttu-id="1caba-126">スタートアップ モードが変更されているため、UM Call Router をホストしているコンピューター上で MsExchangeUMCR サービスを停止および再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1caba-126">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>
  
<span data-ttu-id="1caba-p107">ユニファイド メッセージングのセットアップを完了するには、UM メールボックス ポリシーを作成し、そのポリシーを使用して、ユーザーに対してユニファイド メッセージングを有効にする必要があります。次のようなコマンドを使用して、メールボックス ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1caba-p107">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging. You can create a mailbox policy by using a command similar to this:</span></span>
  
```powershell
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="1caba-129">また、次のようなコマンドを使用して、ユーザーに対してユニファイド メッセージングを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="1caba-129">And you can enable a user for unified messaging by using a command similar to this:</span></span>
  
```powershell
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

<span data-ttu-id="1caba-p108">上のコマンドで、Extensions パラメーターはユーザーの内線番号を表します。この例の場合、ユーザーの内線番号は 100 です。</span><span class="sxs-lookup"><span data-stu-id="1caba-p108">In the preceding command, the Extensions parameter represents the telephone extension number for the user. In this example, the user has the extension number 100.</span></span>
  
<span data-ttu-id="1caba-132">メールボックスを有効にすると、ユーザー kenmyer@litwareinc.com は Exchange ユニファイド メッセージングを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1caba-132">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="1caba-133">Skype for Business Server 管理シェル内から [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) コマンドレットを実行すると、ユーザーが Exchange UM に接続できると確認できます。</span><span class="sxs-lookup"><span data-stu-id="1caba-133">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) cmdlet from within the Skype for Business Server Management Shell:</span></span>
  
```powershell
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

<span data-ttu-id="1caba-134">ユニファイド メッセージングが有効化されている 2 番目のユーザーがいる場合は、[Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) コマンドレットを使用して、この 2 番目のユーザーが最初のユーザーにボイスメール メッセージを残すことができるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1caba-134">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>
  
```powershell
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a><span data-ttu-id="1caba-135">Microsoft Exchange Server でのユニファイド メッセージングのMicrosoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="1caba-135">Configuring Unified Messaging on Microsoft Exchange Server</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="1caba-136">Exchange ユニファイド メッセージング (UM) を使用して エンタープライズ VoIP ユーザーに通話応答、Outlook Voice Access、または自動応答サービスを提供する場合は [、「Plan for Exchange Unified Messaging integration in Skype for Business」](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)を参照し、このセクションの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="1caba-136">If you want to use Exchange Unified Messaging (UM) to provide call answering, Outlook Voice Access, or auto-attendant services for Enterprise Voice users, read [Plan for Exchange Unified Messaging integration in Skype for Business](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md), and then follow the instructions in this section.</span></span> 

<span data-ttu-id="1caba-137">Exchange ユニファイド メッセージング (UM) を構成してメールボックスとエンタープライズ VoIPするには、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1caba-137">To configure Exchange Unified Messaging (UM) to work with Enterprise Voice, you’ll need to perform the following tasks:</span></span>

- <span data-ttu-id="1caba-138">Exchange ユニファイド メッセージング (UM) サービスを実行しているサーバーで証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="1caba-138">Configure certificates on the server running Exchange Unified Messaging (UM) services</span></span>
  > [!NOTE]
  > <span data-ttu-id="1caba-139">すべてのクライアント アクセス サーバーとメールボックス サーバーをすべての UM SIP URI ダイヤル プランに追加します。</span><span class="sxs-lookup"><span data-stu-id="1caba-139">Add all Client Access and Mailbox servers to all UM SIP URI dial plans.</span></span> <span data-ttu-id="1caba-140">設定されていない場合、発信通話ルーティングは期待通り動作しません。</span><span class="sxs-lookup"><span data-stu-id="1caba-140">If not, outbound call routing won’t work as expected.</span></span> 
- <span data-ttu-id="1caba-141">必要に応じて、1 つ以上の UM SIP URI ダイヤル プランとサブスクライバー アクセス電話番号を作成し、対応する L ダイヤル プランを作成します。</span><span class="sxs-lookup"><span data-stu-id="1caba-141">Create one or more UM SIP URI dial plans, along with the subscriber access phone numbers, as needed, and then create corresponding L dial plans.</span></span>

- <span data-ttu-id="1caba-142">次のexchucutil.ps1スクリプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="1caba-142">Use the exchucutil.ps1 script to:</span></span>
    - <span data-ttu-id="1caba-143">UM IP ゲートウェイを作成します。</span><span class="sxs-lookup"><span data-stu-id="1caba-143">Create UM IP gateways.</span></span>
    - <span data-ttu-id="1caba-144">UM ハント グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="1caba-144">Create UM hunt groups.</span></span>
    - <span data-ttu-id="1caba-145">UM Active Directory ドメイン サービス オブジェクトを読み取るアクセス許可を Skype for Business Server に付与します。</span><span class="sxs-lookup"><span data-stu-id="1caba-145">Grant Skype for Business Server permission to read UM Active Directory Domain Services objects.</span></span>
- <span data-ttu-id="1caba-146">UM 自動応答オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="1caba-146">Create a UM auto-attendant object.</span></span>
- <span data-ttu-id="1caba-147">サブスクライバー アクセス オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="1caba-147">Create a subscriber access object.</span></span>
- <span data-ttu-id="1caba-148">各ユーザーの SIP URI を作成し、ユーザーを UM SIP URI ダイヤル プランに関連付けします。</span><span class="sxs-lookup"><span data-stu-id="1caba-148">Create a SIP URI for each user and associating users with a UM SIP URI dial plan.</span></span>

### <a name="requirements-and-recommendations"></a><span data-ttu-id="1caba-149">要件と推奨事項</span><span class="sxs-lookup"><span data-stu-id="1caba-149">Requirements and Recommendations</span></span>

<span data-ttu-id="1caba-150">開始する前に、このセクションのドキュメントでは、Exchange の役割であるクライアント アクセスとメールボックスが展開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1caba-150">Before you begin, the documentation in this section assumes that you have deployed the following Exchange roles: Client Access and Mailbox.</span></span> <span data-ttu-id="1caba-151">このMicrosoft Exchange Server Exchange UM は、これらのサーバー上でサービスとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="1caba-151">In Microsoft Exchange Server, Exchange UM runs as a service on these servers.</span></span>

<span data-ttu-id="1caba-152">以下の点にも注意してください。</span><span class="sxs-lookup"><span data-stu-id="1caba-152">Also note the following:</span></span>
- <span data-ttu-id="1caba-153">Exchange UM が複数のフォレストにインストールされている場合は、各 UM Exchange Serverの統合手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1caba-153">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest.</span></span> <span data-ttu-id="1caba-154">さらに、Skype for Business Server が展開されているフォレストを信頼するように各 UM フォレストを構成し、Skype for Business Server が展開されているフォレストを各 UM フォレストを信頼するように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1caba-154">In addition, each UM forest must be configured to trust the forest in which Skype for Business Server is deployed, and the forest in whichSkype for Business Server is deployed must be configured to trust each UM forest.</span></span>
- <span data-ttu-id="1caba-155">統合手順は、ユニファイド メッセージング サービスが実行されているExchange Serverの役割と、Skype for Business Server を実行しているサーバーの両方で実行されます。</span><span class="sxs-lookup"><span data-stu-id="1caba-155">Integration steps are performed on both the Exchange Server roles where Unified Messaging services are running, and on the server running Skype for Business Server.</span></span> <span data-ttu-id="1caba-156">Lync Server 2013 Exchange Serverを実行する前に、ユニファイド メッセージング統合の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1caba-156">You should perform the Exchange Server Unified Messaging integration steps before you perform the Lync Server 2013 integration steps.</span></span>
  > [!NOTE]
  > <span data-ttu-id="1caba-157">どのサーバーと管理者の役割で実行される統合手順を確認するには、オンプレミスのユニファイド メッセージングと Skype for Business を統合するための展開プロセスの概要を  [参照してください](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="1caba-157">To see which integration steps are performed on which servers and by which administrator roles, see  [Deployment process overview for integrating on-premises Unified Messaging and Skype for Business](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md).</span></span> 

<span data-ttu-id="1caba-158">Exchange UM を実行する各サーバーで次のツールを使用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1caba-158">The following tools must be available on each server running Exchange UM:</span></span>
- <span data-ttu-id="1caba-159">Exchange 管理シェル</span><span class="sxs-lookup"><span data-stu-id="1caba-159">Exchange Management Shell</span></span>
- <span data-ttu-id="1caba-160">exchucutil.ps1 スクリプト。このスクリプトは以下のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="1caba-160">The script exchucutil.ps1, which performs the following tasks:</span></span>
    - <span data-ttu-id="1caba-161">各 Skype for Business Server の UM IP ゲートウェイを作成します。</span><span class="sxs-lookup"><span data-stu-id="1caba-161">Creates a UM IP gateway for each Skype for Business Server.</span></span>
    - <span data-ttu-id="1caba-162">各ゲートウェイのハント グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="1caba-162">Creates a hunt group for each gateway.</span></span> <span data-ttu-id="1caba-163">各ハント グループのパイロット識別子は、ゲートウェイに関連付けられているフロントエンド プールまたは Standard Edition サーバーによって使用される UM SIP URI ダイヤル プランを指定します。</span><span class="sxs-lookup"><span data-stu-id="1caba-163">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Front End pool or Standard Edition server that is associated with the gateway.</span></span>
    - <span data-ttu-id="1caba-164">Skype for Business Server に、Active Directory ドメイン サービスの Exchange UM オブジェクトを読み取るアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="1caba-164">Grants Skype for Business Server permission to read Exchange UM objects in Active Directory Domain Services.</span></span>



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a><span data-ttu-id="1caba-165">ユニファイド メッセージングを使用して Microsoft Exchange でユニファイド メッセージングをExchUCUtil.ps1</span><span class="sxs-lookup"><span data-stu-id="1caba-165">Configure Unified Messaging on Microsoft Exchange with ExchUCUtil.ps1</span></span> 

<span data-ttu-id="1caba-166">Microsoft Skype for Business Server を Exchange ユニファイド メッセージング (UM) と統合する場合は、シェルで ExchUcUtil.ps1 スクリプトを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1caba-166">When you’re integrating Microsoft Skype for Business Server with Exchange Unified Messaging (UM), you have to run the ExchUcUtil.ps1 script in the Shell.</span></span> <span data-ttu-id="1caba-167">ExchUcUtil.ps1 スクリプトは次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="1caba-167">The ExchUcUtil.ps1 script does the following:</span></span>

- <span data-ttu-id="1caba-168">Skype for Business Server プールごとに UM IP ゲートウェイを作成します。</span><span class="sxs-lookup"><span data-stu-id="1caba-168">Creates a UM IP gateway for each Skype for Business Server pool.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1caba-169">ExchUcUtil.ps1 スクリプトは、1 つまたは複数の UM IP ゲートウェイを作成します。</span><span class="sxs-lookup"><span data-stu-id="1caba-169">The ExchUcUtil.ps1 script creates one or more UM IP gateways.</span></span> <span data-ttu-id="1caba-170">スクリプトで作成した 1 つのゲートウェイを除き、すべての UM IP ゲートウェイでの発信呼び出しを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1caba-170">You must disable outgoing calls on all UM IP gateways except one gateway that the script created.</span></span> <span data-ttu-id="1caba-171">これにはスクリプトを実行する前に作成した UM IP ゲートウェイでの発信呼び出しを無効にすることが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1caba-171">This includes disabling outgoing calls on UM IP gateways that were created before you ran the script.</span></span> 

- <span data-ttu-id="1caba-172">UM IP ゲートウェイごとに UM ハント グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="1caba-172">Creates a UM hunt group for each UM IP gateway.</span></span> <span data-ttu-id="1caba-173">各ハント グループのパイロット識別子は、UM IP ゲートウェイに関連付けられている Skype for Business Server フロント エンド プールまたは Standard Edition サーバーによって使用される UM SIP URI ダイヤル プランを指定します。</span><span class="sxs-lookup"><span data-stu-id="1caba-173">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Skype for Business Server Front End pool or Standard Edition server that’s associated with the UM IP gateway.</span></span>
- <span data-ttu-id="1caba-174">UM ダイヤル プラン、自動応答、UM IP ゲートウェイ、UM ハント グループなどの Active Directory UM コンテナー オブジェクトを読み取るアクセス許可を Skype for Business Server に付与します。</span><span class="sxs-lookup"><span data-stu-id="1caba-174">Grants Skype for Business Server permission to read Active Directory UM container objects such as UM dial plans, auto attendants, UM IP gateways, and UM hunt groups.</span></span>
  > [!IMPORTANT]
  > <span data-ttu-id="1caba-175">各 UM フォレストは、Skype for Business Server が展開されているフォレストを信頼するように構成する必要があります。また、Skype for Business Server 2013 が展開されているフォレストは、各 UM フォレストを信頼するように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1caba-175">Each UM forest must be configured to trust the forest in which Skype for Business Server is deployed, and the forest in which Skype for Business Server 2013 is deployed must be configured to trust each UM forest.</span></span> <span data-ttu-id="1caba-176">Exchange UM が複数のフォレストにインストールされている場合は、UM フォレストごとに Exchange Server 統合手順を実行するか、Skype for Business Server ドメインを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1caba-176">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest or you’ll have to specify the Skype for Business Server domain.</span></span> <span data-ttu-id="1caba-177">たとえば、ExchUcUtil.ps1 –Forest:<lync-domain-controller-fqdn>。</span><span class="sxs-lookup"><span data-stu-id="1caba-177">For example, ExchUcUtil.ps1 –Forest:<lync-domain-controller-fqdn>.</span></span> 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a><span data-ttu-id="1caba-178">シェルを使用して ExchUcUtil.ps1 スクリプトを実行する</span><span class="sxs-lookup"><span data-stu-id="1caba-178">Use the Shell to run the ExchUcUtil.ps1 script</span></span>

<span data-ttu-id="1caba-179">Skype for Business Server ExchUcUtil.ps1トポロジ内の任意の Exchange サーバーで、このスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="1caba-179">Run the ExchUcUtil.ps1 script on any Exchange server in your organization that’s in the same topology as Skype for Business Server.</span></span> <span data-ttu-id="1caba-180">シェルを使用してメールボックス サーバーからスクリプトを実行するか、クライアント アクセス サーバーのリモート Windows PowerShell を使用してスクリプトを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="1caba-180">You can run the script from a Mailbox server using the Shell or you can run the script using Remote Windows PowerShell on a Client Access server.</span></span> <span data-ttu-id="1caba-181">組織のクライアント アクセス サーバーでスクリプトを実行すると、クライアント アクセス サーバーがリモート Windows PowerShell セッションを組織のメールボックス サーバーにプロキシ処理します。</span><span class="sxs-lookup"><span data-stu-id="1caba-181">If you run the script on a Client Access server in your organization, the Client Access server will proxy the Remote Windows PowerShell session to a Mailbox server in the organization.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="1caba-182">ExchUcUtil.ps1 スクリプトは、1 つまたは複数の UM IP ゲートウェイを作成します。</span><span class="sxs-lookup"><span data-stu-id="1caba-182">The ExchUcUtil.ps1 script creates one or more UM IP gateways.</span></span> <span data-ttu-id="1caba-183">スクリプトで作成した 1 つのゲートウェイを除き、すべての UM IP ゲートウェイでの発信呼び出しを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1caba-183">You must disable outgoing calls on all UM IP gateways except one gateway that the script created.</span></span> <span data-ttu-id="1caba-184">これにはスクリプトを実行する前に作成した UM IP ゲートウェイでの発信呼び出しを無効にすることが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1caba-184">This includes disabling outgoing calls on UM IP gateways that were created before you ran the script.</span></span> <span data-ttu-id="1caba-185">UM IP ゲートウェイでの発信呼び出しを無効にするには、「UM IP ゲートウェイで送信呼び出しを無効にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1caba-185">To disable outgoing calls on a UM IP gateway, see Disable outgoing calls on UM IP gateways.</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="1caba-186">Exchange 組織管理役割のアクセス許可を保有するか、Exchange 組織管理者セキュリティ グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1caba-186">You must have the permissions of the Exchange Organization Management role or be a member of the Exchange Organization Administrators security group to run the script.</span></span> 

1. <span data-ttu-id="1caba-187">Exchange 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1caba-187">Open the Exchange Management Shell.</span></span>
2. <span data-ttu-id="1caba-188">C:\Windows\System32 プロンプトで **、「cd \<drive letter> :\Program Files\Microsoft\Exchange Server\V15\Scripts>.ExchUcUtil.ps1」** と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1caba-188">At the C:\Windows\System32 prompt, type **cd \<drive letter>:\Program Files\Microsoft\Exchange Server\V15\Scripts>.ExchUcUtil.ps1**, and then press Enter.</span></span>

#### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="1caba-189">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="1caba-189">How do you know this worked?</span></span>

<span data-ttu-id="1caba-190">ExchUcUtul.ps1 スクリプトが正常に完了したことを確認するには、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="1caba-190">To verify that the ExchUcUtul.ps1 script completed successfully, do the following:</span></span>
- <span data-ttu-id="1caba-191">Get-UMIPGateway コマンドレットか EAC を使用し、作成された新しい UM IP ゲートウェイを表示します。</span><span class="sxs-lookup"><span data-stu-id="1caba-191">Use the Get-UMIPGateway cmdlet or the EAC to view the new UM IP gateway or gateways that were created.</span></span>
- <span data-ttu-id="1caba-192">Get-UMHuntGroup コマンドレットか EAC を使用し、作成された新しい UM ハント グループを表示します。</span><span class="sxs-lookup"><span data-stu-id="1caba-192">Use the Get-UMHuntGroup cmdlet or the EAC to view the new UM hunt group or groups that were created.</span></span>

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a><span data-ttu-id="1caba-193">ユニファイド メッセージングを実行しているサーバーでExchange Serverを構成する</span><span class="sxs-lookup"><span data-stu-id="1caba-193">Configure certificates on the server running Exchange Server Unified Messaging</span></span>
 
<span data-ttu-id="1caba-194">「計画」のドキュメントの「Skype for Business Server での Exchange ユニファイド メッセージング統合の計画」の説明に従って Exchange ユニファイド メッセージング (UM) を展開し、組織内の エンタープライズ VoIP ユーザーに Exchange UM 機能を提供する場合は、次の手順を使用して、Exchange UM を実行しているサーバー上で証明書を構成できます。</span><span class="sxs-lookup"><span data-stu-id="1caba-194">If you have deployed Exchange Unified Messaging (UM), as described in Planning for Exchange Unified Messaging integration in Skype for Business Server in the Planning documentation, and you want to provide Exchange UM features to Enterprise Voice users in your organization, you can use the following procedures to configure the certificate on the server running Exchange UM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1caba-195">内部証明書の場合、Skype for Business Server を実行しているサーバーと Microsoft Exchange を実行しているサーバーの両方に、相互に信頼できる信頼されたルート証明機関の証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="1caba-195">For internal certificates, both the servers running Skype for Business Server and the servers running Microsoft Exchange must have trusted root authority certificates that are mutually trusted.</span></span> <span data-ttu-id="1caba-196">証明機関 (CA) は、サーバーが信頼できるルート証明機関の証明書ストアに登録されている証明機関のルート証明書を持っている限り、同じ証明機関または別の証明機関のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="1caba-196">The certification authority (CA) can either be the same, or a different certification authority, as long as the servers have the certification authority’s root certificate registered in their trusted root authority certificate store.</span></span> 

<span data-ttu-id="1caba-197">Skype for Business Exchange Server接続するには、サーバー証明書を使用して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1caba-197">The Exchange Server must be configured with a server certificate in order to connect to Skype for Business Server:</span></span>
1. <span data-ttu-id="1caba-198">Exchange Server の CA 証明書をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="1caba-198">Download the CA certificate for the Exchange Server.</span></span>
2. <span data-ttu-id="1caba-199">Exchange Server の CA 証明書をインストールします。</span><span class="sxs-lookup"><span data-stu-id="1caba-199">Install the CA certificate for the Exchange Server.</span></span>
3. <span data-ttu-id="1caba-200">CA が、Exchange Server の信頼されたルート証明機関一覧にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1caba-200">Verify that the CA is in the list of trusted root CAs of the Exchange Server.</span></span>
4. <span data-ttu-id="1caba-201">Exchange Server の証明書要求を作成し、証明書をインストールします。</span><span class="sxs-lookup"><span data-stu-id="1caba-201">Create a certificate request for the Exchange Server and install the certificate.</span></span> 
5. <span data-ttu-id="1caba-202">Exchange Server の証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1caba-202">Assign the certificate for the Exchange Server.</span></span>


<span data-ttu-id="1caba-203">**CA 証明書をダウンロードするには、**</span><span class="sxs-lookup"><span data-stu-id="1caba-203">**To download the CA certificate:**</span></span>

1. <span data-ttu-id="1caba-204">Exchange UM を実行しているサーバーで、[スタート] ボタン、[ファイル名を指定して実行] の順にクリックし、「http:// **\<name of your Issuing CA Server> /certsrv」** と入力して **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1caba-204">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<name of your Issuing CA Server>/certsrv**, and then click **OK**.</span></span>
2. <span data-ttu-id="1caba-205">[タスクの選択] で **、[CA 証明書、証明書チェーン、または CRL のダウンロード] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1caba-205">Under Select a task, click **Download a CA certificate, certificate chain, or CRL**.</span></span>
3. <span data-ttu-id="1caba-206">[CA **証明書、証明書チェーン、または CRL** のダウンロード] で **、Base 64** へのエンコード方法を選択し、[CA 証明書のダウンロード] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1caba-206">Under **Download a CA Certificate, Certificate Chain, or CRL**, select **Encoding Method to Base 64**, and then click **Download CA certificate**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="1caba-207">この手順では、DER (Distinguished Encoding Rules) エンコードを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="1caba-207">You can also specify Distinguished Encoding Rules (DER) encoding at this step.</span></span> <span data-ttu-id="1caba-208">DER エンコードを選択する場合は、この手順の次のステップと「**CA 証明書をインストールするには**」のステップ 10 のファイル タイプが .cer ではなく、.p7b になります。</span><span class="sxs-lookup"><span data-stu-id="1caba-208">If you select DER encoding, the file type in the next step of this procedure and in step 10 of **To Install the CA certificate** is .p7b rather than .cer.</span></span> 
4. <span data-ttu-id="1caba-p123">**[ファイルのダウンロード]** ダイアログ ボックスで **[保存]** をクリックし、ファイルをサーバー上のハード ディスクに保存します。(このファイルの拡張子は、前のステップで選択したエンコードに応じて、.cer または .p7b となります。)</span><span class="sxs-lookup"><span data-stu-id="1caba-p123">In the **File Download** dialog box, click **Save**, and then save the file to the hard disk on the server. (The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in the previous step.)</span></span>

<span data-ttu-id="1caba-211">**CA 証明書をインストールするには、次の手順を実行します。**</span><span class="sxs-lookup"><span data-stu-id="1caba-211">**To install the CA certificate:**</span></span>

1. <span data-ttu-id="1caba-212">Exchange UM を実行しているサーバーで、[スタート] ボタンをクリックし、[ファイル名を指定して実行] をクリックし、[開く] ボックスに **「mmc」** と入力して **、[OK]** をクリックして、Microsoft 管理コンソール (MMC) を開きます。</span><span class="sxs-lookup"><span data-stu-id="1caba-212">On the server running Exchange UM, open Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the Open box, and then clicking **OK**.</span></span>
2. <span data-ttu-id="1caba-213">**[ファイル]** メニューの **[スナップインの追加と削除]** をクリックし、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1caba-213">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>
3. <span data-ttu-id="1caba-214">**[スタンドアロン スナップインの追加]** ボックスで、**[証明書]** をクリックし、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1caba-214">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>
4. <span data-ttu-id="1caba-215">**[証明書スナップイン]** ダイアログ ボックスの **[コンピューター アカウント]** をクリックし、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1caba-215">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>
5. <span data-ttu-id="1caba-216">[コンピューターの **選択** ] ダイアログ ボックスで、ローカル コンピューター **(** このコンソールが実行されているコンピューター) チェック ボックスがオンに設定され、[完了] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1caba-216">In the **Select Computer** dialog box, verify that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>
6. <span data-ttu-id="1caba-217">**[閉じる]** をクリックし、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1caba-217">Click **Close**, and then click **OK**.</span></span> 
7. <span data-ttu-id="1caba-218">コンソール ツリーで、**[証明書 (ローカル コンピューター)]** を展開し、**[信頼されたルート証明機関]** を展開して **[証明書]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1caba-218">In the console tree, expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>
8. <span data-ttu-id="1caba-219">**[証明書]** を右クリックし、**[すべてのタスク]** をクリックして **[インポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1caba-219">Right-click **Certificates**, click **All Tasks**, and click **Import**.</span></span>
9. <span data-ttu-id="1caba-220">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1caba-220">Click **Next**.</span></span> 
10. <span data-ttu-id="1caba-p124">**[参照]** をクリックしてファイルを特定し、**[次へ]** をクリックします。(このファイルの拡張子は、「**CA 証明書をダウンロードするには**」のステップ 3 で選択したエンコードに応じて、.cer または .p7b となります。)</span><span class="sxs-lookup"><span data-stu-id="1caba-p124">Click **Browse** to locate the file, and then click **Next**. (The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in step 3 of **To download the CA certificate**.</span></span>
11. <span data-ttu-id="1caba-223">[ **すべての証明書を次のストア** に配置する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1caba-223">Click **Place All Certificates** in the following store.</span></span>
12. <span data-ttu-id="1caba-224">**[参照]** をクリックし、**[信頼されたルート証明機関]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1caba-224">Click **Browse**, and then select **Trusted Root Certification Authorities**.</span></span> 
13. <span data-ttu-id="1caba-225">**[次へ]** をクリックし、設定を確認して、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1caba-225">Click **Next** to verify the settings, and then click **Finish**.</span></span> 


<span data-ttu-id="1caba-226">**CA が信頼されたルート CA の一覧に含確認するには、次の手順を実行します。**</span><span class="sxs-lookup"><span data-stu-id="1caba-226">**To verify that the CA is in the list of trusted root CAs:**</span></span>

1. <span data-ttu-id="1caba-227">Exchange UM を実行しているサーバーの MMC で、証明書 (ローカル コンピューター) を展開し、[信頼されたルート証明機関] を展開して、[証明書] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1caba-227">On the server running Exchange UM, in MMC expand Certificates (Local Computer), expand Trusted Root Certification Authorities, and then click Certificates.</span></span>
2. <span data-ttu-id="1caba-228">詳細ウィンドウで、CA が、信頼されたルート証明機関の一覧にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1caba-228">In the details pane, verify that your CA is on the list of trusted CAs.</span></span>


