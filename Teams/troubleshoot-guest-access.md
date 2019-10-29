---
title: Microsoft Teams でのゲストアクセスに関する問題のトラブルシューティング
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: corbinm
search.appverid: MET150
description: Microsoft Teams のゲストアクセスに関する問題のトラブルシューティングと解決に役立つ情報を入手します。
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: eefaece55876bc66905716526884fd21303c630e
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2019
ms.locfileid: "37754363"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="79fc9-103">Microsoft Teams でのゲストアクセスに関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="79fc9-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>
======================================================

> [!IMPORTANT]
> <span data-ttu-id="79fc9-104">変更が有効になるまで最長で24時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="79fc9-104">You may have to wait for up to 24 hours for your changes to take effect.</span></span> 


- <span data-ttu-id="79fc9-105">Teams でのゲストアクセスに関する現在のサポートの問題を確認するには、「 [teams のトラブルシューティング](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79fc9-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="79fc9-106">問題がわかっているかどうかを確認するには、「 [Microsoft Teams の既知の問題](Known-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79fc9-106">To see whether we know about your problem, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="79fc9-107">ゲストとは、自分の組織の外部のユーザーのことです。</span><span class="sxs-lookup"><span data-stu-id="79fc9-107">Guests are users outside your organization.</span></span> <span data-ttu-id="79fc9-108">組織内のユーザー (従業員、オンサイトの請負業者、オンサイトエージェントなど) は、ゲストとして追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="79fc9-108">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="79fc9-109">これは、関連会社にも提供されます。</span><span class="sxs-lookup"><span data-stu-id="79fc9-109">The same applies to your affiliates.</span></span>
- <span data-ttu-id="79fc9-110">今後の新規または更新されたゲストアクセス機能については、「 [Teams のロードマップ](https://aka.ms/teamsroadmap)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79fc9-110">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="79fc9-111">[Teams UserVoice](https://aka.ms/TeamsUserVoice)でご希望のご意見をお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="79fc9-111">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="79fc9-112">ゲストに対してライセンスのエラーが表示されている場合</span><span class="sxs-lookup"><span data-stu-id="79fc9-112">If your guests are seeing license errors</span></span>

<span data-ttu-id="79fc9-113">Teams でのゲストアクセスでは、Azure Active Directory (Azure AD) Business to Business (B2B) とライセンスモデルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="79fc9-113">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="79fc9-114">ゲスト アクセスは、Office 365 Business Premium、Office 365 Enterprise、Office 365 Education のすべてのサブスクリプションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="79fc9-114">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="79fc9-115">追加の Office 365 ライセンスは不要です。</span><span class="sxs-lookup"><span data-stu-id="79fc9-115">No additional Office 365 license is necessary.</span></span>

<span data-ttu-id="79fc9-116">ライセンスエラーが表示される場合は、組織でのゲストアクセスのニーズに合わせて、ライセンス要件を特定するために、 [Azure Active DIRECTORY B2B ライセンスガイダンス](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)をお読みください。</span><span class="sxs-lookup"><span data-stu-id="79fc9-116">If you’re seeing licensing errors, make sure to read the [Azure Active Directory B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>


- <span data-ttu-id="79fc9-117">ゲスト ライセンスは、招待する組織に対してカウントされます。</span><span class="sxs-lookup"><span data-stu-id="79fc9-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="79fc9-118">必要なライセンスの数を算出するときは、このことを考慮に入れます。</span><span class="sxs-lookup"><span data-stu-id="79fc9-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="79fc9-119">招待されたゲストが別の Office 365 テナントからのユーザーであろうと、個人のメール アドレスを使用していようと、ライセンスがカウントされる対象は自分の組織になります。</span><span class="sxs-lookup"><span data-stu-id="79fc9-119">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="79fc9-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="79fc9-120">Related topics</span></span>

[<span data-ttu-id="79fc9-121">Teams でのゲストアクセス</span><span class="sxs-lookup"><span data-stu-id="79fc9-121">Guest access in Teams</span></span>](guest-access.md)


