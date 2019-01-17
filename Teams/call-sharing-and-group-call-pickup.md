---
title: Microsoft Teams での通話の共有およびグループ通話ピックアップ
ms.author: lolaj
author: lolaj
manager: serdars
ms.date: 01/16/19
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 共有を呼び出すし、グループ通話ピックアップできるように、ユーザーが利用できない場合、呼び出しをキャプチャできるように、着信呼び出しを同僚と共有します。
ms.openlocfilehash: 31df45d0420457528fd517c851b845a09cab32e0
ms.sourcegitcommit: 0fcca2d8303da82cc00a504f4183bee50ab23eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2019
ms.locfileid: "28328318"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="ed226-103">Microsoft Teams での通話の共有およびグループ通話ピックアップ</span><span class="sxs-lookup"><span data-stu-id="ed226-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="ed226-104">呼び出しの共有とグループは、着信呼び出しの合計の仕事仲間の仕事仲間は、ユーザーが使用できない時に発生する呼び出しに応答できるように、マイクロソフトのチームがユーザーの共有の機能をピックアップを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ed226-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="ed226-105">グループ コール ピックアップは他の形式のユーザーが共有経由でオーディオとビジュアルの通知、ビジュアルだけでは、着信の通知が必要な方法を構成することができますので、着信の転送または同時呼び出し) などの共有の呼び出しよりも受信者を妨げずやバナーのチームのアプリケーションで)、および、それに応答するかどうかを決定することができます。</span><span class="sxs-lookup"><span data-stu-id="ed226-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="ed226-106">呼び出しを他のユーザーと共有する、するには、ユーザーが呼び出しのグループを作成しでその呼び出しを共有するユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="ed226-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="ed226-107">同時呼び出しを選択するか、設定を転送します。</span><span class="sxs-lookup"><span data-stu-id="ed226-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="ed226-108">詳細については、[チームでの転送と同時の呼び出し音を呼び出す](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed226-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ed226-109">ユーザー、グループの所有者を呼び出し、および呼び出しのグループのメンバーは、展開モードではチームだけである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed226-109">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="ed226-110">チームの展開方法の詳細については、[マイクロソフト チームの理解と Skype ビジネスの共存と相互運用性を](teams-and-skypeforbusiness-coexistence-and-interoperability.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed226-110">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="ed226-111">ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="ed226-111">License required</span></span>

<span data-ttu-id="ed226-112">ユーザーを設定し、呼び出しの共有を使用し、コール ピックアップをグループ化するを有効にするエンタープライズ VoIP をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed226-112">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="ed226-113">ライセンス ・ モデルの詳細については、 [Office 365 は、マイクロソフトのチームのライセンス](office-365-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed226-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="ed226-114">グループ コール ピックアップを設定します。</span><span class="sxs-lookup"><span data-stu-id="ed226-114">Configure group call pickup</span></span>

<span data-ttu-id="ed226-115">コール ピックアップのグループを設定するにユーザーは最初の呼び出しグループ (これは、同じセキュリティ グループ、または、Office 365 のグループとして) を構成しでその呼び出しを共有するユーザーを追加し。</span><span class="sxs-lookup"><span data-stu-id="ed226-115">To set up group call pickup, a user first configures a call group (this is not the same as a security group or an Office 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="ed226-116">同時呼び出しを選択する、転送の設定を呼び出すか。</span><span class="sxs-lookup"><span data-stu-id="ed226-116">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="ed226-117">詳細な情報および詳細な手順についてを参照してください[チームに転送し、同時のリングを呼び出します](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)。</span><span class="sxs-lookup"><span data-stu-id="ed226-117">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="ed226-118">グループの作成と通知の設定は、ユーザー ・ ベースの機能を呼び出す管理者は、ユーザーに対してこれらの機能を構成するのにはありません。</span><span class="sxs-lookup"><span data-stu-id="ed226-118">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="ed226-119">セキュリティ グループまたはグループを Office 365 からの呼び出しのグループを作成できません。これらは、チームで作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed226-119">Call groups cannot be created from security groups or Office 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="ed226-120">管理者は、ユーザー グループを作成し、他のコール ピックアップの設定を変更するを防ぐことはできません。</span><span class="sxs-lookup"><span data-stu-id="ed226-120">Admins cannot prevent users from creating groups and changing other call pickup setting.</span></span> <span data-ttu-id="ed226-121">機能がブロックされていません。</span><span class="sxs-lookup"><span data-stu-id="ed226-121">The functionality is not blocked.</span></span>

## <a name="limitations"></a><span data-ttu-id="ed226-122">制限</span><span class="sxs-lookup"><span data-stu-id="ed226-122">Limitations</span></span>

<span data-ttu-id="ed226-123">テナントには、最大 32,768 の呼び出しのグループを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ed226-123">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="ed226-124">最大 5 ユーザーが各呼び出しのグループのことができます。</span><span class="sxs-lookup"><span data-stu-id="ed226-124">There can be a maximum of 5 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="ed226-125">詳細情報</span><span class="sxs-lookup"><span data-stu-id="ed226-125">More information</span></span>

[<span data-ttu-id="ed226-126">着信の転送およびチームでの同時呼び出し</span><span class="sxs-lookup"><span data-stu-id="ed226-126">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)