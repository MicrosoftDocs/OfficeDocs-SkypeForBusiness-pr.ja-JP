---
title: Microsoft Teams への通信のコンプライアンス
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: コミュニケーションのコンプライアンスについては、「Microsoft Teams の観点からの insider リスクソリューションセットの一部 (M365 通信のコンプライアンス機能の一部)」をご覧ください。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bb9400778b8e000a438343e74bc6b030087ff297
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328256"
---
# <a name="communication-compliance-with-microsoft-teams"></a><span data-ttu-id="86f6b-103">Microsoft Teams への通信のコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="86f6b-103">Communication compliance with Microsoft Teams</span></span>

<span data-ttu-id="86f6b-104">通信のコンプライアンスは、Microsoft 365 の insider のリスクソリューションであり、組織内の不適切なメッセージの検出、キャプチャ、および操作を支援することで、コミュニケーションのリスクを最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="86f6b-104">Communication compliance is an insider risk solution in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and act on inappropriate messages in your organization.</span></span>

<span data-ttu-id="86f6b-105">Microsoft Teams では、コミュニケーションのコンプライアンスは、チームチャネルまたは1:1 およびグループチャットで [次の種類](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) の不適切なコンテンツを特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="86f6b-105">For Microsoft Teams, communication compliance helps identify the [following types](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) of inappropriate content in Teams channels or in 1:1 and group chats:</span></span>

- <span data-ttu-id="86f6b-106">不快感を持つ、欠い、嫌がらせの言葉</span><span class="sxs-lookup"><span data-stu-id="86f6b-106">Offensive, profane, and harassing language</span></span>
- <span data-ttu-id="86f6b-107">アダルト、racy、gory の画像</span><span class="sxs-lookup"><span data-stu-id="86f6b-107">Adult, racy, and gory images</span></span>
- <span data-ttu-id="86f6b-108">機密情報の共有</span><span class="sxs-lookup"><span data-stu-id="86f6b-108">Sharing of sensitive information</span></span>

<span data-ttu-id="86f6b-109">通信のコンプライアンスと組織のポリシーの構成方法の詳細については、「 [Microsoft 365 での通信のコンプライアンス](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86f6b-109">For more information on communication compliance and how to configure policies for your organization, see [Communication compliance in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span></span>

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a><span data-ttu-id="86f6b-110">Microsoft Teams で通信のコンプライアンスを使用する方法</span><span class="sxs-lookup"><span data-stu-id="86f6b-110">How to use communication compliance in Microsoft Teams</span></span>

<span data-ttu-id="86f6b-111">コミュニケーションのコンプライアンスと Microsoft Teams は密接に統合されており、組織の通信リスクを最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="86f6b-111">Communication compliance and Microsoft Teams are tightly integrated and can help minimize communication risks in your organization.</span></span> <span data-ttu-id="86f6b-112">最初の通信のコンプライアンスポリシーを構成した後は、不適切な Microsoft Teams のメッセージやコンテンツが自動的に通知に表示されるように管理できます。</span><span class="sxs-lookup"><span data-stu-id="86f6b-112">After you've configured your first communication compliance policies, you can actively manage inappropriate Microsoft Teams messages and content that is automatically flagged in alerts.</span></span>

### <a name="getting-started"></a><span data-ttu-id="86f6b-113">はじめに</span><span class="sxs-lookup"><span data-stu-id="86f6b-113">Getting started</span></span>

<span data-ttu-id="86f6b-114">Microsoft Teams での通信の概要については、「チームチャネルまたは1:1 およびグループで不適切なユーザーのアクティビティを特定するための事前定義済みまたはカスタムポリシーの [計画](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) と作成」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="86f6b-114">Getting started with communication compliance in Microsoft Teams begins with [planning](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) and creating pre-defined or custom policies to identify inappropriate user activities in Teams channels or in 1:1 and groups.</span></span> <span data-ttu-id="86f6b-115">構成プロセスの一部として、一部の権限と基本的な前提条件を [構成](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="86f6b-115">Keep in mind that you'll need to [configure](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) some permissions and basic prerequisites as part of the configuration process.</span></span>

<span data-ttu-id="86f6b-116">チーム管理者は、次のレベルで通信コンプライアンスポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="86f6b-116">Teams administrators can configure communication compliance policies at the following levels:</span></span>

- <span data-ttu-id="86f6b-117">**ユーザーレベル**: このレベルのポリシーは、個々の teams ユーザーに適用されるか、組織内のすべての teams ユーザーに適用される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="86f6b-117">**User level**: Policies at this level apply to an individual Teams user or may be applied to all Teams users in your organization.</span></span> <span data-ttu-id="86f6b-118">これらのポリシーでは、これらのユーザが1:1 またはグループチャットで送信する可能性のあるメッセージを対象としています。</span><span class="sxs-lookup"><span data-stu-id="86f6b-118">These policies cover messages that these users may send in 1:1 or group chats.</span></span> <span data-ttu-id="86f6b-119">ユーザーのチャットは、ユーザーがメンバーになっているすべての Microsoft Teams で自動的に監視されます。</span><span class="sxs-lookup"><span data-stu-id="86f6b-119">Chat communications for the users are automatically monitored across all Microsoft Teams where the users are a member.</span></span>
- <span data-ttu-id="86f6b-120">**チームレベル**: このレベルのポリシーは、Microsoft チームチャネルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="86f6b-120">**Teams level**: Policies at this level apply to a Microsoft Team channel.</span></span> <span data-ttu-id="86f6b-121">これらのポリシーには、Teams チャネルでのみ送信されたメッセージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="86f6b-121">These policies cover messages sent in the Teams channel only.</span></span>

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a><span data-ttu-id="86f6b-122">Microsoft Teams で不適切なメッセージに対処する</span><span class="sxs-lookup"><span data-stu-id="86f6b-122">Act on inappropriate messages in Microsoft Teams</span></span>

<span data-ttu-id="86f6b-123">ポリシーを構成して、Microsoft Teams メッセージの通信のコンプライアンス警告を受信した後は、組織のコンプライアンスレビュー担当者がこれらのメッセージに対処する時間です。</span><span class="sxs-lookup"><span data-stu-id="86f6b-123">After you have configured your policies and have received communication compliance alerts for Microsoft Teams messages, it's time for compliance reviewers in your organization to take action on these messages.</span></span> <span data-ttu-id="86f6b-124">レビュー担当者は、通信コンプライアンスの警告を確認し、Microsoft Teams のビューからフラグ付きのメッセージを削除することで、組織を保護することができます。</span><span class="sxs-lookup"><span data-stu-id="86f6b-124">Reviewers can help safeguard your organization by reviewing communication compliance alerts and removing flagged messages from view in Microsoft Teams.</span></span>

![Teams でメッセージを削除する](./media/communication-compliance-remove-teams-message.png)

<span data-ttu-id="86f6b-126">削除されたメッセージとコンテンツは、メッセージまたはコンテンツが削除されたこと、および削除に適用できるポリシーを説明する通知に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="86f6b-126">Removed messages and content are replaced with notifications for viewers explaining that the message or content has been removed and what policy is applicable to the removal.</span></span> <span data-ttu-id="86f6b-127">削除されたメッセージまたはコンテンツの送信者は、削除の状態についても通知され、削除に関連するコンテキストについて元のメッセージコンテンツが提供されます。</span><span class="sxs-lookup"><span data-stu-id="86f6b-127">The sender of the removed message or content is also notified of the removal status and provided with original message content for context relating to its removal.</span></span> <span data-ttu-id="86f6b-128">また、送信者は、メッセージの削除に適用される特定のポリシー条件を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="86f6b-128">The sender can also view the specific policy condition that applies to the message removal.</span></span>

<span data-ttu-id="86f6b-129">送信者に表示されるポリシーヒントの例:</span><span class="sxs-lookup"><span data-stu-id="86f6b-129">Example of policy tip seen by sender:</span></span>

![送信者のポリシーヒント](./media/communication-compliance-warning-1.png)

<span data-ttu-id="86f6b-131">送信者に表示されるポリシー条件通知の例:</span><span class="sxs-lookup"><span data-stu-id="86f6b-131">Example of policy condition notification seen by the sender:</span></span>

![送信者のポリシー条件情報](./media/communication-compliance-warning-2.png)

<span data-ttu-id="86f6b-133">受信者に表示されるポリシーヒントの例:</span><span class="sxs-lookup"><span data-stu-id="86f6b-133">Example of policy tip seen by recipient:</span></span>

![受信者のポリシーヒント](./media/communication-compliance-warning-3.png)
