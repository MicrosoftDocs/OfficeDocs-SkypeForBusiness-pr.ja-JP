---
title: Microsoft Teams のゲスト アクセスに関する問題のトラブルシューティング
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: corbinm
search.appverid: MET150
description: Microsoft Teams のゲスト アクセスに関する問題のトラブルシューティングと解決に役立つヘルプをご利用ください。
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0468d0d3d1cc7a8d1c17699e28c1449e1f7800c8
ms.sourcegitcommit: a731226d62d8b23fe73bd7bf61654e16367fbd90
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2021
ms.locfileid: "51948684"
---
# <a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="92f0b-103">Microsoft Teams のゲスト アクセスに関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="92f0b-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>

- <span data-ttu-id="92f0b-104">問題がわかっているかどうかを確認するには、組織内のサポート [チームを参照してください](/MicrosoftTeams/troubleshoot/teams-welcome)。</span><span class="sxs-lookup"><span data-stu-id="92f0b-104">To see whether we know about your problem, check out [Support Teams in your organization](/MicrosoftTeams/troubleshoot/teams-welcome).</span></span>
- <span data-ttu-id="92f0b-105">Teams でのゲスト アクセスに関する最新のサポートの問題を確認するには、[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/)に関するページに移動します。</span><span class="sxs-lookup"><span data-stu-id="92f0b-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="92f0b-106">ゲストは組織外のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="92f0b-106">Guests are people outside your organization.</span></span> <span data-ttu-id="92f0b-107">ユーザーが組織内にいる場合 (社内の従業員、オンサイトの請負業者、オンサイトの代理業者など) は、ゲストとして追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="92f0b-107">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="92f0b-108">これは、関連会社についても同じです。</span><span class="sxs-lookup"><span data-stu-id="92f0b-108">The same applies to your affiliates.</span></span>
- <span data-ttu-id="92f0b-109">今後実装される新機能や更新されたゲスト アクセス機能については、「[Teams のロードマップ](https://aka.ms/teamsroadmap)」で見つけてください。</span><span class="sxs-lookup"><span data-stu-id="92f0b-109">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="92f0b-110">ご要望については、「[Teams UserVoice](https://aka.ms/TeamsUserVoice)」でお知らせください。</span><span class="sxs-lookup"><span data-stu-id="92f0b-110">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="92f0b-111">ゲストに対してライセンスのエラーが表示されている場合</span><span class="sxs-lookup"><span data-stu-id="92f0b-111">If your guests are seeing license errors</span></span>

<span data-ttu-id="92f0b-112">Teams のゲスト アクセスでは Azure Active Directory (Azure AD) ビジネス ツー ビジネス (B2B) およびそのライセンス モデルを使用しています。</span><span class="sxs-lookup"><span data-stu-id="92f0b-112">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="92f0b-113">ゲスト アクセスは、Microsoft 365 Business Standard、Office 365 Enterprise、Office 365 Education のすべてのサブスクリプションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="92f0b-113">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="92f0b-114">追加の Microsoft 365 または Office 365 ライセンスは不要です。</span><span class="sxs-lookup"><span data-stu-id="92f0b-114">No additional Microsoft 365 or Office 365 license is necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="92f0b-115">ゲストがサインインし、別の (リソース) テナントで Teams をゲストとして使用するには、ゲストのホーム テナントで Teams を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="92f0b-115">Teams must be enabled on a guest's home tenant for guests to be able to sign in and use Teams as a guest on another (resource) tenant.</span></span>

<span data-ttu-id="92f0b-116">ライセンス エラーが表示される場合は [、Azure AD](/azure/active-directory/external-identities/external-identities-pricing) 外部 ID の課金モデルを参照して、組織内のゲスト アクセスのニーズを満たすライセンス要件を決定してください。</span><span class="sxs-lookup"><span data-stu-id="92f0b-116">If you're seeing licensing errors, make sure to read the [Billing model for Azure AD External Identities](/azure/active-directory/external-identities/external-identities-pricing) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>

- <span data-ttu-id="92f0b-117">ゲスト ライセンスは、招待する組織に対してカウントされます。</span><span class="sxs-lookup"><span data-stu-id="92f0b-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="92f0b-118">必要なライセンスの数を算出するときは、このことを考慮に入れます。</span><span class="sxs-lookup"><span data-stu-id="92f0b-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="92f0b-119">ライセンスは、招待されたゲストが別の Microsoft 365 組織から来た場合でも、個人のメール アドレスを使用している場合でも、組織に対してカウントされます。</span><span class="sxs-lookup"><span data-stu-id="92f0b-119">Licenses are counted against your organization whether the invited guests come from another Microsoft 365 organization or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="92f0b-120">B2B ユーザーの種類のサポート</span><span class="sxs-lookup"><span data-stu-id="92f0b-120">Support for B2B User types</span></span>

<span data-ttu-id="92f0b-121">現在、Teams Only は、[Azure B2B で定義](/azure/active-directory/b2b/user-properties)されている状態 1 および状態 2 のゲスト ユーザーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="92f0b-121">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="92f0b-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="92f0b-122">Related topics</span></span>

[<span data-ttu-id="92f0b-123">Teams でのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="92f0b-123">Guest access in Teams</span></span>](guest-access.md)

[<span data-ttu-id="92f0b-124">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="92f0b-124">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)