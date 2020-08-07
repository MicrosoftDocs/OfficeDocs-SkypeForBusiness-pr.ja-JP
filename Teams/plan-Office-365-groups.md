---
title: チームを作成するときの Microsoft 365 グループの計画
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/29/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
description: チームの会話 & グループの違い、チームがグループの名前付けポリシーをどのように尊重しているかなど、Teams での Microsoft 365 グループの計画について説明します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 4e714d530e391ad0e5888607df2fb38dfd862581
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581078"
---
<a name="plan-for-microsoft-365-groups-when-creating-teams-in-microsoft-teams"></a><span data-ttu-id="b95f3-103">Microsoft Teams で teams を作成するときに Microsoft 365 グループを計画する</span><span class="sxs-lookup"><span data-stu-id="b95f3-103">Plan for Microsoft 365 Groups when creating teams in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="b95f3-104">Microsoft 365 グループの使用を検討している場合、またはチームを作成する場合は、チームがどのように使用されるか、だれがアクセスできるか、チームが達成したい成果を検討します。</span><span class="sxs-lookup"><span data-stu-id="b95f3-104">When considering the use of Microsoft 365 Groups or when creating teams, consider what the team will be used for, who should have access, and what outcome the team will expect to achieve.</span></span> <span data-ttu-id="b95f3-105">ユーザーが非常に長い (チャネルが多すぎる) ことによって、ユーザーが簡単に超過してしまう可能性があるため、作成するチャネルの数に注意を払ってください。</span><span class="sxs-lookup"><span data-stu-id="b95f3-105">Pay special attention to the number of channels you create as people can quickly become overrun by content spread too thin (across too many channels).</span></span>

<span data-ttu-id="b95f3-106">Microsoft 365 グループの計画、および Microsoft Teams への影響については、次の2つのシナリオを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b95f3-106">There are two scenarios that warrant some discussion around planning of Microsoft 365 Groups and their impact on (or by) Microsoft Teams:</span></span>

-   <span data-ttu-id="b95f3-107">最初に、顧客は既存の投資をグループに含めることができるため、現在、5000メンバーより小さいパブリックグループとプライベートグループの両方をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b95f3-107">First, since customers could have existing investments in Groups, we currently support both Public and Private groups of less than 5000 members.</span></span> <span data-ttu-id="b95f3-108">前に説明したように、Microsoft 365 管理センターではなく、Teams クライアントを使用して、チームのメンバーのメンバーシップを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b95f3-108">As mentioned previously, you want to manage the membership of people to a team using the Teams client rather than the Microsoft 365 admin center.</span></span> <span data-ttu-id="b95f3-109">このシナリオでは、ユーザーが Microsoft 365 グループでスレッド化された会話に使用している場合は、グループの会話が本質的にメールであり、チームチャネルのチャットメッセージと同じではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b95f3-109">Given this scenario, if people are used to threaded conversations in Microsoft 365 Groups, it is worthwhile noting that a Groups conversation is essentially email and not the same as a chat message in a Teams channel.</span></span> <span data-ttu-id="b95f3-110">この違いについてユーザーを教育して、より柔軟なチャットメッセージ形式を Teams で採用し、Outlook または OWA を使ってグループをメールで送信することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b95f3-110">Educate your people about this difference and suggest they adopt the more flexible chat message format in Teams versus emailing the Group using Outlook or OWA.</span></span>

-   <span data-ttu-id="b95f3-111">次に、Microsoft 365 で定義されている既存のグループを持っていないユーザーは、Microsoft 365 管理センター、Teams web、またはデスクトップクライアントを使用してそれらを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b95f3-111">Second, for customers who don't have existing Groups defined in Microsoft 365, you can either create them using the Microsoft 365 admin center, the Teams web, or desktop clients.</span></span> <span data-ttu-id="b95f3-112">前に説明したように、Teams クライアントを使用して、今後の Microsoft 365 グループへのすべてのメンバーシップを管理します。</span><span class="sxs-lookup"><span data-stu-id="b95f3-112">As mentioned previously, manage all future membership to the Microsoft 365 group using the Teams client.</span></span> <span data-ttu-id="b95f3-113">チームのメンバーシップも Microsoft 365 グループへのメンバーシップを定義しているため、この変更についてユーザーを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b95f3-113">Since membership to a team is also defining membership to Microsoft 365 Groups, you should prepare people for this change.</span></span>

## <a name="teams-respects-microsoft-365-groups-naming-policy-in-private-preview"></a><span data-ttu-id="b95f3-114">チームは、Microsoft 365 グループの名前付けポリシーを尊重します (プライベートプレビュー)</span><span class="sxs-lookup"><span data-stu-id="b95f3-114">Teams respects Microsoft 365 Groups naming policy (in private preview)</span></span>

<span data-ttu-id="b95f3-115">管理者によって設定された Microsoft 365 グループの名前付けポリシーは、ユーザーがチーム名を作成または編集したときに Teams に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b95f3-115">Any Microsoft 365 Groups naming policy that has been set by your admin will be applied in Teams when users create or edit team names.</span></span> <span data-ttu-id="b95f3-116">これには必須のプレフィックスやサフィックス、禁止された単語の除外などの事項が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b95f3-116">This includes things like mandatory prefixes or suffixes and excluding banned words.</span></span>

> [!NOTE]
> <span data-ttu-id="b95f3-117">この機能はプライベートプレビューであるため、このプレビューに含まれていない場合、Teams はこの Microsoft 365 グループの名前付けポリシーに準拠していません。</span><span class="sxs-lookup"><span data-stu-id="b95f3-117">This feature is in private preview, which means that if you're not part of this preview, Teams doesn't yet adhere to this Microsoft 365 Groups naming policy.</span></span>

<span data-ttu-id="b95f3-118">詳細については、「 [Teams で Microsoft 365 グループの名前付けポリシー」](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b95f3-118">To learn more, read [Microsoft 365 Groups naming policy in Teams](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

<span data-ttu-id="b95f3-119">次の記事は、Microsoft 365 グループの準備および導入のためのコンテンツを見つけるのに最適な場所です。</span><span class="sxs-lookup"><span data-stu-id="b95f3-119">The following articles are a good place to find readiness and adoption content for your Microsoft 365 Groups:</span></span>

-   [<span data-ttu-id="b95f3-120">Get more with groups in Outlook (Outlook でグループを活用する)</span><span class="sxs-lookup"><span data-stu-id="b95f3-120">Get more with groups in Outlook</span></span>](https://support.office.com/article/Get-more-with-Office-365-Groups-in-Outlook-93132800-5b11-49de-8cc2-605b6075b2b9)

-   [<span data-ttu-id="b95f3-121">Microsoft 365 管理センターを使用して、Microsoft 365 グループのメンバーを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="b95f3-121">Add or remove members from Microsoft 365 Groups using the Microsoft 365 admin center</span></span>](https://support.office.com/article/Manage-Group-membership-in-the-Office-365-admin-center-e186d224-a324-4afa-8300-0e4fc0c3000a)

-   [<span data-ttu-id="b95f3-122">削除したグループを復元する</span><span class="sxs-lookup"><span data-stu-id="b95f3-122">Restore a deleted group</span></span>](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)