---
title: Microsoft Teams のコミュニケーション コンプライアンス
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Microsoft Teams の観点から、Insider リスク ソリューション セットの一部であるコミュニケーション コンプライアンスについて学習します (これは M365 コミュニケーション コンプライアンス機能の一部です)。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cf032669edc7255571e2501774ac0d0ee0df47d8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121535"
---
# <a name="communication-compliance-with-microsoft-teams"></a><span data-ttu-id="3da03-103">Microsoft Teams のコミュニケーション コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="3da03-103">Communication compliance with Microsoft Teams</span></span>

<span data-ttu-id="3da03-104">コミュニケーション コンプライアンスは Microsoft 365 の Insider リスク ソリューションであり、組織内の不適切なメッセージの検出、取り込み、対応を支援することで、コミュニケーション リスクを最小限に抑えるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3da03-104">Communication compliance is an insider risk solution in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and act on inappropriate messages in your organization.</span></span>

<span data-ttu-id="3da03-105">Microsoft Teams の場合、コミュニケーション[](/microsoft-365/compliance/communication-compliance-feature-reference)コンプライアンスは、Teams チャネルまたは 1 対 1 およびグループ チャットで、次の種類の不適切なコンテンツを識別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3da03-105">For Microsoft Teams, communication compliance helps identify the [following types](/microsoft-365/compliance/communication-compliance-feature-reference) of inappropriate content in Teams channels or in 1:1 and group chats:</span></span>

- <span data-ttu-id="3da03-106">不快な言葉、不適切な言葉、嫌がらせをする言葉</span><span class="sxs-lookup"><span data-stu-id="3da03-106">Offensive, profane, and harassing language</span></span>
- <span data-ttu-id="3da03-107">成人向け、人種差別的な画像、およびゴリー画像</span><span class="sxs-lookup"><span data-stu-id="3da03-107">Adult, racy, and gory images</span></span>
- <span data-ttu-id="3da03-108">機密情報の共有</span><span class="sxs-lookup"><span data-stu-id="3da03-108">Sharing of sensitive information</span></span>

<span data-ttu-id="3da03-109">コミュニケーション コンプライアンスと組織のポリシーを構成する方法の詳細については [、Microsoft 365](/microsoft-365/compliance/communication-compliance)のコミュニケーション コンプライアンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3da03-109">For more information on communication compliance and how to configure policies for your organization, see [Communication compliance in Microsoft 365](/microsoft-365/compliance/communication-compliance).</span></span>

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a><span data-ttu-id="3da03-110">Microsoft Teams でコミュニケーション コンプライアンスを使用する方法</span><span class="sxs-lookup"><span data-stu-id="3da03-110">How to use communication compliance in Microsoft Teams</span></span>

<span data-ttu-id="3da03-111">コミュニケーション コンプライアンスと Microsoft Teams は緊密に統合され、組織内のコミュニケーション リスクを最小限に抑えるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3da03-111">Communication compliance and Microsoft Teams are tightly integrated and can help minimize communication risks in your organization.</span></span> <span data-ttu-id="3da03-112">最初のコミュニケーション コンプライアンス ポリシーを構成した後は、警告で自動的にフラグが付けられている不適切な Microsoft Teams のメッセージとコンテンツを積極的に管理できます。</span><span class="sxs-lookup"><span data-stu-id="3da03-112">After you've configured your first communication compliance policies, you can actively manage inappropriate Microsoft Teams messages and content that is automatically flagged in alerts.</span></span>

### <a name="getting-started"></a><span data-ttu-id="3da03-113">はじめに</span><span class="sxs-lookup"><span data-stu-id="3da03-113">Getting started</span></span>

<span data-ttu-id="3da03-114">Microsoft Teams のコミュニケーション コンプライアンスの使用を開始[](/microsoft-365/compliance/communication-compliance-plan)するには、Teams チャネルまたは 1 対 1 およびグループで不適切なユーザー アクティビティを特定するための事前に定義されたポリシーまたはカスタム ポリシーの計画と作成から始めます。</span><span class="sxs-lookup"><span data-stu-id="3da03-114">Getting started with communication compliance in Microsoft Teams begins with [planning](/microsoft-365/compliance/communication-compliance-plan) and creating pre-defined or custom policies to identify inappropriate user activities in Teams channels or in 1:1 and groups.</span></span> <span data-ttu-id="3da03-115">構成プロセスの一環として、いくつかのアクセス[](/microsoft-365/compliance/communication-compliance-configure)許可と基本的な前提条件を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3da03-115">Keep in mind that you'll need to [configure](/microsoft-365/compliance/communication-compliance-configure) some permissions and basic prerequisites as part of the configuration process.</span></span>

<span data-ttu-id="3da03-116">Teams 管理者は、次のレベルでコミュニケーション コンプライアンス ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="3da03-116">Teams administrators can configure communication compliance policies at the following levels:</span></span>

- <span data-ttu-id="3da03-117">**ユーザー レベル**: このレベルのポリシーは、個々の Teams ユーザーに適用するか、組織内のすべての Teams ユーザーに適用できます。</span><span class="sxs-lookup"><span data-stu-id="3da03-117">**User level**: Policies at this level apply to an individual Teams user or may be applied to all Teams users in your organization.</span></span> <span data-ttu-id="3da03-118">これらのポリシーは、これらのユーザーが 1 対 1 またはグループ チャットで送信できるメッセージに適用されます。</span><span class="sxs-lookup"><span data-stu-id="3da03-118">These policies cover messages that these users may send in 1:1 or group chats.</span></span> <span data-ttu-id="3da03-119">ユーザーのチャット通信は、ユーザーがメンバーであるすべての Microsoft Teams で自動的に監視されます。</span><span class="sxs-lookup"><span data-stu-id="3da03-119">Chat communications for the users are automatically monitored across all Microsoft Teams where the users are a member.</span></span>
- <span data-ttu-id="3da03-120">**チーム レベル**: このレベルのポリシーは、Microsoft チーム チャネルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="3da03-120">**Teams level**: Policies at this level apply to a Microsoft Team channel.</span></span> <span data-ttu-id="3da03-121">これらのポリシーは、Teams チャネルで送信されたメッセージにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="3da03-121">These policies cover messages sent in the Teams channel only.</span></span>

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a><span data-ttu-id="3da03-122">Microsoft Teams で不適切なメッセージに対して行動する</span><span class="sxs-lookup"><span data-stu-id="3da03-122">Act on inappropriate messages in Microsoft Teams</span></span>

<span data-ttu-id="3da03-123">ポリシーを構成し、Microsoft Teams メッセージの通信コンプライアンス警告を受け取った後は、組織内のコンプライアンスレビュー担当者がこれらのメッセージに対してアクションを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3da03-123">After you have configured your policies and have received communication compliance alerts for Microsoft Teams messages, it's time for compliance reviewers in your organization to take action on these messages.</span></span> <span data-ttu-id="3da03-124">レビュー担当者は、コミュニケーション コンプライアンスの警告を確認し、Microsoft Teams のビューからフラグ付きメッセージを削除することで、組織を保護できます。</span><span class="sxs-lookup"><span data-stu-id="3da03-124">Reviewers can help safeguard your organization by reviewing communication compliance alerts and removing flagged messages from view in Microsoft Teams.</span></span>

![Teams でメッセージを削除する](./media/communication-compliance-remove-teams-message.png)

<span data-ttu-id="3da03-126">削除されたメッセージとコンテンツは、メッセージまたはコンテンツが削除され、削除に適用されるポリシーを説明する閲覧者向け通知に置き換えられる。</span><span class="sxs-lookup"><span data-stu-id="3da03-126">Removed messages and content are replaced with notifications for viewers explaining that the message or content has been removed and what policy is applicable to the removal.</span></span> <span data-ttu-id="3da03-127">削除されたメッセージまたはコンテンツの送信者にも、削除の状態が通知され、削除に関連するコンテキストの元のメッセージ コンテンツが提供されます。</span><span class="sxs-lookup"><span data-stu-id="3da03-127">The sender of the removed message or content is also notified of the removal status and provided with original message content for context relating to its removal.</span></span> <span data-ttu-id="3da03-128">送信者は、メッセージの削除に適用される特定のポリシー条件を表示できます。</span><span class="sxs-lookup"><span data-stu-id="3da03-128">The sender can also view the specific policy condition that applies to the message removal.</span></span>

<span data-ttu-id="3da03-129">送信者が表示するポリシー ヒントの例:</span><span class="sxs-lookup"><span data-stu-id="3da03-129">Example of policy tip seen by sender:</span></span>

![送信者のポリシー ヒント](./media/communication-compliance-warning-1.png)

<span data-ttu-id="3da03-131">送信者に表示されるポリシー条件通知の例:</span><span class="sxs-lookup"><span data-stu-id="3da03-131">Example of policy condition notification seen by the sender:</span></span>

![送信者のポリシー条件情報](./media/communication-compliance-warning-2.png)

<span data-ttu-id="3da03-133">受信者が表示するポリシー ヒントの例:</span><span class="sxs-lookup"><span data-stu-id="3da03-133">Example of policy tip seen by recipient:</span></span>

![受信者のポリシー ヒント](./media/communication-compliance-warning-3.png)