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

# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a><span data-ttu-id="1eab9-102">Microsoft Lync Server 2013 用 Microsoft Exchange Server 2013 ユニファイドメッセージングの構成ボイスメール</span><span class="sxs-lookup"><span data-stu-id="1eab9-102">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1eab9-103">_**最終更新日:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="1eab9-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="1eab9-104">Microsoft Lync Server 2013 を使用すると、ボイスメールメッセージを Microsoft Exchange Server 2013 に保存することができます。これらのボイスメールメッセージは、ユーザーの受信トレイにメールメッセージとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="1eab9-104">Microsoft Lync Server 2013 enables you to have voicemail messages stored in Microsoft Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> <span data-ttu-id="1eab9-105">この機能は、2010エディションの Lync Server と Exchange にも含まれていました。ただし、この "ユニファイドメッセージング" を構成するプロセスは、UM Call Router コンポーネントの導入により、2013エディションで簡素化されています。</span><span class="sxs-lookup"><span data-stu-id="1eab9-105">This capability was also found in the 2010 editions of Lync Server and Exchange; however, the process of configuring this "unified messaging" has been simplified in the 2013 editions thanks to the introduction of the UM Call Router component.</span></span> <span data-ttu-id="1eab9-106">このコンポーネントは Exchange 2013 クライアントアクセスサーバーにインストールされ、Exchange ユニファイドメッセージング (ボイスメールなど) へのすべての呼び出しは、まず通話ルーター経由でルーティングされ、適切なメールボックスサーバーにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="1eab9-106">This component is installed on the Exchange 2013 Client Access server, and all calls to Exchange unified messaging (such as a voicemail) are first routed through the Call Router and then are redirected to the appropriate Mailbox server.</span></span>

<span data-ttu-id="1eab9-107">Lync Server 2013 と Exchange 2013 間のサーバー間認証を既に構成している場合は、ユニファイドメッセージングを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="1eab9-107">If you have already configured server-to-server authentication between Lync Server 2013 and Exchange 2013 then you are ready to setup unified messaging.</span></span> <span data-ttu-id="1eab9-108">そのためには、まず Exchange server で新しいユニファイドメッセージングダイヤルプランを作成して割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1eab9-108">To do so, you must first create and assign a new unified messaging dial plan on your Exchange server.</span></span> <span data-ttu-id="1eab9-109">たとえば、次の2つのコマンド (Exchange 管理シェル内から実行) では、Exchange 用の新しい3桁のダイヤルプランを構成します。</span><span class="sxs-lookup"><span data-stu-id="1eab9-109">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

<span data-ttu-id="1eab9-p103">例の最初のコマンドで、VoIPSecurity パラメーターおよびパラメーター値 "Secured" は、信号チャネルがトランスポート層セキュリティ (TLS) を使用して暗号化されることを指定します。URIType "SipName" は、SIP プロトコルを使用してメッセージが送受信されることを指定し、CountryOrRegionCode の 1 は、ダイヤル プランが米国に適用されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="1eab9-p103">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicate that the signaling channel is encrypted by using Transport Layer Security (TLS). The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>

<span data-ttu-id="1eab9-112">2 番目のコマンドで、ConfiguredInCountryOrRegionGroups パラメーターに渡されるパラメーター値は、このダイヤル プランで使用できる国内のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="1eab9-112">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="1eab9-113">"Anywhere、\*,\*\*" というパラメーター値は、次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="1eab9-113">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>

  - <span data-ttu-id="1eab9-114">グループ名 ("Anywhere")</span><span class="sxs-lookup"><span data-stu-id="1eab9-114">Group name ("Anywhere")</span></span>

  - <span data-ttu-id="1eab9-115">Allowed連番文字列 (\*任意の数字文字列が許可されていることを示すワイルドカード文字)</span><span class="sxs-lookup"><span data-stu-id="1eab9-115">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>

  - <span data-ttu-id="1eab9-116">[ダイヤル番号]\*文字列 (およびダイヤルされた番号が許可されていることを示すワイルドカード文字)</span><span class="sxs-lookup"><span data-stu-id="1eab9-116">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>

  - <span data-ttu-id="1eab9-117">TextComment (\*任意のテキストコマンドが許可されていることを示すワイルドカード文字)</span><span class="sxs-lookup"><span data-stu-id="1eab9-117">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1eab9-118">新しいダイヤル プランを作成すると、既定のメールボックス ポリシーも作成されます。</span><span class="sxs-lookup"><span data-stu-id="1eab9-118">Creating a new dial plan will also create a Default Mailbox Policy.</span></span>



</div>

<span data-ttu-id="1eab9-119">新しいダイヤルプランを作成して構成した後、新しいダイヤルプランをユニファイドメッセージングサーバーに追加し、そのサーバーのスタートアップモードを変更する必要があります。特に、スタートアップモードを "デュアル" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1eab9-119">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="1eab9-120">Exchange 管理シェルでは、次の2つのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="1eab9-120">You can perform both of these tasks from within the Exchange Management Shell:</span></span>

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

<span data-ttu-id="1eab9-121">ユニファイドメッセージングサーバーの構成が完了したら、次に、Import-exchangecertificate コマンドレットを実行して、Exchange 証明書がユニファイドメッセージングサービスに適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1eab9-121">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

<span data-ttu-id="1eab9-p106">証明書の割り当てが適切に行われた後、ユニファイド メッセージング サーバー上の MsExchangeUM サービスを停止して、再起動する必要があります。このサービスは、スタートアップ モードを変更した場合はいつでも、停止して再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1eab9-p106">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server. This service must be stopped and restarted any time you change the startup mode.</span></span>

<span data-ttu-id="1eab9-124">ユニファイド メッセージング サーバーの構成が終了すると、UM Call Router を構成できます。</span><span class="sxs-lookup"><span data-stu-id="1eab9-124">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

<span data-ttu-id="1eab9-125">スタートアップ モードが変更されているため、UM Call Router をホストしているコンピューター上で MsExchangeUMCR サービスを停止および再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1eab9-125">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>

<span data-ttu-id="1eab9-p107">ユニファイド メッセージングのセットアップを完了するには、UM メールボックス ポリシーを作成し、そのポリシーを使用して、ユーザーのユニファイド メッセージングを有効にする必要があります。次のようなコマンドを使用して、メールボックス ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1eab9-p107">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging. You can create a mailbox policy by using a command similar to this:</span></span>

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

<span data-ttu-id="1eab9-128">また、次のようなコマンドを使用して、ユーザーのユニファイド メッセージングを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="1eab9-128">And you can enable a user for unified messaging by using a command similar to this:</span></span>

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

<span data-ttu-id="1eab9-p108">上のコマンドで、Extensions パラメーターはユーザーの内線番号を表します。この例の場合、ユーザーの内線番号は 100 です。</span><span class="sxs-lookup"><span data-stu-id="1eab9-p108">In the preceding command, the Extensions parameter represents the telephone extension number for the user. In this example, the user has the extension number 100.</span></span>

<span data-ttu-id="1eab9-131">メールボックスを有効にすると、ユーザー kenmyer@litwareinc.com は Exchange ユニファイド メッセージングを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1eab9-131">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="1eab9-132">Lync Server 管理シェル内から[テスト用の CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity)コマンドレットを実行することで、ユーザーが Exchange UM に接続できることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1eab9-132">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) cmdlet from within the Lync Server Management Shell:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="1eab9-133">ユニファイド メッセージングが有効化されている 2 番目のユーザーがいる場合は、[Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) コマンドレットを使用して、この 2 番目のユーザーが最初のユーザーにボイスメール メッセージを残せることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1eab9-133">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

</div>

<span> </span>

</div>

</div>

</div>

