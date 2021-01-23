---
title: 組織のリスト アプリを管理する
author: cichur
ms.author: v-cichur
ms.reviewer: anach,v-jasuk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: 組織内のユーザーの Teams でリスト アプリを管理する方法について学習します。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
- m365initiative-lists
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: e0fb125ede9300395e045a0c5640abd075547562
ms.sourcegitcommit: 04eba352d9e203aa9cd1282c4f4c7158a0469678
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2021
ms.locfileid: "49944612"
---
# <a name="manage-the-lists-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="4ed88-103">Microsoft Teams で組織のリスト アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="4ed88-103">Manage the Lists app for your organization in Microsoft Teams</span></span>

## <a name="overview-of-lists"></a><span data-ttu-id="4ed88-104">リストの概要</span><span class="sxs-lookup"><span data-stu-id="4ed88-104">Overview of Lists</span></span>

<span data-ttu-id="4ed88-105">Microsoft Teams のリスト アプリは、組織内のユーザーが情報を追跡し、作業を整理し、ワークフローを管理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4ed88-105">The Lists app in Microsoft Teams helps users in your organization track information, organize work, and manage workflows.</span></span> <span data-ttu-id="4ed88-106">リストを使用すると、ユーザーはカスタマイズ可能なビュー、ルール、警告を使用して、問題、資産、ルーチン、連絡先、在庫、インシデント、ローン、患者などのデータを追跡し、チームの全員の同期を維持できます。</span><span class="sxs-lookup"><span data-stu-id="4ed88-106">With Lists, users can track data such as issues, assets, routines, contacts, inventory, incidents, loans, patients, and more using customizable views, rules, and alerts to keep everyone on the team in sync.</span></span>

<span data-ttu-id="4ed88-107">Teams では、ユーザーはチャネルのタブとしてリストにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="4ed88-107">In Teams, users access Lists as a tab in a channel.</span></span> <span data-ttu-id="4ed88-108">タブ **+** ギャラリーをクリックして開き、新しいリスト アプリ タブ インスタンスをチャネルに追加して開始します。</span><span class="sxs-lookup"><span data-stu-id="4ed88-108">Click **+** to open the tab gallery and add a new Lists app tab instance to a channel to get started.</span></span>

![タブ ギャラリーのリスト アプリ](media/lists-tab.png)

<span data-ttu-id="4ed88-110">ユーザーは、新しいリストを作成したり、同じチーム内またはアクセス権を持つ別の SharePoint サイトから既存のリストを固定することができます。</span><span class="sxs-lookup"><span data-stu-id="4ed88-110">Users can create new lists or pin existing lists from within the same team or from a different SharePoint site that they have access to.</span></span> <span data-ttu-id="4ed88-111">新しいリストは、一から作成したり、組み込みのテンプレートから作成したり、既存のリストの構造に基づいて作成したり、Excel ブックからデータをインポートしたりして作成できます。</span><span class="sxs-lookup"><span data-stu-id="4ed88-111">New lists can be created from scratch, from built-in templates, based on the structure of an existing list, or by importing data from an Excel workbook.</span></span> <span data-ttu-id="4ed88-112">リスト アプリは、Teams デスクトップ、Web、モバイル クライアントで使用できます。</span><span class="sxs-lookup"><span data-stu-id="4ed88-112">The Lists app is available in Teams desktop, web, and mobile clients.</span></span>

![リスト アプリでリストを作成する方法](media/lists-create-list.png)

## <a name="templates"></a><span data-ttu-id="4ed88-114">テンプレート</span><span class="sxs-lookup"><span data-stu-id="4ed88-114">Templates</span></span>

<span data-ttu-id="4ed88-115">リスト内のテンプレートは、ユーザーの一般的な情報追跡シナリオに合わせて調整されます。</span><span class="sxs-lookup"><span data-stu-id="4ed88-115">Templates in Lists are tailored to common information tracking scenarios for users.</span></span> <span data-ttu-id="4ed88-116">各テンプレートには、定義済みのリスト構造、フォーム レイアウト、書式設定オプションがリスト ビューと詳細ビュー レベルの両方に用意され、ユーザーがすぐに使い始めることができます。</span><span class="sxs-lookup"><span data-stu-id="4ed88-116">Each template comes with a predefined list structure, form layouts, and formatting options at both a list view and a details view level to help users get started quickly.</span></span> <span data-ttu-id="4ed88-117">テンプレートを選択すると、ユーザーはリストの外観とサンプル データのプレビューを取得します。</span><span class="sxs-lookup"><span data-stu-id="4ed88-117">After selecting a template, users get a preview of what the list will look like, along with some sample data.</span></span> <span data-ttu-id="4ed88-118">次に、組織内のチームがリストで定義済みのテンプレートを使用する方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="4ed88-118">Here's some examples of how teams in your organization can use the predefined templates in Lists:</span></span>

- <span data-ttu-id="4ed88-119">問題を追跡し、問題追跡テンプレートを使用してそれらを終了します。</span><span class="sxs-lookup"><span data-stu-id="4ed88-119">Track issues and bring them to closure using the Issue tracker template.</span></span>
- <span data-ttu-id="4ed88-120">イベント日程テンプレートを使用して、すべてのイベントの詳細を整理します。</span><span class="sxs-lookup"><span data-stu-id="4ed88-120">Organize all your event details with the Event itinerary template.</span></span>
- <span data-ttu-id="4ed88-121">患者テンプレートを使用して、医療組織の医療チームの患者のニーズと状態を記録し、ケアを監視および調整します。</span><span class="sxs-lookup"><span data-stu-id="4ed88-121">Use the Patients template to record the needs and status of patients for health teams in your healthcare organization to monitor and coordinate care.</span></span>
- <span data-ttu-id="4ed88-122">ローン申請の状況を、[ローン] テンプレートで追跡します。</span><span class="sxs-lookup"><span data-stu-id="4ed88-122">Track the status of loan applications with the Loans template.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="4ed88-123">シナリオ例</span><span class="sxs-lookup"><span data-stu-id="4ed88-123">Example scenario</span></span>

<span data-ttu-id="4ed88-124">地域内でメールの並べ替えと配信を行うのは、現地の郵便会社が担当します。</span><span class="sxs-lookup"><span data-stu-id="4ed88-124">A local post office is responsible for sorting and delivering mail in their district.</span></span> <span data-ttu-id="4ed88-125">毎日の目標を確認し、お知らせを共有し、既知のインシデントについて話し合うチームのメンバーが、今朝、オフィスにいます。</span><span class="sxs-lookup"><span data-stu-id="4ed88-125">Each morning, the post office has a team huddle to review daily goals, share announcements, and discuss known incidents.</span></span>

<span data-ttu-id="4ed88-126">連絡を受け取ると、メール会社はメールを受け取り、配送ルートを開始します。</span><span class="sxs-lookup"><span data-stu-id="4ed88-126">After the huddle, mail carriers pick up their mail and start their delivery route.</span></span> <span data-ttu-id="4ed88-127">インシデントは、自動車の事故、犬関連の問題、社会不安の原因など、ルート上で発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4ed88-127">Incidents can occur along a route, for example, a vehicle accident, dog-related issue, or social unrest protest.</span></span> <span data-ttu-id="4ed88-128">メールの携帯電話会社がインシデントに遭遇すると、モバイル デバイス上の Teams を使用してインシデントの詳細を記録します。これは、チーム チャネルのリストで追跡されます。</span><span class="sxs-lookup"><span data-stu-id="4ed88-128">When mail carriers encounter an incident, they use Teams on their mobile devices to record the incident details, which are tracked in a list in the team channel.</span></span> <span data-ttu-id="4ed88-129">フィールド内のメール通信事業者を含むチームの全員が、この情報を確認し、最新の情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="4ed88-129">Everyone on the team, including mail carriers in the field, can see this information and stay informed.</span></span>

<span data-ttu-id="4ed88-130">Teams に移行する前に、メールの通信事業者は、Excel スプレッドシートに入力されたインシデントを報告するために、ハード コピーフォームを完成するために、郵便会社に戻る必要がありました。</span><span class="sxs-lookup"><span data-stu-id="4ed88-130">Before moving to Teams, mail carriers had to go back to the post office to complete a hard-copy form to report an incident which was entered in an Excel spreadsheet.</span></span> <span data-ttu-id="4ed88-131">Teams は、メール携帯電話会社に最初にモバイル機能を提供し、リストを使用して発生したインシデントを現場で報告し、インシデントの詳細をチーム メンバーと共有し、チャネルでインシデントに関する会話を行い、インシデントを解決に追い込む操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4ed88-131">Teams gives mail carriers a mobile first, experience where they can use Lists to report incidents in the field as they happen, share incident details with team members, have conversations about them on the channel, and drive incidents to resolution.</span></span>

## <a name="what-you-need-to-know-about-lists"></a><span data-ttu-id="4ed88-132">リストについて知る必要がある情報</span><span class="sxs-lookup"><span data-stu-id="4ed88-132">What you need to know about Lists</span></span>

### <a name="lists-is-available-in-every-team-and-channel"></a><span data-ttu-id="4ed88-133">リストは、すべてのチームとチャネルで利用できます</span><span class="sxs-lookup"><span data-stu-id="4ed88-133">Lists is available in every team and channel</span></span>

<span data-ttu-id="4ed88-134">リストは、すべての Teams ユーザーにプレインストールされ、すべてのチームとチャネルのタブ ギャラリーで直接利用できます。</span><span class="sxs-lookup"><span data-stu-id="4ed88-134">Lists is pre-installed for all Teams users and is available directly in the tab gallery of every team and channel.</span></span> <span data-ttu-id="4ed88-135">つまり、ユーザーは Teams アプリ ストアにアクセスしてインストールする必要が生じます。</span><span class="sxs-lookup"><span data-stu-id="4ed88-135">This means that users don't have to go to the Teams app store to install it.</span></span>

### <a name="lists-and-sharepoint"></a><span data-ttu-id="4ed88-136">リストと SharePoint</span><span class="sxs-lookup"><span data-stu-id="4ed88-136">Lists and SharePoint</span></span>

<span data-ttu-id="4ed88-137">リスト データは SharePoint Online チーム サイトに保存されます。</span><span class="sxs-lookup"><span data-stu-id="4ed88-137">Lists data is stored in the SharePoint Online team site.</span></span> <span data-ttu-id="4ed88-138">SharePoint Online が Teams とやり取りする方法の詳細については [、「SharePoint Online](SharePoint-OneDrive-interact.md)と OneDrive for Business が Teams と対話する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ed88-138">To learn more about how SharePoint Online interacts with Teams, see [How SharePoint Online and OneDrive for Business interact with Teams](SharePoint-OneDrive-interact.md).</span></span>

<span data-ttu-id="4ed88-139">SharePoint で設定されたアクセス許可は、リスト アプリで作成されたリストに適用されます。</span><span class="sxs-lookup"><span data-stu-id="4ed88-139">Permissions set in SharePoint apply to lists created in the Lists app.</span></span> <span data-ttu-id="4ed88-140">既定では、リストは属するサイトから権限を継承します。</span><span class="sxs-lookup"><span data-stu-id="4ed88-140">By default, lists inherit permissions from the site to which they belong.</span></span> <span data-ttu-id="4ed88-141">これらのアクセス許可は、リストを作成または編集できるかどうかなど、ユーザーが実行できる操作の種類に適用されます。</span><span class="sxs-lookup"><span data-stu-id="4ed88-141">These permissions govern the types of actions that users can do, such as whether they can create or edit lists.</span></span> <span data-ttu-id="4ed88-142">詳細については [、「SharePoint のアクセス許可レベル」および「SharePoint](https://docs.microsoft.com/sharepoint/understanding-permission-levels) Server のユーザー権限と権限 [レベル」を参照してください](https://docs.microsoft.com/sharepoint/sites/user-permissions-and-permission-levels)。</span><span class="sxs-lookup"><span data-stu-id="4ed88-142">To learn more, see [Permission levels in SharePoint](https://docs.microsoft.com/sharepoint/understanding-permission-levels) and [User permissions and permission levels in SharePoint Server](https://docs.microsoft.com/sharepoint/sites/user-permissions-and-permission-levels).</span></span>

<span data-ttu-id="4ed88-143">特定のシナリオでは、ユーザーがリストで実行できる操作を制限する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="4ed88-143">In certain scenarios, you may want restrict what actions users can do in lists.</span></span> <span data-ttu-id="4ed88-144">たとえば、チームのユーザーがリスト ビューを編集すると、すべてのチーム メンバーに対して変更され、チーム所有者または特定のチーム メンバーだけがリスト ビューを編集できるとします。</span><span class="sxs-lookup"><span data-stu-id="4ed88-144">For example, a person on a team edits a list view, which changes it for all team members, and you want to allow only the team owner or certain team members to edit list views.</span></span> <span data-ttu-id="4ed88-145">詳細については、「SharePoint リストまたはライブラリ [のアクセス許可をカスタマイズする」を参照してください](https://support.microsoft.com/office/customize-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782#ID0EAACAAA=Online,_2019,_2016,_2013)。</span><span class="sxs-lookup"><span data-stu-id="4ed88-145">To learn more, see [Customize permissions for a SharePoint list or library](https://support.microsoft.com/office/customize-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782#ID0EAACAAA=Online,_2019,_2016,_2013).</span></span>

> [!NOTE]
> <span data-ttu-id="4ed88-146">この時点では、チームの所有者とメンバーのアクセス許可は、リストまたはリスト アプリの動作を制御するチーム サイトのアクセス許可にリンクされるものではありません。</span><span class="sxs-lookup"><span data-stu-id="4ed88-146">At this point, owner and member permissions in a team aren't linked in any way to permissions in the team site that govern the behavior of lists or the Lists App.</span></span> <span data-ttu-id="4ed88-147">ただし、お客様からのフィードバックと利用状況に基づいて、これは製品の将来の反復について考慮されます。</span><span class="sxs-lookup"><span data-stu-id="4ed88-147">However, based on customer feedback and usage, this will be considered for a future iteration of the product.</span></span>  

### <a name="limitations"></a><span data-ttu-id="4ed88-148">制限事項</span><span class="sxs-lookup"><span data-stu-id="4ed88-148">Limitations</span></span>

<span data-ttu-id="4ed88-149">リストを使用すると、ユーザーはデスクトップ、Web、モバイルの操作環境を利用できます。</span><span class="sxs-lookup"><span data-stu-id="4ed88-149">With Lists, users get a desktop, web, and mobile experience.</span></span> <span data-ttu-id="4ed88-150">Teams モバイル クライアントのリストを使用して、ユーザーが新しいリストを作成したり、既存のリストを固定したりできないという点を知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ed88-150">It's important to know that users can't create new lists or pin existing lists using Lists on the Teams mobile client.</span></span> <span data-ttu-id="4ed88-151">Teams モバイル クライアントでリストを表示または編集するには、最初に Teams デスクトップまたは Web クライアントのリストを使用してリストを作成または追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ed88-151">To view or edit a list on the Teams mobile client, a list must first be created or added using Lists on the Teams desktop or web client.</span></span>

<span data-ttu-id="4ed88-152">ゲストはリストを作成または削除できない。</span><span class="sxs-lookup"><span data-stu-id="4ed88-152">Guests can't create or delete a list.</span></span> <span data-ttu-id="4ed88-153">既存のリストにリスト アイテムを追加したり、リスト アイテムに関する新しい会話を開始したり、リスト アイテムに関する既存の会話に返信することができます。</span><span class="sxs-lookup"><span data-stu-id="4ed88-153">They can add list items to existing lists, start new conversations about list items, and reply to existing conversations about list items.</span></span>

### <a name="lists-and-the-sharepoint-app"></a><span data-ttu-id="4ed88-154">リストと SharePoint アプリ</span><span class="sxs-lookup"><span data-stu-id="4ed88-154">Lists and the SharePoint app</span></span>

<span data-ttu-id="4ed88-155">組織内のユーザーが SharePoint アプリを使用してリストを作成した場合、それらのリストは、ユーザーからの操作を行わずにリストに自動的に移動されます。</span><span class="sxs-lookup"><span data-stu-id="4ed88-155">If users in your organization created lists using the SharePoint app, those lists will be automatically moved to Lists without any action needed from the user.</span></span> <span data-ttu-id="4ed88-156">Teams で最適で豊富なリスト統合エクスペリエンスを得る場合は、リスト アプリを使用して既存のリストを固定します。</span><span class="sxs-lookup"><span data-stu-id="4ed88-156">To get the best and richest lists integration experience in Teams, use the Lists app and pin your existing lists.</span></span>

## <a name="set-up-lists"></a><span data-ttu-id="4ed88-157">リストを設定する</span><span class="sxs-lookup"><span data-stu-id="4ed88-157">Set up Lists</span></span>

### <a name="enable-or-disable-lists-in-your-organization"></a><span data-ttu-id="4ed88-158">組織内のリストを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="4ed88-158">Enable or disable Lists in your organization</span></span>

<span data-ttu-id="4ed88-159">リストは、組織内のすべての Teams ユーザーに対して既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="4ed88-159">Lists is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="4ed88-160">Microsoft Teams 管理センターの [アプリの管理] ページ[](manage-apps.md)で、組織レベルでアプリをオフまたはオンにできます。</span><span class="sxs-lookup"><span data-stu-id="4ed88-160">You can turn off or turn on the app at the org level on the [Manage apps](manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="4ed88-161">Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの [アプリの **管理]**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="4ed88-161">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps** .</span></span>
2. <span data-ttu-id="4ed88-162">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4ed88-162">Do one of the following:</span></span>

    - <span data-ttu-id="4ed88-163">組織のリストをオフにする場合は、リスト アプリを検索して選び、[ブロック] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="4ed88-163">To turn off Lists for your organization, search for the Lists app, select it, and then click **Block**.</span></span>
    - <span data-ttu-id="4ed88-164">組織のリストを有効にする場合は、リスト アプリを検索して選び、[許可] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="4ed88-164">To turn on Lists for your organization, search for the Lists app, select it, and then click **Allow**.</span></span>

### <a name="enable-or-disable-lists-for-specific-users-in-your-organization"></a><span data-ttu-id="4ed88-165">組織内の特定のユーザーのリストを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="4ed88-165">Enable or disable Lists for specific users in your organization</span></span>

<span data-ttu-id="4ed88-166">組織内の特定のユーザーによるリストの使用を許可またはブロックするには、[アプリの管理] ページで組織の[](manage-apps.md)リストが有効になっていることを確認し、カスタム アプリのアクセス許可ポリシーを作成し、それらのユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ed88-166">To allow or block specific users in your organization from using Lists, make sure Lists is turned on for your organization on the [Manage apps](manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="4ed88-167">詳細については、「Teams でアプリ [のアクセス許可ポリシーを管理する」を参照してください](teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="4ed88-167">To learn more, see [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

## <a name="search-the-audit-log-for-list-events"></a><span data-ttu-id="4ed88-168">リスト イベントの監査ログを検索する</span><span class="sxs-lookup"><span data-stu-id="4ed88-168">Search the audit log for list events</span></span>

<span data-ttu-id="4ed88-169">リストはエンタープライズ レベルの監査で有効になっているので、セキュリティ/コンプライアンス センターの監査ログでリストとリスト アイテム&できます。</span><span class="sxs-lookup"><span data-stu-id="4ed88-169">Lists are enabled with enterprise-level auditing so you can search for lists and list item events in the audit log in the Security & Compliance Center.</span></span> <span data-ttu-id="4ed88-170">詳細については、セキュリティ/コンプライアンス センターで監査 [ログ&参照してください](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)。</span><span class="sxs-lookup"><span data-stu-id="4ed88-170">To learn more, see [Search the audit log in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span></span>

<span data-ttu-id="4ed88-171">Teams のリスト アプリに関連する監査イベントの一覧については [、SharePoint リストアクティビティを参照してください](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#sharepoint-list-activities)。</span><span class="sxs-lookup"><span data-stu-id="4ed88-171">For a list of audit events that are relevant to the Lists app in Teams, see [SharePoint list activities](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#sharepoint-list-activities).</span></span>

<span data-ttu-id="4ed88-172">監査ログを検索するには、まずセキュリティ/コンプライアンス センターで監査 [を&があります](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="4ed88-172">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="4ed88-173">監査データは、監査を有効にした時点からのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="4ed88-173">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="power-automate-power-apps-and-graph-api"></a><span data-ttu-id="4ed88-174">Power Automate、Power Apps、Graph API</span><span class="sxs-lookup"><span data-stu-id="4ed88-174">Power Automate, Power Apps, and Graph API</span></span>

<span data-ttu-id="4ed88-175">リストでは [、ワークフロー用の Power Automate](https://docs.microsoft.com/power-automate/flow-types) とリスト [フォーム用の Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form) がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="4ed88-175">Lists supports [Power Automate](https://docs.microsoft.com/power-automate/flow-types) for workflows and [Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form) for list forms.</span></span> <span data-ttu-id="4ed88-176">開発者はリスト API を [使用して、Microsoft](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest) Graph を介してソースとしてリスト データを接続できます。</span><span class="sxs-lookup"><span data-stu-id="4ed88-176">Developers can use the [Lists API](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest) to connect list data as a source through Microsoft Graph.</span></span>

## <a name="give-feedback-or-report-an-issue"></a><span data-ttu-id="4ed88-177">フィードバックを送信する、または問題を報告する</span><span class="sxs-lookup"><span data-stu-id="4ed88-177">Give feedback or report an issue</span></span>
  
<span data-ttu-id="4ed88-178">フィードバックを送信したり、問題を報告したりするには、Teams の左側のナビゲーションの下部にある [ヘルプ] をクリックし、[問題の報告] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4ed88-178">To send us feedback or report an issue, click **Help** near the bottom of the left navigation in Teams, and then select **Report a problem**.</span></span> <span data-ttu-id="4ed88-179">[ **リスト]** を選択し、発生している問題に関するフィードバックまたは詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="4ed88-179">Select **Lists**, and then enter your feedback or details about the issue you're experiencing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4ed88-180">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ed88-180">Related topics</span></span>

- [<span data-ttu-id="4ed88-181">ヘルプ ドキュメントの一覧</span><span class="sxs-lookup"><span data-stu-id="4ed88-181">Lists help documentation</span></span>](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Lists)
