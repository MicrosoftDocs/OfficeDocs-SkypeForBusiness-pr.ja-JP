---
title: ユーザーとの通信Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: ラーニング(これは M365 通信コンプライアンス機能の一部) の観点から、insider リスク ソリューション セットの一部である通信コンプライアンスについて説明します (Microsoft Teams)。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c5957e8900a9b3d9915a88e3ad8bf5e18c7a08b3
ms.sourcegitcommit: d77104d5606ff93a792e8712d6c7780ae247b536
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "53126903"
---
# <a name="communication-compliance-with-microsoft-teams"></a><span data-ttu-id="120a8-103">ユーザーとの通信Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="120a8-103">Communication compliance with Microsoft Teams</span></span>

<span data-ttu-id="120a8-104">コミュニケーション コンプライアンスは、組織内の不適切なメッセージの検出、キャプチャ、および操作を支援することで、通信リスクを最小限に抑えるために役立つ Microsoft 365 の Insider リスク ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="120a8-104">Communication compliance is an insider risk solution in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and act on inappropriate messages in your organization.</span></span>

<span data-ttu-id="120a8-105">通信Microsoft Teams、Teams チャネル、プライベート Teams[](/microsoft-365/compliance/communication-compliance-feature-reference)チャネル、または 1:1 およびグループ チャットで、次の種類の不適切なコンテンツを識別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="120a8-105">For Microsoft Teams, communication compliance helps identify the [following types](/microsoft-365/compliance/communication-compliance-feature-reference) of inappropriate content in Teams channels, Private Teams channels, or in 1:1 and group chats:</span></span>

- <span data-ttu-id="120a8-106">不快な言葉、不適切な言葉、嫌がらせをする言葉</span><span class="sxs-lookup"><span data-stu-id="120a8-106">Offensive, profane, and harassing language</span></span>
- <span data-ttu-id="120a8-107">成人向け、人種差別的な画像、およびゴリー 画像</span><span class="sxs-lookup"><span data-stu-id="120a8-107">Adult, racy, and gory images</span></span>
- <span data-ttu-id="120a8-108">機密情報の共有</span><span class="sxs-lookup"><span data-stu-id="120a8-108">Sharing of sensitive information</span></span>

<span data-ttu-id="120a8-109">通信コンプライアンスと組織のポリシーを構成する方法の詳細については、「組織の通信コンプライアンス」を[Microsoft 365。](/microsoft-365/compliance/communication-compliance)</span><span class="sxs-lookup"><span data-stu-id="120a8-109">For more information on communication compliance and how to configure policies for your organization, see [Communication compliance in Microsoft 365](/microsoft-365/compliance/communication-compliance).</span></span>

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a><span data-ttu-id="120a8-110">Microsoft Teams で通信コンプライアンスを使用するMicrosoft Teams</span><span class="sxs-lookup"><span data-stu-id="120a8-110">How to use communication compliance in Microsoft Teams</span></span>

<span data-ttu-id="120a8-111">通信コンプライアンスとMicrosoft Teamsは緊密に統合され、組織内の通信リスクを最小限に抑えるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="120a8-111">Communication compliance and Microsoft Teams are tightly integrated and can help minimize communication risks in your organization.</span></span> <span data-ttu-id="120a8-112">最初の通信コンプライアンス ポリシーを構成した後は、アラートで自動的にフラグが設定されたメッセージMicrosoft Teams不適切なメッセージやコンテンツを積極的に管理できます。</span><span class="sxs-lookup"><span data-stu-id="120a8-112">After you've configured your first communication compliance policies, you can actively manage inappropriate Microsoft Teams messages and content that is automatically flagged in alerts.</span></span>

### <a name="getting-started"></a><span data-ttu-id="120a8-113">はじめに</span><span class="sxs-lookup"><span data-stu-id="120a8-113">Getting started</span></span>

<span data-ttu-id="120a8-114">Microsoft Teams でのコミュニケーション コンプライアンスの開始は、Teams チャネルまたは[](/microsoft-365/compliance/communication-compliance-plan)1:1 およびグループで不適切なユーザー アクティビティを識別する定義済みポリシーまたはカスタム ポリシーの計画と作成から始まります。</span><span class="sxs-lookup"><span data-stu-id="120a8-114">Getting started with communication compliance in Microsoft Teams begins with [planning](/microsoft-365/compliance/communication-compliance-plan) and creating pre-defined or custom policies to identify inappropriate user activities in Teams channels or in 1:1 and groups.</span></span> <span data-ttu-id="120a8-115">構成プロセスの一環として、いくつかのアクセス[](/microsoft-365/compliance/communication-compliance-configure)許可と基本的な前提条件を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="120a8-115">Keep in mind that you'll need to [configure](/microsoft-365/compliance/communication-compliance-configure) some permissions and basic prerequisites as part of the configuration process.</span></span>

<span data-ttu-id="120a8-116">Teams管理者は、次のレベルで通信コンプライアンス ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="120a8-116">Teams administrators can configure communication compliance policies at the following levels:</span></span>

- <span data-ttu-id="120a8-117">**ユーザー レベル**: このレベルのポリシーは、個々のユーザー Teams適用するか、組織内のすべてのユーザー Teamsに適用できます。</span><span class="sxs-lookup"><span data-stu-id="120a8-117">**User level**: Policies at this level apply to an individual Teams user or may be applied to all Teams users in your organization.</span></span> <span data-ttu-id="120a8-118">これらのポリシーは、これらのユーザーが 1 対 1 またはグループ チャットで送信できるメッセージをカバーします。</span><span class="sxs-lookup"><span data-stu-id="120a8-118">These policies cover messages that these users may send in 1:1 or group chats.</span></span> <span data-ttu-id="120a8-119">ユーザーのチャット通信は、ユーザーがメンバーであるすべてのMicrosoft Teams自動的に監視されます。</span><span class="sxs-lookup"><span data-stu-id="120a8-119">Chat communications for the users are automatically monitored across all Microsoft Teams where the users are a member.</span></span>
- <span data-ttu-id="120a8-120">**Teams レベル**: このレベルのポリシーは、プライベート チャネルを含む Microsoft チーム チャネルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="120a8-120">**Teams level**: Policies at this level apply to a Microsoft Team channel, including a Private channel.</span></span> <span data-ttu-id="120a8-121">これらのポリシーは、チャネル内で送信されたTeamsのみをカバーします。</span><span class="sxs-lookup"><span data-stu-id="120a8-121">These policies cover messages sent in the Teams channel only.</span></span>

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a><span data-ttu-id="120a8-122">メッセージ内の不適切なメッセージにMicrosoft Teams</span><span class="sxs-lookup"><span data-stu-id="120a8-122">Act on inappropriate messages in Microsoft Teams</span></span>

<span data-ttu-id="120a8-123">ポリシーを構成し、Microsoft Teams メッセージの通信コンプライアンス アラートを受け取った後は、組織内のコンプライアンスレビュー担当者がこれらのメッセージに対してアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="120a8-123">After you have configured your policies and have received communication compliance alerts for Microsoft Teams messages, it's time for compliance reviewers in your organization to take action on these messages.</span></span> <span data-ttu-id="120a8-124">レビュー担当者は、コミュニケーション コンプライアンスの警告を確認し、フラグ付きメッセージをグループ内のビューから削除することで、組織を保護Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="120a8-124">Reviewers can help safeguard your organization by reviewing communication compliance alerts and removing flagged messages from view in Microsoft Teams.</span></span>

![メッセージを削除Teams](./media/communication-compliance-remove-teams-message.png)

<span data-ttu-id="120a8-126">削除されたメッセージとコンテンツは、メッセージまたはコンテンツが削除され、削除に適用できるポリシーを説明する閲覧者向け通知に置き換えられる。</span><span class="sxs-lookup"><span data-stu-id="120a8-126">Removed messages and content are replaced with notifications for viewers explaining that the message or content has been removed and what policy is applicable to the removal.</span></span> <span data-ttu-id="120a8-127">削除されたメッセージまたはコンテンツの送信者にも、削除の状態が通知され、削除に関連するコンテキストの元のメッセージ コンテンツが提供されます。</span><span class="sxs-lookup"><span data-stu-id="120a8-127">The sender of the removed message or content is also notified of the removal status and provided with original message content for context relating to its removal.</span></span> <span data-ttu-id="120a8-128">送信者は、メッセージの削除に適用される特定のポリシー条件を表示できます。</span><span class="sxs-lookup"><span data-stu-id="120a8-128">The sender can also view the specific policy condition that applies to the message removal.</span></span>

<span data-ttu-id="120a8-129">送信者によって表示されるポリシー ヒントの例:</span><span class="sxs-lookup"><span data-stu-id="120a8-129">Example of policy tip seen by sender:</span></span>

![送信者のポリシー ヒント](./media/communication-compliance-warning-1.png)

<span data-ttu-id="120a8-131">送信者に表示されるポリシー条件通知の例:</span><span class="sxs-lookup"><span data-stu-id="120a8-131">Example of policy condition notification seen by the sender:</span></span>

![送信者のポリシー条件情報](./media/communication-compliance-warning-2.png)

<span data-ttu-id="120a8-133">受信者が表示するポリシー ヒントの例:</span><span class="sxs-lookup"><span data-stu-id="120a8-133">Example of policy tip seen by recipient:</span></span>

![受信者のポリシー ヒント](./media/communication-compliance-warning-3.png)