---
title: Teams における承認アプリケーションの利用の可否
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
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
ms.openlocfilehash: f916b4e794c862a05a42f075ca2f210a079ff42a
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909521"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="cc7a3-103">Teams 承認アプリの利用の可否</span><span class="sxs-lookup"><span data-stu-id="cc7a3-103">Teams Approvals app availability</span></span>

<span data-ttu-id="cc7a3-104">Microsoft Teams ユーザーは、個人用アプリとして承認アプリを利用することができます。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="cc7a3-105">承認アプリは、Teams 内の構造化された承認と構造化されていない承認の両方に対して、監査、コンプライアンス、説明責任、およびワークフローを簡単にする方法を提供します。 </span><span class="sxs-lookup"><span data-stu-id="cc7a3-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![承認アプリを表示する](media/approvals-selection.png)

<span data-ttu-id="cc7a3-107">ユーザーは承認アプリをピン留めしてメニュー バーに保存できます。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![PIN オプションを使用する承認アプリを表示する](media/approvalApp-pin.png)

<span data-ttu-id="cc7a3-109">承認アプリから最初の承認が作成されると、既定の共通データ サービス (CDS) 環境にて承認ソリューションがプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="cc7a3-110">承認アプリから作成された承認は、既定の CDS 環境に保存されます。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="cc7a3-111">この記事では、承認アプリの要件と役割について説明します。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-111">This article describes the Approvals app requirements and roles.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="cc7a3-112">必要なアクセス許可とライセンス</span><span class="sxs-lookup"><span data-stu-id="cc7a3-112">Required permissions and licenses</span></span>

<span data-ttu-id="cc7a3-113">承認アプリを使用するには、次のアイテムに対する権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-113">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="cc7a3-114">Microsoft CDS データベースを作成する権限。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-114">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="cc7a3-115">[flow.microsoft.com](https://flow.microsoft.com/) のアカウント </span><span class="sxs-lookup"><span data-stu-id="cc7a3-115">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="cc7a3-116">ターゲット環境における管理者の役割。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-116">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="cc7a3-117">[Power Automate](https://docs.microsoft.com/power-automate/get-started-approvals)、Office 365、または Dynamics 365 のライセンス。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-117">License for a [Power Automate](https://docs.microsoft.com/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="cc7a3-118">CDS を使用するストレージ</span><span class="sxs-lookup"><span data-stu-id="cc7a3-118">Storage with CDS</span></span>

<span data-ttu-id="cc7a3-119">共通データ モデル (CDM) は、CDS のビジネス アプリケーションや分析アプリケーションで使用される共有データ言語です。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-119">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="cc7a3-120">これは、Microsoft とそのパートナーによって公開された、一連の標準化された拡張可能なデータ スキーマで構成されており、アプリケーションとビジネス プロセス全体でデータとその意味の一貫性を実現します。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-120">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="cc7a3-121">[Microsoft Power Platform の共通データ モデル](https://docs.microsoft.com/power-automate/get-started-approvals)の詳細については、以下をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-121">Learn more about the [Common Data Model of the Microsoft Power Platform](https://docs.microsoft.com/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="cc7a3-122">[承認ワークフロー](https://docs.microsoft.com/power-automate/modern-approvals)の詳細。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-122">Learn more about the [Approval workflow](https://docs.microsoft.com/power-automate/modern-approvals).</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="cc7a3-123">Teams アプリの権限の承認</span><span class="sxs-lookup"><span data-stu-id="cc7a3-123">Approvals Teams app permissions</span></span>

<span data-ttu-id="cc7a3-124">Teams アプリの承認では、次の機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-124">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="cc7a3-125">メッセージやデータを受信します。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-125">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="cc7a3-126">メッセージと通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-126">Send you messages and notifications.</span></span>

- <span data-ttu-id="cc7a3-127">Teams が提供するヘッダーを必要とすることなく、個人用アプリとダイアログをレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-127">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="cc7a3-128">[名前]、[電子メールアドレス]、[会社名]、[優先する言語] などの個人用プロフィール情報にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-128">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="cc7a3-129">チーム メンバーがチャネルで提供するメッセージとデータを受信します。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-129">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="cc7a3-130">チャネルでメッセージと通知を送信する。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-130">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="cc7a3-131">チームの情報にアクセスする:</span><span class="sxs-lookup"><span data-stu-id="cc7a3-131">Access your team's information:</span></span>
  - <span data-ttu-id="cc7a3-132">チーム名</span><span class="sxs-lookup"><span data-stu-id="cc7a3-132">team name</span></span>
  - <span data-ttu-id="cc7a3-133">チャネル リスト</span><span class="sxs-lookup"><span data-stu-id="cc7a3-133">channel list</span></span>
  - <span data-ttu-id="cc7a3-134">名簿 (チーム メンバーの名前とメール アドレス)。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-134">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="cc7a3-135">チームの情報を使用してメンバーに連絡します。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-135">Use the team's information to contact them.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="cc7a3-136">承認アプリを無効にする</span><span class="sxs-lookup"><span data-stu-id="cc7a3-136">Disable the Approvals app</span></span>

<span data-ttu-id="cc7a3-137">承認アプリは既定で利用可能です。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-137">The Approvals app is available by default.</span></span> <span data-ttu-id="cc7a3-138">Teams 管理センターでアプリを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-138">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="cc7a3-139">Teams 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-139">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="cc7a3-140">［**Teams アプリ**］ を開き、［**アプリの管理**］ を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-140">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="cc7a3-141">承認アプリを検索します。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-141">Search for the Approvals app.</span></span>

![強調表示されている [Teams アプリ] > [アプリの管理] を使用して、管理センター ナビゲーションを表示する](media/manage-approval-apps.png)

  4. <span data-ttu-id="cc7a3-143">[承認] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-143">Select Approvals.</span></span>

  5. <span data-ttu-id="cc7a3-144">切り替えを選択して、組織のアプリを無効にします。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-144">Select the toggle to disable the app for your organization.</span></span>

![承認アプリの詳細を表示する](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="cc7a3-146">アイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="cc7a3-146">Retention policy</span></span>

<span data-ttu-id="cc7a3-147">承認アプリから作成された承認は既定の CDS 環境に保存されます。現時点では、バックアップはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-147">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="cc7a3-148">詳細については、「[環境のバックアップと復元の方法Power Platform \|Microsoft Docs](https://docs.microsoft.com/power-platform/admin/backup-restore-environments)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-148">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).</span></span>

## <a name="auditing"></a><span data-ttu-id="cc7a3-149">監査</span><span class="sxs-lookup"><span data-stu-id="cc7a3-149">Auditing</span></span>

<span data-ttu-id="cc7a3-150">承認アプリは、Microsoft 365 セキュリティ/コンプライアンス センター内の監査イベントをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-150">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="cc7a3-151">監査ログを表示できます。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-151">You can view the audit log.</span></span>

1. <span data-ttu-id="cc7a3-152">Microsoft 365 コンプライアンス センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-152">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="cc7a3-153">[**監査**］ セクションを選択 します。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-153">Select the **Audit** section.</span></span>

3. <span data-ttu-id="cc7a3-154">「**Microsoft Teams の承認アクティビティ**」からアクティビティを検索します。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-154">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="cc7a3-155">次のアクティビティを検索できます。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-155">You can search for the following activities:</span></span>

- <span data-ttu-id="cc7a3-156">新しい承認要求を作成する</span><span class="sxs-lookup"><span data-stu-id="cc7a3-156">Create new approval request</span></span>

- <span data-ttu-id="cc7a3-157">承認要求の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="cc7a3-157">View approval request details</span></span>

- <span data-ttu-id="cc7a3-158">承認要求が承認されました</span><span class="sxs-lookup"><span data-stu-id="cc7a3-158">Approved approval request</span></span>

- <span data-ttu-id="cc7a3-159">承認要求が拒否されました</span><span class="sxs-lookup"><span data-stu-id="cc7a3-159">Rejected approval request</span></span>

- <span data-ttu-id="cc7a3-160">承認要求がキャンセルされました</span><span class="sxs-lookup"><span data-stu-id="cc7a3-160">Canceled approval request</span></span>

- <span data-ttu-id="cc7a3-161">共有された承認要求</span><span class="sxs-lookup"><span data-stu-id="cc7a3-161">Shared approval request</span></span>

- <span data-ttu-id="cc7a3-162">承認要求に添付されているファイル</span><span class="sxs-lookup"><span data-stu-id="cc7a3-162">File attached to approval request</span></span>

- <span data-ttu-id="cc7a3-163">再割り当てされた承認要求</span><span class="sxs-lookup"><span data-stu-id="cc7a3-163">Reassigned approval request</span></span>

- <span data-ttu-id="cc7a3-164">電子署名が追加された承認要求</span><span class="sxs-lookup"><span data-stu-id="cc7a3-164">Added e-signature to approval request</span></span>

<span data-ttu-id="cc7a3-165">フロー内の他の監査承認にアクセスするには、プライマリ承認エンティティの承認、承認要求、承認応答の既定の環境において、監査を有効にして構成します。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-165">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="cc7a3-166">作成、更新、および削除の操作は、承認レコードにて監査可能なイベントです。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-166">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="cc7a3-167">詳細については、「[セキュリティとコンプライアンスのための監査データとユーザー アクティビティ - Power Platform \|Microsoft Docs](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-167">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="cc7a3-168">監査は、「[Microsoft 365 セキュリティとコンプライアンス センター](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)」にてさらにカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-168">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="cc7a3-169">構成済みのレポートを使用するには、「Microsoft 365 のセキュリティとコンプライアンス」にサインインします。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-169">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="cc7a3-170">「**検索と調査**」を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-170">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="cc7a3-171">監査ログを検索し、[**Dynamics 365 アクティビティ**］を選択 します。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-171">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="cc7a3-172">詳細については、「[Microsoft Dataverse モデルベース アプリ アクティビティ ログ - Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-172">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="cc7a3-173">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="cc7a3-173">Security</span></span>

<span data-ttu-id="cc7a3-174">ユーザーは、Teams 承認アプリから新しい承認を作成することができ、自分が送受信した承認を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-174">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="cc7a3-175">ユーザーは、要求の回答者または閲覧者ではない限り、他のユーザーが作成した承認にはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-175">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="cc7a3-176">ユーザーが、承認の作成されたチャットまたはチャネルの一部である場合、要求の閲覧者の役割が与えられます。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-176">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="cc7a3-177">承認が作成された際に、その役割が与えられなかった場合は、要求に対してアクションを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="cc7a3-177">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>
