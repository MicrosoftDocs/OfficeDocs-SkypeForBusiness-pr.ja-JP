---
title: "Exchange ユニファイド メッセージングを管理して、ボイス メールのホストされています。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: "PowerShell を使用すると、for Business Online の自動応答、サブスクライバー アクセスと Skype でホストされているボイス メールなどの Exchange ユニファイド メッセージング機能を管理できます。"
ms.openlocfilehash: 98a7847f6d8ec5bebd1889aef57298bd36696918
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a><span data-ttu-id="02890-103">Exchange ユニファイド メッセージングを管理して、ボイス メールのホストされています。</span><span class="sxs-lookup"><span data-stu-id="02890-103">Manage Exchange Unified Messaging and hosted voicemail</span></span>

<span data-ttu-id="02890-104">Exchange ユニファイド メッセージングを管理できるして for Business Online のコマンドレットを使用して Skype でボイス メールをホストします。</span><span class="sxs-lookup"><span data-stu-id="02890-104">You can manage Exchange Unified Messaging and hosted voicemail in Skype for Business Online by using a set of cmdlets.</span></span>
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a><span data-ttu-id="02890-105">Exchange ユニファイド メッセージングを管理して、ボイス メールのホストされています。</span><span class="sxs-lookup"><span data-stu-id="02890-105">Manage Exchange unified messaging and hosted voice mail</span></span>

<span data-ttu-id="02890-106">次のコマンドレットでは、Exchange ユニファイド メッセージング (UM) を管理するために使用して、ボイス メールのポリシーをホストされています。</span><span class="sxs-lookup"><span data-stu-id="02890-106">The following cmdlets can be used to manage Exchange Unified Messaging (UM) and hosted voicemail policies:</span></span>
  
|<span data-ttu-id="02890-107">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="02890-107">**Cmdlet**</span></span>|<span data-ttu-id="02890-108">**{Description}**</span><span class="sxs-lookup"><span data-stu-id="02890-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="02890-109">Get CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="02890-109">Get-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [<span data-ttu-id="02890-110">新しい-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="02890-110">New-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[<span data-ttu-id="02890-111">削除 CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="02890-111">Remove-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[<span data-ttu-id="02890-112">設定 CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="02890-112">Set-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> |<span data-ttu-id="02890-113">作成し、ホストされているサービスが Exchange UM とき、サービスの自動応答、サブスクライバー アクセスに使用される連絡先のオブジェクトを管理します。</span><span class="sxs-lookup"><span data-stu-id="02890-113">Creates and manages contact objects used for Auto Attendant and Subscriber Access services, when Exchange UM is a hosted service.</span></span>  <br/><br/> <span data-ttu-id="02890-p101">Skype for Business Online 機能 UM 自動応答、サブスクライバー アクセスなどのいくつかの音声機能を提供します。自動応答には、通話が自動的に応答して適切な宛先にルーティングするための方法が用意されています。サブスクライバー アクセスでは、UM Exchange に接続してメール、音声メッセージ、連絡先、および予定表の情報を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="02890-p101">Skype for Business Online works with Exchange UM to provide several voice-related capabilities, including Auto Attendant and Subscriber Access. Auto Attendant provides a way for calls to automatically be answered and routed to the correct person. Subscriber Access enables users to connect to Exchange UM and retrieve email, voice messages, contacts, and calendar information.  </span></span><br/><br/> <span data-ttu-id="02890-p102">UM がホストされているサービスとして指定する場合、Microsoft PowerShell を使用して、自動応答とサブスクライバー アクセス サービスのために、連絡先のオブジェクトを作成する必要があります。これらのオブジェクトが作成され、 **CsExUmContact**コマンドレットを使用して管理します。</span><span class="sxs-lookup"><span data-stu-id="02890-p102">When Exchange UM is provided as a hosted service, contact objects used for the Auto Attendant and Subscriber Access services must be created by using Microsoft PowerShell. These objects are created and managed by using the **CsExUmContact** cmdlets. </span></span><br/> |
|[<span data-ttu-id="02890-119">Get CSHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="02890-119">Get-CSHostedVoicemailPolicy</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[<span data-ttu-id="02890-120">許可を付与する CSHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="02890-120">Grant-CSHostedVoicemailPolicy</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/> |<span data-ttu-id="02890-p103">組織内で使用されているボイス メールのホスト ポリシーを管理します。ボイス メールのホストのポリシーの指定方法不在時の着信は、UM サービスにルーティングします。これらのポリシーでは、UM ホストされているボイス メールが有効になっているユーザーだけに影響します。</span><span class="sxs-lookup"><span data-stu-id="02890-p103">Manages hosted voicemail policies used in the organization. Hosted voicemail policies specify how unanswered calls are routed to the Exchange UM service. These policies affect only users who have been enabled for Exchange UM hosted voicemail.</span></span>  <br/><br/> <span data-ttu-id="02890-124">ボイス メールのホストのユーザーが有効になっているかどうかを確認するには、PowerShell のプロンプトで、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="02890-124">To verify whether a user is enabled for hosted voicemail, run a command similar to the following from the PowerShell prompt.</span></span>  <br/> <span data-ttu-id="02890-125">' Get CsOnlineUser-"kenmyer@litwareinc.com"の Id</span><span class="sxs-lookup"><span data-stu-id="02890-125">\`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"</span></span> | <span data-ttu-id="02890-126">[オブジェクトの HostedVoiceMail'</span><span class="sxs-lookup"><span data-stu-id="02890-126">Select-Object HostedVoiceMail\`</span></span>|
   

## <a name="related-topics"></a><span data-ttu-id="02890-127">関連トピック</span><span class="sxs-lookup"><span data-stu-id="02890-127">Related topics</span></span>
[<span data-ttu-id="02890-128">Skype for business online 管理の Windows PowerShell を使用して、コンピューターを設定します。</span><span class="sxs-lookup"><span data-stu-id="02890-128">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)