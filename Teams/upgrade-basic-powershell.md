---
title: 基本的なアップグレード PowerShell |Microsoft Teams |アップグレードの相互運用ポリシーを付与する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: テナントで管理センターが使用されていない場合に、Teams にアップグレードするための Stopgap
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 945422f6bb61fca8d2b17379a7c9bf4695e7dd09
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236543"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="5caa3-103">ユーザーを Skype for Business Online から Microsoft Teams にアップグレードする</span><span class="sxs-lookup"><span data-stu-id="5caa3-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="5caa3-104">この記事で説明しているコマンドは、[アップグレードの基本的な](https://aka.ms/UpgradeBasic)チェックリストの一部として使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="5caa3-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](https://aka.ms/UpgradeBasic) checklist.</span></span>

<span data-ttu-id="5caa3-105">アップグレードの技術的な移行には、Skype for Business が Teams にアップグレードされることをユーザーに通知し、それを**チーム専用**モードに移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5caa3-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="5caa3-106">これらの手順は、Skype for Business リモート Windows PowerShell セッションまたは Microsoft Teams 管理センターを使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5caa3-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="5caa3-107">[Microsoft Teams 管理センター](manage-teams-skypeforbusiness-admin-center.md)でアップグレードツールを積極的にロールアウトしています。この機能は、お使いのテナントから間もなく利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="5caa3-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="5caa3-108">この機能が利用可能になったら、ユーザーを移行するための情報を、[共存とアップグレードの設定](https://aka.ms/SkypeToTeams-SetCoexistence)で確認できます。</span><span class="sxs-lookup"><span data-stu-id="5caa3-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>

<span data-ttu-id="5caa3-109">今すぐアップグレードする準備ができたら、次の表に示す[PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)コマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5caa3-109">If you're ready to upgrade today, you can use the [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="5caa3-110">アップグレードの基本手順#</span><span class="sxs-lookup"><span data-stu-id="5caa3-110">Upgrade Basic step #</span></span> | <span data-ttu-id="5caa3-111">Mode</span><span class="sxs-lookup"><span data-stu-id="5caa3-111">Mode</span></span> | <span data-ttu-id="5caa3-112">PowerShell コマンド</span><span class="sxs-lookup"><span data-stu-id="5caa3-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="5caa3-113">5</span><span class="sxs-lookup"><span data-stu-id="5caa3-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="5caa3-114">諸島 + Skype for Business ユーザーに通知する</span><span class="sxs-lookup"><span data-stu-id="5caa3-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="5caa3-115">(現在、ユーザーが現在**諸島**モード (既定) である場合は、このコマンドを使用します)。</span><span class="sxs-lookup"><span data-stu-id="5caa3-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="5caa3-116">*($SipAddress = ' TestUser@contoso.com ' など)*</span><span class="sxs-lookup"><span data-stu-id="5caa3-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span><br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingDefaultChatDefault -Identity $SipAddress``` |
| [<span data-ttu-id="5caa3-117">5</span><span class="sxs-lookup"><span data-stu-id="5caa3-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="5caa3-118">Skype for Business で Skype for business のユーザーに通知する</span><span class="sxs-lookup"><span data-stu-id="5caa3-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="5caa3-119">(現在、ユーザーが**Skype For business のみ**のモードである場合は、このコマンドを使用)</span><span class="sxs-lookup"><span data-stu-id="5caa3-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingSfBChatSfB -Identity $SipAddress``` |
| [<span data-ttu-id="5caa3-120">7</span><span class="sxs-lookup"><span data-stu-id="5caa3-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="5caa3-121">Teams Only</span><span class="sxs-lookup"><span data-stu-id="5caa3-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity $SipAddress``` |
