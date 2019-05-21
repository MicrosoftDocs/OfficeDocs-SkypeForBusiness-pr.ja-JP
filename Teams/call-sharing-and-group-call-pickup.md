---
title: Microsoft Teams での通話の共有およびグループ通話ピックアップ
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 通話共有とグループ通話のピックアップユーザーが着信した通話を同僚と共有できるようにして、ユーザーが連絡不能なときに通話をキャプチャできるようにします。
ms.openlocfilehash: 02c6605f3a5ea1df3457eaadea9956727431a827
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283480"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="7d719-103">Microsoft Teams での通話の共有およびグループ通話ピックアップ</span><span class="sxs-lookup"><span data-stu-id="7d719-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="7d719-104">Microsoft Teams の通話共有とグループ通話のピックアップ機能を使用すると、ユーザーは着信通話を同僚と共有できるため、ユーザーが連絡できない間に発生した通話に同僚が応答できます。</span><span class="sxs-lookup"><span data-stu-id="7d719-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="7d719-105">グループ通話のピックアップは、他の形式の通話共有 (着信の転送または同時呼び出しなど) よりも、受信者に対してはあまり影響がありません。ユーザーは、着信共有通話の通知方法 (音声と視覚的な通知を介して) を構成することができます。または、[Teams] アプリのバナーで、それに応答するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="7d719-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="7d719-106">通話を他のユーザーと共有するには、ユーザーが通話グループを作成し、通話を共有するユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="7d719-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="7d719-107">次に、同時呼び出しまたは転送設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="7d719-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="7d719-108">詳しくは[、「Teams での着信の転送と同時](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)呼び出し」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7d719-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d719-109">ユーザー、通話グループの所有者、通話グループのメンバーは、Teams のみの展開モードである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d719-109">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="7d719-110">Teams の展開モードの詳細については、「 [Microsoft teams と Skype For business の共存と相互運用性につい](teams-and-skypeforbusiness-coexistence-and-interoperability.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d719-110">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="7d719-111">ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="7d719-111">License required</span></span>

<span data-ttu-id="7d719-112">通話共有とグループ通話のピックアップをセットアップして使用するには、ユーザーはエンタープライズ Voip を有効にしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d719-112">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="7d719-113">ライセンスモデルの詳細については、「 [Microsoft Teams の Office 365 ライセンス](office-365-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d719-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="7d719-114">グループ通話のピックアップを構成する</span><span class="sxs-lookup"><span data-stu-id="7d719-114">Configure group call pickup</span></span>

<span data-ttu-id="7d719-115">グループ通話のピックアップを設定するために、ユーザーは最初に通話グループ (セキュリティグループまたは Office 365 グループとは異なります) を構成し、通話を共有するユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="7d719-115">To set up group call pickup, a user first configures a call group (this is not the same as a security group or an Office 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="7d719-116">次に、同時呼び出しまたは [着信の転送] 設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="7d719-116">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="7d719-117">詳細とステップバイステップの手順については、「 [Teams での着信の転送と同時呼び出し](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d719-117">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="7d719-118">通話グループの作成と通知の設定は、ユーザー主導の機能です。管理者は、これらの機能をユーザーに対して構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7d719-118">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="7d719-119">通話グループは、セキュリティグループまたは Office 365 グループから作成することはできません。チームで作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d719-119">Call groups cannot be created from security groups or Office 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="7d719-120">管理者は、ユーザーの**Teampolicy のポリシー AllowCallGroups**の設定を使って、通話グループを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d719-120">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="7d719-121">管理者は、このユーザーが通話グループを構成できるかどうかを制御することのみができます。</span><span class="sxs-lookup"><span data-stu-id="7d719-121">Admins can only control whether this user can configure call groups.</span></span> <span data-ttu-id="7d719-122">このビットが true に設定されると、管理者は、ユーザーが選択した通話グループのユーザーを構成および追加できないようにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7d719-122">Once the bit is set to true, admins cannot prevent the user from configuring and adding the call group users of their choice.</span></span>

## <a name="limitations"></a><span data-ttu-id="7d719-123">伴う</span><span class="sxs-lookup"><span data-stu-id="7d719-123">Limitations</span></span>

<span data-ttu-id="7d719-124">テナントには、最大32768の通話グループを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="7d719-124">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="7d719-125">各通話グループには、最大5人のユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7d719-125">There can be a maximum of 5 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="7d719-126">詳細情報</span><span class="sxs-lookup"><span data-stu-id="7d719-126">More information</span></span>

[<span data-ttu-id="7d719-127">チームでの着信の転送と同時呼び出し</span><span class="sxs-lookup"><span data-stu-id="7d719-127">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)