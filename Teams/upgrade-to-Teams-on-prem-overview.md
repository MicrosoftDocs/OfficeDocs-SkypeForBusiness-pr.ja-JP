---
title: Skype for Business オンプレミス展開から Teams へのアップグレード - Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Skype for Business から Teams へのアップグレード
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: aa87941300f87abb320ddad7e8bc1311c62addf0
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940577"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="1bc3d-103">Skype for Business から Teams へのアップグレード &mdash; IT 管理者向け</span><span class="sxs-lookup"><span data-stu-id="1bc3d-103">Upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

## <a name="overview"></a><span data-ttu-id="1bc3d-104">概要</span><span class="sxs-lookup"><span data-stu-id="1bc3d-104">Overview</span></span>

<span data-ttu-id="1bc3d-105">Skype for Business から Teams にアップグレードする場合、一部の組織では、その組織の IT 部門によって計画と管理が実施されるプログレッシブ ロールアウトが必要になります。</span><span class="sxs-lookup"><span data-stu-id="1bc3d-105">When upgrading from Skype for Business to Teams, some organizations require a progressive rollout that is planned and managed by their IT departments.</span></span> <span data-ttu-id="1bc3d-106">このセクションの記事は、主に大規模な組織の IT 管理者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="1bc3d-106">The articles in this section apply primarily to IT administrators in large organizations.</span></span> <span data-ttu-id="1bc3d-107">通常、これらの組織はオンプレミスですが、大規模な Skype for Business Online 組織の場合もあります。</span><span class="sxs-lookup"><span data-stu-id="1bc3d-107">These organizations are typically on-premises, but they might also be large Skype for Business Online organizations.</span></span> <span data-ttu-id="1bc3d-108">これらの記事を読む前に、「 [チームのアップグレードの](upgrade-start-here.md) 概要」と「 [アップグレードフレームワークについ](upgrade-framework.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bc3d-108">Before reading these articles, be sure to read [Getting started with your Teams Upgrade](upgrade-start-here.md) and [About the Upgrade framework](upgrade-framework.md).</span></span>


<span data-ttu-id="1bc3d-109">次の記事では、組織のアップグレードプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1bc3d-109">The following articles will guide you through the upgrade process for your organization:</span></span> 

- [<span data-ttu-id="1bc3d-110">アップグレード方法</span><span class="sxs-lookup"><span data-stu-id="1bc3d-110">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="1bc3d-111">アップグレードを管理するためのツール</span><span class="sxs-lookup"><span data-stu-id="1bc3d-111">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="1bc3d-112">Skype for Business オンプレミスの組織に関するその他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="1bc3d-112">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="1bc3d-113">アップグレードを実装する</span><span class="sxs-lookup"><span data-stu-id="1bc3d-113">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="1bc3d-114">公衆交換電話網 (PSTN) に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="1bc3d-114">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="1bc3d-115">さらに、次の記事では、アップグレードの重要な概念と共存の動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="1bc3d-115">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="1bc3d-116">Teams と Skype for Business の共存</span><span class="sxs-lookup"><span data-stu-id="1bc3d-116">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="1bc3d-117">共存モード-参照</span><span class="sxs-lookup"><span data-stu-id="1bc3d-117">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="1bc3d-118">Teams のクライアント エクスペリエンスおよび共存モードへの準拠</span><span class="sxs-lookup"><span data-stu-id="1bc3d-118">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
><span data-ttu-id="1bc3d-119">この記事では、Skype for Business Online、オンプレミスの Skype for Business Server、Skype for Business という用語を使用します。</span><span class="sxs-lookup"><span data-stu-id="1bc3d-119">These articles use the terms Skype for Business Online, Skype for Business Server on-premises, and Skype for Business.</span></span> <span data-ttu-id="1bc3d-120">最後の用語は、オンライン バージョンとオンプレミス バージョンの両方を指します。</span><span class="sxs-lookup"><span data-stu-id="1bc3d-120">The latter term refers to both online and on-premises versions.</span></span>

<span data-ttu-id="1bc3d-121">作業を開始する前に、チームに移行されたユーザーが skype for business クライアントを使用しなくなったことに注意してください。ただし、Skype for Business でホストされている会議に参加することはありません。</span><span class="sxs-lookup"><span data-stu-id="1bc3d-121">Before you get started, be aware that a user who has been migrated to Teams no longer uses a Skype for Business client except to join a meeting hosted in Skype for Business.</span></span>  <span data-ttu-id="1bc3d-122">着信したチャットや通話すべては、送信者が Teams と Skype for Business のいずれを使用しているかに関わらず、ユーザーの Teams クライアントに配信されます。</span><span class="sxs-lookup"><span data-stu-id="1bc3d-122">All incoming chats and calls land in the user’s Teams client, regardless of whether the sender uses Teams or Skype for Business.</span></span> <span data-ttu-id="1bc3d-123">移行済みユーザーによって開催される新しい会議は、Teams 会議としてスケジュールされます。</span><span class="sxs-lookup"><span data-stu-id="1bc3d-123">Any new meetings organized by the migrated user will be scheduled as Teams meetings.</span></span> <span data-ttu-id="1bc3d-124">ユーザーが Skype for Business クライアントを使用しようとすると、チャットと通話の開始がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="1bc3d-124">If the user attempts to use the Skype for Business client, initiation of chats and calls is blocked.</span></span>  <span data-ttu-id="1bc3d-125">ただし、ユーザーは引き続き Skype for business クライアントを使用して、招待された Skype for Business 会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="1bc3d-125">However, the user can (and must) still use the Skype for Business client to join Skype for Business meetings they are invited to.</span></span> <span data-ttu-id="1bc3d-126">(2017 年より前に出荷された以前の Skype for Business クライアントでは、TeamsUpgradePolicy は優先されません。</span><span class="sxs-lookup"><span data-stu-id="1bc3d-126">(Older Skype for Business clients that shipped before 2017 do not honor TeamsUpgradePolicy.</span></span> <span data-ttu-id="1bc3d-127">最新の Skype for Business クライアントを使用していることをご確認ください)。</span><span class="sxs-lookup"><span data-stu-id="1bc3d-127">Make sure you are using the latest Skype for Business client.)</span></span>
 
<span data-ttu-id="1bc3d-128">[TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)のプロパティである[モード](migration-interop-guidance-for-teams-with-skype.md)の概念を使って、チームへのユーザーの移行を管理します。</span><span class="sxs-lookup"><span data-stu-id="1bc3d-128">You manage your user's transition to Teams using the concept of [mode](migration-interop-guidance-for-teams-with-skype.md), which is a property of [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> <span data-ttu-id="1bc3d-129">上で説明したように、Teams に移行されたユーザーは、"TeamsOnly" モードになります。</span><span class="sxs-lookup"><span data-stu-id="1bc3d-129">A user who has been migrated to Teams as described above is in “TeamsOnly” mode.</span></span>  <span data-ttu-id="1bc3d-130">Teams に移行する組織の最終的な目標は、すべてのユーザーを TeamsOnly モードに移行することです。</span><span class="sxs-lookup"><span data-stu-id="1bc3d-130">For an organization that is migrating to Teams, the ultimate goal is to move all users to TeamsOnly mode.</span></span>

<span data-ttu-id="1bc3d-131">わかりました。</span><span class="sxs-lookup"><span data-stu-id="1bc3d-131">OK.</span></span> <span data-ttu-id="1bc3d-132">では、始めましょう。</span><span class="sxs-lookup"><span data-stu-id="1bc3d-132">Let's get started.</span></span>  <span data-ttu-id="1bc3d-133">最初のステップでは、 [利用可能なアップグレード方法](upgrade-to-teams-on-prem-upgrade-methods.md)を理解しています。</span><span class="sxs-lookup"><span data-stu-id="1bc3d-133">The first step is understanding the [upgrade methods available to you](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>







   

## <a name="related-links"></a><span data-ttu-id="1bc3d-134">関連リンク</span><span class="sxs-lookup"><span data-stu-id="1bc3d-134">Related links</span></span>

[<span data-ttu-id="1bc3d-135">Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス</span><span class="sxs-lookup"><span data-stu-id="1bc3d-135">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="1bc3d-136">Skype for Business Server と Microsoft 365 または Office 365 間のハイブリッド接続を構成する</span><span class="sxs-lookup"><span data-stu-id="1bc3d-136">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="1bc3d-137">オンプレミスとクラウドの間でユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="1bc3d-137">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="1bc3d-138">共存およびアップグレードを設定する</span><span class="sxs-lookup"><span data-stu-id="1bc3d-138">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="1bc3d-139">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="1bc3d-139">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="1bc3d-140">会議移行サービス (MMS) を使用する</span><span class="sxs-lookup"><span data-stu-id="1bc3d-140">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

