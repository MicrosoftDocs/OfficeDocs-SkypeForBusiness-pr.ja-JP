---
title: Microsoft Teams での通話の共有およびグループ通話ピックアップ
ms.author: lolaj
author: lolaj
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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 共有を呼び出すし、グループ通話ピックアップできるように、ユーザーが利用できない場合、呼び出しをキャプチャできるように、着信呼び出しを同僚と共有します。
ms.openlocfilehash: df98dd4df064b23b687ddcc569e6c5a431137527
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2019
ms.locfileid: "30351331"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="55f99-103">Microsoft Teams での通話の共有およびグループ通話ピックアップ</span><span class="sxs-lookup"><span data-stu-id="55f99-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="55f99-104">呼び出しの共有とグループは、着信呼び出しの合計の仕事仲間の仕事仲間は、ユーザーが使用できない時に発生する呼び出しに応答できるように、マイクロソフトのチームがユーザーの共有の機能をピックアップを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="55f99-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="55f99-105">グループ コール ピックアップは他の形式のユーザーが共有経由でオーディオとビジュアルの通知、ビジュアルだけでは、着信の通知が必要な方法を構成することができますので、着信の転送または同時呼び出し) などの共有の呼び出しよりも受信者を妨げずやバナーのチームのアプリケーションで)、および、それに応答するかどうかを決定することができます。</span><span class="sxs-lookup"><span data-stu-id="55f99-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="55f99-106">呼び出しを他のユーザーと共有する、するには、ユーザーが呼び出しのグループを作成しでその呼び出しを共有するユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="55f99-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="55f99-107">同時呼び出しを選択するか、設定を転送します。</span><span class="sxs-lookup"><span data-stu-id="55f99-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="55f99-108">詳細については、[チームでの転送と同時の呼び出し音を呼び出す](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55f99-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="55f99-109">ユーザー、グループの所有者を呼び出し、および呼び出しのグループのメンバーは、展開モードではチームだけである必要があります。</span><span class="sxs-lookup"><span data-stu-id="55f99-109">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="55f99-110">チームの展開方法の詳細については、[マイクロソフト チームの理解と Skype ビジネスの共存と相互運用性を](teams-and-skypeforbusiness-coexistence-and-interoperability.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="55f99-110">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="55f99-111">ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="55f99-111">License required</span></span>

<span data-ttu-id="55f99-112">ユーザーを設定し、呼び出しの共有を使用し、コール ピックアップをグループ化するを有効にするエンタープライズ VoIP をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="55f99-112">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="55f99-113">ライセンス ・ モデルの詳細については、 [Office 365 は、マイクロソフトのチームのライセンス](office-365-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55f99-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="55f99-114">グループ コール ピックアップを設定します。</span><span class="sxs-lookup"><span data-stu-id="55f99-114">Configure group call pickup</span></span>

<span data-ttu-id="55f99-115">コール ピックアップのグループを設定するにユーザーは最初の呼び出しグループ (これは、同じセキュリティ グループ、または、Office 365 のグループとして) を構成しでその呼び出しを共有するユーザーを追加し。</span><span class="sxs-lookup"><span data-stu-id="55f99-115">To set up group call pickup, a user first configures a call group (this is not the same as a security group or an Office 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="55f99-116">同時呼び出しを選択する、転送の設定を呼び出すか。</span><span class="sxs-lookup"><span data-stu-id="55f99-116">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="55f99-117">詳細な情報および詳細な手順についてを参照してください[チームに転送し、同時のリングを呼び出します](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)。</span><span class="sxs-lookup"><span data-stu-id="55f99-117">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="55f99-118">グループの作成と通知の設定は、ユーザー ・ ベースの機能を呼び出す管理者は、ユーザーに対してこれらの機能を構成するのにはありません。</span><span class="sxs-lookup"><span data-stu-id="55f99-118">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="55f99-119">セキュリティ グループまたはグループを Office 365 からの呼び出しのグループを作成できません。これらは、チームで作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55f99-119">Call groups cannot be created from security groups or Office 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="55f99-120">管理者は、ユーザーの**TeamsCallingPolicy の AllowCallGroups**設定を使用して呼び出しのグループを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="55f99-120">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="55f99-121">管理者は、このユーザーが呼び出しのグループを構成できるかどうかを制御することができますだけ。</span><span class="sxs-lookup"><span data-stu-id="55f99-121">Admins can only control whether this user can configure call groups.</span></span> <span data-ttu-id="55f99-122">True の場合、管理者に設定すると、ビットを設定して、任意のユーザーをグループ化する呼び出しを追加することからユーザーを防ぐことはできません。</span><span class="sxs-lookup"><span data-stu-id="55f99-122">Once the bit is set to true, admins cannot prevent the user from configuring and adding the call group users of their choice.</span></span>

## <a name="limitations"></a><span data-ttu-id="55f99-123">制限</span><span class="sxs-lookup"><span data-stu-id="55f99-123">Limitations</span></span>

<span data-ttu-id="55f99-124">テナントには、最大 32,768 の呼び出しのグループを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="55f99-124">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="55f99-125">最大 5 ユーザーが各呼び出しのグループのことができます。</span><span class="sxs-lookup"><span data-stu-id="55f99-125">There can be a maximum of 5 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="55f99-126">詳細情報</span><span class="sxs-lookup"><span data-stu-id="55f99-126">More information</span></span>

[<span data-ttu-id="55f99-127">着信の転送およびチームでの同時呼び出し</span><span class="sxs-lookup"><span data-stu-id="55f99-127">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)