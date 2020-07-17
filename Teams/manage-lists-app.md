---
title: 組織のリストアプリを管理する
author: LanaChin
ms.author: v-lanac
ms.reviewer: anach,v-jasuk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 組織内のユーザーのために Teams のリストアプリを管理する方法について説明します。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: b7e237ffd041c2207516b714147d555b3a1b9043
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138402"
---
# <a name="manage-the-lists-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="e9d55-103">Microsoft Teams で組織のリストアプリを管理する</span><span class="sxs-lookup"><span data-stu-id="e9d55-103">Manage the Lists app for your organization in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview-of-lists"></a><span data-ttu-id="e9d55-104">リストの概要</span><span class="sxs-lookup"><span data-stu-id="e9d55-104">Overview of Lists</span></span>

<span data-ttu-id="e9d55-105">Microsoft Teams のリストアプリは、組織内のユーザーが情報を追跡したり、作業を整理したり、ワークフローを管理したりするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e9d55-105">The Lists app in Microsoft Teams helps users in your organization track information, organize work, and manage workflows.</span></span> <span data-ttu-id="e9d55-106">リストを使用すると、問題、資産、ルーチン、連絡先、在庫、インシデント、ローン、患者などのデータを、カスタマイズ可能なビュー、ルール、およびアラートを使って追跡できます。</span><span class="sxs-lookup"><span data-stu-id="e9d55-106">With Lists, users can track data such as issues, assets, routines, contacts, inventory, incidents, loans, patients, and more using customizable views, rules, and alerts to keep everyone on the team in sync.</span></span>

<span data-ttu-id="e9d55-107">Teams では、ユーザーはリストをチャネル内のタブとしてアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e9d55-107">In Teams, users access Lists as a tab in a channel.</span></span> <span data-ttu-id="e9d55-108">クリック **+** するとタブギャラリーが開き、新しいリストアプリのタブインスタンスをチャネルに追加して、開始することができます。</span><span class="sxs-lookup"><span data-stu-id="e9d55-108">Click **+** to open the tab gallery and add a new Lists app tab instance to a channel to get started.</span></span> 

![タブギャラリーのリストアプリのスクリーンショット](media/lists-tab.png)

<span data-ttu-id="e9d55-110">ユーザーは、同じチーム内から、またはアクセス権のある別の SharePoint サイトから、新しいリストを作成したり、既存のリストをピン留めしたりできます。</span><span class="sxs-lookup"><span data-stu-id="e9d55-110">Users can create new lists or pin existing lists from within the same team or from a different SharePoint site that they have access to.</span></span> <span data-ttu-id="e9d55-111">新しいリストは、組み込みのテンプレートから、既存のリストの構造に基づいて、または Excel ブックからデータをインポートすることによって、最初から作成することができます。</span><span class="sxs-lookup"><span data-stu-id="e9d55-111">New lists can be created from scratch, from built-in templates, based on the structure of an existing list, or by importing data from an Excel workbook.</span></span> <span data-ttu-id="e9d55-112">リストアプリは、Teams のデスクトップ、web、モバイルクライアントで利用できます。</span><span class="sxs-lookup"><span data-stu-id="e9d55-112">The Lists app is available in Teams desktop, web, and mobile clients.</span></span>

![リストアプリでリストを作成する方法を示すスクリーンショット](media/lists-create-list.png)

## <a name="templates"></a><span data-ttu-id="e9d55-114">Templates</span><span class="sxs-lookup"><span data-stu-id="e9d55-114">Templates</span></span>

<span data-ttu-id="e9d55-115">リスト内のテンプレートは、ユーザー向けの一般的な情報管理シナリオに合わせてカスタマイズされます。</span><span class="sxs-lookup"><span data-stu-id="e9d55-115">Templates in Lists are tailored to common information tracking scenarios for users.</span></span> <span data-ttu-id="e9d55-116">各テンプレートには、事前に定義されたリスト構造、フォームレイアウト、および書式設定オプションが用意されています。リストビューと詳細表示レベルでは、ユーザーがすぐに使い始めるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e9d55-116">Each template comes with a predefined list structure, form layouts, and formatting options at both a list view and a details view level to help users get started quickly.</span></span> <span data-ttu-id="e9d55-117">テンプレートを選択すると、リストがどのように表示されるか、サンプルデータと共に、ユーザーにプレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9d55-117">After selecting a template, users get a preview of what the list will look like, along with some sample data.</span></span> <span data-ttu-id="e9d55-118">組織内のチームがリストで定義済みのテンプレートを使用する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e9d55-118">Here's some examples of how teams in your organization can use the predefined templates in Lists:</span></span>

- <span data-ttu-id="e9d55-119">問題を追跡して、問題追跡テンプレートを使用して、問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="e9d55-119">Track issues and bring them to closure using the Issue tracker template.</span></span>
- <span data-ttu-id="e9d55-120">すべてのイベントの詳細をイベント旅程テンプレートで整理します。</span><span class="sxs-lookup"><span data-stu-id="e9d55-120">Organize all your event details with the Event itinerary template.</span></span>
- <span data-ttu-id="e9d55-121">患者のテンプレートを使用して、患者のニーズと状態を記録し、医療機関の治療チームがお客さまの治療を監視および調整できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e9d55-121">Use the Patients template to record the needs and status of patients so care teams in your healthcare organization can monitor and coordinate care.</span></span>
- <span data-ttu-id="e9d55-122">ローン申請の状態をローンテンプレートで追跡します。</span><span class="sxs-lookup"><span data-stu-id="e9d55-122">Track the status of loan applications with the Loans template.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="e9d55-123">シナリオ例</span><span class="sxs-lookup"><span data-stu-id="e9d55-123">Example scenario</span></span>

<span data-ttu-id="e9d55-124">地元の投稿会社は、地域内でのメールの並べ替えと配信を担当します。</span><span class="sxs-lookup"><span data-stu-id="e9d55-124">A local post office is responsible for sorting and delivering mail in their district.</span></span> <span data-ttu-id="e9d55-125">毎朝、office の投稿には、毎日の目標を確認し、お知らせを共有し、既知の問題について話し合うためのチーム huddle があります。</span><span class="sxs-lookup"><span data-stu-id="e9d55-125">Each morning, the post office has a team huddle to review daily goals, share announcements, and discuss known incidents.</span></span>

<span data-ttu-id="e9d55-126">Huddle は、メールキャリアがメールを受け取り、配信ルートを開始します。</span><span class="sxs-lookup"><span data-stu-id="e9d55-126">After the huddle, mail carriers pick up their mail and start their delivery route.</span></span> <span data-ttu-id="e9d55-127">障害は、自動車事故、犬関連の問題、ソーシャル unrest 受取拒否など、ルートに沿って発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e9d55-127">Incidents can occur along a route, for example, a vehicle accident, dog-related issue, or social unrest protest.</span></span> <span data-ttu-id="e9d55-128">メールキャリアでインシデントが発生した場合は、モバイルデバイスで Teams を使って、チームチャネルのリストで追跡されたインシデントの詳細を記録します。</span><span class="sxs-lookup"><span data-stu-id="e9d55-128">When mail carriers encounter an incident, they use Teams on their mobile devices to record the incident details, which are tracked in a list in the team channel.</span></span> <span data-ttu-id="e9d55-129">フィールドのメールキャリアを含む、チームの全員がこの情報を表示して、最新情報を入手できます。</span><span class="sxs-lookup"><span data-stu-id="e9d55-129">Everyone on the team, including mail carriers in the field, can see this information and stay informed.</span></span>

<span data-ttu-id="e9d55-130">チームに移行する前に、メールの運送会社は、Excel スプレッドシートに入力されたインシデントを報告するために、ハードコピーフォームを完成させるために、office のポストオフィスに戻っている必要がありました。</span><span class="sxs-lookup"><span data-stu-id="e9d55-130">Before moving to Teams, mail carriers had to go back to the post office to complete a hard-copy form to report an incident which was entered in an Excel spreadsheet.</span></span> <span data-ttu-id="e9d55-131">チームでは、メールキャリアを携帯電話にすることができます。これは、リストを使って、発生時にフィールドのインシデントを報告し、チームメンバーとインシデントの詳細を共有し、問題を解決するための問題を解決することを意図しています。</span><span class="sxs-lookup"><span data-stu-id="e9d55-131">Teams gives mail carriers a mobile first, experience where they can use Lists to report incidents in the field as they happen, share incident details with team members, have conversations about them on the channel, and drive incidents to resolution.</span></span>

## <a name="what-you-need-to-know-about-lists"></a><span data-ttu-id="e9d55-132">リストについて知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="e9d55-132">What you need to know about Lists</span></span>

### <a name="lists-is-available-in-every-team-and-channel"></a><span data-ttu-id="e9d55-133">すべてのチームおよびチャネルでリストを使用できます</span><span class="sxs-lookup"><span data-stu-id="e9d55-133">Lists is available in every team and channel</span></span>

<span data-ttu-id="e9d55-134">リストはすべての Teams ユーザー用にプレインストールされており、すべてのチームとチャネルのタブギャラリーで直接利用できます。</span><span class="sxs-lookup"><span data-stu-id="e9d55-134">Lists is pre-installed for all Teams users and is available directly in the tab gallery of every team and channel.</span></span> <span data-ttu-id="e9d55-135">これは、ユーザーが Teams app store に移動してインストールする必要がないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="e9d55-135">This means that users don't have to go to the Teams app store to install it.</span></span>

### <a name="lists-and-sharepoint"></a><span data-ttu-id="e9d55-136">リストと SharePoint</span><span class="sxs-lookup"><span data-stu-id="e9d55-136">Lists and SharePoint</span></span>

<span data-ttu-id="e9d55-137">リストデータは、SharePoint Online チームサイトに保存されます。</span><span class="sxs-lookup"><span data-stu-id="e9d55-137">Lists data is stored in the SharePoint Online team site.</span></span> <span data-ttu-id="e9d55-138">SharePoint Online と Teams の相互作用の詳細については、「 [Sharepoint online と OneDrive For business が teams を操作する方法](SharePoint-OneDrive-interact.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9d55-138">To learn more about how SharePoint Online interacts with Teams, see [How SharePoint Online and OneDrive for Business interact with Teams](SharePoint-OneDrive-interact.md).</span></span>

<span data-ttu-id="e9d55-139">SharePoint で設定した権限は、リストアプリで作成されたリストに適用されます。</span><span class="sxs-lookup"><span data-stu-id="e9d55-139">Permissions set in SharePoint apply to lists created in the Lists app.</span></span> <span data-ttu-id="e9d55-140">既定では、リストは、所属するサイトから権限を継承します。</span><span class="sxs-lookup"><span data-stu-id="e9d55-140">By default, lists inherit permissions from the site to which they belong.</span></span> <span data-ttu-id="e9d55-141">これらのアクセス許可は、リストを作成または編集できるかどうかなど、ユーザーが実行できる操作の種類を制御します。</span><span class="sxs-lookup"><span data-stu-id="e9d55-141">These permissions govern the types of actions that users can do, such as whether they can create or edit lists.</span></span> <span data-ttu-id="e9d55-142">詳細については、「sharepoint[のアクセス許可レベル](https://docs.microsoft.com/sharepoint/understanding-permission-levels)」および「 [sharepoint Server でのユーザーのアクセス許可レベル](https://docs.microsoft.com/sharepoint/sites/user-permissions-and-permission-levels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9d55-142">To learn more, see [Permission levels in SharePoint](https://docs.microsoft.com/sharepoint/understanding-permission-levels) and [User permissions and permission levels in SharePoint Server](https://docs.microsoft.com/sharepoint/sites/user-permissions-and-permission-levels).</span></span>

<span data-ttu-id="e9d55-143">特定のシナリオでは、ユーザーがリストで実行できる操作を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="e9d55-143">In certain scenarios, you may want restrict what actions users can do in lists.</span></span> <span data-ttu-id="e9d55-144">たとえば、チームのユーザーがリストビューを編集して、すべてのチームメンバーに対してそれを変更し、チーム所有者または特定のチームメンバーのみがリストビューを編集できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e9d55-144">For example, a person on a team edits a list view, which changes it for all team members, and you want to allow only the team owner or certain team members to edit list views.</span></span> <span data-ttu-id="e9d55-145">詳細については、「 [SharePoint リストまたはライブラリの権限をカスタマイズ](https://support.microsoft.com/office/customize-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782#ID0EAACAAA=Online,_2019,_2016,_2013)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9d55-145">To learn more, see [Customize permissions for a SharePoint list or library](https://support.microsoft.com/office/customize-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782#ID0EAACAAA=Online,_2019,_2016,_2013).</span></span>

> [!NOTE]
> <span data-ttu-id="e9d55-146">この時点では、チームの所有者とメンバーのアクセス許可は、リストアプリまたはリストアプリの動作を管理するチームサイトのアクセス許可にリンクされません。</span><span class="sxs-lookup"><span data-stu-id="e9d55-146">At this point, owner and member permissions in a team aren't linked in any way to permissions in the team site that govern the behavior of lists or the Lists App.</span></span> <span data-ttu-id="e9d55-147">ただし、お客様のフィードバックと使用状況に基づいて、この製品は今後のイテレーションで考慮されます。</span><span class="sxs-lookup"><span data-stu-id="e9d55-147">However, based on customer feedback and usage, this will be considered for a future iteration of the product.</span></span>  

### <a name="limitations"></a><span data-ttu-id="e9d55-148">伴う</span><span class="sxs-lookup"><span data-stu-id="e9d55-148">Limitations</span></span>

<span data-ttu-id="e9d55-149">リストを使用すると、ユーザーはデスクトップ、web、モバイル環境を利用できます。</span><span class="sxs-lookup"><span data-stu-id="e9d55-149">With Lists, users get a desktop, web, and mobile experience.</span></span> <span data-ttu-id="e9d55-150">ユーザーは、チームのモバイルクライアントのリストを使って、新しいリストを作成したり、既存のリストをピン留めしたりすることはできないことを知っておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="e9d55-150">It's important to know that users can't create new lists or pin existing lists using Lists on the Teams mobile client.</span></span> <span data-ttu-id="e9d55-151">Teams モバイルクライアントでリストを表示または編集するには、まず Teams のデスクトップまたは web クライアントのリストを使用してリストを作成または追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d55-151">To view or edit a list on the Teams mobile client, a list must first be created or added using Lists on the Teams desktop or web client.</span></span>

<span data-ttu-id="e9d55-152">[プライベートチャネル](private-channels.md)のゲストは、リストを作成または削除したり、リストアイテムに関する新しい会話を開始したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e9d55-152">Guests in [private channels](private-channels.md) can't create or delete a list or start a new conversation about a list item.</span></span> <span data-ttu-id="e9d55-153">リストアイテムを既存のリストに追加したり、リストアイテムに関する既存の会話に返信したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="e9d55-153">They can add list items to existing lists and reply to an existing conversations about a list item.</span></span> <span data-ttu-id="e9d55-154">これらの制限は、プライベートチャネルにのみ適用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e9d55-154">Keep in mind that these limitations apply only to private channels.</span></span>

### <a name="lists-and-the-sharepoint-app"></a><span data-ttu-id="e9d55-155">リストと SharePoint アプリ</span><span class="sxs-lookup"><span data-stu-id="e9d55-155">Lists and the SharePoint app</span></span>

<span data-ttu-id="e9d55-156">組織内のユーザーが SharePoint アプリを使用してリストを作成した場合、ユーザーからのアクションを必要とせずに、リストに自動的に移動されます。</span><span class="sxs-lookup"><span data-stu-id="e9d55-156">If users in your organization created lists using the SharePoint app, those lists will be automatically moved to Lists without any action needed from the user.</span></span> <span data-ttu-id="e9d55-157">Teams で最も機能が豊富なリストの統合エクスペリエンスを実現するには、Lists アプリを使用して、既存のリストをピン留めします。</span><span class="sxs-lookup"><span data-stu-id="e9d55-157">To get the best and richest lists integration experience in Teams, use the Lists app and pin your existing lists.</span></span>

## <a name="set-up-lists"></a><span data-ttu-id="e9d55-158">リストを設定する</span><span class="sxs-lookup"><span data-stu-id="e9d55-158">Set up Lists</span></span>

### <a name="enable-or-disable-lists-in-your-organization"></a><span data-ttu-id="e9d55-159">組織内のリストを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="e9d55-159">Enable or disable Lists in your organization</span></span>

<span data-ttu-id="e9d55-160">リストは、組織内のすべての Teams ユーザーに対して既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="e9d55-160">Lists is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="e9d55-161">Microsoft Teams 管理センターの [[アプリの管理](manage-apps.md)] ページで、組織レベルでアプリをオンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e9d55-161">You can turn off or turn on the app at the org level on the [Manage apps](manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="e9d55-162">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**の管理] に移動  >  **Manage apps**します。</span><span class="sxs-lookup"><span data-stu-id="e9d55-162">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps** .</span></span>
2. <span data-ttu-id="e9d55-163">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e9d55-163">Do one of the following:</span></span>

    - <span data-ttu-id="e9d55-164">組織のリストをオフにするには、リストアプリを検索して選択し、[**ブロック**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9d55-164">To turn off Lists for your organization, search for the Lists app, select it, and then click **Block**.</span></span>
    - <span data-ttu-id="e9d55-165">組織のリストを有効にするには、リストアプリを検索して選択し、[**許可**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9d55-165">To turn on Lists for your organization, search for the Lists app, select it, and then click **Allow**.</span></span>

### <a name="enable-or-disable-lists-for-specific-users-in-your-organization"></a><span data-ttu-id="e9d55-166">組織内の特定のユーザーのリストを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="e9d55-166">Enable or disable Lists for specific users in your organization</span></span>

<span data-ttu-id="e9d55-167">組織内の特定のユーザーによるリストの使用を許可またはブロックするには、[[アプリの管理](manage-apps.md)] ページで組織のリストが有効になっていることを確認してから、カスタムのアプリのアクセス許可ポリシーを作成して、それらのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e9d55-167">To allow or block specific users in your organization from using Lists, make sure Lists is turned on for your organization on the [Manage apps](manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="e9d55-168">詳細については、「 [Teams でアプリのアクセス許可ポリシーを管理](teams-app-permission-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9d55-168">To learn more, see [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

## <a name="search-the-audit-log-for-list-events"></a><span data-ttu-id="e9d55-169">監査ログでリストイベントを検索する</span><span class="sxs-lookup"><span data-stu-id="e9d55-169">Search the audit log for list events</span></span>

<span data-ttu-id="e9d55-170">エンタープライズレベルの監査ではリストが有効になっているため、セキュリティ & コンプライアンスセンターの監査ログでリストとリストアイテムのイベントを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="e9d55-170">Lists are enabled with enterprise-level auditing so you can search for lists and list item events in the audit log in the Security & Compliance Center.</span></span> <span data-ttu-id="e9d55-171">詳細については、「[セキュリティ & コンプライアンスセンターで監査ログを検索](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9d55-171">To learn more, see [Search the audit log in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span></span>

<span data-ttu-id="e9d55-172">Teams のリストアプリに関連する監査イベントの一覧については、「 [SharePoint リストアクティビティ](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#sharepoint-list-activities)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e9d55-172">For a list of audit events that are relevant to the Lists app in Teams, see [SharePoint list activities](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#sharepoint-list-activities).</span></span>

<span data-ttu-id="e9d55-173">監査ログを検索する前に、まず[セキュリティ & コンプライアンスセンター](https://protection.office.com)で監査を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d55-173">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="e9d55-174">監査データは、監査を有効にした時点でのみ利用可能であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e9d55-174">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="power-automate-power-apps-and-graph-api"></a><span data-ttu-id="e9d55-175">Power オートメーション、Power Apps、Graph API</span><span class="sxs-lookup"><span data-stu-id="e9d55-175">Power Automate, Power Apps, and Graph API</span></span>

<span data-ttu-id="e9d55-176">リストフォームのワークフローと[Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form)の[power オートメーション](https://preview.flow.microsoft.comconnectors/shared_sharepointonline/?slug=sharepoint)をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e9d55-176">Lists supports [Power Automate](https://preview.flow.microsoft.comconnectors/shared_sharepointonline/?slug=sharepoint) for workflows and [Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form) for list forms.</span></span> <span data-ttu-id="e9d55-177">開発者は、 [LISTS API](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest)を使用して、リストデータをソースとして Microsoft Graph で接続できます。</span><span class="sxs-lookup"><span data-stu-id="e9d55-177">Developers can use the [Lists API](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest) to connect list data as a source through Microsoft Graph.</span></span>

## <a name="give-feedback-or-report-an-issue"></a><span data-ttu-id="e9d55-178">フィードバックを送信する、または問題を報告する</span><span class="sxs-lookup"><span data-stu-id="e9d55-178">Give feedback or report an issue</span></span>
  
<span data-ttu-id="e9d55-179">フィードバックを送信したり、問題を報告したりするには、Teams の左側のナビゲーションの下部にある [**ヘルプ**] をクリックして、[**問題の報告**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e9d55-179">To send us feedback or report an issue, click **Help** near the bottom of the left navigation in Teams, and then select **Report a problem**.</span></span> <span data-ttu-id="e9d55-180">[**リスト**] を選択し、お客様のフィードバックまたは発生した問題に関する詳細情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e9d55-180">Select **Lists**, and then enter your feedback or details about the issue you're experiencing.</span></span>
