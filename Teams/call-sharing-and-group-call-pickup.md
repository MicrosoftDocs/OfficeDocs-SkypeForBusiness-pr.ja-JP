---
title: 通話の共有およびグループ通話ピックアップ
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: 通話共有とグループ通話の受け取りを使用すると、ユーザーは着信通話を同僚と共有し、ユーザーが応答できないときに通話をキャプチャすることができます。
ms.openlocfilehash: 1ec3c389bf2eb69f30e13ebbba6c7d5d1d5fe38c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102793"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="2a140-103">Microsoft Teams での通話の共有およびグループ通話ピックアップ</span><span class="sxs-lookup"><span data-stu-id="2a140-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="2a140-104">Microsoft Teams の通話共有機能とグループ通話の受け取り機能を使用すると、ユーザーは着信通話を同僚と共有して、ユーザーが応答できない間に発生した通話に同僚が応答できます。</span><span class="sxs-lookup"><span data-stu-id="2a140-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="2a140-105">グループ通話の受け取りは、他の形式の通話共有 (着信の転送や同時呼び出しなど) よりも受信者の混乱を減らします。これは、ユーザーが着信共有通話の通知方法 (音声および視覚的な通知、視覚的な通知、Teams アプリの視覚的な通知、バナー) を構成し、応答するかどうかを決定することができるためです。</span><span class="sxs-lookup"><span data-stu-id="2a140-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="2a140-106">他のユーザーと通話を共有するために、ユーザーは通話グループを作成し、通話を共有するユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="2a140-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="2a140-107">次に、同時呼び出しまたは転送設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a140-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="2a140-108">詳細 [については、「Teams での通話の転送と同時呼び出](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) し」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a140-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span> <span data-ttu-id="2a140-109">モバイル デバイスには、バナーと着信音が設定されている場合にのみ通知されます。</span><span class="sxs-lookup"><span data-stu-id="2a140-109">Note that mobile devices will only get notified if they're set for banner and ringtone.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a140-110">ユーザー、通話グループの所有者、および通話グループのメンバーは、Teams のみ展開モードである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a140-110">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="2a140-111">Teams 展開モードの詳細については、「Microsoft Teams と Skype for Business の共存と相互運用性について[」を参照してください](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。</span><span class="sxs-lookup"><span data-stu-id="2a140-111">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="2a140-112">ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="2a140-112">License required</span></span>

<span data-ttu-id="2a140-113">通話共有とグループエンタープライズ VoIPを設定して使用するには、ユーザーが有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a140-113">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="2a140-114">ライセンス モデルの詳細については、Microsoft Teams サービスの [説明を参照してください](/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="2a140-114">For additional details on the licensing model, see [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="2a140-115">グループ通話の受け取りを構成する</span><span class="sxs-lookup"><span data-stu-id="2a140-115">Configure group call pickup</span></span>

<span data-ttu-id="2a140-116">グループ通話の受け取りを設定するには、ユーザーが最初に通話グループを構成し (これはセキュリティ グループや Microsoft 365 グループとは異なる)、通話を共有するユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="2a140-116">To set up group call pickup, a user first configures a call group (this is not the same as a security group or a Microsoft 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="2a140-117">次に、同時呼び出しまたは呼び出し転送設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a140-117">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="2a140-118">詳細と詳しい手順については、「Teams での通話の転送と同時呼び出し [」を参照してください](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)。</span><span class="sxs-lookup"><span data-stu-id="2a140-118">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="2a140-119">通話グループの作成と通知の基本設定は、ユーザー駆動型の機能です。管理者は、ユーザーに対してこれらの機能を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a140-119">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="2a140-120">通話グループは、セキュリティ グループまたは Microsoft 365 グループから作成することはできません。Teams で作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a140-120">Call groups cannot be created from security groups or Microsoft 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="2a140-121">管理者は、ユーザーの **TeamsCallingPolicy AllowCallGroups** 設定を使用して通話グループを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a140-121">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="2a140-122">管理者は、Teams 管理ポータルからこれを有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2a140-122">Admins can also enable this via Teams Admin portal.</span></span>  <span data-ttu-id="2a140-123">さらに、構成済みのユーザーは、クライアント経由で通話グループを直接構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="2a140-123">In addition, the configured user can also configure their call groups via the client directly.</span></span> <span data-ttu-id="2a140-124">管理者またはエンド ユーザーは、互いに構成をブロックすることはできませんが、Teams 管理ポータルと Teams クライアントは両方の場所でこの関係を正確に表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a140-124">Admin or end users cannot block the configuration by each other, but Teams Admin portal and Teams client should show this relationship accurately in both places.</span></span> 

<span data-ttu-id="2a140-125">重要: 管理者がユーザーの通話グループをオフにすると (それが有効になっていて、通話グループの関係が構成された後)、管理者は、不適切な通話ルーティングを回避するために、Teams 管理センターでユーザーの通話グループの関係をクリーンアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a140-125">Important: When admins turn off call groups for users (after it has been turned on and the call group relationships are configured), the admins have to clean up the call group relationships for users in the Teams admin center to avoid incorrect call routing.</span></span> 

## <a name="limitations"></a><span data-ttu-id="2a140-126">制限事項</span><span class="sxs-lookup"><span data-stu-id="2a140-126">Limitations</span></span>

<span data-ttu-id="2a140-127">テナントには、最大 32,768 の通話グループを含めできます。</span><span class="sxs-lookup"><span data-stu-id="2a140-127">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="2a140-128">各通話グループには最大 25 人のユーザーを含めできます。</span><span class="sxs-lookup"><span data-stu-id="2a140-128">There can be a maximum of 25 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="2a140-129">詳細情報</span><span class="sxs-lookup"><span data-stu-id="2a140-129">More information</span></span>

[<span data-ttu-id="2a140-130">Teams での通話の転送と同時呼び出し</span><span class="sxs-lookup"><span data-stu-id="2a140-130">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)