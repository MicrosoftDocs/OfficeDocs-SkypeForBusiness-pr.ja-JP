---
title: Teams における承認アプリケーションの利用の可否
author: cichur
ms.author: v-cichur
ms.reviewer: farhazk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Microsoft Teams で承認アプリケーションを使用する方法について説明します。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 127fc2831e58e7ddea152c7754015a9126390ecc
ms.sourcegitcommit: 5a738cbb96f09edd8c3779f9385bc9ed126e3001
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2021
ms.locfileid: "52212170"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="6c457-103">Teams 承認アプリの利用の可否</span><span class="sxs-lookup"><span data-stu-id="6c457-103">Teams Approvals app availability</span></span>

<span data-ttu-id="6c457-104">Microsoft Teams ユーザーは、個人用アプリとして承認アプリを利用することができます。</span><span class="sxs-lookup"><span data-stu-id="6c457-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="6c457-105">承認アプリは、Teams 内の構造化された承認と構造化されていない承認の両方に対して、監査、コンプライアンス、説明責任、およびワークフローを簡単にする方法を提供します。 </span><span class="sxs-lookup"><span data-stu-id="6c457-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![承認アプリを表示する](media/approvals-selection.png)

<span data-ttu-id="6c457-107">ユーザーは承認アプリをピン留めしてメニュー バーに保存できます。</span><span class="sxs-lookup"><span data-stu-id="6c457-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![PIN オプションを使用する承認アプリを表示する](media/approvalApp-pin.png)

<span data-ttu-id="6c457-109">承認アプリから最初の承認が作成されると、既定の共通データ サービス (CDS) 環境にて承認ソリューションがプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="6c457-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="6c457-110">承認アプリから作成された承認は、既定の CDS 環境に保存されます。</span><span class="sxs-lookup"><span data-stu-id="6c457-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="6c457-111">この記事では、承認アプリの要件と役割について説明します。</span><span class="sxs-lookup"><span data-stu-id="6c457-111">This article describes the Approvals app requirements and roles.</span></span>

> [!NOTE]
> <span data-ttu-id="6c457-112">この機能は、Government Community Cloud (GCC)、Government Community Cloud High (GCCH)、および国防総省 (DOD) ユーザーにはまだリリースされていません。</span><span class="sxs-lookup"><span data-stu-id="6c457-112">This feature hasn't been released to Government Community Cloud (GCC), Government Community Cloud High (GCCH), and Department of Defense (DOD) users yet.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="6c457-113">必要なアクセス許可とライセンス</span><span class="sxs-lookup"><span data-stu-id="6c457-113">Required permissions and licenses</span></span>

<span data-ttu-id="6c457-114">承認アプリを使用するには、次のアイテムに対する権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="6c457-114">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="6c457-115">Microsoft CDS データベースを作成する権限。</span><span class="sxs-lookup"><span data-stu-id="6c457-115">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="6c457-116">[flow.microsoft.com](https://flow.microsoft.com/) のアカウント </span><span class="sxs-lookup"><span data-stu-id="6c457-116">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="6c457-117">ターゲット環境における管理者の役割。</span><span class="sxs-lookup"><span data-stu-id="6c457-117">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="6c457-118">[Power Automate](/power-automate/get-started-approvals)、Office 365、または Dynamics 365 のライセンス。</span><span class="sxs-lookup"><span data-stu-id="6c457-118">License for a [Power Automate](/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

- <span data-ttu-id="6c457-119">ユーザーが新しい承認テンプレートを設定するには、Microsoft Forms のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="6c457-119">License for Microsoft Forms is required for users to set up new approval templates.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="6c457-120">CDS を使用するストレージ</span><span class="sxs-lookup"><span data-stu-id="6c457-120">Storage with CDS</span></span>

<span data-ttu-id="6c457-121">共通データ モデル (CDM) は、CDS のビジネス アプリケーションや分析アプリケーションで使用される共有データ言語です。</span><span class="sxs-lookup"><span data-stu-id="6c457-121">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="6c457-122">これは、Microsoft とそのパートナーによって公開された、一連の標準化された拡張可能なデータ スキーマで構成されており、アプリケーションとビジネス プロセス全体でデータとその意味の一貫性を実現します。</span><span class="sxs-lookup"><span data-stu-id="6c457-122">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="6c457-123">[Microsoft Power Platform の共通データ モデル](/power-automate/get-started-approvals)の詳細については、以下をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6c457-123">Learn more about the [Common Data Model of the Microsoft Power Platform](/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="6c457-124">[承認ワークフロー](/power-automate/modern-approvals)の詳細。</span><span class="sxs-lookup"><span data-stu-id="6c457-124">Learn more about the [Approval workflow](/power-automate/modern-approvals).</span></span>

<span data-ttu-id="6c457-125">テンプレートから作成された承認では、タイトル、詳細、テンプレート ID など、CDS にデータが保存されます。</span><span class="sxs-lookup"><span data-stu-id="6c457-125">Approvals that are created from a template still store data in CDS, such as their title, details, template ID, and more.</span></span> <span data-ttu-id="6c457-126">承認要求で送信された応答は、フォームに格納されます。</span><span class="sxs-lookup"><span data-stu-id="6c457-126">Responses that are submitted on the approval request are stored in Forms.</span></span> <span data-ttu-id="6c457-127">Microsoft Forms の  [データ ストレージの詳細については、 を参照してください](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe)。</span><span class="sxs-lookup"><span data-stu-id="6c457-127">Learn more about  [Data storage for Microsoft Forms](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe).</span></span>

>[!Note]
><span data-ttu-id="6c457-128">Microsoft Forms サイトでフォーム テンプレートを削除すると、承認テンプレートが破損し、ユーザーは要求を開始できます。</span><span class="sxs-lookup"><span data-stu-id="6c457-128">If you delete the Form template on the Microsoft Forms site, it will break your Approval template and users will not be able to start the request.</span></span> <span data-ttu-id="6c457-129">Microsoft Forms で削除された承認テンプレートを開こうとすると、ユーザーに "CDB TableNotFound" というエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c457-129">Users will get an error "CDB TableNotFound" when trying to open an Approval template that has been deleted on Microsoft Forms.</span></span>

<span data-ttu-id="6c457-130">承認テンプレートは、Microsoft 内部でのみ内部的に使用Storage準拠しているストレージ プラットフォームである、2013 年 3 月 1 日に保存されます。</span><span class="sxs-lookup"><span data-stu-id="6c457-130">The approval templates are stored in Substrate Data Storage (SDS), which is a compliant storage platform used internally only inside Microsoft.</span></span> <span data-ttu-id="6c457-131">組織スコープのテンプレートは SDS の "テナント シャード" に格納され、チームスコープテンプレートは SDS の "グループ シャード" に格納されます。</span><span class="sxs-lookup"><span data-stu-id="6c457-131">The organization-scoped templates are stored in “tenant shard” of SDS, and team-scoped templates are stored in “group shards” of SDS.</span></span> <span data-ttu-id="6c457-132">つまり、組織スコープのテンプレートは、テナントとチーム スコープのテンプレートの同じ有効期間を共有し、チームの同じ有効期間を共有します。</span><span class="sxs-lookup"><span data-stu-id="6c457-132">This means that the org-scoped templates share the same lifetime of the tenant and team-scoped templates share the same lifetime of the team.</span></span> <span data-ttu-id="6c457-133">そのため、チームを完全に削除すると、関連するテンプレートが削除されます。</span><span class="sxs-lookup"><span data-stu-id="6c457-133">So, permanently deleting the team deletes the related templates.</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="6c457-134">Teams アプリの権限の承認</span><span class="sxs-lookup"><span data-stu-id="6c457-134">Approvals Teams app permissions</span></span>

<span data-ttu-id="6c457-135">Teams アプリの承認では、次の機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6c457-135">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="6c457-136">メッセージやデータを受信します。</span><span class="sxs-lookup"><span data-stu-id="6c457-136">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="6c457-137">メッセージと通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="6c457-137">Send you messages and notifications.</span></span>

- <span data-ttu-id="6c457-138">Teams が提供するヘッダーを必要とすることなく、個人用アプリとダイアログをレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="6c457-138">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="6c457-139">[名前]、[電子メールアドレス]、[会社名]、[優先する言語] などの個人用プロフィール情報にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="6c457-139">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="6c457-140">チーム メンバーがチャネルで提供するメッセージとデータを受信します。</span><span class="sxs-lookup"><span data-stu-id="6c457-140">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="6c457-141">チャネルでメッセージと通知を送信する。</span><span class="sxs-lookup"><span data-stu-id="6c457-141">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="6c457-142">チームの情報にアクセスする:</span><span class="sxs-lookup"><span data-stu-id="6c457-142">Access your team's information:</span></span>
  - <span data-ttu-id="6c457-143">チーム名</span><span class="sxs-lookup"><span data-stu-id="6c457-143">team name</span></span>
  - <span data-ttu-id="6c457-144">チャネル リスト</span><span class="sxs-lookup"><span data-stu-id="6c457-144">channel list</span></span>
  - <span data-ttu-id="6c457-145">名簿 (チーム メンバーの名前とメール アドレス)。</span><span class="sxs-lookup"><span data-stu-id="6c457-145">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="6c457-146">チームの情報を使用してメンバーに連絡します。</span><span class="sxs-lookup"><span data-stu-id="6c457-146">Use the team's information to contact them.</span></span>

<span data-ttu-id="6c457-147">承認テンプレートのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="6c457-147">Approval Template Permissions</span></span>

- <span data-ttu-id="6c457-148">すべてのチーム所有者は、自分が所有するチームの承認テンプレートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="6c457-148">All team owners can create an approval template for teams that they own.</span></span>

- <span data-ttu-id="6c457-149">管理者が初めて組織全体のテンプレートを作成すると、グローバル管理者やチームのサービス管理者を含む、テナントのすべての管理者用に新しい Teams チームが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="6c457-149">When an Admin creates a template for their entire organization for the first time, it will automatically create a new Teams team for all admins of the tenant, including the global and Team’s service admins.</span></span> <span data-ttu-id="6c457-150">これらの管理者はチームの所有者として追加され、組織のテンプレートを共同管理できます。</span><span class="sxs-lookup"><span data-stu-id="6c457-150">These admins will be added as owners of the team, so they can co-manage organizational templates.</span></span> <span data-ttu-id="6c457-151">チームの作成後に組織に新しい管理者を手動でチーム所有者として追加して、組織全体のテンプレートを管理する権限を同じに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c457-151">Admins that are new to the organization after the team has been created need to be manually added as team owners so they have the same permissions to manage organization-wide templates.</span></span>

> [!Note]
> <span data-ttu-id="6c457-152">管理者がチームを削除した場合、Azure Active Directory (AAD) ポータル内でチームを復元して、関連するデータを復元できます。</span><span class="sxs-lookup"><span data-stu-id="6c457-152">If an admin deletes the team, you have one month to restore it within the Azure Active Directory (AAD) portal to restore all related data.</span></span> <span data-ttu-id="6c457-153">1 か月後、または管理者がごみ箱内でこのチームを削除すると、関連するデータはすべて失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6c457-153">After one month, or if the admin deletes this team within the recycle bin, you will lose all the related data.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="6c457-154">承認アプリを無効にする</span><span class="sxs-lookup"><span data-stu-id="6c457-154">Disable the Approvals app</span></span>

<span data-ttu-id="6c457-155">承認アプリは既定で利用可能です。</span><span class="sxs-lookup"><span data-stu-id="6c457-155">The Approvals app is available by default.</span></span> <span data-ttu-id="6c457-156">Teams 管理センターでアプリを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="6c457-156">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="6c457-157">Teams 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="6c457-157">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="6c457-158">［**Teams アプリ**］ を開き、［**アプリの管理**］ を選択します。</span><span class="sxs-lookup"><span data-stu-id="6c457-158">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="6c457-159">承認アプリを検索します。</span><span class="sxs-lookup"><span data-stu-id="6c457-159">Search for the Approvals app.</span></span>

     ![強調表示されている [Teams アプリ] > [アプリの管理] を使用して、管理センター ナビゲーションを表示する](media/manage-approval-apps.png)

  4. <span data-ttu-id="6c457-161">[承認] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6c457-161">Select Approvals.</span></span>

  5. <span data-ttu-id="6c457-162">切り替えを選択して、組織のアプリを無効にします。</span><span class="sxs-lookup"><span data-stu-id="6c457-162">Select the toggle to disable the app for your organization.</span></span>

     ![承認アプリの詳細を表示する](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="6c457-164">アイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="6c457-164">Retention policy</span></span>

<span data-ttu-id="6c457-165">承認アプリから作成された承認は既定の CDS 環境に保存されます。現時点では、バックアップはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="6c457-165">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="6c457-166">詳細については、「[環境のバックアップと復元の方法Power Platform \|Microsoft Docs](/power-platform/admin/backup-restore-environments)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6c457-166">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span></span>

<span data-ttu-id="6c457-167">チーム所有者が Microsoft Forms Web アプリの [削除済みフォーム] タブからデータをクリーンアップするまで、フォームに保存されているデータは削除されません。</span><span class="sxs-lookup"><span data-stu-id="6c457-167">Data stored in Forms will not be deleted until the team owners clean it up from the **deleted forms** tab in the Microsoft Forms web app.</span></span>

## <a name="data-limitations"></a><span data-ttu-id="6c457-168">データの制限事項</span><span class="sxs-lookup"><span data-stu-id="6c457-168">Data limitations</span></span>

<span data-ttu-id="6c457-169">各チームには最大 400 の承認テンプレートを含め、各テンプレートは Microsoft Forms の現在の機能に基づいて最大 50,000 件の要求を収集できます。</span><span class="sxs-lookup"><span data-stu-id="6c457-169">Each team can contain at most 400 approvals templates, and each template can collect a maximum of 50,000 requests based on the current capability in Microsoft Forms.</span></span>

## <a name="auditing"></a><span data-ttu-id="6c457-170">監査</span><span class="sxs-lookup"><span data-stu-id="6c457-170">Auditing</span></span>

<span data-ttu-id="6c457-171">承認アプリは、Microsoft 365 セキュリティ/コンプライアンス センター内の監査イベントをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="6c457-171">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="6c457-172">監査ログを表示できます。</span><span class="sxs-lookup"><span data-stu-id="6c457-172">You can view the audit log.</span></span>

1. <span data-ttu-id="6c457-173">Microsoft 365 コンプライアンス センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="6c457-173">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="6c457-174">[**監査**］ セクションを選択 します。</span><span class="sxs-lookup"><span data-stu-id="6c457-174">Select the **Audit** section.</span></span>

3. <span data-ttu-id="6c457-175">「**Microsoft Teams の承認アクティビティ**」からアクティビティを検索します。</span><span class="sxs-lookup"><span data-stu-id="6c457-175">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="6c457-176">次のアクティビティを検索できます。</span><span class="sxs-lookup"><span data-stu-id="6c457-176">You can search for the following activities:</span></span>

- <span data-ttu-id="6c457-177">新しい承認要求を作成する</span><span class="sxs-lookup"><span data-stu-id="6c457-177">Create new approval request</span></span>

- <span data-ttu-id="6c457-178">承認要求の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="6c457-178">View approval request details</span></span>

- <span data-ttu-id="6c457-179">承認要求が承認されました</span><span class="sxs-lookup"><span data-stu-id="6c457-179">Approved approval request</span></span>

- <span data-ttu-id="6c457-180">承認要求が拒否されました</span><span class="sxs-lookup"><span data-stu-id="6c457-180">Rejected approval request</span></span>

- <span data-ttu-id="6c457-181">承認要求がキャンセルされました</span><span class="sxs-lookup"><span data-stu-id="6c457-181">Canceled approval request</span></span>

- <span data-ttu-id="6c457-182">共有された承認要求</span><span class="sxs-lookup"><span data-stu-id="6c457-182">Shared approval request</span></span>

- <span data-ttu-id="6c457-183">承認要求に添付されているファイル</span><span class="sxs-lookup"><span data-stu-id="6c457-183">File attached to approval request</span></span>

- <span data-ttu-id="6c457-184">再割り当てされた承認要求</span><span class="sxs-lookup"><span data-stu-id="6c457-184">Reassigned approval request</span></span>

- <span data-ttu-id="6c457-185">電子署名が追加された承認要求</span><span class="sxs-lookup"><span data-stu-id="6c457-185">Added e-signature to approval request</span></span>

- <span data-ttu-id="6c457-186">表示された電子署名要求の詳細</span><span class="sxs-lookup"><span data-stu-id="6c457-186">Viewed e-signature request details</span></span>

- <span data-ttu-id="6c457-187">レビューされた電子署名要求</span><span class="sxs-lookup"><span data-stu-id="6c457-187">Reviewed e-signature request</span></span>

- <span data-ttu-id="6c457-188">取り消された電子署名要求</span><span class="sxs-lookup"><span data-stu-id="6c457-188">Canceled e-signature request</span></span>

- <span data-ttu-id="6c457-189">新しいテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="6c457-189">Create a new template</span></span>

- <span data-ttu-id="6c457-190">既存のテンプレートを編集する</span><span class="sxs-lookup"><span data-stu-id="6c457-190">Edit an existing template</span></span>

- <span data-ttu-id="6c457-191">テンプレートを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="6c457-191">Enable/disable a template</span></span>

- <span data-ttu-id="6c457-192">表示されたテンプレート</span><span class="sxs-lookup"><span data-stu-id="6c457-192">Viewed template</span></span>

<span data-ttu-id="6c457-193">フロー内の他の監査承認にアクセスするには、プライマリ承認エンティティの承認、承認要求、承認応答の既定の環境において、監査を有効にして構成します。</span><span class="sxs-lookup"><span data-stu-id="6c457-193">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="6c457-194">作成、更新、および削除の操作は、承認レコードにて監査可能なイベントです。</span><span class="sxs-lookup"><span data-stu-id="6c457-194">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="6c457-195">詳細については、「[セキュリティとコンプライアンスのための監査データとユーザー アクティビティ - Power Platform \|Microsoft Docs](/power-platform/admin/audit-data-user-activity)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6c457-195">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="6c457-196">監査は、「[Microsoft 365 セキュリティとコンプライアンス センター](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)」にてさらにカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="6c457-196">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="6c457-197">構成済みのレポートを使用するには、「Microsoft 365 のセキュリティとコンプライアンス」にサインインします。</span><span class="sxs-lookup"><span data-stu-id="6c457-197">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="6c457-198">「**検索と調査**」を選択します。</span><span class="sxs-lookup"><span data-stu-id="6c457-198">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="6c457-199">監査ログを検索し、[**Dynamics 365 アクティビティ**］を選択 します。</span><span class="sxs-lookup"><span data-stu-id="6c457-199">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="6c457-200">詳細については、「[Microsoft Dataverse モデルベース アプリ アクティビティ ログ - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c457-200">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="6c457-201">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="6c457-201">Security</span></span>

<span data-ttu-id="6c457-202">ユーザーは、Teams 承認アプリから新しい承認を作成することができ、自分が送受信した承認を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="6c457-202">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="6c457-203">ユーザーは、要求の回答者または閲覧者ではない限り、他のユーザーが作成した承認にはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="6c457-203">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="6c457-204">ユーザーが、承認の作成されたチャットまたはチャネルの一部である場合、要求の閲覧者の役割が与えられます。</span><span class="sxs-lookup"><span data-stu-id="6c457-204">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="6c457-205">承認が作成された際に、その役割が与えられなかった場合は、要求に対してアクションを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="6c457-205">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>

## <a name="approvals-e-signature-integration"></a><span data-ttu-id="6c457-206">承認の電子署名の統合</span><span class="sxs-lookup"><span data-stu-id="6c457-206">Approvals e-signature integration</span></span>

<span data-ttu-id="6c457-207">承認アプリから作成された電子署名承認は、選択したプロバイダーのクラウド環境に格納されます。</span><span class="sxs-lookup"><span data-stu-id="6c457-207">E-signature approvals created from the Approvals app are stored in the selected provider's cloud environment.</span></span> <span data-ttu-id="6c457-208">電子署名契約に関するストレージの詳細については、選択したプロバイダーのストレージに関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c457-208">For further information about storage around the e-signature agreement, view the selected provider's storage documentation.</span></span>

<span data-ttu-id="6c457-209">承認アプリの電子署名機能を使用するには、次の項目が必要です。</span><span class="sxs-lookup"><span data-stu-id="6c457-209">To use the Approvals app e-signature feature, you need the following items:</span></span>

- <span data-ttu-id="6c457-210">使用する特定の電子署名プロバイダーのライセンス。</span><span class="sxs-lookup"><span data-stu-id="6c457-210">License for the specific e-signature provider you're choosing to use.</span></span> <span data-ttu-id="6c457-211">組織のライセンスを取得するには、プロバイダーのサイトに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c457-211">In order to obtain a license for your organization, you'll need to go to the provider’s site.</span></span>

<span data-ttu-id="6c457-212">承認電子署名機能の場合、サード パーティの署名パートナーは既定で Teams 承認アプリに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c457-212">For the Approvals e-signature functionality, third-party signature partners will appear in the Teams Approvals app by default.</span></span> <span data-ttu-id="6c457-213">管理センターのアプリ設定にアクセスして、特定の電子署名プロバイダー Teamsできます。</span><span class="sxs-lookup"><span data-stu-id="6c457-213">You can disable specific e-signature providers by accessing app settings in the Teams admin center.</span></span>

1. <span data-ttu-id="6c457-214">管理センター Teamsの [アプリの管理]**で**、[**承認**] アプリを選択し、[設定。</span><span class="sxs-lookup"><span data-stu-id="6c457-214">In the Teams admin center, under **Manage apps**, select the **Approvals app** and choose **Settings**.</span></span>

2. <span data-ttu-id="6c457-215">各電子署名プロバイダーの横には、既定でオンの位置 (右) にあるトグルがあります。</span><span class="sxs-lookup"><span data-stu-id="6c457-215">Each e-signature provider has a toggle next to it that is in the on position (right) by default.</span></span> <span data-ttu-id="6c457-216">切り替えスイッチを左にスライドして、特定の電子署名プロバイダーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="6c457-216">Slide the toggle to the left to disable a specific e-signature provider.</span></span> <span data-ttu-id="6c457-217">管理者がTeamsプロバイダーを無効にすると、承認を作成するときにエンド ユーザーにプロバイダーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c457-217">If a Teams admin disables a provider, end users won't see the provider when creating an approval.</span></span> <span data-ttu-id="6c457-218">また、エンド ユーザーは、そのプロバイダーで行われた電子署名要求を表示できません。</span><span class="sxs-lookup"><span data-stu-id="6c457-218">End users will also be unable to view any e-signature requests that were made with that provider.</span></span>

<span data-ttu-id="6c457-219">承認アプリから作成された電子署名承認は、選択したプロバイダーのクラウドに格納されます。</span><span class="sxs-lookup"><span data-stu-id="6c457-219">E-signature Approvals created from the Approvals App are stored in the selected provider’s cloud.</span></span> <span data-ttu-id="6c457-220">そのため、電子署名に関するデータをエクスポートするには、プロバイダーのサイトに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c457-220">You will therefore need to go to the provider's site in order to export any data about e-signatures.</span></span> <span data-ttu-id="6c457-221">これらの契約のエクスポートと保持については、プロバイダーのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c457-221">Refer to the provider's documentation about export and retention of these agreements.</span></span>
