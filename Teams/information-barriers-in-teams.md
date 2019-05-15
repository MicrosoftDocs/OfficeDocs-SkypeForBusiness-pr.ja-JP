---
title: Microsoft Teams プレビューでの情報障壁
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/14/2019
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: vikramju
description: 情報障壁とチームにどのように影響について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5cf9891e44df3e656255da90dc495d8f0bda8c72
ms.sourcegitcommit: 9a99be1365df439f9443f31240aa5311782458df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "33993922"
---
# <a name="information-barriers-in-microsoft-teams-preview"></a><span data-ttu-id="677a5-103">Microsoft Teams プレビューでの情報障壁</span><span class="sxs-lookup"><span data-stu-id="677a5-103">Information barriers in Microsoft Teams preview</span></span>

> [!INCLUDE [Preview feature](includes/preview-feature.md)]

<span data-ttu-id="677a5-104">情報障壁は、個人またはグループが相互に通信することを防ぐために管理者が構成可能なポリシーです。</span><span class="sxs-lookup"><span data-stu-id="677a5-104">Information barriers are policies that an admin can configure to prevent individuals or groups from communicating with each other.</span></span> <span data-ttu-id="677a5-105">これは、機能は、たとえば、1 つの部門が他の部門と共有するべきではない情報を処理またはグループは、外部の連絡先と通信するを防ぐ必要がある場合に、便利です。</span><span class="sxs-lookup"><span data-stu-id="677a5-105">This is useful if, for example, one department is handling information that shouldn’t be shared with other departments or a group needs to be prevented from communicating with any outside contacts.</span></span>

> [!NOTE]
> - <span data-ttu-id="677a5-106">テナント間での情報障壁のグループを作成できません。</span><span class="sxs-lookup"><span data-stu-id="677a5-106">Information barrier groups cannot be created across tenants.</span></span>
> - <span data-ttu-id="677a5-107">Bot を使用してユーザーを追加するのには、バージョン 1 ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="677a5-107">Using bots to add users is not supported in version 1.</span></span>
> - <span data-ttu-id="677a5-108">情報障壁のバージョン 1 には、SharePoint とビジネスの OneDrive のサポートが含まれていません。</span><span class="sxs-lookup"><span data-stu-id="677a5-108">Information barriers version 1 doesn't include support for SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="677a5-109">SharePoint の機能を有効にすることで作業しているし、通信に使用可能になるとします。</span><span class="sxs-lookup"><span data-stu-id="677a5-109">We are working on enabling the feature in SharePoint and will communicate once it's available.</span></span>

<span data-ttu-id="677a5-110">情報障壁のポリシーは、検索および検出にも禁止します。</span><span class="sxs-lookup"><span data-stu-id="677a5-110">Information barrier policies also prevent lookups and discovery.</span></span> <span data-ttu-id="677a5-111">このする必要があると通信していないユーザーと通信しようとする場合するが見つけることをそのユーザー ユーザー選択ウィンドウにします。</span><span class="sxs-lookup"><span data-stu-id="677a5-111">This means that if you attempt to communicate with someone you should not be communicating with, you will not find that user in the people picker.</span></span>

## <a name="background"></a><span data-ttu-id="677a5-112">背景</span><span class="sxs-lookup"><span data-stu-id="677a5-112">Background</span></span>

<span data-ttu-id="677a5-113">情報障壁の主な要因は、金融サービス業界から取得されます。</span><span class="sxs-lookup"><span data-stu-id="677a5-113">The primary driver for Information Barriers comes from the financial services industry.</span></span> <span data-ttu-id="677a5-114">金融業界規制機関 ([FINRA]( http://www.finra.org/)) は、情報関連の障壁とメンバー企業内での利害の対立を確認し、(FINRA 2241、[借入金の研究規制通知 15-31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)は、このような競合を管理する方法に関するガイダンスを提供</span><span class="sxs-lookup"><span data-stu-id="677a5-114">The Financial Industry Regulatory Authority ([FINRA]( http://www.finra.org/)) reviews information barriers and conflicts of interest within member firms and provides guidance as to how to manage such conflicts (FINRA 2241, [Debt Research Regulatory Notice 15-31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).</span></span>  

## <a name="when-should-i-use-information-barriers"></a><span data-ttu-id="677a5-115">情報障壁を使用するか。</span><span class="sxs-lookup"><span data-stu-id="677a5-115">When should I use information barriers?</span></span>

<span data-ttu-id="677a5-116">このような状況での情報障壁を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="677a5-116">You might want to use information barriers in situations like these:</span></span>

- <span data-ttu-id="677a5-117">チームできないようにするとの通信や、特定のデータを共有する他のチームです。</span><span class="sxs-lookup"><span data-stu-id="677a5-117">A team must be prevented from communicating or sharing data with a specific other team.</span></span>
- <span data-ttu-id="677a5-118">チームは、通信またはチーム以外のすべてのユーザーとデータを共有する必要がありますできません。</span><span class="sxs-lookup"><span data-stu-id="677a5-118">A team must not communicate or share data with anyone outside of the team.</span></span>

<span data-ttu-id="677a5-119">情報障壁のポリシー評価サービスは、通信がバリアの情報ポリシーに準拠しているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="677a5-119">The Information Barrier Policy Evaluation Service determines whether a communication complies with information barrier policies.</span></span> 

## <a name="managing-information-barrier-policies"></a><span data-ttu-id="677a5-120">情報障壁のポリシーを管理します。</span><span class="sxs-lookup"><span data-stu-id="677a5-120">Managing information barrier policies</span></span>

<span data-ttu-id="677a5-121">情報障壁のポリシーは、セキュリティ & コンプライアンス センター (SCC) の PowerShell コマンドレットで管理されます。</span><span class="sxs-lookup"><span data-stu-id="677a5-121">Information barrier policies are managed with Security & Compliance Center (SCC) PowerShell cmdlets.</span></span> <span data-ttu-id="677a5-122">詳細については[ここでサインアップして](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR1UzUQTEgHVPtD9W5uih2OlUMEwwUzhJSktIMUw2SDJJOE5FT1lTVzVTSS4u)、これらのコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="677a5-122">For more information about using these cmdlets, [sign up here](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR1UzUQTEgHVPtD9W5uih2OlUMEwwUzhJSktIMUw2SDJJOE5FT1lTVzVTSS4u).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="677a5-123">前に、を設定または、**マイクロソフトのチームでのスコープ指定されたディレクトリ検索を有効にする必要があります**、ポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="677a5-123">Before you set up or define policies, **you must enable scoped directory search in Microsoft Teams**.</span></span> <span data-ttu-id="677a5-124">設定または情報の障壁のポリシーを定義する前に、スコープ指定されたディレクトリの検索を有効にした後は、少なくとも 24 時間を待機します。</span><span class="sxs-lookup"><span data-stu-id="677a5-124">Wait at least 24 hours after enabling scoped directory search before you set up or define policies for information barriers.</span></span>

## <a name="information-barriers-administrator-role"></a><span data-ttu-id="677a5-125">情報障壁の管理者の役割</span><span class="sxs-lookup"><span data-stu-id="677a5-125">Information barriers administrator role</span></span>

<span data-ttu-id="677a5-126">情報障壁の管理者の役割は、バリアの情報ポリシーの管理を担当します。</span><span class="sxs-lookup"><span data-stu-id="677a5-126">The information barriers administrator role is responsible for managing information barrier policies.</span></span> <span data-ttu-id="677a5-127">このロールについて、[ここでサインアップして](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR1UzUQTEgHVPtD9W5uih2OlUMEwwUzhJSktIMUw2SDJJOE5FT1lTVzVTSS4u)、プレビューに参加する詳細については。</span><span class="sxs-lookup"><span data-stu-id="677a5-127">For more information about this role and to participate in the preview, [sign up here](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR1UzUQTEgHVPtD9W5uih2OlUMEwwUzhJSktIMUw2SDJJOE5FT1lTVzVTSS4u).</span></span>

## <a name="when-are-information-barrier-policies-checked"></a><span data-ttu-id="677a5-128">情報障壁のポリシーは、チェックされています。</span><span class="sxs-lookup"><span data-stu-id="677a5-128">When are information barrier policies checked?</span></span>

<span data-ttu-id="677a5-129">チームの次のイベントが発生すると、情報のバリアのポリシーが確認されます。</span><span class="sxs-lookup"><span data-stu-id="677a5-129">Information barrier policies are checked when the following Teams events take place:</span></span>

- <span data-ttu-id="677a5-130">**メンバーがチームに追加**のチームが、ユーザーのポリシーにユーザーを追加するときに、他のチーム メンバーの情報障壁のポリシーに対して評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="677a5-130">**Members are added to a team** - Whenever you add a user to a team, the user’s policy must be evaluated against the information barrier policies of other team members.</span></span> <span data-ttu-id="677a5-131">ユーザーが正常に追加されると、ユーザーはチーム追加の確認なしですべての機能を実行できます。</span><span class="sxs-lookup"><span data-stu-id="677a5-131">After the user is successfully added, the user can perform all functions in the team without further checks.</span></span> <span data-ttu-id="677a5-132">ユーザーのポリシーでは、チームに追加されるからそれらをブロックする場合、ユーザーは検索にない表示します。</span><span class="sxs-lookup"><span data-stu-id="677a5-132">If the user's policy blocks them from being added to the team, the user will not show up in search.</span></span>
- <span data-ttu-id="677a5-133">**新しいチャットが要求された**- 新しいチャットが要求されるたびに 2 つまたは複数のユーザー間での情報障壁のポリシーに違反していないことを確認するのには、チャットが評価されます。</span><span class="sxs-lookup"><span data-stu-id="677a5-133">**A new chat is requested** - Each time a new chat is requested between two or more users, the chat is evaluated to make sure that it isn’t violating any Information barrier policies.</span></span> <span data-ttu-id="677a5-134">会話は、情報のバリア ポリシーに違反する場合、会話はありませんが開始され、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="677a5-134">If the conversation violates an information barrier policy, then the conversation isn’t initiated, and an error message appears.</span></span>
- <span data-ttu-id="677a5-135">**ユーザーがミーティングへの参加に招待された**のと、ユーザーがミーティングへの参加に招待された、ユーザーのポリシーが、他のチーム メンバーのポリシーに対して評価し、違反がある場合は、ユーザーがミーティングに参加するのには許可されません、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="677a5-135">**A user is invited to join a meeting** - When a user is invited to join a meeting, the user's policy is evaluated against the policies of other team members, and if there’s a violation, the user will not be allowed to join the meeting and will see an error message.</span></span>
- <span data-ttu-id="677a5-136">**画面が 2 つまたは複数のユーザー間で共有**の画面をいつでもが 2 つまたは複数のユーザー間で共有、他のユーザーの情報障壁のポリシーに違反していないことを確認する画面の共有を評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="677a5-136">**A screen is shared between two or more users** - Any time a screen is shared between two or more users, the screen share must be evaluated to make sure that it doesn’t violate the information barrier policies of other users.</span></span> <span data-ttu-id="677a5-137">情報バリア ポリシーに違反した場合、は、画面共有を許可しない、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="677a5-137">If an information barrier policy is violated, the screen share won’t be allowed, and an error message will appear.</span></span>
- <span data-ttu-id="677a5-138">**チームにユーザーが電話をかける (VOIP) を置く**- oher のチーム メンバーの情報障壁のポリシーに違反していないことを確認するのにはユーザーが別のユーザーまたはユーザー グループ、電話で音声通話が開始されたすべての時間が評価されます。</span><span class="sxs-lookup"><span data-stu-id="677a5-138">**A user places a phone call (VOIP) in Teams** - Any time a voice call is initiated by a user to another user or group of users, the call is evaluated to make sure that it doesn’t violate the information barrier policies of oher team members.</span></span> <span data-ttu-id="677a5-139">違反がある場合は、音声通話がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="677a5-139">If there is any violation, the voice call is blocked.</span></span>

## <a name="what-happens-to-existing-chat-threads-when-a-policy-is-changed"></a><span data-ttu-id="677a5-140">ポリシーが変更されたときの既存のチャットのスレッドを動作でしょうか。</span><span class="sxs-lookup"><span data-stu-id="677a5-140">What happens to existing chat threads when a policy is changed?</span></span>

<span data-ttu-id="677a5-141">情報障壁のポリシー管理者は、ポリシーに変更を加えるか、ポリシーの変更開始効果に変更するユーザーのジョブまたは同様の理由であり、情報のバリアのポリシー評価サービスにより自動的にあることを確認するのにはメンバーを検索します。チームのメンバーは、すべてのポリシーを違反していません。</span><span class="sxs-lookup"><span data-stu-id="677a5-141">When the information  barrier policy admin makes changes to the policy or a policy change kicks into effect because of a user’s job changing or a similar reason, the Information Barrier Policy Evaluation Service automatically searches the members to ensure that members of the Team are not violating any policies.</span></span> 

<span data-ttu-id="677a5-142">既存のチャットや、ユーザー間の通信と新しいポリシーが設定されて、既存のポリシーが変更された場合、サービスはことそれらは「ウイルスに感染して」(使用できなくなった) ことを確認するのには既存の通信を評価します。</span><span class="sxs-lookup"><span data-stu-id="677a5-142">If there is an existing chat or other communication between users, and a new policy is set or an existing policy is changed, the service evaluates existing communications to make sure that they aren’t “poisoned” (no longer allowed):</span></span> 

- <span data-ttu-id="677a5-143">**1:1 チャット**- (1 つまたは両方のユーザーの通信をブロックするポリシーが適用される) 場合、2 つのユーザー間の通信が許可されていません、さらに通信がブロックされているし、会話は読み取り専用になります。</span><span class="sxs-lookup"><span data-stu-id="677a5-143">**1:1 chat** - If communication between the two users is no longer allowed (if a policy blocking communication is applied to one or both users), further communication is blocked and the chat conversation will become read-only.</span></span>
- <span data-ttu-id="677a5-144">**グループ チャット**- グループ チャットからは、ポリシーに違反する他のユーザーとユーザーを削除する場合があります、グループとの通信を続けることはできません (たとえば、ユーザーには、ジョブが変更された) 場合に、グループに 1 人のユーザーからの通信が使用できなくなった場合許可します。</span><span class="sxs-lookup"><span data-stu-id="677a5-144">**Group chat** - If communication from one user to the group is no longer allowed (for example, if a user changes jobs), the user along with the other users who violate the policy may be removed from group chat and further communication with the group will not be allowed.</span></span> <span data-ttu-id="677a5-145">ユーザーがまだ古い会話 (読み取り専用になります) を参照してくださいことができますが参照するか、グループに新しい会話に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="677a5-145">The user can still see old conversations (which will be read-only), but will not be able to see or participate in any new conversations with the group.</span></span> <span data-ttu-id="677a5-146">通信を防止する新規または変更されたポリシーは、複数のユーザーに適用されている場合は、ポリシーによって影響を受けるユーザーがグループ チャットから削除可能性があります。</span><span class="sxs-lookup"><span data-stu-id="677a5-146">If the new or changed policy preventing communication is applied to more than one user, the users who are affected by the policy may be removed from group chat.</span></span> <span data-ttu-id="677a5-147">古い会話も確認できます。</span><span class="sxs-lookup"><span data-stu-id="677a5-147">They can still see old conversations.</span></span> 
- <span data-ttu-id="677a5-148">**チーム**・ グループから削除されているすべてのユーザーは、チームから削除され、参照するか、既存または新規の会話に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="677a5-148">**Team** - Any users who have been removed from the group are removed from the team and will not be able to see or participate in existing or new conversations.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="677a5-149">必要なライセンスと権限</span><span class="sxs-lookup"><span data-stu-id="677a5-149">Required licenses and permissions</span></span>

<span data-ttu-id="677a5-150">現在、情報バリア機能は、パブリック プレビューでは。</span><span class="sxs-lookup"><span data-stu-id="677a5-150">Currently, the information barrier features are in public preview.</span></span> <span data-ttu-id="677a5-151">これらの機能が一般に利用可能なときは、それらがするサブスクリプションに含まれる、次のように。</span><span class="sxs-lookup"><span data-stu-id="677a5-151">When these features are generally available, they'll be included in subscriptions, such as:</span></span>

- <span data-ttu-id="677a5-152">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="677a5-152">Microsoft 365 E5</span></span>
- <span data-ttu-id="677a5-153">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="677a5-153">Office 365 E5</span></span>
- <span data-ttu-id="677a5-154">Office 365 コンプライアンスの詳細</span><span class="sxs-lookup"><span data-stu-id="677a5-154">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="677a5-155">Microsoft 365 E5 のコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="677a5-155">Microsoft 365 E5 Compliance</span></span>

<span data-ttu-id="677a5-156">詳細については、プランを含め、価格設定、[コンプライアンス ・ ソリューション](https://products.office.com/business/security-and-compliance/compliance-solutions?rtc=1)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="677a5-156">For more details, including plans and pricing, see [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions?rtc=1).</span></span>
