---
title: Microsoft Teams の情報バリア
description: この記事では、データ の情報バリアと、Microsoft Teamsにどのような影響を与える可能性Teams。
author: robmazz
ms.author: robmazz
manager: laurawi
ms.reviewer: vikramju
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7946d6c098979d478f91d8ef67a3214c11823d7d
ms.sourcegitcommit: dba7984f899f8921b462a56d158fa0a1cc2c2a8b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929323"
---
# <a name="information-barriers-in-microsoft-teams"></a><span data-ttu-id="8de68-103">Microsoft Teams の情報バリア</span><span class="sxs-lookup"><span data-stu-id="8de68-103">Information barriers in Microsoft Teams</span></span>

<span data-ttu-id="8de68-104">情報バリア (IB) は、個人またはグループが互いに通信し合うのを防ぐために管理者が構成できるポリシーです。</span><span class="sxs-lookup"><span data-stu-id="8de68-104">Information barriers (IBs) are policies that an admin can configure to prevent individuals or groups from communicating with each other.</span></span> <span data-ttu-id="8de68-105">たとえば、ある部署が他の部署と共有してはならない情報を処理している場合、IB は便利です。</span><span class="sxs-lookup"><span data-stu-id="8de68-105">IBs are useful if, for example, one department is handling information that shouldn't be shared with other departments.</span></span> <span data-ttu-id="8de68-106">また、グループを分離したり、そのグループ外のユーザーとの通信を妨げる必要がある場合にも便利です。</span><span class="sxs-lookup"><span data-stu-id="8de68-106">IBs are also useful when a group needs to be isolated or prevented from communicating with anyone outside of that group.</span></span>

>[!NOTE]
>- <span data-ttu-id="8de68-107">テナント間で情報バリア (IB) グループを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="8de68-107">Information barrier (IB) groups cannot be created across tenants.</span></span>
>- <span data-ttu-id="8de68-108">ボット、Azure Active Directory (Azure AD) アプリ、アクティビティ フィード通知を送信する API、およびユーザーを追加する一部の API の使用は、バージョン 1 ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8de68-108">Using bots, Azure Active Directory (Azure AD) apps, APIs to send activity feed notifications, and some APIs to add users is not supported in version 1.</span></span>
>- <span data-ttu-id="8de68-109">プライベート チャネルは、構成する IB ポリシーに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="8de68-109">Private channels are compliant to IB policies that you configure.</span></span>
>- <span data-ttu-id="8de68-110">新機能: SharePoint に接続されているサイトのバリアのサポートについては、「Teams サイトに関連付けられているセグメント」[をMicrosoft Teamsしてください](/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)。</span><span class="sxs-lookup"><span data-stu-id="8de68-110">New: For information about support for barriers for SharePoint sites that are connected to Teams, see [Segments associated with Microsoft Teams sites](/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites).</span></span>

<span data-ttu-id="8de68-111">IB ポリシーは、ルックアップと検出も防止します。</span><span class="sxs-lookup"><span data-stu-id="8de68-111">IB policies also prevent lookups and discovery.</span></span> <span data-ttu-id="8de68-112">通信してはいけない相手と通信しようとすると、そのユーザーが相手の選択リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8de68-112">If you attempt to communicate with someone you shouldn't be communicating with, you won't find that user in the people picker.</span></span>

## <a name="background"></a><span data-ttu-id="8de68-113">背景</span><span class="sxs-lookup"><span data-stu-id="8de68-113">Background</span></span>

<span data-ttu-id="8de68-114">IB の主要なドライバーは、金融サービス業界から得たものとなっています。</span><span class="sxs-lookup"><span data-stu-id="8de68-114">The primary driver for IBs comes from the financial services industry.</span></span> <span data-ttu-id="8de68-115">金融業界規制機関[(FINRA)]( https://www.finra.org)は、メンバー企業内の IBs と利益の競合をレビューし、そのような競合の管理に関するガイダンスを提供します (FINRA 2241、借金調査規制通知[15-31)。](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)</span><span class="sxs-lookup"><span data-stu-id="8de68-115">The Financial Industry Regulatory Authority ([FINRA]( https://www.finra.org)) reviews IBs and conflicts of interest within member firms and provides guidance about managing such conflicts (FINRA 2241, [Debt Research Regulatory Notice 15-31](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).</span></span>

<span data-ttu-id="8de68-116">ただし、IB の導入以降、他の多くの領域で役立つ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8de68-116">However, since introducing IBs, many other areas have found them to be useful.</span></span> <span data-ttu-id="8de68-117">その他の一般的なシナリオは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8de68-117">Other common scenarios include:</span></span>

- <span data-ttu-id="8de68-118">教育: ある学校の学生は、他の学校の学生の連絡先情報を参照できない。</span><span class="sxs-lookup"><span data-stu-id="8de68-118">Education: Students in one school aren't able to look up contact details for students of other schools.</span></span>

- <span data-ttu-id="8de68-119">法律: あるクライアントの法律家によって取得されたデータの機密性を維持し、別のクライアントを代表する同じ会社の法律家によってアクセスされるのを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="8de68-119">Legal: Maintaining the confidentiality of data that is obtained by the lawyer of one client and preventing it from being accessed by a lawyer for the same firm who represents a different client.</span></span>

- <span data-ttu-id="8de68-120">政府機関: 情報のアクセスと制御は、部門やグループ間で制限されます。</span><span class="sxs-lookup"><span data-stu-id="8de68-120">Government: Information access and control are limited across departments and groups.</span></span>

- <span data-ttu-id="8de68-121">Professionalサービス: 会社のユーザーのグループは、顧客エンゲージメント中にゲスト アクセスを介してクライアントまたは特定の顧客とのみチャットできます。</span><span class="sxs-lookup"><span data-stu-id="8de68-121">Professional services: A group of people in a company is only able to chat with a client or a specific customer via guest access during a customer engagement.</span></span>

<span data-ttu-id="8de68-122">たとえば、Enrico は銀行セグメントに属し、Pradeep は財務アドバイザー セグメントに属しています。</span><span class="sxs-lookup"><span data-stu-id="8de68-122">For example, Enrico belongs to the Banking segment and Pradeep belongs to the Financial advisor segment.</span></span> <span data-ttu-id="8de68-123">Enrico と Pradeep は、組織の IB ポリシーがこれら 2 つのセグメント間の通信とコラボレーションをブロックするために相互に通信できない。</span><span class="sxs-lookup"><span data-stu-id="8de68-123">Enrico and Pradeep can't communicate with each other because the organization's IB policy blocks communication and collaboration between these two segments.</span></span> <span data-ttu-id="8de68-124">ただし、Enrico と Pradeep は HR で Lee と通信できます。</span><span class="sxs-lookup"><span data-stu-id="8de68-124">However, Enrico and Pradeep can communicate with Lee in HR.</span></span>

![セグメント間の通信を妨げている情報バリアを示す例](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a><span data-ttu-id="8de68-126">情報バリアを使用する場合</span><span class="sxs-lookup"><span data-stu-id="8de68-126">When to use information barriers</span></span>

<span data-ttu-id="8de68-127">次のような状況で、IB を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8de68-127">You might want to use IBs in situations like these:</span></span>

- <span data-ttu-id="8de68-128">チームは、特定の他のチームとデータの通信や共有を行うのを防ぐ必要があります。</span><span class="sxs-lookup"><span data-stu-id="8de68-128">A team must be prevented from communicating or sharing data with a specific other team.</span></span>
- <span data-ttu-id="8de68-129">チームは、チーム外のユーザーと通信したり、データを共有したりしなけってはいません。</span><span class="sxs-lookup"><span data-stu-id="8de68-129">A team must not communicate or share data with anyone outside of the team.</span></span>

<span data-ttu-id="8de68-130">Information Barrier Policy Evaluation Service は、通信が IB ポリシーに準拠するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="8de68-130">The Information Barrier Policy Evaluation Service determines whether a communication complies with IB policies.</span></span>

## <a name="managing-information-barrier-policies"></a><span data-ttu-id="8de68-131">情報バリア ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="8de68-131">Managing information barrier policies</span></span>

<span data-ttu-id="8de68-132">IB ポリシーは、PowerShell コマンドレットMicrosoft 365コンプライアンス センター (SCC) で管理されます。</span><span class="sxs-lookup"><span data-stu-id="8de68-132">IB policies are managed in the Microsoft 365 Compliance Center (SCC) using PowerShell cmdlets.</span></span> <span data-ttu-id="8de68-133">詳細については、「情報バリアの [ポリシーを定義する」を参照してください](/office365/securitycompliance/information-barriers-policies)。</span><span class="sxs-lookup"><span data-stu-id="8de68-133">For more information, see [Define policies for information barriers](/office365/securitycompliance/information-barriers-policies).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8de68-134">ポリシーを設定または定義する前に、スコープを持つディレクトリ検索を有効にする必要Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="8de68-134">Before you set up or define policies, you must enable scoped directory search in Microsoft Teams.</span></span> <span data-ttu-id="8de68-135">情報バリアのポリシーを設定または定義する前に、範囲指定されたディレクトリ検索を有効にしてから、少なくとも数時間待ちます。</span><span class="sxs-lookup"><span data-stu-id="8de68-135">Wait at least a few hours after enabling scoped directory search before you set up or define policies for information barriers.</span></span> <span data-ttu-id="8de68-136">詳細については、「情報バリア ポリシー [を定義する」を参照してください](/office365/securitycompliance/information-barriers-policies#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="8de68-136">For more information, see [Define information barrier policies](/office365/securitycompliance/information-barriers-policies#prerequisites).</span></span>

## <a name="information-barriers-administrator-role"></a><span data-ttu-id="8de68-137">情報バリア管理者ロール</span><span class="sxs-lookup"><span data-stu-id="8de68-137">Information barriers administrator role</span></span>

<span data-ttu-id="8de68-138">IB コンプライアンス管理ロールは、IB ポリシーの管理を担当します。</span><span class="sxs-lookup"><span data-stu-id="8de68-138">The IB Compliance Management role is responsible for managing IB policies.</span></span> <span data-ttu-id="8de68-139">このロールの詳細については、「コンプライアンス センターのアクセス許可[」Microsoft 365参照してください](/office365/securitycompliance/permissions-in-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="8de68-139">For more information about this role, see [Permissions in the Microsoft 365 Compliance Center](/office365/securitycompliance/permissions-in-the-security-and-compliance-center).</span></span>

## <a name="information-barrier-triggers"></a><span data-ttu-id="8de68-140">情報バリア トリガー</span><span class="sxs-lookup"><span data-stu-id="8de68-140">Information barrier triggers</span></span>

<span data-ttu-id="8de68-141">IB ポリシーは、次のイベントが発生Teamsアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="8de68-141">IB policies are activated when the following Teams events take place:</span></span>

- <span data-ttu-id="8de68-142">**メンバーはチームに追加されます** 。ユーザーをチームに追加するたびに、ユーザーのポリシーを他のチーム メンバーの IB ポリシーに対して評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8de68-142">**Members are added to a team** - Whenever you add a user to a team, the user's policy must be evaluated against the IB policies of other team members.</span></span> <span data-ttu-id="8de68-143">ユーザーが正常に追加されると、ユーザーは、それ以上のチェックを行わずにチーム内のすべての関数を実行できます。</span><span class="sxs-lookup"><span data-stu-id="8de68-143">After the user is successfully added, the user can perform all functions in the team without further checks.</span></span> <span data-ttu-id="8de68-144">ユーザーのポリシーによってチームへの追加がブロックされた場合、ユーザーは検索に表示されません。</span><span class="sxs-lookup"><span data-stu-id="8de68-144">If the user's policy blocks them from being added to the team, the user won't show up in search.</span></span>

    ![チームに追加する新しいメンバーを検索し、一致を見つけ出すスクリーンショット](media/information-barriers-add-members.png)

- <span data-ttu-id="8de68-146">**新しいチャット** が要求される - ユーザーが 1 人または複数の他のユーザーとの新しいチャットを要求するたび、IB ポリシーに違反しないチャットが評価されます。</span><span class="sxs-lookup"><span data-stu-id="8de68-146">**A new chat is requested** - Each time that a user requests a new chat with one or more other users, the chat is evaluated to make sure that it isn't violating any IB policies.</span></span> <span data-ttu-id="8de68-147">会話が IB ポリシーに違反した場合、会話は開始されます。</span><span class="sxs-lookup"><span data-stu-id="8de68-147">If the conversation violates an IB policy, then the conversation isn't started.</span></span>

    <span data-ttu-id="8de68-148">1 対 1 のチャットの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8de68-148">Here's an example of a 1:1 chat.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8de68-149">![1:1 チャットでの通信のブロックを示すスクリーンショット](media/information-barriers-one-one-chat.png)</span><span class="sxs-lookup"><span data-stu-id="8de68-149">![Screenshot showing blocked communication in 1:1 chat](media/information-barriers-one-one-chat.png)</span></span>

    <span data-ttu-id="8de68-150">グループ チャットの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8de68-150">Here's an example of a group chat.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8de68-151">![グループ チャットを示すスクリーンショット](media/information-barriers-group-chat.png)</span><span class="sxs-lookup"><span data-stu-id="8de68-151">![Screenshot showing group chat](media/information-barriers-group-chat.png)</span></span>

- <span data-ttu-id="8de68-152">**ユーザーが** 会議への参加を招待される - ユーザーが会議に参加するために招待された場合、ユーザーに適用される IB ポリシーは、他のチーム メンバーに適用される IB ポリシーに対して評価されます。</span><span class="sxs-lookup"><span data-stu-id="8de68-152">**A user is invited to join a meeting** - When a user is invited to join a meeting, the IB policy that applies to the user is evaluated against the IB policies that apply to the other team members.</span></span> <span data-ttu-id="8de68-153">違反がある場合、ユーザーは会議への参加を許可されません。</span><span class="sxs-lookup"><span data-stu-id="8de68-153">If there's a violation, the user won't be allowed to join the meeting.</span></span>

    ![ユーザーが会議でブロックされた状態を示すスクリーンショット](media/information-barriers-meeting.png)

- <span data-ttu-id="8de68-155">**2** 人または複数のユーザー間で画面を共有する - ユーザーが他のユーザーと画面を共有する場合は、共有が他のユーザーの IB ポリシーに違反していないか確認するために、共有を評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8de68-155">**A screen is shared between two or more users** - When a user shares a screen with other users, the sharing must be evaluated to make sure that it doesn't violate the IB policies of other users.</span></span> <span data-ttu-id="8de68-156">IB ポリシーに違反した場合、画面共有は許可されません。</span><span class="sxs-lookup"><span data-stu-id="8de68-156">If an IB policy is violated, the screen share won't be allowed.</span></span>

    <span data-ttu-id="8de68-157">ポリシーを適用する前の画面共有の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8de68-157">Here's an example of screen share before the policy is applied.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8de68-158">![ユーザー チャットを示すスクリーンショット](media/ib-before-screen-share-policy.png)</span><span class="sxs-lookup"><span data-stu-id="8de68-158">![Screenshot showing a user chat](media/ib-before-screen-share-policy.png)</span></span>

    <span data-ttu-id="8de68-159">ポリシーが適用された後の画面共有の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8de68-159">Here's an example of screen share after the policy is applied.</span></span> <span data-ttu-id="8de68-160">画面共有アイコンと通話アイコンは表示されません。</span><span class="sxs-lookup"><span data-stu-id="8de68-160">The screen share and call icons aren't visible.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8de68-161">![ブロック設定のユーザー文字を示すスクリーンショット](media/ib-after-screen-share-policy.png)</span><span class="sxs-lookup"><span data-stu-id="8de68-161">![Screenshot showing user char with blocked settings](media/ib-after-screen-share-policy.png)</span></span>

- <span data-ttu-id="8de68-162">**ユーザー** が Teams で通話を行う - ユーザーが別のユーザーまたはユーザー のグループに対して (VOIP を介して) 音声通話を開始するたびに、その通話が評価され、他のチーム メンバーの IB ポリシーに違反していないと判断されます。</span><span class="sxs-lookup"><span data-stu-id="8de68-162">**A user places a phone call in Teams** - Whenever a user initiates a voice call (via VOIP) to another user or group of users, the call is evaluated to make sure that it doesn't violate the IB policies of other team members.</span></span> <span data-ttu-id="8de68-163">違反がある場合、音声通話はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="8de68-163">If there's any violation, the voice call is blocked.</span></span>

- <span data-ttu-id="8de68-164">**ゲストのTeams** - IB ポリシーは、Teamsゲストに適用されます。</span><span class="sxs-lookup"><span data-stu-id="8de68-164">**Guests in Teams** - IB policies apply to guests in Teams, too.</span></span> <span data-ttu-id="8de68-165">組織のグローバル アドレス一覧でゲストを検出できる必要がある場合は、「グループでゲスト アクセスを管理する」[をMicrosoft 365してください](/microsoft-365/admin/create-groups/manage-guest-access-in-groups)。</span><span class="sxs-lookup"><span data-stu-id="8de68-165">If guests need to be discoverable in your organization's global address list, see [Manage guest access in Microsoft 365 Groups](/microsoft-365/admin/create-groups/manage-guest-access-in-groups).</span></span> <span data-ttu-id="8de68-166">ゲストが検出可能な場合は [、IB ポリシー を定義できます](/office365/securitycompliance/information-barriers-policies)。</span><span class="sxs-lookup"><span data-stu-id="8de68-166">Once guests are discoverable, you can [define IB policies](/office365/securitycompliance/information-barriers-policies).</span></span>

## <a name="how-policy-changes-impact-existing-chats"></a><span data-ttu-id="8de68-167">ポリシーの変更が既存のチャットに与える影響</span><span class="sxs-lookup"><span data-stu-id="8de68-167">How policy changes impact existing chats</span></span>

<span data-ttu-id="8de68-168">IB ポリシー管理者がポリシーに変更を加えた場合、またはユーザーのプロファイルの変更 (ジョブの変更など) が理由でポリシーの変更がアクティブ化された場合、Information Barrier Policy Evaluation Service はメンバーを自動的に検索して、チームのメンバーシップがポリシーに違反していないか確認します。</span><span class="sxs-lookup"><span data-stu-id="8de68-168">When the IB policy administrator makes changes to a policy, or when a policy change is activated because of a change to a user's profile (such as for a job change), the Information Barrier Policy Evaluation Service automatically searches the members to ensure that their membership in the team doesn't violate any policies.</span></span>

<span data-ttu-id="8de68-169">ユーザー間に既存のチャットや他の通信が存在し、新しいポリシーが設定されている場合、または既存のポリシーが変更された場合、サービスは既存の通信を評価して、通信が引き続き許可されるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="8de68-169">If there's an existing chat or other communication between users, and a new policy is set or an existing policy is changed, the service evaluates existing communications to make sure that the communications are still allowed to occur.</span></span> 

- <span data-ttu-id="8de68-170">**1:1** チャット - 2 人のユーザー間の通信が許可されなくなった場合 (通信をブロックするポリシーの 1 人または両方のユーザーへのアプリケーションのため)、それ以上の通信がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="8de68-170">**1:1 chat** - If communication between two users is no longer allowed (because of application to one or both users of a policy that blocks communication), further communication is blocked.</span></span> <span data-ttu-id="8de68-171">既存のチャット会話は読み取り専用になります。</span><span class="sxs-lookup"><span data-stu-id="8de68-171">Their existing chat conversations become read-only.</span></span>

    <span data-ttu-id="8de68-172">チャットが表示されている例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8de68-172">Here's an example that shows the chat is visible.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8de68-173">![ユーザー チャットが利用可能な状態を示すスクリーンショット](media/ib-before-1-1chat-policy.png)</span><span class="sxs-lookup"><span data-stu-id="8de68-173">![Screenshot showing user chat is available](media/ib-before-1-1chat-policy.png)</span></span>

    <span data-ttu-id="8de68-174">チャットが無効になっている例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8de68-174">Here's an example that shows the chat is disabled.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8de68-175">![ユーザー チャットが無効になっている状態を示すスクリーンショット](media/ib-after-1-1chat-policy.png)</span><span class="sxs-lookup"><span data-stu-id="8de68-175">![Screenshot showing user chat is disabled](media/ib-after-1-1chat-policy.png)</span></span>

- <span data-ttu-id="8de68-176">**グループ** チャット - 1 人のユーザーからグループへの通信が許可されなくなった場合 (たとえば、ユーザーがジョブを変更した場合など)、参加がポリシーに違反している他のユーザーと共に、グループ チャットから削除され、グループとのコミュニケーションは許可されません。</span><span class="sxs-lookup"><span data-stu-id="8de68-176">**Group chat** - If communication from one user to a group is no longer allowed (for example, because a user changed jobs), the user—along with the other users whose participation violates the policy—may be removed from group chat, and further communication with the group won't be allowed.</span></span> <span data-ttu-id="8de68-177">ユーザーは古い会話を表示できますが、グループとの新しい会話を表示したり、参加したりできません。</span><span class="sxs-lookup"><span data-stu-id="8de68-177">The user can still see old conversations, but won't be able to see or participate in any new conversations with the group.</span></span> <span data-ttu-id="8de68-178">通信を妨げる新しいポリシーまたは変更されたポリシーが複数のユーザーに適用されている場合、ポリシーの影響を受けるユーザーはグループ チャットから削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8de68-178">If the new or changed policy that prevents communication is applied to more than one user, the users who are affected by the policy may be removed from group chat.</span></span> <span data-ttu-id="8de68-179">古い会話は引き続き表示できます。</span><span class="sxs-lookup"><span data-stu-id="8de68-179">They can still see old conversations.</span></span>

  <span data-ttu-id="8de68-180">この例では、Enrico は組織内の別の部署に移動し、グループ チャットから削除されます。</span><span class="sxs-lookup"><span data-stu-id="8de68-180">In this example, Enrico moved to a different department within the organization and is removed from the group chat.</span></span>

  ![ユーザーが削除されたグループ チャットのスクリーンショット](media/information-barriers-user-changes-job.png)

  <span data-ttu-id="8de68-182">Enrico は、グループ チャットにメッセージを送信できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="8de68-182">Enrico can no longer send messages to the group chat.</span></span>

  ![ユーザーがグループから削除されたため、グループ チャットにメッセージを送信できないスクリーンショット](media/information-barriers-user-changes-job-2.png)

- <span data-ttu-id="8de68-184">**チーム** - グループから削除されたユーザーは、チームから削除され、既存または新しい会話を表示したり、参加したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8de68-184">**Team** - Any users who have been removed from the group are removed from the team and won't be able to see or participate in existing or new conversations.</span></span>

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a><span data-ttu-id="8de68-185">シナリオ: 既存のチャットのユーザーがブロックされる</span><span class="sxs-lookup"><span data-stu-id="8de68-185">Scenario: A user in an existing chat becomes blocked</span></span>

<span data-ttu-id="8de68-186">現在、IB ポリシーによって別のユーザーがブロックされている場合、ユーザーには次のシナリオが発生します。</span><span class="sxs-lookup"><span data-stu-id="8de68-186">Currently, users experience the following scenarios if an IB policy blocks another user:</span></span>

- <span data-ttu-id="8de68-187">**[ユーザー]** タブ - ユーザーが [ユーザー] タブにブロックされたユーザー **を表示** できない。</span><span class="sxs-lookup"><span data-stu-id="8de68-187">**People tab** - A user can't see blocked users on the **People** tab.</span></span>

- <span data-ttu-id="8de68-188">**[ユーザー選択]** - ブロックされたユーザーは、ユーザー選択には表示されません。</span><span class="sxs-lookup"><span data-stu-id="8de68-188">**People Picker** - Blocked users won't be visible in the people picker.</span></span>

    ![ポリシーがTeamsユーザーの情報の表示を妨げるアラートをユーザーに通知するスクリーンショット](media/information-barriers-people-picker.png)

- <span data-ttu-id="8de68-190">**[アクティビティ]** タブ - ユーザーがブロックされたユーザーの [アクティビティ] タブにアクセスした場合、投稿は表示されません。</span><span class="sxs-lookup"><span data-stu-id="8de68-190">**Activity tab** - If a user visits the **Activity** tab of a blocked user, no posts will appear.</span></span> <span data-ttu-id="8de68-191">([ **アクティビティ] タブ** にはチャネルの投稿だけが表示され、2 人のユーザー間に共通のチャネルはありません)。</span><span class="sxs-lookup"><span data-stu-id="8de68-191">(The **Activity** tab displays channel posts only, and there would be no common channels between the two users.)</span></span>

    <span data-ttu-id="8de68-192">ブロックされているアクティビティ タブ ビューの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8de68-192">Here's an example of the activity tab view that is blocked.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8de68-193">![ブロックされているアクティビティ タブを示すスクリーンショット](media/ib-after-activity-tab-policy.png)</span><span class="sxs-lookup"><span data-stu-id="8de68-193">![Screenshot showing the activity tab that is blocked](media/ib-after-activity-tab-policy.png)</span></span>

- <span data-ttu-id="8de68-194">**組織図** - ブロックされたユーザーが表示される組織図にユーザーがアクセスした場合、ブロックされたユーザーは組織図に表示されません。</span><span class="sxs-lookup"><span data-stu-id="8de68-194">**Org charts** - If a user accesses an org chart on which a blocked user appears, the blocked user won't appear on the org chart.</span></span> <span data-ttu-id="8de68-195">代わりに、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8de68-195">Instead, an error message will appear.</span></span>

- <span data-ttu-id="8de68-196">**ユーザー** カード - ユーザーが会話に参加し、そのユーザーが後でブロックされた場合、他のユーザーは、ブロックされたユーザーの名前にマウス ポインターを合わせると、ユーザー カードの代わりにエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8de68-196">**People card** - If a user participates in a conversation and the user is later blocked, other users will see an error message instead of the people card when they hover over the blocked user's name.</span></span> <span data-ttu-id="8de68-197">カードに表示されている操作 (通話やチャットなど) は使用できません。</span><span class="sxs-lookup"><span data-stu-id="8de68-197">Actions listed on the card (such as calling and chat) will be unavailable.</span></span>

- <span data-ttu-id="8de68-198">**連絡先の候補** - ブロックされたユーザーは、候補の連絡先リスト (新しいユーザーに対して表示される最初の連絡先リスト) には表示されません。</span><span class="sxs-lookup"><span data-stu-id="8de68-198">**Suggested contacts** - Blocked users don't appear on the suggested contacts list (the initial contact list that appears for new users).</span></span>

- <span data-ttu-id="8de68-199">**チャットの連絡先** - ユーザーはチャットの連絡先リストにブロックされたユーザーを表示できますが、ブロックされたユーザーは識別されます。</span><span class="sxs-lookup"><span data-stu-id="8de68-199">**Chat contacts** - A user can see blocked users on the chats contact list, but the blocked users will be identified.</span></span> <span data-ttu-id="8de68-200">ブロックされたユーザーに対してユーザーが実行できる唯一のアクションは、ユーザーを削除する操作です。</span><span class="sxs-lookup"><span data-stu-id="8de68-200">The only action that the user can perform on the blocked users is to delete them.</span></span> <span data-ttu-id="8de68-201">ユーザーは、ユーザーをクリックして過去の会話を表示できます。</span><span class="sxs-lookup"><span data-stu-id="8de68-201">The user can also click on them to view their past conversation.</span></span>

- <span data-ttu-id="8de68-202">**連絡先の呼** び出し - ユーザーは通話の連絡先リストにブロックされたユーザーを表示できますが、ブロックされたユーザーは識別されます。</span><span class="sxs-lookup"><span data-stu-id="8de68-202">**Calls contacts** - A user can see blocked users on the calls contact list, but the blocked users will be identified.</span></span> <span data-ttu-id="8de68-203">ユーザーがブロック ユーザーに対して実行できる唯一のアクションは、ユーザーを削除する操作です。</span><span class="sxs-lookup"><span data-stu-id="8de68-203">The only action that the user can perform on the block users is to delete them.</span></span>

    <span data-ttu-id="8de68-204">通話連絡先リストのブロックされたユーザーの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8de68-204">Here's an example of a blocked user in the calls contact list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8de68-205">![ユーザー のチャットを示すスクリーンショット](media/ib-before-chat-contacts-policy.png)</span><span class="sxs-lookup"><span data-stu-id="8de68-205">![Screenshot showing user user chat](media/ib-before-chat-contacts-policy.png)</span></span>

    <span data-ttu-id="8de68-206">通話コンテンツ リストのユーザーに対して無効になっているチャットの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8de68-206">Here's an example of the chat being disabled for a user on the calls content list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8de68-207">![ユーザーがチャットからブロックされた状態を示すスクリーンショット](media/ib-after-chat-contacts-policy.png)</span><span class="sxs-lookup"><span data-stu-id="8de68-207">![Screenshot showing user blocked from chat](media/ib-after-chat-contacts-policy.png)</span></span>

- <span data-ttu-id="8de68-208">**Skype** 移行へのTeams - Skype for Business から Teams への移行中は、IB ポリシーによってブロックされているユーザーも含め、すべてのユーザーが Teams に移行されます。</span><span class="sxs-lookup"><span data-stu-id="8de68-208">**Skype to Teams migration** - During a migration from Skype for Business to Teams, all users—even those users who are blocked by IB policies—will be migrated to Teams.</span></span> <span data-ttu-id="8de68-209">これらのユーザーは、上記のように処理されます。</span><span class="sxs-lookup"><span data-stu-id="8de68-209">Those users are then handled as described above.</span></span>

## <a name="teams-policies-and-sharepoint-sites"></a><span data-ttu-id="8de68-210">TeamsポリシーとSharePointサイト</span><span class="sxs-lookup"><span data-stu-id="8de68-210">Teams policies and SharePoint sites</span></span>

<span data-ttu-id="8de68-211">チームが作成されると、SharePointサイトがプロビジョニングされ、ファイル エクスペリエンスMicrosoft Teamsに関連付けられる。</span><span class="sxs-lookup"><span data-stu-id="8de68-211">When a team is created, a SharePoint site is provisioned and associated with Microsoft Teams for the files experience.</span></span> <span data-ttu-id="8de68-212">情報バリア ポリシーは、既定では、このSharePointポリシーには適用されません。</span><span class="sxs-lookup"><span data-stu-id="8de68-212">Information barrier policies aren't honored on this SharePoint site and files by default.</span></span> <span data-ttu-id="8de68-213">SharePoint および OneDrive で情報バリアを有効にするには、「情報バリアを使用する」トピックのガイダンスと[手順SharePoint](/sharepoint/information-barriers#enable-sharepoint-and-onedrive-information-barriers-in-your-organization)してください。</span><span class="sxs-lookup"><span data-stu-id="8de68-213">To enable information barriers in SharePoint and OneDrive, follow the guidance and steps in the [Use information barriers with SharePoint](/sharepoint/information-barriers#enable-sharepoint-and-onedrive-information-barriers-in-your-organization) topic.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="8de68-214">必要なライセンスとアクセス許可</span><span class="sxs-lookup"><span data-stu-id="8de68-214">Required licenses and permissions</span></span>

<span data-ttu-id="8de68-215">プランや価格など、ライセンスとアクセス許可の詳細については、「セキュリティとコンプライアンスに関するMicrosoft 365ライセンス ガイダンス[」を&してください](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="8de68-215">For more information on licenses and permissions, including plans and pricing, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

## <a name="known-issues"></a><span data-ttu-id="8de68-216">既知の問題</span><span class="sxs-lookup"><span data-stu-id="8de68-216">Known Issues</span></span>

- <span data-ttu-id="8de68-217">**ユーザーはアドホック** 会議に参加できません: IB ポリシーが有効になっている場合、会議リストのサイズが会議出席制限 を超える場合、ユーザーは会議に参加 [できません。](limits-specifications-teams.md)</span><span class="sxs-lookup"><span data-stu-id="8de68-217">**Users can't join ad-hoc meetings**: If IB policies are enabled, users aren't allowed to join meetings if the size of the meeting roster is greater than the [meeting attendance limits](limits-specifications-teams.md).</span></span> <span data-ttu-id="8de68-218">根本的な原因は、IB チェックは、ユーザーを会議チャットリストに追加できるかどうかに依存し、ユーザーをリストに追加できる場合にのみ、会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="8de68-218">The root cause is that IB checks rely on whether users can be added to a meeting chat roster, and only when they can be added to the roster are they allowed to join the meeting.</span></span> <span data-ttu-id="8de68-219">会議に参加したユーザーは、そのユーザーをリストに追加します。そのため、定期的な会議では、名簿が速くいっぱいになじむ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8de68-219">A user joining a meeting once adds that user to the roster; hence for recurring meetings, the roster can fill up fast.</span></span> <span data-ttu-id="8de68-220">チャットリストが会議出席制限に達[](limits-specifications-teams.md)すると、会議に追加のユーザーは追加されません。</span><span class="sxs-lookup"><span data-stu-id="8de68-220">Once the chat roster reaches the [meeting attendance limits](limits-specifications-teams.md), no additional users are allowed to be added to the meeting.</span></span> <span data-ttu-id="8de68-221">テナントに対して IB が有効で、チャット リストが会議に対していっぱいになっている場合、新しいユーザー (まだリストに参加していないユーザー) は会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="8de68-221">If IB is enabled for the tenant and the chat roster is full for a meeting, new users (those users who aren't already on the roster) aren't allowed to join the meeting.</span></span> <span data-ttu-id="8de68-222">ただし、テナントに対して IB が有効になっていない場合、会議のチャット リストがいっぱいの場合、新しいユーザー (まだリストに参加していないユーザー) は会議に参加できますが、会議にはチャット オプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="8de68-222">But if IB isn't enabled for the tenant and the meeting chat roster is full, new users (those users who aren't already on the roster) are allowed to join the meeting, though they won't see the chat option in the meeting.</span></span> <span data-ttu-id="8de68-223">短期的な解決策は、会議チャットリストから非アクティブなメンバーを削除して、新しいユーザーのためのスペースを作る方法です。</span><span class="sxs-lookup"><span data-stu-id="8de68-223">A short-term solution is to remove inactive members from the meeting chat roster to make space for new users.</span></span> <span data-ttu-id="8de68-224">ただし、後日、会議チャットのリストのサイズを増やす予定です。</span><span class="sxs-lookup"><span data-stu-id="8de68-224">We will, however, be increasing the size of meeting chat rosters at a later date.</span></span>
- <span data-ttu-id="8de68-225">**ユーザーはチャネル** 会議に参加できません: IB ポリシーが有効になっている場合、ユーザーがチームのメンバーでない場合、チャネル会議に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="8de68-225">**Users can't join channel meetings**: If IB policies are enabled, users aren't allowed to join channel meetings if they're not a member of the team.</span></span> <span data-ttu-id="8de68-226">根本的な原因は、IB チェックは、ユーザーを会議チャットリストに追加できるかどうかに依存し、ユーザーをリストに追加できる場合にのみ、会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="8de68-226">The root cause is that IB checks rely on whether users can be added to a meeting chat roster, and only when they can be added to the roster are they allowed to join the meeting.</span></span> <span data-ttu-id="8de68-227">チャネル会議のチャット スレッドは、Team/Channel メンバーだけが使用できます。また、メンバー以外のメンバーはチャット スレッドを表示したり、チャット スレッドにアクセスしたりできません。</span><span class="sxs-lookup"><span data-stu-id="8de68-227">The chat thread in a channel meeting is available to Team/Channel members only, and non-members can't see or access the chat thread.</span></span> <span data-ttu-id="8de68-228">テナントに対して IB が有効で、チーム 以外のメンバーがチャネル会議への参加を試みる場合、そのユーザーは会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="8de68-228">If IB is enabled for the tenant and a non-team member attempts to join a channel meeting, that user isn't allowed to join the meeting.</span></span> <span data-ttu-id="8de68-229">ただし、テナントに対して IB が有効になっていない場合、チーム 以外のメンバーがチャネル会議に参加しようとすると、ユーザーは会議に参加できますが、会議にはチャット オプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="8de68-229">However, if IB is *not* enabled for the tenant and a non-team member attempts to join a channel meeting, the user is allowed to join the meeting—but they won't see the chat option in the meeting.</span></span>
- <span data-ttu-id="8de68-230">**チーム** 所有者が削除されない: 新しい IB ポリシーが適用され、2 つ以上の競合するセグメントが Teams チャネルに存在する場合、チーム所有者を含むセグメントの方が優先され、他のセグメント ユーザーは削除されます。</span><span class="sxs-lookup"><span data-stu-id="8de68-230">**Team owners are not removed**: If a new IB policy is applied that results in two or more conflicting segments present in a Teams channel, the segments with team owners are given higher preference and other segment users are removed.</span></span> <span data-ttu-id="8de68-231">また、現時点では、他の所有者/ユーザーと競合している場合でも、チーム所有者は削除されません。</span><span class="sxs-lookup"><span data-stu-id="8de68-231">Also, at this time, team owners are not getting removed, even if they are in conflict with other owners/users.</span></span> <span data-ttu-id="8de68-232">テナント管理者と他のチャネル所有者は、競合する所有者を手動で削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8de68-232">Tenant admins and other channel owners will have to remove conflicting owners manually.</span></span>
- <span data-ttu-id="8de68-233">**テナントで許可される** セグメントの最大数: IB ポリシーを構成するときに、各テナントは最大 100 セグメントを設定できます。</span><span class="sxs-lookup"><span data-stu-id="8de68-233">**Maximum number of segments allowed in a tenant**: Each tenant can set up to 100 segments when configuring IB policies.</span></span> <span data-ttu-id="8de68-234">構成できるポリシーの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="8de68-234">There is no limit on the number of policies that can be configured.</span></span>

- <span data-ttu-id="8de68-235">**IB ポリシーは** フェデレーション ユーザーには機能しません: 外部テナントとのフェデレーションを許可する場合、それらのテナントのユーザーは IB ポリシーによって制限されません。</span><span class="sxs-lookup"><span data-stu-id="8de68-235">**IB policies don't work for federated users**: If you allow federation with external tenants, the users of those tenants won't be restricted by IB policies.</span></span> <span data-ttu-id="8de68-236">組織のユーザーが外部のフェデレーション ユーザーによって開催されたチャットまたは会議に参加する場合、IB ポリシーは組織のユーザー間の通信も制限されません。</span><span class="sxs-lookup"><span data-stu-id="8de68-236">If users of your organization join a chat or meeting organized by external federated users, then IB policies also won't restrict communication between users of your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="8de68-237">詳細情報</span><span class="sxs-lookup"><span data-stu-id="8de68-237">More information</span></span>

- <span data-ttu-id="8de68-238">IB の詳細については、「情報バリア [」を参照してください](/office365/securitycompliance/information-barriers)。</span><span class="sxs-lookup"><span data-stu-id="8de68-238">To learn more about IBs, see [Information barriers](/office365/securitycompliance/information-barriers).</span></span>

- <span data-ttu-id="8de68-239">IB ポリシーを設定するには、「情報バリアのポリシー [を定義する」を参照してください](/office365/securitycompliance/information-barriers-policies)。</span><span class="sxs-lookup"><span data-stu-id="8de68-239">To set up IB policies, see [Define policies for information barriers](/office365/securitycompliance/information-barriers-policies).</span></span>

- <span data-ttu-id="8de68-240">IB ポリシーを編集または削除するには、「情報バリア ポリシーを編集 [(または削除) する」を参照してください](/microsoft-365/compliance/information-barriers-edit-segments-policies)。</span><span class="sxs-lookup"><span data-stu-id="8de68-240">To edit or remove IB policies, see [Edit (or remove) information barrier policies](/microsoft-365/compliance/information-barriers-edit-segments-policies).</span></span>

## <a name="availability"></a><span data-ttu-id="8de68-241">使用するための条件</span><span class="sxs-lookup"><span data-stu-id="8de68-241">Availability</span></span>

- <span data-ttu-id="8de68-242">この機能は、パブリック クラウドで利用できます。2021 年 1 月に、新しいクラウドに Information Barriers GCCしました。</span><span class="sxs-lookup"><span data-stu-id="8de68-242">The feature is available in our public cloud; in January 2021, we rolled out Information Barriers in the GCC cloud.</span></span>
- <span data-ttu-id="8de68-243">この機能は、GCCH クラウドと DOD クラウドではまだ使用できません。</span><span class="sxs-lookup"><span data-stu-id="8de68-243">The feature is not yet available in the GCCH and DOD clouds.</span></span>
