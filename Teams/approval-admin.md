---
title: Teams での承認アプリケーションの可用性
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
description: Microsoft Teams での承認アプリケーションの可用性について説明します。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4326408b7e27aa19af8e6c404d7275d26ba90969
ms.sourcegitcommit: d73d732591944b899a9366f79b4ea97f4a7f2260
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2020
ms.locfileid: "49675195"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="82df5-103">Teams 承認アプリの可用性</span><span class="sxs-lookup"><span data-stu-id="82df5-103">Teams Approvals app availability</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="82df5-104">承認アプリは、すべての Microsoft Teams ユーザーの個人用アプリとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="82df5-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="82df5-105">承認アプリは、監査、コンプライアンス、責任、ワークフローを Teams の構造化された承認と非構造化承認の両方に表示する簡単な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="82df5-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![承認アプリを表示する](media/approvals-selection.png)

<span data-ttu-id="82df5-107">ユーザーは承認アプリをピン留めして、メニュー バーに保存できます。</span><span class="sxs-lookup"><span data-stu-id="82df5-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![[ピン] オプションが表示された承認アプリ](media/approvalApp-pin.png)

<span data-ttu-id="82df5-109">承認アプリから最初に作成された承認は、既定の Common Data Service (CDS) 環境での承認ソリューションのプロビジョニングをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="82df5-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="82df5-110">承認アプリから作成された承認は、既定の CDS 環境に保存されます。</span><span class="sxs-lookup"><span data-stu-id="82df5-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="82df5-111">この記事では、承認アプリの要件とロールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="82df5-111">This article describes the Approvals app requirements and roles.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="82df5-112">必要なアクセス許可とライセンス</span><span class="sxs-lookup"><span data-stu-id="82df5-112">Required permissions and licenses</span></span>

<span data-ttu-id="82df5-113">承認アプリを使用するには、次のアイテムに対するアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="82df5-113">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="82df5-114">Microsoft CDS データベースを作成する権限。</span><span class="sxs-lookup"><span data-stu-id="82df5-114">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="82df5-115">アカウント [のflow.microsoft.com](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="82df5-115">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="82df5-116">ターゲット環境の管理者ロール。</span><span class="sxs-lookup"><span data-stu-id="82df5-116">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="82df5-117">[Power Automate、Office](https://docs.microsoft.com/power-automate/get-started-approvals)365、または Dynamics 365 のライセンス。</span><span class="sxs-lookup"><span data-stu-id="82df5-117">License for a [Power Automate](https://docs.microsoft.com/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="82df5-118">CDS 付きストレージ</span><span class="sxs-lookup"><span data-stu-id="82df5-118">Storage with CDS</span></span>

<span data-ttu-id="82df5-119">共通データ モデル (CDM) は、CDS のビジネス アプリケーションや分析アプリケーションで使用される共有データ言語です。</span><span class="sxs-lookup"><span data-stu-id="82df5-119">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="82df5-120">Microsoft とパートナーが公開する標準化された拡張データ スキーマのセットで構成され、アプリケーションやビジネス プロセス全体でデータとその意味の一貫性を保ちます。</span><span class="sxs-lookup"><span data-stu-id="82df5-120">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="82df5-121">Microsoft Power [Platform の共通データ モデルの詳細については、以下を参照してください](https://docs.microsoft.com/power-automate/get-started-approvals)。</span><span class="sxs-lookup"><span data-stu-id="82df5-121">Learn more about the [Common Data Model of the Microsoft Power Platform](https://docs.microsoft.com/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="82df5-122">承認ワークフローの [詳細については、以下を参照してください](https://docs.microsoft.com/power-automate/modern-approvals)。</span><span class="sxs-lookup"><span data-stu-id="82df5-122">Learn more about the [Approval workflow](https://docs.microsoft.com/power-automate/modern-approvals).</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="82df5-123">承認 Teams アプリのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="82df5-123">Approvals Teams app permissions</span></span>

<span data-ttu-id="82df5-124">承認チーム アプリでは、次の機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="82df5-124">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="82df5-125">指定したメッセージとデータを受信します。</span><span class="sxs-lookup"><span data-stu-id="82df5-125">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="82df5-126">メッセージと通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="82df5-126">Send you messages and notifications.</span></span>

- <span data-ttu-id="82df5-127">Teams が提供するヘッダーなしで個人用アプリとダイアログを表示します。</span><span class="sxs-lookup"><span data-stu-id="82df5-127">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="82df5-128">名前、メール アドレス、会社名、優先する言語などのプロファイル情報にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="82df5-128">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="82df5-129">チャネルでチーム メンバーが提供するメッセージとデータを受信します。</span><span class="sxs-lookup"><span data-stu-id="82df5-129">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="82df5-130">チャネルでメッセージと通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="82df5-130">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="82df5-131">チームの情報にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="82df5-131">Access your team's information:</span></span>
  - <span data-ttu-id="82df5-132">チーム名</span><span class="sxs-lookup"><span data-stu-id="82df5-132">team name</span></span>
  - <span data-ttu-id="82df5-133">チャネル リスト</span><span class="sxs-lookup"><span data-stu-id="82df5-133">channel list</span></span>
  - <span data-ttu-id="82df5-134">リスト (チーム メンバーの名前とメール アドレス)</span><span class="sxs-lookup"><span data-stu-id="82df5-134">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="82df5-135">チームの情報を使用して、チームに連絡します。</span><span class="sxs-lookup"><span data-stu-id="82df5-135">Use the team's information to contact them.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="82df5-136">承認アプリを無効にする</span><span class="sxs-lookup"><span data-stu-id="82df5-136">Disable the Approvals app</span></span>

<span data-ttu-id="82df5-137">承認アプリは既定で使用できます。</span><span class="sxs-lookup"><span data-stu-id="82df5-137">The Approvals app is available by default.</span></span> <span data-ttu-id="82df5-138">Teams 管理センターでアプリを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="82df5-138">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="82df5-139">Teams 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="82df5-139">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="82df5-140">Teams アプリ **を展開し、[** アプリの **管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="82df5-140">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="82df5-141">承認アプリを検索します。</span><span class="sxs-lookup"><span data-stu-id="82df5-141">Search for the Approvals app.</span></span>

![[Teams アプリ] と [アプリの管理] が>管理センターのナビゲーションを表示する](media/manage-approval-apps.png)

  4. <span data-ttu-id="82df5-143">[承認] を選択します。</span><span class="sxs-lookup"><span data-stu-id="82df5-143">Select Approvals.</span></span>

  5. <span data-ttu-id="82df5-144">トグルを選択して、組織のアプリを無効にします。</span><span class="sxs-lookup"><span data-stu-id="82df5-144">Select the toggle to disable the app for your organization.</span></span>

![承認アプリの詳細を表示する](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="82df5-146">アイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="82df5-146">Retention policy</span></span>

<span data-ttu-id="82df5-147">承認アプリから作成された承認は既定の CDS 環境に保存されます。現時点ではバックアップはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="82df5-147">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="82df5-148">環境をバックアップおよび復元 [する方法の詳細については、Power Platform \| Microsoft Docs を参照してください](https://docs.microsoft.com/power-platform/admin/backup-restore-environments)。</span><span class="sxs-lookup"><span data-stu-id="82df5-148">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).</span></span>

## <a name="auditing"></a><span data-ttu-id="82df5-149">監査</span><span class="sxs-lookup"><span data-stu-id="82df5-149">Auditing</span></span>

<span data-ttu-id="82df5-150">承認アプリは、Microsoft 365 セキュリティ/コンプライアンス センター内の監査イベントをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="82df5-150">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="82df5-151">監査ログを表示できます。</span><span class="sxs-lookup"><span data-stu-id="82df5-151">You can view the audit log.</span></span>

1. <span data-ttu-id="82df5-152">M365 コンプライアンス サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="82df5-152">Go to the M365 Compliance Site.</span></span>

2. <span data-ttu-id="82df5-153">[監査] **セクションを選択** します。</span><span class="sxs-lookup"><span data-stu-id="82df5-153">Select the **Audit** section.</span></span>

3. <span data-ttu-id="82df5-154">Microsoft Teams の承認アクティビティ **の下でアクティビティを検索します**。</span><span class="sxs-lookup"><span data-stu-id="82df5-154">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="82df5-155">次のアクティビティを検索できます。</span><span class="sxs-lookup"><span data-stu-id="82df5-155">You can search for the following activities:</span></span>

- <span data-ttu-id="82df5-156">新しい承認要求を作成する</span><span class="sxs-lookup"><span data-stu-id="82df5-156">Create new approval request</span></span>

- <span data-ttu-id="82df5-157">承認要求の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="82df5-157">View approval request details</span></span>

- <span data-ttu-id="82df5-158">承認された承認要求</span><span class="sxs-lookup"><span data-stu-id="82df5-158">Approved approval request</span></span>

- <span data-ttu-id="82df5-159">承認要求が却下されました</span><span class="sxs-lookup"><span data-stu-id="82df5-159">Rejected approval request</span></span>

- <span data-ttu-id="82df5-160">承認要求が取り消されました</span><span class="sxs-lookup"><span data-stu-id="82df5-160">Canceled approval request</span></span>

- <span data-ttu-id="82df5-161">共有承認要求</span><span class="sxs-lookup"><span data-stu-id="82df5-161">Shared approval request</span></span>

- <span data-ttu-id="82df5-162">承認要求に添付されたファイル</span><span class="sxs-lookup"><span data-stu-id="82df5-162">File attached to approval request</span></span>

- <span data-ttu-id="82df5-163">再割り当てされた承認要求</span><span class="sxs-lookup"><span data-stu-id="82df5-163">Reassigned approval request</span></span>

- <span data-ttu-id="82df5-164">承認要求に電子署名が追加されました</span><span class="sxs-lookup"><span data-stu-id="82df5-164">Added e-signature to approval request</span></span>

<span data-ttu-id="82df5-165">Flow 内で他の監査承認にアクセスするには、プライマリ承認エンティティの承認、承認要求、承認応答の既定の環境で監査を有効にして構成します。</span><span class="sxs-lookup"><span data-stu-id="82df5-165">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="82df5-166">作成、更新、削除の操作は、承認レコードの監査可能なイベントです。</span><span class="sxs-lookup"><span data-stu-id="82df5-166">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="82df5-167">セキュリティとコンプライアンスの [データとユーザー アクティビティの監査について詳しくは、Power Platform Microsoft Docs をご \| 覧ください](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity)。</span><span class="sxs-lookup"><span data-stu-id="82df5-167">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="82df5-168">監査は [、Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)セキュリティ/コンプライアンス センターでさらにカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="82df5-168">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="82df5-169">事前に構成されたレポートを使用するには、Office 365 セキュリティ/コンプライアンスにサインインします。</span><span class="sxs-lookup"><span data-stu-id="82df5-169">To use the preconfigured reports, sign in to Office 365 Security and Compliance.</span></span>

2. <span data-ttu-id="82df5-170">[検索 **と調査&選択します**。</span><span class="sxs-lookup"><span data-stu-id="82df5-170">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="82df5-171">監査ログを検索し **、[Dynamics 365 アクティビティ] タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="82df5-171">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="82df5-172">[Microsoft Dataverse とモデル駆動型アプリのアクティビティ ログの詳細については、Power Platform を参照してください](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing)。</span><span class="sxs-lookup"><span data-stu-id="82df5-172">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="82df5-173">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="82df5-173">Security</span></span>

<span data-ttu-id="82df5-174">Teams 承認アプリから、ユーザーは新しい承認を作成し、送信および受信した承認を表示するアクセス権を持っています。</span><span class="sxs-lookup"><span data-stu-id="82df5-174">From the Teams Approval App, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="82df5-175">他のユーザーが作成した承認へのアクセス権は、ユーザーが回答者または要求の閲覧者ではない限り、アクセスできません。</span><span class="sxs-lookup"><span data-stu-id="82df5-175">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="82df5-176">承認が作成されたチャットまたはチャネルの一部である場合、ユーザーにはリクエストの閲覧者の役割が与えられる。</span><span class="sxs-lookup"><span data-stu-id="82df5-176">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="82df5-177">承認が作成された際にロールが与えらなかった場合、要求に対してアクションを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="82df5-177">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>
