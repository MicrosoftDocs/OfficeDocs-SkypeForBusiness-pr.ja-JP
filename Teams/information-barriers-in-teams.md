---
title: Microsoft Teams の情報障壁
author: chrfox
ms.author: chrfox
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: vikramju
f1.keywords:
- NOCSH
description: この記事では、Microsoft Teams の情報障壁の概要と、チームへの影響について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c545b6289cd1a40fdf9ca967ebd44cd2d781605d
ms.sourcegitcommit: 950c04ce49064209ee04880e7c7473a4f931df50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2020
ms.locfileid: "48996018"
---
# <a name="information-barriers-in-microsoft-teams"></a><span data-ttu-id="bf364-103">Microsoft Teams の情報障壁</span><span class="sxs-lookup"><span data-stu-id="bf364-103">Information barriers in Microsoft Teams</span></span>

<span data-ttu-id="bf364-104">情報障壁 (IB) は、管理者が互いに連絡することを防止するために構成できるポリシーです。</span><span class="sxs-lookup"><span data-stu-id="bf364-104">Information barriers (IB) are policies that an admin can configure to prevent individuals or groups from communicating with each other.</span></span> <span data-ttu-id="bf364-105">IB は、たとえば、ある部門が他の部署と共有する必要のない情報を処理している場合や、グループ外の人との通信を禁止または分離する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="bf364-105">IB is useful if, for example, one department is handling information that shouldn't be shared with other departments or a group needs to be prevented, or isolated, from communicating with anyone outside of that group.</span></span>

> [!NOTE]
> - <span data-ttu-id="bf364-106">情報バリアグループはテナント全体で作成できません。</span><span class="sxs-lookup"><span data-stu-id="bf364-106">Information barrier groups cannot be created across tenants.</span></span>
> - <span data-ttu-id="bf364-107">ボット、AAD アプリ、および一部の Api を使用したユーザーの追加は、バージョン1ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bf364-107">Using bots, AAD apps, and some APIs to add users is not supported in version 1.</span></span>
> - <span data-ttu-id="bf364-108">プライベートチャネルは、構成する情報バリアーポリシーに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="bf364-108">Private channels are compliant to information barrier policies that you configure.</span></span>
> - <span data-ttu-id="bf364-109">新規: Teams に接続された SharePoint サイトの障壁のサポートについて [は、ここ](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)をクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="bf364-109">New: For Information about barriers support for SharePoint site connected to Teams, click [here](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites).</span></span>

<span data-ttu-id="bf364-110">情報バリアポリシーによって、検索と検出を防ぐこともできます。</span><span class="sxs-lookup"><span data-stu-id="bf364-110">Information barrier policies also prevent lookups and discovery.</span></span> <span data-ttu-id="bf364-111">通信しようとしていない相手と通信しようとしても、そのユーザーは [連絡先] 選択画面に表示されません。</span><span class="sxs-lookup"><span data-stu-id="bf364-111">If you attempt to communicate with someone you shouldn't be communicating with, you won't find that user in the people picker.</span></span>

## <a name="background"></a><span data-ttu-id="bf364-112">背景</span><span class="sxs-lookup"><span data-stu-id="bf364-112">Background</span></span>

<span data-ttu-id="bf364-113">情報障壁の主要なドライバーは、金融サービス業界から提供されています。</span><span class="sxs-lookup"><span data-stu-id="bf364-113">The primary driver for information barriers comes from the financial services industry.</span></span> <span data-ttu-id="bf364-114">金融業界規制機関 ([finra]( http://www.finra.org)) は、メンバー企業内での重要な情報の障壁と競合を確認し、そのような競合を管理する方法についてのガイダンスを提供します (finra 2241、 [負債調査法通知 15-31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)。</span><span class="sxs-lookup"><span data-stu-id="bf364-114">The Financial Industry Regulatory Authority ([FINRA]( http://www.finra.org)) reviews information barriers and conflicts of interest within member firms and provides guidance as to how to manage such conflicts (FINRA 2241, [Debt Research Regulatory Notice 15-31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).</span></span>  

<span data-ttu-id="bf364-115">ただし、情報の壁を取り入れるために、他の多くの領域で役に立つものが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="bf364-115">However, since introducing information barriers, many other areas have found them to be useful.</span></span> <span data-ttu-id="bf364-116">その他の一般的なシナリオを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="bf364-116">Other common scenarios include:</span></span>

- <span data-ttu-id="bf364-117">教育: ある学校の学生は、他の学校の学生の連絡先情報を検索することはできません。</span><span class="sxs-lookup"><span data-stu-id="bf364-117">Education: Students in one school aren't able to look up contact details for students of other schools.</span></span>
- <span data-ttu-id="bf364-118">法的: 1 つのクライアントによって得られたデータの機密性を、異なる顧客を表す同じ企業の弁護士によってアクセスされないようにします。</span><span class="sxs-lookup"><span data-stu-id="bf364-118">Legal: Maintaining confidentiality of data obtained by the lawyer of one client from being accessed by a lawyer for the same firm representing a different client.</span></span>
- <span data-ttu-id="bf364-119">行政: 情報のアクセスと制御は、部門とグループで制限されています。</span><span class="sxs-lookup"><span data-stu-id="bf364-119">Government: Information access and control are limited across departments and groups.</span></span>
- <span data-ttu-id="bf364-120">プロフェッショナルサービス: 社内の複数のユーザーが、顧客契約中にゲストアクセスでクライアントまたは特定の顧客とチャットすることができます。</span><span class="sxs-lookup"><span data-stu-id="bf364-120">Professional services: A group of people in a company is only able to chat with a client or specific customer via guest access during a customer engagement.</span></span>

<span data-ttu-id="bf364-121">たとえば、"プエルトリコ" は銀行口座に属し、Pradeep は財務アドバイザーセグメントに属します。</span><span class="sxs-lookup"><span data-stu-id="bf364-121">For example, Enrico belongs to the Banking segment and Pradeep belongs to the Financial advisor segment.</span></span> <span data-ttu-id="bf364-122">この2つのセグメント間の通信とコラボレーションは、組織の IB ポリシーによってブロックされるため、Pradeep とお互いの通信はできません。</span><span class="sxs-lookup"><span data-stu-id="bf364-122">Enrico and Pradeep can't communicate with each other because the organization's IB policy blocks communication and collaboration between these two segments.</span></span> <span data-ttu-id="bf364-123">ただし、Pradeep は、秀樹との通信を人事で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bf364-123">However, Enrico and Pradeep can communicate with Lee in HR.</span></span>

![セグメント間の通信を防止するための情報障壁を示す例](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a><span data-ttu-id="bf364-125">情報バリアを使用する状況</span><span class="sxs-lookup"><span data-stu-id="bf364-125">When to use information barriers</span></span>

<span data-ttu-id="bf364-126">次のような状況では、情報バリアを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="bf364-126">You might want to use information barriers in situations like these:</span></span>

- <span data-ttu-id="bf364-127">チームは、特定の他のチームとデータのやり取りや共有を行うことができないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf364-127">A team must be prevented from communicating or sharing data with a specific other team.</span></span>
- <span data-ttu-id="bf364-128">チームは、チームの外部の人とデータをやり取りしたり、共有したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="bf364-128">A team must not communicate or share data with anyone outside of the team.</span></span>

<span data-ttu-id="bf364-129">情報バリアポリシー評価サービスは、通信が情報バリアポリシーに準拠しているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="bf364-129">The Information Barrier Policy Evaluation Service determines whether a communication complies with information barrier policies.</span></span>

## <a name="managing-information-barrier-policies"></a><span data-ttu-id="bf364-130">情報バリアポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="bf364-130">Managing information barrier policies</span></span>

<span data-ttu-id="bf364-131">情報バリアポリシーは、PowerShell コマンドレットを使用して Microsoft 365 コンプライアンスセンター (SCC) で管理されます。</span><span class="sxs-lookup"><span data-stu-id="bf364-131">Information barrier policies are managed in the Microsoft 365 Compliance Center (SCC) using PowerShell cmdlets.</span></span> <span data-ttu-id="bf364-132">詳細については、「 [情報バリアのポリシーを定義](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf364-132">For more information, see [Define policies for information barriers](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bf364-133">ポリシーを設定または定義する前に、 **Microsoft Teams でスコープ指定されたディレクトリ検索を有効にする必要があり** ます。</span><span class="sxs-lookup"><span data-stu-id="bf364-133">Before you set up or define policies, **you must enable scoped directory search in Microsoft Teams**.</span></span> <span data-ttu-id="bf364-134">スコープ指定されたディレクトリ検索を有効にしてから、情報バリアのポリシーを設定または定義する前に、少なくとも数時間待ってください。</span><span class="sxs-lookup"><span data-stu-id="bf364-134">Wait at least a few hours after enabling scoped directory search before you set up or define policies for information barriers.</span></span> <span data-ttu-id="bf364-135">詳細に[ついては、「情報の障壁の前提条件」を参照して](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites)ください。</span><span class="sxs-lookup"><span data-stu-id="bf364-135">[Learn more about prerequisites for information barriers](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites).</span></span>

## <a name="information-barriers-administrator-role"></a><span data-ttu-id="bf364-136">情報障壁管理者の役割</span><span class="sxs-lookup"><span data-stu-id="bf364-136">Information barriers administrator role</span></span>

<span data-ttu-id="bf364-137">IB コンプライアンス管理の役割は、情報バリアポリシーの管理を担当します。</span><span class="sxs-lookup"><span data-stu-id="bf364-137">The IB Compliance Management role is responsible for managing information barrier policies.</span></span> <span data-ttu-id="bf364-138">この役割の詳細については、「 [Microsoft 365 コンプライアンスセンターの権限](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf364-138">For more information about this role, see [Permissions in the Microsoft 365 Compliance Center](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center).</span></span>

## <a name="information-barrier-triggers"></a><span data-ttu-id="bf364-139">情報バリアトリガー</span><span class="sxs-lookup"><span data-stu-id="bf364-139">Information barrier triggers</span></span>

<span data-ttu-id="bf364-140">以下の Teams イベントが発生すると、情報バリアポリシーが有効になります。</span><span class="sxs-lookup"><span data-stu-id="bf364-140">Information barrier policies are activated when the following Teams events take place:</span></span>

- <span data-ttu-id="bf364-141">**メンバーがチームに追加される** -ユーザーをチームに追加するときは、他のチームメンバーの情報バリアポリシーに対してユーザーのポリシーを評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf364-141">**Members are added to a team** - Whenever you add a user to a team, the user's policy must be evaluated against the information barrier policies of other team members.</span></span> <span data-ttu-id="bf364-142">ユーザーが正常に追加されると、ユーザーはさらにチェックを行わなくても、チーム内のすべての機能を実行できます。</span><span class="sxs-lookup"><span data-stu-id="bf364-142">After the user is successfully added, the user can perform all functions in the team without further checks.</span></span> <span data-ttu-id="bf364-143">ユーザーのポリシーによってチームに追加されないようにブロックされている場合、ユーザーは検索に表示されません。</span><span class="sxs-lookup"><span data-stu-id="bf364-143">If the user's policy blocks them from being added to the team, the user will not show up in search.</span></span>

    ![グループチャットを示すスクリーンショット](media/information-barriers-add-members.png)

- <span data-ttu-id="bf364-145">**新しいチャットが要求** されました-2 人以上のユーザ間で新しいチャットがリクエストされるたびに、チャットが評価され、情報バリアポリシーに違反していないことが確認されます。</span><span class="sxs-lookup"><span data-stu-id="bf364-145">**A new chat is requested** - Each time a new chat is requested between two or more users, the chat is evaluated to make sure that it isn't violating any information barrier policies.</span></span> <span data-ttu-id="bf364-146">会話が情報バリアポリシーに違反した場合、その会話は開始されません。</span><span class="sxs-lookup"><span data-stu-id="bf364-146">If the conversation violates an information barrier policy, then the conversation isn't initiated.</span></span>

    <span data-ttu-id="bf364-147">1:1 チャットの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bf364-147">Here's an example of a 1:1 chat.</span></span>

     ![1:1 チャットでのブロックされた通信を示すスクリーンショット](media/information-barriers-one-one-chat.png)

    <span data-ttu-id="bf364-149">グループチャットの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bf364-149">Here's an example of a group chat.</span></span>

    ![グループチャットを示すスクリーンショット](media/information-barriers-group-chat.png)

- <span data-ttu-id="bf364-151">**ユーザーが会議に参加するように招待され** ました-ユーザーが会議に参加するよう招待されたときに、ユーザーのポリシーが他のチームメンバーのポリシーに対して評価され、違反がある場合は、ユーザーが会議に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="bf364-151">**A user is invited to join a meeting** - When a user is invited to join a meeting, the user's policy is evaluated against the policies of other team members, and if there's a violation, the user will not be allowed to join the meeting.</span></span>

    ![会議からブロックされたユーザーを示すスクリーンショット](media/information-barriers-meeting.png)

- <span data-ttu-id="bf364-153">画面は2人以上の **ユーザー間で共有さ** れる-画面を2人以上のユーザーで共有している場合は、画面共有を評価して、他のユーザーの情報バリアポリシーに違反しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf364-153">**A screen is shared between two or more users** - When a screen is shared between two or more users, the screen share must be evaluated to make sure that it doesn't violate the information barrier policies of other users.</span></span> <span data-ttu-id="bf364-154">情報バリアのポリシーに違反した場合、画面の共有は許可されません。</span><span class="sxs-lookup"><span data-stu-id="bf364-154">If an information barrier policy is violated, the screen share won't be allowed.</span></span> 
 
    <span data-ttu-id="bf364-155">ポリシーが適用される前の画面共有の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bf364-155">Here's an example of screen share before the policy is applied.</span></span> 

    ![ユーザーチャットを示すスクリーンショット](media/ib-before-screen-share-policy.png)

    <span data-ttu-id="bf364-157">ポリシーが適用された後の画面共有の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bf364-157">Here's an example of screen share after the policy is applied.</span></span> <span data-ttu-id="bf364-158">画面共有と通話アイコンは表示されません。</span><span class="sxs-lookup"><span data-stu-id="bf364-158">The screen share and call icons aren't visible.</span></span>

    ![ユーザーの char とブロックされた設定を示すスクリーンショット](media/ib-after-screen-share-policy.png)

- <span data-ttu-id="bf364-160">**ユーザーがチームに電話による通話 (VOIP) を** 行う-音声通話が他のユーザーまたはユーザーのグループによって開始されたときは、他のチームメンバーの情報バリアポリシーに違反していないことを確認するために、通話が評価されます。</span><span class="sxs-lookup"><span data-stu-id="bf364-160">**A user places a phone call (VOIP) in Teams** - Any time a voice call is initiated by a user to another user or group of users, the call is evaluated to make sure that it doesn't violate the information barrier policies of other team members.</span></span> <span data-ttu-id="bf364-161">違反が発生した場合、音声通話はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="bf364-161">If there is any violation, the voice call is blocked.</span></span>
- <span data-ttu-id="bf364-162">**Teams のゲストユーザー** (情報バリアポリシー) は、teams のゲストユーザーにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="bf364-162">**Guest users in Teams** - Information barrier policies apply to guest users in Teams too.</span></span> <span data-ttu-id="bf364-163">組織のグローバルアドレス一覧でゲストユーザーを検出できるようにする必要がある場合は、「 [Microsoft 365 グループでゲストアクセスを管理](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf364-163">If guest users need to be discoverable in your organization's global address list, see [Manage guest access in Microsoft 365 Groups](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups).</span></span> <span data-ttu-id="bf364-164">ゲストユーザーが検出可能になったら、 [情報バリアポリシーを定義](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)できます。</span><span class="sxs-lookup"><span data-stu-id="bf364-164">Once guest users are discoverable, you can [define information barrier policies](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).</span></span>

## <a name="how-policy-changes-impact-existing-chats"></a><span data-ttu-id="bf364-165">ポリシーの変更による既存のチャットへの影響</span><span class="sxs-lookup"><span data-stu-id="bf364-165">How policy changes impact existing chats</span></span>

<span data-ttu-id="bf364-166">情報バリアポリシー管理者がポリシーに変更を加えた場合、またはユーザーのプロファイルが変更されたため (ジョブの変更や同様の理由で) ポリシーの変更が反映される場合、情報バリアポリシー評価サービスは、メンバーを自動的に検索して、チームのメンバーがポリシーに違反していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="bf364-166">When the information barrier policy administrator makes changes to a policy, or a policy change kicks into effect because of a change to a user's profile (such as for a job change or a similar reason), the Information Barrier Policy Evaluation Service automatically searches the members to ensure that members of the Team are not violating any policies.</span></span>

<span data-ttu-id="bf364-167">ユーザー間に既存のチャットやその他の通信が存在し、新しいポリシーが設定されている場合、または既存のポリシーが変更されている場合、サービスは既存の通信を評価して、通信が引き続き許可されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bf364-167">If there is an existing chat or other communication between users, and a new policy is set or an existing policy is changed, the service evaluates existing communications to make sure that the communications are still allowed to occur.</span></span> 

- <span data-ttu-id="bf364-168">**1:1 チャット** -2 人のユーザ間の通信が許可されなくなった場合 (ポリシーをブロックしている場合に、一方または両方のユーザーに対して通信がブロックされている場合)、チャットスレッドは読み取り専用になります。</span><span class="sxs-lookup"><span data-stu-id="bf364-168">**1:1 chat** - If communication between the two users is no longer allowed (if a policy blocking communication is applied to one or both users), further communication is blocked and the chat conversation will become read-only.</span></span> 

    <span data-ttu-id="bf364-169">次の例は、チャットが表示されていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="bf364-169">Here's an example that shows the chat is visible.</span></span>

    ![ユーザーチャットが利用可能であることを示すスクリーンショット](media/ib-before-1-1chat-policy.png)

    <span data-ttu-id="bf364-171">次の例は、チャットが無効になっていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="bf364-171">Here's an example that shows the chat is disabled.</span></span>

    ![ユーザーチャットが無効になっていることを示すスクリーンショット](media/ib-after-1-1chat-policy.png)

- <span data-ttu-id="bf364-173">**グループチャット** -1 人のユーザーがグループに対して通信することが許可されなくなった場合 (たとえば、ユーザーがジョブを変更した場合など)、そのポリシーに違反した他のユーザーとの間でそのユーザーとの通信がグループチャットから削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bf364-173">**Group chat** - If communication from one user to the group is no longer allowed (for example, if a user changes jobs), the user along with the other users who violate the policy may be removed from group chat and further communication with the group will not be allowed.</span></span> <span data-ttu-id="bf364-174">ユーザーには、以前の会話 (読み取り専用) は引き続き表示されますが、グループとの新しい会話を表示したり、参加したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="bf364-174">The user can still see old conversations (read-only), but won't be able to see or participate in any new conversations with the group.</span></span> <span data-ttu-id="bf364-175">新しいポリシーまたは変更されたポリシーによって複数のユーザーに通信が適用されない場合、ポリシーの影響を受けるユーザーはグループチャットから削除されることがあります。</span><span class="sxs-lookup"><span data-stu-id="bf364-175">If the new or changed policy preventing communication is applied to more than one user, the users who are affected by the policy may be removed from group chat.</span></span> <span data-ttu-id="bf364-176">以前の会話は引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="bf364-176">They can still see old conversations.</span></span>

<span data-ttu-id="bf364-177">この例では、Enrico が組織内の別の部門に移動され、グループチャットから削除されます。</span><span class="sxs-lookup"><span data-stu-id="bf364-177">In this example, Enrico moved to a different department within the organization and is removed from the group chat.</span></span>

  ![グループチャットを示すスクリーンショット](media/information-barriers-user-changes-job.png)

<span data-ttu-id="bf364-179">Enrico は、グループチャットにメッセージを送信することはできなくなりました。</span><span class="sxs-lookup"><span data-stu-id="bf364-179">Enrico can no longer send messages to the group chat.</span></span>

  ![グループチャットを示すスクリーンショット](media/information-barriers-user-changes-job-2.png)

- <span data-ttu-id="bf364-181">**チーム** -グループから削除されたユーザーはチームから削除され、既存の会話または新規の会話を表示したり、新しい会話に参加したりすることはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="bf364-181">**Team** - Any users who have been removed from the group are removed from the team and will not be able to see or participate in existing or new conversations.</span></span>

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a><span data-ttu-id="bf364-182">シナリオ: 既存のチャットのユーザーがブロックされる</span><span class="sxs-lookup"><span data-stu-id="bf364-182">Scenario: A user in an existing chat becomes blocked</span></span>

<span data-ttu-id="bf364-183">現時点では、情報バリアポリシーで別のユーザーがブロックされている場合、ユーザーは次のシナリオを体験します。</span><span class="sxs-lookup"><span data-stu-id="bf364-183">Currently, users experience the following scenarios if an information barrier policy blocks another user:</span></span>

- <span data-ttu-id="bf364-184">[ **連絡先] タブ** -ユーザーは [ **連絡先** ] タブでブロックされたユーザーを表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="bf364-184">**People tab** - A user cannot see blocked users on the **People** tab.</span></span>
- <span data-ttu-id="bf364-185">**People picker** -ブロックされたユーザーは、people picker に表示されません。</span><span class="sxs-lookup"><span data-stu-id="bf364-185">**People Picker** - Blocked users will not be visible in the people picker.</span></span>

    ![グループチャットを示すスクリーンショット](media/information-barriers-people-picker.png)
    
- <span data-ttu-id="bf364-187">**[アクティビティ] タブ** -ユーザーがブロックしたユーザーの [ **アクティビティ** ] タブにアクセスした場合、投稿は表示されません。</span><span class="sxs-lookup"><span data-stu-id="bf364-187">**Activity tab** - If a user visits the **Activity** tab of a blocked user, no posts will appear.</span></span> <span data-ttu-id="bf364-188">([ **アクティビティ** ] タブには、チャネルの投稿のみが表示され、2人のユーザーに共通のチャネルはありません)。</span><span class="sxs-lookup"><span data-stu-id="bf364-188">(The **Activity** tab displays channel posts only, and there would be no common channels between the two users.)</span></span>

    <span data-ttu-id="bf364-189">ブロックされている [アクティビティ] タブビューの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bf364-189">Here's an example of the activity tab view that is blocked.</span></span>

    ![ブロックされている [アクティビティ] タブを示すスクリーンショット](media/ib-after-activity-tab-policy.png)


- <span data-ttu-id="bf364-191">**組織** 図-ブロックしたユーザーが表示されている組織図にユーザーがアクセスすると、ブロックしたユーザーは組織図に表示されず、代わりにエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bf364-191">**Org charts** - If a user accesses an org chart on which a blocked user appears, the blocked user won't appear on the org chart and an error message will appear instead.</span></span>
- <span data-ttu-id="bf364-192">**連絡先カード** -ユーザーが会話に参加している場合、そのユーザーがブロックされたユーザーの名前の上にマウスポインターを置いたときに、他のユーザーには、連絡先カードの代わりにエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bf364-192">**People card** - If a user participates in a conversation and the user is subsequently blocked, other users will see an error message instead of the people card when they hover over the blocked user's name.</span></span> <span data-ttu-id="bf364-193">カードに記載されているアクション (通話やチャットなど) は利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="bf364-193">Actions listed on the card (such as calling and chat) will be unavailable.</span></span>
- <span data-ttu-id="bf364-194">**おすすめの連絡先** -ブロックされたユーザーは、おすすめの連絡先リスト (新規ユーザーに対して表示される最初の連絡先リスト) に表示されません。</span><span class="sxs-lookup"><span data-stu-id="bf364-194">**Suggested contacts** - Blocked users don't appear on the suggested contacts list (the initial contact list that appears for new users).</span></span>
- <span data-ttu-id="bf364-195">**チャットの連絡先** -ユーザーは、チャットの連絡先リストでブロックしているユーザーを確認できますが、ブロックされたユーザーは特定され、ユーザーが実行できる操作は、それらを削除することだけです。</span><span class="sxs-lookup"><span data-stu-id="bf364-195">**Chat contacts** - A user can see blocked users on the chats contact list, but the blocked users will be identified and the only action the user can perform is to delete them.</span></span> <span data-ttu-id="bf364-196">ユーザーはそれをクリックして、過去の会話を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="bf364-196">The user can also click on them to view their past conversation.</span></span>
- <span data-ttu-id="bf364-197">**連絡先** への通話-ユーザーは [着信] の連絡先リストでブロックされたユーザーを確認できますが、ブロックされたユーザーは特定され、ユーザーが実行できる操作は、それらを削除することだけです。</span><span class="sxs-lookup"><span data-stu-id="bf364-197">**Calls contacts** - A user can see blocked users on the calls contact list, but the blocked users will be identified and the only action the user can perform is to delete them.</span></span>

    <span data-ttu-id="bf364-198">次の例は、[通話] の連絡先リストでブロックされているユーザーを示しています。</span><span class="sxs-lookup"><span data-stu-id="bf364-198">Here's an example of a blocked user in the calls contact list.</span></span>

    ![ユーザーのチャットを示すスクリーンショット](media/ib-before-chat-contacts-policy.png)

    <span data-ttu-id="bf364-200">通話コンテンツリストのユーザーに対して無効になっているチャットの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bf364-200">Here's an example of the chat being disabled for a user on the calls content list.</span></span>

    ![チャットからブロックされているユーザーを示すスクリーンショット](media/ib-after-chat-contacts-policy.png)

- <span data-ttu-id="bf364-202">**Skype から teams** への移行-Skype for Business から teams への移行中、すべてのユーザーは、情報バリアポリシーによってブロックされたユーザーを含めて teams に移行され、その後で説明したように処理されます。</span><span class="sxs-lookup"><span data-stu-id="bf364-202">**Skype to Teams migration** - During a Skype for Business to Teams migration, all users, even those blocked by information barrier policies, will be migrated to Teams and then will be handled as described above.</span></span>

## <a name="teams-policies-and-sharepoint-sites"></a><span data-ttu-id="bf364-203">Teams のポリシーと SharePoint サイト</span><span class="sxs-lookup"><span data-stu-id="bf364-203">Teams policies and SharePoint sites</span></span>

<span data-ttu-id="bf364-204">チームを作成すると、SharePoint サイトがプロビジョニングされ、ファイルエクスペリエンスのために Microsoft Teams と関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="bf364-204">When a team is created, a SharePoint site is provisioned and associated with Microsoft Teams for the files experience.</span></span> <span data-ttu-id="bf364-205">既定では、この SharePoint サイトとファイルに関する情報バリアポリシーは無視されます。</span><span class="sxs-lookup"><span data-stu-id="bf364-205">Information barrier policies are not honored on this SharePoint site and files by default.</span></span> <span data-ttu-id="bf364-206">情報バリアポリシーを有効にするには、管理者が既にフォームに入力しており、その IB ポリシーが SharePoint と OneDrive で有効になっていることを要求しています (「 [情報バリア](https://docs.microsoft.com/sharepoint/information-barriers#prerequisites)」の *前提条件* セクションを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="bf364-206">To enable Information Barrier policies, the administrator has already filled out a form, requesting that IB policies be enabled on SharePoint and OneDrive (see the *Prerequisite* section in [Information barriers](https://docs.microsoft.com/sharepoint/information-barriers#prerequisites)).</span></span> <span data-ttu-id="bf364-207">SharePoint と OneDrive で情報バリアポリシーが有効になっている場合は、Microsoft Teams でチームを作成したときに、そのサービスがプロビジョニングされている SharePoint サイトで、IB ポリシーが機能します。</span><span class="sxs-lookup"><span data-stu-id="bf364-207">If the Information Barrier policy is turned on in SharePoint and OneDrive, then the IB policies will work on SharePoint sites provisioned when a team is created with Microsoft Teams.</span></span>

<span data-ttu-id="bf364-208">**チームの SharePoint サイト上の IB ポリシーの例** : Contoso Bank corporation では、ユーザー ' Sesha@contosobank.onmicrosoft.com ' は投資銀行取引セグメントに属し、ユーザー ' Nikita@contosobank.onmicrosoft.com ' はセグメント勧告に属しています。</span><span class="sxs-lookup"><span data-stu-id="bf364-208">**Example of IB policies on SharePoint site of a team** : In Contoso Bank corporation, user 'Sesha@contosobank.onmicrosoft.com' belongs to Investment Banking segment and user 'Nikita@contosobank.onmicrosoft.com' belongs to segment Advisory.</span></span> <span data-ttu-id="bf364-209">この2つのセグメント間の通信とコラボレーションは、組織の IB ポリシーによってブロックされます。</span><span class="sxs-lookup"><span data-stu-id="bf364-209">The organization's IB policy blocks communication and collaboration between these two segments.</span></span>
<span data-ttu-id="bf364-210">ユーザーが、投資銀行取引先のチームを作成すると、そのチームとそれをバックアップした SharePoint サイトにアクセスできるのは、投資銀行セグメントのユーザーのみになります。</span><span class="sxs-lookup"><span data-stu-id="bf364-210">When user Sesha creates a team for Investment Banking segment, the team and the SharePoint site that backs it will be accessible only to Investment Banking segment users.</span></span> <span data-ttu-id="bf364-211">ユーザー Nikita は、サイトリンクを持っている場合でも、そのサイトにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="bf364-211">User Nikita can't access that site even if she has the site link.</span></span>

<span data-ttu-id="bf364-212">詳細については、 [情報障壁](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites) の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf364-212">See the [Information barriers](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites) article for more details.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="bf364-213">必要なライセンスと権限</span><span class="sxs-lookup"><span data-stu-id="bf364-213">Required licenses and permissions</span></span>

<span data-ttu-id="bf364-214">プランや価格などの詳細については、「 [ライセンスガイダンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf364-214">For more information, including plans and pricing, see [Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

## <a name="known-issues"></a><span data-ttu-id="bf364-215">既知の問題</span><span class="sxs-lookup"><span data-stu-id="bf364-215">Known Issues</span></span>
- <span data-ttu-id="bf364-216">臨時の **会議に参加でき** ない場合: IB ポリシーが有効になっていると、会議リストのサイズが会議の出席 [制限](limits-specifications-teams.md)を超えている場合、ユーザーは会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="bf364-216">**Users can't join ad-hoc meetings** : If IB policies are enabled, users are not allowed to join meetings IF the meeting roster size is more than the [meeting attendance limits](limits-specifications-teams.md).</span></span> <span data-ttu-id="bf364-217">ルートの理由は、IB のチェックによって、ユーザーが会議チャットリストに追加できるかどうかに依存し、ユーザーが会議に参加することを許可することになります。</span><span class="sxs-lookup"><span data-stu-id="bf364-217">The root cause is that IB checks rely on whether users can be added to a meeting chat roster and takes that signal to allow users to join meetings.</span></span> <span data-ttu-id="bf364-218">会議に一度参加すると、そのユーザーがリストに追加されます。そのため、定期的な会議の場合、名簿はすぐにいっぱいになります。</span><span class="sxs-lookup"><span data-stu-id="bf364-218">Joining a meeting once will add that user to the roster, hence for recurring meetings, the roster fills up fast.</span></span> <span data-ttu-id="bf364-219">会議の出席 [制限](limits-specifications-teams.md)に達すると、追加のユーザーを会議のチャットリストに追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="bf364-219">Once it reaches the [meeting attendance limits](limits-specifications-teams.md), no additional users are allowed to be added to the meeting chat roster.</span></span> <span data-ttu-id="bf364-220">このテナントで IB が有効になっていて、会議のチャットリストがいっぱいになっている場合、会議に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="bf364-220">If IB is enabled for the tenant and the chat roster is full for a meeting, new users (those not already on the roster) are not allowed to join the meeting.</span></span> <span data-ttu-id="bf364-221">ただし、テナントの IB が有効になっておらず、会議のチャットリストがいっぱいになっている場合は、会議に参加することはできません。ただし、会議にはチャットオプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="bf364-221">But if IB is not enabled for the tenant and the meeting chat roster is full, new users (those not already on the roster) are allowed to join the meeting, though they won't see the chat option in the meeting.</span></span> <span data-ttu-id="bf364-222">短期的な解決策として、新しいユーザーのためのスペースを確保するため、会議のチャットリストから非アクティブなメンバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="bf364-222">A short term solution is to remove inactive members from the meeting chat roster to make space for new users.</span></span> <span data-ttu-id="bf364-223">ただし、後日、会議チャットの選手名簿のサイズが大きくなります。</span><span class="sxs-lookup"><span data-stu-id="bf364-223">We will, however, be increasing the size of meeting chat rosters at a later date.</span></span>

- <span data-ttu-id="bf364-224">**ユーザーがチャネル会議に参加でき** ない: IB ポリシーが有効になっている場合、ユーザーはチャネル会議に参加することはできません (チームのメンバーでない場合)。</span><span class="sxs-lookup"><span data-stu-id="bf364-224">**Users can't join channel meetings** : If IB policies are enabled, users are not allowed to join channel meetings IF they are not a member of the team.</span></span> <span data-ttu-id="bf364-225">ルートの理由は、IB のチェックによって、ユーザーが会議チャットリストに追加できるかどうかに依存し、ユーザーが会議に参加することを許可することになります。</span><span class="sxs-lookup"><span data-stu-id="bf364-225">The root cause is that IB checks rely on whether users can be added to a meeting chat roster and takes that signal to allow users to join meetings.</span></span> <span data-ttu-id="bf364-226">チャネル会議のチャットスレッドは、チームまたはチャネルメンバーのみが利用でき、メンバー以外はチャットスレッドの表示/アクセスはできません。</span><span class="sxs-lookup"><span data-stu-id="bf364-226">The chat thread in a channel meeting is available to Team/Channel members only, and non-members cannot see/access the chat thread.</span></span> <span data-ttu-id="bf364-227">このテナントで IB が有効であり、チーム以外のメンバーがチャネル会議に参加しようとした場合、ユーザーは会議に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="bf364-227">If IB is enabled for the tenant and a non-team member attempts to join a channel meeting, the user is not allowed to join the meeting.</span></span> <span data-ttu-id="bf364-228">ただし、ユーザーがテナントの IB を有効にしておらず、チーム以外のメンバーがチャネル会議に参加しようとしても、会議に参加することはできますが、会議にはチャットオプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="bf364-228">But if IB is not enabled for the tenant and a non-team member attempts to join a channel meeting, the user is allowed to join the meeting, however, they won't see the chat option in the meeting.</span></span>

## <a name="more-information"></a><span data-ttu-id="bf364-229">詳細情報</span><span class="sxs-lookup"><span data-stu-id="bf364-229">More information</span></span>

- <span data-ttu-id="bf364-230">情報の障壁の詳細については、「 [情報の障壁](https://docs.microsoft.com/office365/securitycompliance/information-barriers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf364-230">To learn more about information barriers, see [Information barriers](https://docs.microsoft.com/office365/securitycompliance/information-barriers).</span></span>

- <span data-ttu-id="bf364-231">情報バリアポリシーを設定する方法については、「 [情報バリアのポリシーを定義](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf364-231">To set up information barrier policies, see [Define policies for information barriers](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).</span></span>

- <span data-ttu-id="bf364-232">情報バリアポリシーを編集または削除するには、「 [情報バリアポリシーを編集 (または削除)](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-edit-segments-policies)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf364-232">To edit or remove information barrier policies, see [Edit (or remove) information barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-edit-segments-policies).</span></span>
