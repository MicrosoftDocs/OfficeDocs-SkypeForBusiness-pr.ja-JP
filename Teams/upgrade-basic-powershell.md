---
title: PowerShell の基本的なアップグレード | Microsoft Teams | アップグレード相互運用ポリシーの付与
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: 管理センターがテナントで起動していない場合、Teams にアップグレードするための一時的な作業
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 20864b6b0a4be8cf9a0a88c6f3ce63c18687f2af
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837237"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="1bb9d-103">Skype for Business Online から Microsoft Teams へのユーザーのアップグレード</span><span class="sxs-lookup"><span data-stu-id="1bb9d-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="1bb9d-104">この記事で説明するコマンドは、「[アップグレードの基本](https://aka.ms/UpgradeBasic)」チェックリストの一部として使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="1bb9d-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](https://aka.ms/UpgradeBasic) checklist.</span></span>

<span data-ttu-id="1bb9d-105">アップグレードの技術的な移行の側面では、Skype for Business が Teams にアップグレードされることをユーザーに通知し、**Teams only** モードに移行します。</span><span class="sxs-lookup"><span data-stu-id="1bb9d-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="1bb9d-106">これらの手順を実行するには、Skype for Business のリモート Windows PowerShell セッションを使用するか、Microsoft Teams 管理センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1bb9d-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="1bb9d-107">アップグレード ツールは [Microsoft Teams 管理センター](manage-teams-skypeforbusiness-admin-center.md)で積極的に展開しており、すぐにテナントで使用可能になる予定です。</span><span class="sxs-lookup"><span data-stu-id="1bb9d-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="1bb9d-108">使用可能になり次第、「[共存およびアップグレードを設定する](https://aka.ms/SkypeToTeams-SetCoexistence)」でユーザーの移行に関する情報を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="1bb9d-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>

<span data-ttu-id="1bb9d-109">今日アップグレードする準備ができている場合は、次の表にリストされている [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) コマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1bb9d-109">If you're ready to upgrade today, you can use the [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="1bb9d-110">アップグレードの基本手順 ＃</span><span class="sxs-lookup"><span data-stu-id="1bb9d-110">Upgrade Basic step #</span></span> | <span data-ttu-id="1bb9d-111">モード</span><span class="sxs-lookup"><span data-stu-id="1bb9d-111">Mode</span></span> | <span data-ttu-id="1bb9d-112">PowerShell コマンド</span><span class="sxs-lookup"><span data-stu-id="1bb9d-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="1bb9d-113">5</span><span class="sxs-lookup"><span data-stu-id="1bb9d-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="1bb9d-114">アイランド + Skype for Business ユーザーへの通知</span><span class="sxs-lookup"><span data-stu-id="1bb9d-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="1bb9d-115">(ユーザが現在**アイランド** モード (既定) の場合、このコマンドを使用する)</span><span class="sxs-lookup"><span data-stu-id="1bb9d-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="1bb9d-116">*(たとえば、$SipAddress='TestUser@contoso.com')*</span><span class="sxs-lookup"><span data-stu-id="1bb9d-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span> |
| [<span data-ttu-id="1bb9d-117">5</span><span class="sxs-lookup"><span data-stu-id="1bb9d-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="1bb9d-118">Skype for Business のみ + Skype for Business ユーザーへの通知</span><span class="sxs-lookup"><span data-stu-id="1bb9d-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="1bb9d-119">(ユーザが現在 **Skype for Business のみ** モードの場合、このコマンドを使用する)</span><span class="sxs-lookup"><span data-stu-id="1bb9d-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [<span data-ttu-id="1bb9d-120">7</span><span class="sxs-lookup"><span data-stu-id="1bb9d-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="1bb9d-121">Teams のみ</span><span class="sxs-lookup"><span data-stu-id="1bb9d-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
