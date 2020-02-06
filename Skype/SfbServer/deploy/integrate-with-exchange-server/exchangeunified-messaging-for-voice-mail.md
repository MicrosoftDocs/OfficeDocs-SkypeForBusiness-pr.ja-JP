---
title: Skype for Business Server ボイス メールに対する Exchange Server ユニファイド メッセージングの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '概要: Skype for Business Server ボイスメール用に Exchange Server ユニファイドメッセージングを構成します。'
ms.openlocfilehash: affaf5eb25b755d51d4ce47dd75834b6704d7610
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797068"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a><span data-ttu-id="b6a8f-103">Skype for Business Server ボイス メールに対する Exchange Server ユニファイド メッセージングの構成</span><span class="sxs-lookup"><span data-stu-id="b6a8f-103">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>
 
<span data-ttu-id="b6a8f-104">**概要:** Skype for Business Server ボイスメール用に Exchange Server ユニファイドメッセージングを構成します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-104">**Summary:** Configure Exchange Server Unified Messaging for Skype for Business Server voice mail.</span></span>
  
<span data-ttu-id="b6a8f-105">Skype for Business Server を使用すると、ボイスメールメッセージを Exchange Server 2016 または Exchange Server 2013 に保存することができます。これらのボイスメールメッセージは、ユーザーの受信トレイにメールメッセージとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-105">Skype for Business Server enables you to have voicemail messages stored in Exchange Server 2016 or Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> 

> [!NOTE]
> <span data-ttu-id="b6a8f-106">以前に認識されていた exchange ユニファイドメッセージングは Exchange 2019 では利用できなくなりましたが、電話システムを使ってボイスメールメッセージを録音し、ユーザーの Exchange メールボックスに記録を残すことができます。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-106">Exchange Unified Messaging as previously known is no longer available in Exchange 2019, but you can still use Phone System to record voicemail messages and then leave the recording in a user's Exchange mailbox.</span></span> <span data-ttu-id="b6a8f-107">詳細については、「[クラウドボイスメールサービスの計画](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-107">See [Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) for more information.</span></span>
  
<span data-ttu-id="b6a8f-108">Skype for Business Server と Exchange Server 2016 または Exchange Server 2013 の間にサーバー間認証を既に構成している場合は、ユニファイドメッセージングを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-108">If you have already configured server-to-server authentication between Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, then you are ready to setup unified messaging.</span></span> <span data-ttu-id="b6a8f-109">そのためには、まず Exchange Server で新しいユニファイドメッセージングダイヤルプランを作成して割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-109">To do so, you must first create and assign a new unified messaging dial plan on your Exchange Server.</span></span> <span data-ttu-id="b6a8f-110">たとえば、次の2つのコマンド (Exchange 管理シェル内から実行) では、Exchange 用の新しい3桁のダイヤルプランを構成します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-110">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>
  
```powershell
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="b6a8f-111">この例の最初のコマンドでは、VoIPSecurity パラメーターとパラメーター値 "セキュリティ保護" は、シグナリングチャネルがトランスポート層セキュリティ (TLS) を使用して暗号化されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-111">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicates that the signaling channel is encrypted by using Transport Layer Security (TLS).</span></span> <span data-ttu-id="b6a8f-112">URIType "SipName" は、SIP プロトコルを使用してメッセージが送受信されることを指定し、CountryOrRegionCode の 1 は、ダイヤル プランが米国に適用されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-112">The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>
  
<span data-ttu-id="b6a8f-113">2 番目のコマンドで、ConfiguredInCountryOrRegionGroups パラメーターに渡されるパラメーター値は、このダイヤル プランで使用できる国内のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-113">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="b6a8f-114">"Anywhere、\*,\*\*" というパラメーター値は、次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-114">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>
  
- <span data-ttu-id="b6a8f-115">グループ名 ("Anywhere")</span><span class="sxs-lookup"><span data-stu-id="b6a8f-115">Group name ("Anywhere")</span></span>
    
- <span data-ttu-id="b6a8f-116">Allowed連番文字列 (\*任意の数字文字列が許可されていることを示すワイルドカード文字)</span><span class="sxs-lookup"><span data-stu-id="b6a8f-116">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>
    
- <span data-ttu-id="b6a8f-117">[ダイヤル番号]\*文字列 (およびダイヤルされた番号が許可されていることを示すワイルドカード文字)</span><span class="sxs-lookup"><span data-stu-id="b6a8f-117">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>
    
- <span data-ttu-id="b6a8f-118">TextComment (\*任意のテキストコマンドが許可されていることを示すワイルドカード文字)</span><span class="sxs-lookup"><span data-stu-id="b6a8f-118">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>
    
> [!NOTE]
> <span data-ttu-id="b6a8f-119">新しいダイヤル プランを作成すると、既定のメールボックス ポリシーも作成されます。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-119">Creating a new dial plan will also create a Default Mailbox Policy.</span></span> 
  
<span data-ttu-id="b6a8f-120">新しいダイヤルプランを作成して構成した後、新しいダイヤルプランをユニファイドメッセージングサーバーに追加し、そのサーバーのスタートアップモードを変更する必要があります。特に、スタートアップモードを "デュアル" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-120">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="b6a8f-121">Exchange 管理シェルでは、次の2つのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-121">You can perform both of these tasks from within the Exchange Management Shell:</span></span>
  
```powershell
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

<span data-ttu-id="b6a8f-122">ユニファイドメッセージングサーバーの構成が完了したら、次に、Import-exchangecertificate コマンドレットを実行して、Exchange 証明書がユニファイドメッセージングサービスに適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-122">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>
  
```powershell
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

<span data-ttu-id="b6a8f-p106">証明書の割り当てが適切に行われた後、ユニファイド メッセージング サーバー上の MsExchangeUM サービスを停止して、再起動する必要があります。このサービスは、スタートアップ モードを変更した場合はいつでも、停止して再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-p106">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server. This service must be stopped and restarted any time you change the startup mode.</span></span>
  
<span data-ttu-id="b6a8f-125">ユニファイド メッセージング サーバーの構成が終了すると、UM Call Router を構成できます。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-125">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>
  
```powershell
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

<span data-ttu-id="b6a8f-126">スタートアップ モードが変更されているため、UM Call Router をホストしているコンピューター上で MsExchangeUMCR サービスを停止および再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-126">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>
  
<span data-ttu-id="b6a8f-p107">ユニファイド メッセージングのセットアップを完了するには、UM メールボックス ポリシーを作成し、そのポリシーを使用して、ユーザーのユニファイド メッセージングを有効にする必要があります。次のようなコマンドを使用して、メールボックス ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-p107">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging. You can create a mailbox policy by using a command similar to this:</span></span>
  
```powershell
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="b6a8f-129">また、次のようなコマンドを使用して、ユーザーのユニファイド メッセージングを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-129">And you can enable a user for unified messaging by using a command similar to this:</span></span>
  
```powershell
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

<span data-ttu-id="b6a8f-p108">上のコマンドで、Extensions パラメーターはユーザーの内線番号を表します。この例の場合、ユーザーの内線番号は 100 です。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-p108">In the preceding command, the Extensions parameter represents the telephone extension number for the user. In this example, the user has the extension number 100.</span></span>
  
<span data-ttu-id="b6a8f-132">メールボックスを有効にすると、ユーザー kenmyer@litwareinc.com は Exchange ユニファイド メッセージングを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-132">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="b6a8f-133">Skype for Business Server 管理シェル内から[テスト用の CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps)コマンドレットを実行することで、ユーザーが Exchange UM に接続できることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-133">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) cmdlet from within the Skype for Business Server Management Shell:</span></span>
  
```powershell
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

<span data-ttu-id="b6a8f-134">ユニファイド メッセージングが有効化されている 2 番目のユーザーがいる場合は、[Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) コマンドレットを使用して、この 2 番目のユーザーが最初のユーザーにボイスメール メッセージを残せることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-134">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>
  
```powershell
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a><span data-ttu-id="b6a8f-135">Microsoft Exchange Server でのユニファイドメッセージングの構成</span><span class="sxs-lookup"><span data-stu-id="b6a8f-135">Configuring Unified Messaging on Microsoft Exchange Server</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="b6a8f-136">Exchange ユニファイドメッセージング (UM) を使用して、通話応答、Outlook Voice Access、またはエンタープライズボイスユーザー向けの自動応答サービスを提供する場合は、「 [Skype For business での Exchange ユニファイドメッセージングの統合の計画](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)」を参照して、このセクションの手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-136">If you want to use Exchange Unified Messaging (UM) to provide call answering, Outlook Voice Access, or auto-attendant services for Enterprise Voice users, read [Plan for Exchange Unified Messaging integration in Skype for Business](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md), and then follow the instructions in this section.</span></span> 

<span data-ttu-id="b6a8f-137">エンタープライズ Voip と連携するように Exchange ユニファイドメッセージング (UM) を構成するには、次の作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-137">To configure Exchange Unified Messaging (UM) to work with Enterprise Voice, you’ll need to perform the following tasks:</span></span>

- <span data-ttu-id="b6a8f-138">Exchange ユニファイドメッセージング (UM) サービスを実行しているサーバーで証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="b6a8f-138">Configure certificates on the server running Exchange Unified Messaging (UM) services</span></span>
  > [!NOTE]
  > <span data-ttu-id="b6a8f-139">すべてのクライアントアクセスとメールボックスサーバーを UM SIP のすべての URI ダイヤルプランに追加します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-139">Add all Client Access and Mailbox servers to all UM SIP URI dial plans.</span></span> <span data-ttu-id="b6a8f-140">そうしないと、発信通話のルーティングが予期したとおりに機能しません。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-140">If not, outbound call routing won’t work as expected.</span></span> 
- <span data-ttu-id="b6a8f-141">必要に応じて、サブスクライバーアクセス用電話番号と共に1つまたは複数の UM SIP URI ダイヤルプランを作成して、対応する L dial プランを作成します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-141">Create one or more UM SIP URI dial plans, along with the subscriber access phone numbers, as needed, and then create corresponding L dial plans.</span></span>

- <span data-ttu-id="b6a8f-142">次のような操作を実行するために exchucutil スクリプトを使います。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-142">Use the exchucutil.ps1 script to:</span></span>
    - <span data-ttu-id="b6a8f-143">UM IP ゲートウェイを作成します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-143">Create UM IP gateways.</span></span>
    - <span data-ttu-id="b6a8f-144">UM ハントグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-144">Create UM hunt groups.</span></span>
    - <span data-ttu-id="b6a8f-145">UM Active Directory ドメインサービスオブジェクトを読み取るための Skype for Business Server 権限を付与します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-145">Grant Skype for Business Server permission to read UM Active Directory Domain Services objects.</span></span>
- <span data-ttu-id="b6a8f-146">UM 自動応答オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-146">Create a UM auto-attendant object.</span></span>
- <span data-ttu-id="b6a8f-147">サブスクライバーアクセスオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-147">Create a subscriber access object.</span></span>
- <span data-ttu-id="b6a8f-148">ユーザーごとに SIP URI を作成し、UM SIP URI ダイヤルプランを使用してユーザーを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-148">Create a SIP URI for each user and associating users with a UM SIP URI dial plan.</span></span>

### <a name="requirements-and-recommendations"></a><span data-ttu-id="b6a8f-149">要件と推奨事項</span><span class="sxs-lookup"><span data-stu-id="b6a8f-149">Requirements and Recommendations</span></span>

<span data-ttu-id="b6a8f-150">始める前に、このセクションのドキュメントでは、クライアントアクセスとメールボックスという Exchange ロールが展開されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-150">Before you begin, the documentation in this section assumes that you have deployed the following Exchange roles: Client Access and Mailbox.</span></span> <span data-ttu-id="b6a8f-151">Microsoft Exchange Server では、Exchange UM はこれらのサーバーでサービスとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-151">In Microsoft Exchange Server, Exchange UM runs as a service on these servers.</span></span>

<span data-ttu-id="b6a8f-152">次の点にも注意してください。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-152">Also note the following:</span></span>
- <span data-ttu-id="b6a8f-153">Exchange UM が複数のフォレストにインストールされている場合は、各 UM フォレストで Exchange Server の統合手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-153">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest.</span></span> <span data-ttu-id="b6a8f-154">さらに、各 UM フォレストが、Skype for Business Server が展開されているフォレストを信頼するように構成されている必要があります。また、Skype for Business Server が展開されているフォレストが各 UM フォレストを信頼するように構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-154">In addition, each UM forest must be configured to trust the forest in which Skype for Business Server is deployed, and the forest in whichSkype for Business Server is deployed must be configured to trust each UM forest.</span></span>
- <span data-ttu-id="b6a8f-155">統合手順は、ユニファイドメッセージングサービスが実行されている Exchange Server の役割と、Skype for Business Server を実行しているサーバーで実行されます。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-155">Integration steps are performed on both the Exchange Server roles where Unified Messaging services are running, and on the server running Skype for Business Server.</span></span> <span data-ttu-id="b6a8f-156">Lync Server 2013 の統合手順を実行する前に、Exchange Server ユニファイドメッセージング統合の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-156">You should perform the Exchange Server Unified Messaging integration steps before you perform the Lync Server 2013 integration steps.</span></span>
  > [!NOTE]
  > <span data-ttu-id="b6a8f-157">どのサーバーに対して実行される統合手順と管理者の役割を確認するには、「[展開プロセスの概要」でオンプレミスのユニファイドメッセージングと Skype For business を統合](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-157">To see which integration steps are performed on which servers and by which administrator roles, see  [Deployment process overview for integrating on-premises Unified Messaging and Skype for Business](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md).</span></span> 

<span data-ttu-id="b6a8f-158">Exchange UM を実行している各サーバーでは、次のツールを使用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-158">The following tools must be available on each server running Exchange UM:</span></span>
- <span data-ttu-id="b6a8f-159">Exchange 管理シェル</span><span class="sxs-lookup"><span data-stu-id="b6a8f-159">Exchange Management Shell</span></span>
- <span data-ttu-id="b6a8f-160">スクリプト exchucutil は、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-160">The script exchucutil.ps1, which performs the following tasks:</span></span>
    - <span data-ttu-id="b6a8f-161">各 Skype for Business Server 用に UM IP ゲートウェイを作成します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-161">Creates a UM IP gateway for each Skype for Business Server.</span></span>
    - <span data-ttu-id="b6a8f-162">各ゲートウェイのハントグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-162">Creates a hunt group for each gateway.</span></span> <span data-ttu-id="b6a8f-163">各ハントグループのパイロット識別子は、ゲートウェイに関連付けられているフロントエンドプールまたは Standard Edition サーバーで使用される UM SIP URI ダイヤルプランを指定します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-163">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Front End pool or Standard Edition server that is associated with the gateway.</span></span>
    - <span data-ttu-id="b6a8f-164">Active Directory ドメインサービスの Exchange UM オブジェクトを読み取るための Skype for Business Server 権限を付与します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-164">Grants Skype for Business Server permission to read Exchange UM objects in Active Directory Domain Services.</span></span>



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a><span data-ttu-id="b6a8f-165">Configure Unified Messaging on Microsoft Exchange with ExchUCUtil.ps1</span><span class="sxs-lookup"><span data-stu-id="b6a8f-165">Configure Unified Messaging on Microsoft Exchange with ExchUCUtil.ps1</span></span> 

<span data-ttu-id="b6a8f-166">Microsoft Skype for Business Server を Exchange ユニファイドメッセージング (UM) と統合する場合は、シェルで ExchUcUtil というスクリプトを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-166">When you’re integrating Microsoft Skype for Business Server with Exchange Unified Messaging (UM), you have to run the ExchUcUtil.ps1 script in the Shell.</span></span> <span data-ttu-id="b6a8f-167">ExchUcUtil スクリプトは、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-167">The ExchUcUtil.ps1 script does the following:</span></span>

- <span data-ttu-id="b6a8f-168">各 Skype for Business Server プール用に UM IP ゲートウェイを作成します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-168">Creates a UM IP gateway for each Skype for Business Server pool.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6a8f-169">ExchUcUtil スクリプトは、1つ以上の UM IP ゲートウェイを作成します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-169">The ExchUcUtil.ps1 script creates one or more UM IP gateways.</span></span> <span data-ttu-id="b6a8f-170">スクリプトで作成された1つのゲートウェイを除き、すべての UM IP ゲートウェイで発信通話を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-170">You must disable outgoing calls on all UM IP gateways except one gateway that the script created.</span></span> <span data-ttu-id="b6a8f-171">これには、スクリプトを実行する前に作成された UM IP ゲートウェイでの発信通話の無効化が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-171">This includes disabling outgoing calls on UM IP gateways that were created before you ran the script.</span></span> 

- <span data-ttu-id="b6a8f-172">UM IP ゲートウェイごとに UM ハントグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-172">Creates a UM hunt group for each UM IP gateway.</span></span> <span data-ttu-id="b6a8f-173">各ハントグループのパイロット識別子は、UM IP ゲートウェイに関連付けられている Skype for Business Server のフロントエンドプールまたは Standard Edition サーバーで使用される UM SIP URI ダイヤルプランを指定します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-173">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Skype for Business Server Front End pool or Standard Edition server that’s associated with the UM IP gateway.</span></span>
- <span data-ttu-id="b6a8f-174">UM ダイヤルプラン、自動応答、UM IP ゲートウェイ、UM ハントグループなどの Active Directory UM コンテナーオブジェクトを読み取るための Skype for Business Server 権限を付与します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-174">Grants Skype for Business Server permission to read Active Directory UM container objects such as UM dial plans, auto attendants, UM IP gateways, and UM hunt groups.</span></span>
  > [!IMPORTANT]
  > <span data-ttu-id="b6a8f-175">各 UM フォレストは、Skype for Business Server が展開されているフォレストを信頼するように構成する必要があります。また、Skype for Business Server 2013 が展開されているフォレストは、各 UM フォレストを信頼するように構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-175">Each UM forest must be configured to trust the forest in which Skype for Business Server is deployed, and the forest in which Skype for Business Server 2013 is deployed must be configured to trust each UM forest.</span></span> <span data-ttu-id="b6a8f-176">Exchange UM が複数のフォレストにインストールされている場合は、UM フォレストごとに Exchange Server の統合手順を実行するか、Skype for Business Server ドメインを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-176">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest or you’ll have to specify the Skype for Business Server domain.</span></span> <span data-ttu-id="b6a8f-177">たとえば、ExchUcUtil は、<lync-ドメインコントローラー-fqdn>] のようになります。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-177">For example, ExchUcUtil.ps1 –Forest:<lync-domain-controller-fqdn>.</span></span> 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a><span data-ttu-id="b6a8f-178">Shell を使用して ExchUcUtil を実行します。 ps1 スクリプト</span><span class="sxs-lookup"><span data-stu-id="b6a8f-178">Use the Shell to run the ExchUcUtil.ps1 script</span></span>

<span data-ttu-id="b6a8f-179">組織内のすべての Exchange server で、Skype for Business Server と同じトポロジを使用している場合は、ExchUcUtil スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-179">Run the ExchUcUtil.ps1 script on any Exchange server in your organization that’s in the same topology as Skype for Business Server.</span></span> <span data-ttu-id="b6a8f-180">シェルを使用してメールボックスサーバーからスクリプトを実行することも、クライアントアクセスサーバーでリモート Windows PowerShell を使用してスクリプトを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-180">You can run the script from a Mailbox server using the Shell or you can run the script using Remote Windows PowerShell on a Client Access server.</span></span> <span data-ttu-id="b6a8f-181">組織内のクライアントアクセスサーバーでスクリプトを実行すると、クライアントアクセスサーバーは、リモートの Windows PowerShell セッションを組織内のメールボックスサーバーにプロキシします。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-181">If you run the script on a Client Access server in your organization, the Client Access server will proxy the Remote Windows PowerShell session to a Mailbox server in the organization.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="b6a8f-182">ExchUcUtil スクリプトは、1つ以上の UM IP ゲートウェイを作成します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-182">The ExchUcUtil.ps1 script creates one or more UM IP gateways.</span></span> <span data-ttu-id="b6a8f-183">スクリプトで作成された1つのゲートウェイを除き、すべての UM IP ゲートウェイで発信通話を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-183">You must disable outgoing calls on all UM IP gateways except one gateway that the script created.</span></span> <span data-ttu-id="b6a8f-184">これには、スクリプトを実行する前に作成された UM IP ゲートウェイでの発信通話の無効化が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-184">This includes disabling outgoing calls on UM IP gateways that were created before you ran the script.</span></span> <span data-ttu-id="b6a8f-185">UM IP ゲートウェイでの発信通話を無効にするには、「UM IP ゲートウェイでの発信通話の無効化」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-185">To disable outgoing calls on a UM IP gateway, see Disable outgoing calls on UM IP gateways.</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="b6a8f-186">スクリプトを実行するには、Exchange 組織管理役割のアクセス許可、または Exchange 組織管理者セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-186">You must have the permissions of the Exchange Organization Management role or be a member of the Exchange Organization Administrators security group to run the script.</span></span> 

1. <span data-ttu-id="b6a8f-187">Exchange 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-187">Open the Exchange Management Shell.</span></span>
2. <span data-ttu-id="b6a8f-188">C:\Windows\System32 プロンプトで、 \*\* \<cd ドライブ文字>: Files\Microsoft\Exchange Server\V15\Scripts> を入力します。「ExchUcUtil\*\*」と入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-188">At the C:\Windows\System32 prompt, type **cd \<drive letter>:\Program Files\Microsoft\Exchange Server\V15\Scripts>.ExchUcUtil.ps1**, and then press Enter.</span></span>

#### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="b6a8f-189">これが機能したことを知る方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-189">How do you know this worked?</span></span>

<span data-ttu-id="b6a8f-190">ExchUcUtul. ps1 スクリプトが正常に完了したことを確認するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-190">To verify that the ExchUcUtul.ps1 script completed successfully, do the following:</span></span>
- <span data-ttu-id="b6a8f-191">Get-UMIPGateway コマンドレットまたは EAC を使用して、作成された新しい UM IP ゲートウェイまたはゲートウェイを表示します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-191">Use the Get-UMIPGateway cmdlet or the EAC to view the new UM IP gateway or gateways that were created.</span></span>
- <span data-ttu-id="b6a8f-192">Get-UMHuntGroup コマンドレットまたは EAC を使用して、作成された新しい UM ハントグループまたはグループを表示します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-192">Use the Get-UMHuntGroup cmdlet or the EAC to view the new UM hunt group or groups that were created.</span></span>

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a><span data-ttu-id="b6a8f-193">Exchange Server ユニファイドメッセージングを実行しているサーバーで証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="b6a8f-193">Configure certificates on the server running Exchange Server Unified Messaging</span></span>
 
<span data-ttu-id="b6a8f-194">計画ドキュメントの「Skype for Business Server での Exchange ユニファイドメッセージングの統合を計画する」の説明に従って、Exchange ユニファイドメッセージング (UM) を展開している場合、Exchange UM 機能を組織内のエンタープライズボイスユーザーに提供する必要があります。組織では、次の手順を使用して、Exchange UM を実行しているサーバー上で証明書を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-194">If you have deployed Exchange Unified Messaging (UM), as described in Planning for Exchange Unified Messaging integration in Skype for Business Server in the Planning documentation, and you want to provide Exchange UM features to Enterprise Voice users in your organization, you can use the following procedures to configure the certificate on the server running Exchange UM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6a8f-195">内部証明書については、Skype for Business Server を実行しているサーバーと、Microsoft Exchange を実行しているサーバーの両方が相互に信頼されている信頼できるルート証明書を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-195">For internal certificates, both the servers running Skype for Business Server and the servers running Microsoft Exchange must have trusted root authority certificates that are mutually trusted.</span></span> <span data-ttu-id="b6a8f-196">証明機関 (CA) は、信頼されたルート機関の証明書ストアに証明機関のルート証明書が登録されている限り、同じまたは別の証明機関とすることができます。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-196">The certification authority (CA) can either be the same, or a different certification authority, as long as the servers have the certification authority’s root certificate registered in their trusted root authority certificate store.</span></span> 

<span data-ttu-id="b6a8f-197">Skype for Business Server に接続するには、Exchange Server がサーバー証明書を使用して構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-197">The Exchange Server must be configured with a server certificate in order to connect to Skype for Business Server:</span></span>
1. <span data-ttu-id="b6a8f-198">Exchange サーバーの CA 証明書をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-198">Download the CA certificate for the Exchange Server.</span></span>
2. <span data-ttu-id="b6a8f-199">Exchange サーバーの CA 証明書をインストールします。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-199">Install the CA certificate for the Exchange Server.</span></span>
3. <span data-ttu-id="b6a8f-200">CA が Exchange Server の信頼されているルート Ca のリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-200">Verify that the CA is in the list of trusted root CAs of the Exchange Server.</span></span>
4. <span data-ttu-id="b6a8f-201">Exchange Server の証明書要求を作成して、証明書をインストールします。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-201">Create a certificate request for the Exchange Server and install the certificate.</span></span> 
5. <span data-ttu-id="b6a8f-202">Exchange Server の証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-202">Assign the certificate for the Exchange Server.</span></span>


<span data-ttu-id="b6a8f-203">**CA 証明書をダウンロードするには:**</span><span class="sxs-lookup"><span data-stu-id="b6a8f-203">**To download the CA certificate:**</span></span>

1. <span data-ttu-id="b6a8f-204">Exchange UM を実行しているサーバーで [**スタート**] をクリックし、[**実行**] をクリックし**て、\<http://の発行 CA> サーバーの名前**を入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-204">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<name of your Issuing CA Server>/certsrv**, and then click **OK**.</span></span>
2. <span data-ttu-id="b6a8f-205">[タスクの選択] で、[ **CA 証明書、証明書チェーン、または CRL をダウンロード**します] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-205">Under Select a task, click **Download a CA certificate, certificate chain, or CRL**.</span></span>
3. <span data-ttu-id="b6a8f-206">**Ca 証明書、証明書チェーン、または CRL**をダウンロード**するに**は、[エンコード方法] を [ベース 64] に、[**ca 証明書のダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-206">Under **Download a CA Certificate, Certificate Chain, or CRL**, select **Encoding Method to Base 64**, and then click**Download CA certificate**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="b6a8f-207">この手順では、識別エンコード規則 (DER) のエンコードを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-207">You can also specify Distinguished Encoding Rules (DER) encoding at this step.</span></span> <span data-ttu-id="b6a8f-208">DER エンコードを選択した場合は、この手順の次の手順のファイルの種類と、 **CA 証明書をインストールする**手順10については .cer ではなく. p7b を使用します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-208">If you select DER encoding, the file type in the next step of this procedure and in step 10 of **To Install the CA certificate** is .p7b rather than .cer.</span></span> 
4. <span data-ttu-id="b6a8f-209">[**ファイルのダウンロード**] ダイアログボックスで、[**保存**] をクリックし、サーバーのハードディスクにファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-209">In the **File Download** dialog box, click **Save**, and then save the file to the hard disk on the server.</span></span> <span data-ttu-id="b6a8f-210">(前の手順で選んだエンコードに応じて、ファイル拡張子は .cer または. p7b のいずれかになります)。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-210">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in the previous step.)</span></span>

<span data-ttu-id="b6a8f-211">**CA 証明書をインストールするには、次の操作を行います。**</span><span class="sxs-lookup"><span data-stu-id="b6a8f-211">**To install the CA certificate:**</span></span>

1. <span data-ttu-id="b6a8f-212">Exchange UM を実行しているサーバーで、[**スタート**]、[**実行**]、[名前を指定して実行 **] の順にクリック**し、[ **OK**] をクリックして、Microsoft 管理コンソール (mmc) を開きます。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-212">On the server running Exchange UM, open Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the Open box, and then clicking **OK**.</span></span>
2. <span data-ttu-id="b6a8f-213">[**ファイル**] メニューで、[スナップインの**追加と削除**] をクリックし、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-213">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>
3. <span data-ttu-id="b6a8f-214">[**スタンドアロンスナップ**インの追加] ボックスで、[**証明書**] をクリックし、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-214">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>
4. <span data-ttu-id="b6a8f-215">[**証明書スナップイン**] ダイアログ ボックスの [**コンピューター アカウント**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-215">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>
5. <span data-ttu-id="b6a8f-216">**[コンピューターの選択**] ダイアログボックスで、[**ローカルコンピューター: (このコンソールが実行されているコンピューター)** ] チェックボックスがオンになっていることを確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-216">In the **Select Computer** dialog box, verify that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>
6. <span data-ttu-id="b6a8f-217">[**閉じる**] をクリックし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-217">Click **Close**, and then click **OK**.</span></span> 
7. <span data-ttu-id="b6a8f-218">コンソールツリーで、[**証明書 (ローカルコンピューター)**]、[**信頼されたルート証明機関**] の順に展開し、[**証明書**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-218">In the console tree, expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>
8. <span data-ttu-id="b6a8f-219">[**証明書**] を右クリックし、[**すべてのタスク**] をクリックして、[**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-219">Right-click **Certificates**, click **All Tasks**, and click **Import**.</span></span>
9. <span data-ttu-id="b6a8f-220">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-220">Click **Next**.</span></span> 
10. <span data-ttu-id="b6a8f-221">[**参照**] をクリックしてファイルを指定し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-221">Click **Browse** to locate the file, and then click **Next**.</span></span> <span data-ttu-id="b6a8f-222">(手順3で選択したエンコード方法によって、 **CA 証明書をダウンロードする**場合は、.cer または. p7b のファイル拡張子のいずれかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-222">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in step 3 of **To download the CA certificate**.</span></span>
11. <span data-ttu-id="b6a8f-223">[**証明書をすべて**次のストアに配置する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-223">Click **Place All Certificates** in the following store.</span></span>
12. <span data-ttu-id="b6a8f-224">[**参照**] をクリックし、[**信頼されたルート証明機関**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-224">Click **Browse**, and then select **Trusted Root Certification Authorities**.</span></span> 
13. <span data-ttu-id="b6a8f-225">[**次へ**] をクリックして設定を確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-225">Click **Next** to verify the settings, and then click **Finish**.</span></span> 


<span data-ttu-id="b6a8f-226">**CA が信頼できるルート Ca のリストに含まれていることを確認するには、次の操作を行います。**</span><span class="sxs-lookup"><span data-stu-id="b6a8f-226">**To verify that the CA is in the list of trusted root CAs:**</span></span>

1. <span data-ttu-id="b6a8f-227">Exchange UM を実行しているサーバーで、MMC で [証明書 (ローカルコンピューター)]、[信頼されたルート証明機関] の順に展開し、[証明書] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-227">On the server running Exchange UM, in MMC expand Certificates (Local Computer), expand Trusted Root Certification Authorities, and then click Certificates.</span></span>
2. <span data-ttu-id="b6a8f-228">[詳細] ウィンドウで、CA が信頼できる Ca の一覧にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6a8f-228">In the details pane, verify that your CA is on the list of trusted CAs.</span></span>


