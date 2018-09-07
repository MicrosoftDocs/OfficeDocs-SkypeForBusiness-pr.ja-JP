---
title: 基本の PowerShell コマンド - マイクロソフトのチームをアップグレードします。
author: dearbeen
ms.author: dearbeen
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 管理センターは、テナントに点灯していない場合は、チームにアップグレードするための暫定的な
localization_priority: Priority
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: bf44cbca9c6836c462802293f37ef6b916566520
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23860584"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="ade37-103">ユーザーをアップグレードする、Skype のオンライン ビジネスのマイクロソフトのチームに</span><span class="sxs-lookup"><span data-stu-id="ade37-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="ade37-104">この資料で説明するコマンドは、[基本のアップグレード](https://aka.ms/UpgradeBasic)のチェックリストの一部として使用するために設計されています。</span><span class="sxs-lookup"><span data-stu-id="ade37-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](https://aka.ms/UpgradeBasic) checklist.</span></span>

<span data-ttu-id="ade37-105">アップグレードの移行の技術的な側面、ビジネス用の Skype はチームへのアップグレード、**チームのみ**のモードに移動して、ユーザーに通知することが必要になります。</span><span class="sxs-lookup"><span data-stu-id="ade37-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="ade37-106">リモートの Windows PowerShell セッションをビジネス用またはマイクロソフトのチームとビジネス管理センターの Skype、Skype 経由でこれらの手順を実現できます。</span><span class="sxs-lookup"><span data-stu-id="ade37-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams & Skype for Business Admin Center.</span></span> 
 
<span data-ttu-id="ade37-107">[マイクロソフトのチームとビジネス管理センターの Skype](manage-teams-skypeforbusiness-admin-center.md)で、ツールのアップグレードを積極的に展開してと、テナントですぐに利用可能な場合があります。</span><span class="sxs-lookup"><span data-stu-id="ade37-107">We're actively rolling out upgrade tooling in the [Microsoft Teams & Skype for Business Admin Center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="ade37-108">使用可能になると[の共存を設定](https://aka.ms/SkypeToTeams-SetCoexistence)および設定をアップグレードするユーザーの移行に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ade37-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span> 
 
<span data-ttu-id="ade37-109">今すぐアップグレードする準備が整ったら、 [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)コマンドを次の表に記載されているを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="ade37-109">If you're ready to upgrade today, you can use the [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span> 
 
 |<span data-ttu-id="ade37-110">アップグレードの基本的なステップ #</span><span class="sxs-lookup"><span data-stu-id="ade37-110">Upgrade Basic step #</span></span> | <span data-ttu-id="ade37-111">モード</span><span class="sxs-lookup"><span data-stu-id="ade37-111">Mode</span></span> | <span data-ttu-id="ade37-112">PowerShell コマンド</span><span class="sxs-lookup"><span data-stu-id="ade37-112">PowerShell command</span></span> |
|-------|--------|------|
| [<span data-ttu-id="ade37-113">5</span><span class="sxs-lookup"><span data-stu-id="ade37-113">5</span></span>](upgrade-basic.md#step-5) |<span data-ttu-id="ade37-114">諸島 +、Skype をビジネス ユーザーに通知</span><span class="sxs-lookup"><span data-stu-id="ade37-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="ade37-115">(**諸島**モード (既定値) でユーザーがいる場合は、このコマンドを使用して)</span><span class="sxs-lookup"><span data-stu-id="ade37-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="ade37-116">_(たとえば、$SipAddress = 'TestUser@contoso.com')_</span><span class="sxs-lookup"><span data-stu-id="ade37-116">_(for example, $SipAddress='TestUser@contoso.com')_</span></span><br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingDefaultChatDefault -Identity $SipAddress``` |
| [<span data-ttu-id="ade37-117">5</span><span class="sxs-lookup"><span data-stu-id="ade37-117">5</span></span>](upgrade-basic.md#step-5)  | <span data-ttu-id="ade37-118">ビジネスのみの Skype、Skype をビジネス ユーザーに通知する +</span><span class="sxs-lookup"><span data-stu-id="ade37-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="ade37-119">( **Skype**ビジネスのみのモードでユーザーがいる場合は、このコマンドを使用します)</span><span class="sxs-lookup"><span data-stu-id="ade37-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingSfBChatSfB -Identity $SipAddress``` |
| [<span data-ttu-id="ade37-120">7</span><span class="sxs-lookup"><span data-stu-id="ade37-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="ade37-121">チームのみ</span><span class="sxs-lookup"><span data-stu-id="ade37-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity $SipAddress``` |


