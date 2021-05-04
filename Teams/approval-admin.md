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
ms.openlocfilehash: c71f08840ffa9c41622d07376933c14a7ae6b493
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2021
ms.locfileid: "52129796"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="39de2-103">Teams 承認アプリの利用の可否</span><span class="sxs-lookup"><span data-stu-id="39de2-103">Teams Approvals app availability</span></span>

<span data-ttu-id="39de2-104">Microsoft Teams ユーザーは、個人用アプリとして承認アプリを利用することができます。</span><span class="sxs-lookup"><span data-stu-id="39de2-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="39de2-105">承認アプリは、Teams 内の構造化された承認と構造化されていない承認の両方に対して、監査、コンプライアンス、説明責任、およびワークフローを簡単にする方法を提供します。 </span><span class="sxs-lookup"><span data-stu-id="39de2-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![承認アプリを表示する](media/approvals-selection.png)

<span data-ttu-id="39de2-107">ユーザーは承認アプリをピン留めしてメニュー バーに保存できます。</span><span class="sxs-lookup"><span data-stu-id="39de2-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![PIN オプションを使用する承認アプリを表示する](media/approvalApp-pin.png)

<span data-ttu-id="39de2-109">承認アプリから最初の承認が作成されると、既定の共通データ サービス (CDS) 環境にて承認ソリューションがプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="39de2-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="39de2-110">承認アプリから作成された承認は、既定の CDS 環境に保存されます。</span><span class="sxs-lookup"><span data-stu-id="39de2-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="39de2-111">この記事では、承認アプリの要件と役割について説明します。</span><span class="sxs-lookup"><span data-stu-id="39de2-111">This article describes the Approvals app requirements and roles.</span></span>

> [!NOTE]
> <span data-ttu-id="39de2-112">この機能は、Government Community Cloud (GCC)、Government Community Cloud (GCCH)、国防総省 (DOD) ユーザーにはまだリリースされていません。</span><span class="sxs-lookup"><span data-stu-id="39de2-112">This feature hasn't been released to Government Community Cloud (GCC), Government Community Cloud High (GCCH), and Department of Defense (DOD) users yet.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="39de2-113">必要なアクセス許可とライセンス</span><span class="sxs-lookup"><span data-stu-id="39de2-113">Required permissions and licenses</span></span>

<span data-ttu-id="39de2-114">承認アプリを使用するには、次のアイテムに対する権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="39de2-114">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="39de2-115">Microsoft CDS データベースを作成する権限。</span><span class="sxs-lookup"><span data-stu-id="39de2-115">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="39de2-116">[flow.microsoft.com](https://flow.microsoft.com/) のアカウント </span><span class="sxs-lookup"><span data-stu-id="39de2-116">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="39de2-117">ターゲット環境における管理者の役割。</span><span class="sxs-lookup"><span data-stu-id="39de2-117">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="39de2-118">[Power Automate](/power-automate/get-started-approvals)、Office 365、または Dynamics 365 のライセンス。</span><span class="sxs-lookup"><span data-stu-id="39de2-118">License for a [Power Automate](/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="39de2-119">CDS を使用するストレージ</span><span class="sxs-lookup"><span data-stu-id="39de2-119">Storage with CDS</span></span>

<span data-ttu-id="39de2-120">共通データ モデル (CDM) は、CDS のビジネス アプリケーションや分析アプリケーションで使用される共有データ言語です。</span><span class="sxs-lookup"><span data-stu-id="39de2-120">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="39de2-121">これは、Microsoft とそのパートナーによって公開された、一連の標準化された拡張可能なデータ スキーマで構成されており、アプリケーションとビジネス プロセス全体でデータとその意味の一貫性を実現します。</span><span class="sxs-lookup"><span data-stu-id="39de2-121">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="39de2-122">[Microsoft Power Platform の共通データ モデル](/power-automate/get-started-approvals)の詳細については、以下をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="39de2-122">Learn more about the [Common Data Model of the Microsoft Power Platform](/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="39de2-123">[承認ワークフロー](/power-automate/modern-approvals)の詳細。</span><span class="sxs-lookup"><span data-stu-id="39de2-123">Learn more about the [Approval workflow](/power-automate/modern-approvals).</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="39de2-124">Teams アプリの権限の承認</span><span class="sxs-lookup"><span data-stu-id="39de2-124">Approvals Teams app permissions</span></span>

<span data-ttu-id="39de2-125">Teams アプリの承認では、次の機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="39de2-125">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="39de2-126">メッセージやデータを受信します。</span><span class="sxs-lookup"><span data-stu-id="39de2-126">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="39de2-127">メッセージと通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="39de2-127">Send you messages and notifications.</span></span>

- <span data-ttu-id="39de2-128">Teams が提供するヘッダーを必要とすることなく、個人用アプリとダイアログをレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="39de2-128">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="39de2-129">[名前]、[電子メールアドレス]、[会社名]、[優先する言語] などの個人用プロフィール情報にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="39de2-129">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="39de2-130">チーム メンバーがチャネルで提供するメッセージとデータを受信します。</span><span class="sxs-lookup"><span data-stu-id="39de2-130">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="39de2-131">チャネルでメッセージと通知を送信する。</span><span class="sxs-lookup"><span data-stu-id="39de2-131">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="39de2-132">チームの情報にアクセスする:</span><span class="sxs-lookup"><span data-stu-id="39de2-132">Access your team's information:</span></span>
  - <span data-ttu-id="39de2-133">チーム名</span><span class="sxs-lookup"><span data-stu-id="39de2-133">team name</span></span>
  - <span data-ttu-id="39de2-134">チャネル リスト</span><span class="sxs-lookup"><span data-stu-id="39de2-134">channel list</span></span>
  - <span data-ttu-id="39de2-135">名簿 (チーム メンバーの名前とメール アドレス)。</span><span class="sxs-lookup"><span data-stu-id="39de2-135">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="39de2-136">チームの情報を使用してメンバーに連絡します。</span><span class="sxs-lookup"><span data-stu-id="39de2-136">Use the team's information to contact them.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="39de2-137">承認アプリを無効にする</span><span class="sxs-lookup"><span data-stu-id="39de2-137">Disable the Approvals app</span></span>

<span data-ttu-id="39de2-138">承認アプリは既定で利用可能です。</span><span class="sxs-lookup"><span data-stu-id="39de2-138">The Approvals app is available by default.</span></span> <span data-ttu-id="39de2-139">Teams 管理センターでアプリを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="39de2-139">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="39de2-140">Teams 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="39de2-140">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="39de2-141">［**Teams アプリ**］ を開き、［**アプリの管理**］ を選択します。</span><span class="sxs-lookup"><span data-stu-id="39de2-141">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="39de2-142">承認アプリを検索します。</span><span class="sxs-lookup"><span data-stu-id="39de2-142">Search for the Approvals app.</span></span>

     ![強調表示されている [Teams アプリ] > [アプリの管理] を使用して、管理センター ナビゲーションを表示する](media/manage-approval-apps.png)

  4. <span data-ttu-id="39de2-144">[承認] を選択します。</span><span class="sxs-lookup"><span data-stu-id="39de2-144">Select Approvals.</span></span>

  5. <span data-ttu-id="39de2-145">切り替えを選択して、組織のアプリを無効にします。</span><span class="sxs-lookup"><span data-stu-id="39de2-145">Select the toggle to disable the app for your organization.</span></span>

     ![承認アプリの詳細を表示する](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="39de2-147">アイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="39de2-147">Retention policy</span></span>

<span data-ttu-id="39de2-148">承認アプリから作成された承認は既定の CDS 環境に保存されます。現時点では、バックアップはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="39de2-148">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="39de2-149">詳細については、「[環境のバックアップと復元の方法Power Platform \|Microsoft Docs](/power-platform/admin/backup-restore-environments)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="39de2-149">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span></span>

## <a name="auditing"></a><span data-ttu-id="39de2-150">監査</span><span class="sxs-lookup"><span data-stu-id="39de2-150">Auditing</span></span>

<span data-ttu-id="39de2-151">承認アプリは、Microsoft 365 セキュリティ/コンプライアンス センター内の監査イベントをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="39de2-151">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="39de2-152">監査ログを表示できます。</span><span class="sxs-lookup"><span data-stu-id="39de2-152">You can view the audit log.</span></span>

1. <span data-ttu-id="39de2-153">Microsoft 365 コンプライアンス センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="39de2-153">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="39de2-154">[**監査**］ セクションを選択 します。</span><span class="sxs-lookup"><span data-stu-id="39de2-154">Select the **Audit** section.</span></span>

3. <span data-ttu-id="39de2-155">「**Microsoft Teams の承認アクティビティ**」からアクティビティを検索します。</span><span class="sxs-lookup"><span data-stu-id="39de2-155">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="39de2-156">次のアクティビティを検索できます。</span><span class="sxs-lookup"><span data-stu-id="39de2-156">You can search for the following activities:</span></span>

- <span data-ttu-id="39de2-157">新しい承認要求を作成する</span><span class="sxs-lookup"><span data-stu-id="39de2-157">Create new approval request</span></span>

- <span data-ttu-id="39de2-158">承認要求の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="39de2-158">View approval request details</span></span>

- <span data-ttu-id="39de2-159">承認要求が承認されました</span><span class="sxs-lookup"><span data-stu-id="39de2-159">Approved approval request</span></span>

- <span data-ttu-id="39de2-160">承認要求が拒否されました</span><span class="sxs-lookup"><span data-stu-id="39de2-160">Rejected approval request</span></span>

- <span data-ttu-id="39de2-161">承認要求がキャンセルされました</span><span class="sxs-lookup"><span data-stu-id="39de2-161">Canceled approval request</span></span>

- <span data-ttu-id="39de2-162">共有された承認要求</span><span class="sxs-lookup"><span data-stu-id="39de2-162">Shared approval request</span></span>

- <span data-ttu-id="39de2-163">承認要求に添付されているファイル</span><span class="sxs-lookup"><span data-stu-id="39de2-163">File attached to approval request</span></span>

- <span data-ttu-id="39de2-164">再割り当てされた承認要求</span><span class="sxs-lookup"><span data-stu-id="39de2-164">Reassigned approval request</span></span>

- <span data-ttu-id="39de2-165">電子署名が追加された承認要求</span><span class="sxs-lookup"><span data-stu-id="39de2-165">Added e-signature to approval request</span></span>

- <span data-ttu-id="39de2-166">表示された電子署名要求の詳細</span><span class="sxs-lookup"><span data-stu-id="39de2-166">Viewed e-signature request details</span></span>

- <span data-ttu-id="39de2-167">レビューされた電子署名要求</span><span class="sxs-lookup"><span data-stu-id="39de2-167">Reviewed e-signature request</span></span>

- <span data-ttu-id="39de2-168">取り消された電子署名要求</span><span class="sxs-lookup"><span data-stu-id="39de2-168">Canceled e-signature request</span></span>

<span data-ttu-id="39de2-169">フロー内の他の監査承認にアクセスするには、プライマリ承認エンティティの承認、承認要求、承認応答の既定の環境において、監査を有効にして構成します。</span><span class="sxs-lookup"><span data-stu-id="39de2-169">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="39de2-170">作成、更新、および削除の操作は、承認レコードにて監査可能なイベントです。</span><span class="sxs-lookup"><span data-stu-id="39de2-170">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="39de2-171">詳細については、「[セキュリティとコンプライアンスのための監査データとユーザー アクティビティ - Power Platform \|Microsoft Docs](/power-platform/admin/audit-data-user-activity)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="39de2-171">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="39de2-172">監査は、「[Microsoft 365 セキュリティとコンプライアンス センター](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)」にてさらにカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="39de2-172">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="39de2-173">構成済みのレポートを使用するには、「Microsoft 365 のセキュリティとコンプライアンス」にサインインします。</span><span class="sxs-lookup"><span data-stu-id="39de2-173">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="39de2-174">「**検索と調査**」を選択します。</span><span class="sxs-lookup"><span data-stu-id="39de2-174">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="39de2-175">監査ログを検索し、[**Dynamics 365 アクティビティ**］を選択 します。</span><span class="sxs-lookup"><span data-stu-id="39de2-175">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="39de2-176">詳細については、「[Microsoft Dataverse モデルベース アプリ アクティビティ ログ - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39de2-176">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="39de2-177">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="39de2-177">Security</span></span>

<span data-ttu-id="39de2-178">ユーザーは、Teams 承認アプリから新しい承認を作成することができ、自分が送受信した承認を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="39de2-178">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="39de2-179">ユーザーは、要求の回答者または閲覧者ではない限り、他のユーザーが作成した承認にはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="39de2-179">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="39de2-180">ユーザーが、承認の作成されたチャットまたはチャネルの一部である場合、要求の閲覧者の役割が与えられます。</span><span class="sxs-lookup"><span data-stu-id="39de2-180">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="39de2-181">承認が作成された際に、その役割が与えられなかった場合は、要求に対してアクションを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="39de2-181">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>

## <a name="approvals-e-signature-integration"></a><span data-ttu-id="39de2-182">承認の電子署名の統合</span><span class="sxs-lookup"><span data-stu-id="39de2-182">Approvals e-signature integration</span></span>

<span data-ttu-id="39de2-183">承認アプリから作成された電子署名の承認は、選択したプロバイダーのクラウド環境に格納されます。</span><span class="sxs-lookup"><span data-stu-id="39de2-183">E-signature approvals created from the Approvals app are stored in the selected provider's cloud environment.</span></span> <span data-ttu-id="39de2-184">電子署名契約に関するストレージの詳細については、選択したプロバイダーのストレージ ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="39de2-184">For further information about storage around the e-signature agreement, view the selected provider's storage documentation.</span></span>

<span data-ttu-id="39de2-185">Approvals アプリの電子署名機能を使用するには、次の項目が必要です。</span><span class="sxs-lookup"><span data-stu-id="39de2-185">To use the Approvals app e-signature feature, you need the following items:</span></span>

- <span data-ttu-id="39de2-186">使用する特定の電子署名プロバイダーのライセンス。</span><span class="sxs-lookup"><span data-stu-id="39de2-186">License for the specific e-signature provider you're choosing to use.</span></span> <span data-ttu-id="39de2-187">組織のライセンスを取得するには、プロバイダーのサイトに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39de2-187">In order to obtain a license for your organization, you'll need to go to the provider’s site.</span></span>

<span data-ttu-id="39de2-188">承認の電子署名機能の場合、既定ではサード パーティの署名パートナーが Teams承認アプリに表示されます。</span><span class="sxs-lookup"><span data-stu-id="39de2-188">For the Approvals e-signature functionality, third-party signature partners will appear in the Teams Approvals app by default.</span></span> <span data-ttu-id="39de2-189">管理者センターのアプリ設定にアクセスして、特定の電子署名プロバイダー Teamsできます。</span><span class="sxs-lookup"><span data-stu-id="39de2-189">You can disable specific e-signature providers by accessing app settings in the Teams admin center.</span></span>

1. <span data-ttu-id="39de2-190">管理センター Teams [アプリの管理]**で**[承認] アプリを選択し、[承認]**を** 選択設定。</span><span class="sxs-lookup"><span data-stu-id="39de2-190">In the Teams admin center, under **Manage apps**, select the **Approvals app** and choose **Settings**.</span></span>

2. <span data-ttu-id="39de2-191">各電子署名プロバイダーには、既定でオンの位置 (右) にあるトグルが横に表示されます。</span><span class="sxs-lookup"><span data-stu-id="39de2-191">Each e-signature provider has a toggle next to it that is in the on position (right) by default.</span></span> <span data-ttu-id="39de2-192">トグルを左にスライドして、特定の電子署名プロバイダーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="39de2-192">Slide the toggle to the left to disable a specific e-signature provider.</span></span> <span data-ttu-id="39de2-193">管理者がTeamsプロバイダーを無効にした場合、エンド ユーザーは承認を作成するときにプロバイダーを表示しない。</span><span class="sxs-lookup"><span data-stu-id="39de2-193">If a Teams admin disables a provider, end users won't see the provider when creating an approval.</span></span> <span data-ttu-id="39de2-194">エンド ユーザーは、そのプロバイダーで行われた電子署名要求も表示できません。</span><span class="sxs-lookup"><span data-stu-id="39de2-194">End users will also be unable to view any e-signature requests that were made with that provider.</span></span>

<span data-ttu-id="39de2-195">承認アプリから作成された電子署名承認は、選択したプロバイダーのクラウドに格納されます。</span><span class="sxs-lookup"><span data-stu-id="39de2-195">E-signature Approvals created from the Approvals App are stored in the selected provider’s cloud.</span></span> <span data-ttu-id="39de2-196">そのため、電子署名に関するデータをエクスポートするには、プロバイダーのサイトに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39de2-196">You will therefore need to go to the provider's site in order to export any data about e-signatures.</span></span> <span data-ttu-id="39de2-197">これらの契約のエクスポートと保持に関するプロバイダーのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="39de2-197">Refer to the provider's documentation about export and retention of these agreements.</span></span>
