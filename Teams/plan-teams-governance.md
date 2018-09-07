---
title: チームのマイクロソフトのチームでの管理のための計画
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 08/10/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: チームでの管理機能の実装を計画する方法について説明します。
localization_priority: Priority
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: ddb93c883786413f18f20c98452d8e04a6534ea7
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23870102"
---
# <a name="plan-for-governance-in-teams"></a><span data-ttu-id="1b90d-103">チームの管理のための計画</span><span class="sxs-lookup"><span data-stu-id="1b90d-103">Plan for governance in Teams</span></span>

<span data-ttu-id="1b90d-104">チームは、組織が必要な場合があります、管理機能を実装するためのツールの豊富なセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="1b90d-104">Teams provides a rich set of tools to implement any governance capabilities your organization might require.</span></span> <span data-ttu-id="1b90d-105">この資料では、IT プロフェッショナルが、ガバナンス、およびそれらに対応する方法についての要件を確認するのには、正しい質問をガイドします。</span><span class="sxs-lookup"><span data-stu-id="1b90d-105">This article guides IT pros to ask the right questions to determine their requirements for governance, and how to meet them.</span></span> 

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a><span data-ttu-id="1b90d-106">グループとチームの作成、名前付け、分類、およびゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="1b90d-106">Group and team creation, naming, classification, and guest access</span></span>

<span data-ttu-id="1b90d-107">組織は、チームの名前し分類方法、来園者をチームのメンバーとして追加するか、およびチームを作成できるユーザーを厳密な制御を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b90d-107">Your organization might require that you implement strict controls on how teams are named and classified, whether guests can be added as team members, and who can create teams.</span></span> <span data-ttu-id="1b90d-108">Azure Active Directory (AD の Azure) を使用して、これらの各領域を設定できます。</span><span class="sxs-lookup"><span data-stu-id="1b90d-108">You can configure each of these areas by using Azure Active Directory (Azure AD).</span></span> 

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="1b90d-109">意思決定ポイント</span><span class="sxs-lookup"><span data-stu-id="1b90d-109">Decision points</span></span>|<ul><li><span data-ttu-id="1b90d-110">組織はチームの特定の命名規則を必要とするか。</span><span class="sxs-lookup"><span data-stu-id="1b90d-110">Does your organization require a specific naming convention for teams?</span></span></li><li><span data-ttu-id="1b90d-111">チーム作成者にチームを組織に固有の分類を割り当てる機能が必要ですか。</span><span class="sxs-lookup"><span data-stu-id="1b90d-111">Do team creators need the ability to assign organization-specific classifications to teams?</span></span></li><li><span data-ttu-id="1b90d-112">チーム別のチームにゲストを追加する機能を制限する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="1b90d-112">Do you need to restrict the ability to add guests to teams on a per-team basis?</span></span></li><li><span data-ttu-id="1b90d-113">組織は、チームを作成できるユーザーを制限することを必要ですか。</span><span class="sxs-lookup"><span data-stu-id="1b90d-113">Does your organization require limiting who can create teams?</span></span></li></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="1b90d-114">次のステップ</span><span class="sxs-lookup"><span data-stu-id="1b90d-114">Next steps</span></span>|<ul><li><span data-ttu-id="1b90d-115">チームの作成、名前付け、分類、およびゲスト アクセスのため、組織の要件を文書化します。</span><span class="sxs-lookup"><span data-stu-id="1b90d-115">Document your organization’s requirements for team creation, naming, classification, and guest access.</span></span></li><li><span data-ttu-id="1b90d-116">チームの展開の一部としてこれらの要件を実装するために計画します。</span><span class="sxs-lookup"><span data-stu-id="1b90d-116">Plan to implement these requirements as a part of your Teams rollout.</span></span></li><li><span data-ttu-id="1b90d-117">通信し、その動作のチームのユーザーに通知するポリシーを公開します。</span><span class="sxs-lookup"><span data-stu-id="1b90d-117">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

> [!TIP]
<span data-ttu-id="1b90d-118">組織の要件をキャプチャするのにには、次の表を使用します。</span><span class="sxs-lookup"><span data-stu-id="1b90d-118">Use the following table to capture your organization’s requirements.</span></span>
|<span data-ttu-id="1b90d-119">機能</span><span class="sxs-lookup"><span data-stu-id="1b90d-119">Capability</span></span> |<span data-ttu-id="1b90d-120">詳細</span><span class="sxs-lookup"><span data-stu-id="1b90d-120">Details</span></span> |<span data-ttu-id="1b90d-121">Azure AD プレミアム</span><span class="sxs-lookup"><span data-stu-id="1b90d-121">Azure AD Premium</span></span> <br> <span data-ttu-id="1b90d-122">ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="1b90d-122">license required</span></span> |<span data-ttu-id="1b90d-123">意思決定</span><span class="sxs-lookup"><span data-stu-id="1b90d-123">Decision</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="1b90d-124">チームの名前付けポリシー</span><span class="sxs-lookup"><span data-stu-id="1b90d-124">Team naming policy</span></span> | <span data-ttu-id="1b90d-125">プレフィックス、サフィックスに基づく、カスタム ブロックの単語を使用します。</span><span class="sxs-lookup"><span data-stu-id="1b90d-125">Use Prefix-Suffix–based, Custom Blocked Words.</span></span> |<span data-ttu-id="1b90d-126">P1</span><span class="sxs-lookup"><span data-stu-id="1b90d-126">P1</span></span> |<span data-ttu-id="1b90d-127">未定</span><span class="sxs-lookup"><span data-stu-id="1b90d-127">TBD</span></span> |
|<span data-ttu-id="1b90d-128">チーム分類</span><span class="sxs-lookup"><span data-stu-id="1b90d-128">Team classification</span></span> |<span data-ttu-id="1b90d-129">分類をチームに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1b90d-129">Assign classifications to teams.</span></span> |<span data-ttu-id="1b90d-130">P1</span><span class="sxs-lookup"><span data-stu-id="1b90d-130">P1</span></span> |<span data-ttu-id="1b90d-131">未定</span><span class="sxs-lookup"><span data-stu-id="1b90d-131">TBD</span></span> |
|<span data-ttu-id="1b90d-132">チームのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="1b90d-132">Team guest access</span></span> |<span data-ttu-id="1b90d-133">許可するか、来園者がチームに追加されることを防止します。</span><span class="sxs-lookup"><span data-stu-id="1b90d-133">Allow or prevent guests from being added to teams.</span></span> |<span data-ttu-id="1b90d-134">なし</span><span class="sxs-lookup"><span data-stu-id="1b90d-134">No</span></span> |<span data-ttu-id="1b90d-135">未定</span><span class="sxs-lookup"><span data-stu-id="1b90d-135">TBD</span></span> |
|<span data-ttu-id="1b90d-136">チームの作成</span><span class="sxs-lookup"><span data-stu-id="1b90d-136">Team creation</span></span> |<span data-ttu-id="1b90d-137">管理者のチームの作成を制限します。</span><span class="sxs-lookup"><span data-stu-id="1b90d-137">Limit team creation to administrators.</span></span> |<span data-ttu-id="1b90d-138">なし</span><span class="sxs-lookup"><span data-stu-id="1b90d-138">No</span></span> |<span data-ttu-id="1b90d-139">未定</span><span class="sxs-lookup"><span data-stu-id="1b90d-139">TBD</span></span>|
|<span data-ttu-id="1b90d-140">チームの作成</span><span class="sxs-lookup"><span data-stu-id="1b90d-140">Team creation</span></span> |<span data-ttu-id="1b90d-141">セキュリティ グループのメンバーにチームの作成を制限します。</span><span class="sxs-lookup"><span data-stu-id="1b90d-141">Limit team creation to security group members.</span></span> |<span data-ttu-id="1b90d-142">P1</span><span class="sxs-lookup"><span data-stu-id="1b90d-142">P1</span></span> |<span data-ttu-id="1b90d-143">未定</span><span class="sxs-lookup"><span data-stu-id="1b90d-143">TBD</span></span>|

> [!NOTE]
> <span data-ttu-id="1b90d-144">[学ぶ必要があるライセンスの詳細については、これらのポリシーを設定し、どのような](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)事前の計画に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1b90d-144">To help you plan ahead, [learn more about setting these policies and what licenses they require](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings).</span></span>

> [!NOTE]
> <span data-ttu-id="1b90d-145">グループとチームの作成を制限することと、多くの Office 365 サービスは、サービスが機能するためにグループを作成することを必要とするために、ユーザーの生産性が低下することが。</span><span class="sxs-lookup"><span data-stu-id="1b90d-145">Limiting group and team creation can slow your users’ productivity, because many Office 365 services require that groups be created for the service to function.</span></span> <span data-ttu-id="1b90d-146">詳細についてに移動し、 [Office 365 のグループを作成したユーザーを制御する理由](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)を展開します。</span><span class="sxs-lookup"><span data-stu-id="1b90d-146">For additional information, navigate to and expand [Why control who creates Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why).</span></span>


#### <a name="additional-information"></a><span data-ttu-id="1b90d-147">追加情報</span><span class="sxs-lookup"><span data-stu-id="1b90d-147">Additional information</span></span>

<span data-ttu-id="1b90d-148">お客様の要件を決定した後は、Azure AD コントロールを使用して実装できます。</span><span class="sxs-lookup"><span data-stu-id="1b90d-148">After you’ve determined your requirements, you can implement them by using Azure AD controls.</span></span> <span data-ttu-id="1b90d-149">これらの設定を実装する方法についての技術的なガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b90d-149">For technical guidance on how to implement these settings, see:</span></span>

-   <span data-ttu-id="1b90d-150">[Azure Active Directory グループの設定を構成するコマンドレット](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)です。</span><span class="sxs-lookup"><span data-stu-id="1b90d-150">[Azure Active Directory cmdlets for configuring group settings](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets).</span></span>

-   <span data-ttu-id="1b90d-151">[Azure Active Directory 内の Office 365 のグループの名前付けポリシーを適用します](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)。</span><span class="sxs-lookup"><span data-stu-id="1b90d-151">[Enforce a naming policy for Office 365 groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy).</span></span>

-   <span data-ttu-id="1b90d-152">[Office 365 のグループ ポリシーに名前を付ける](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。</span><span class="sxs-lookup"><span data-stu-id="1b90d-152">[Office 365 Groups naming policy](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>


## <a name="group-and-team-expiration-retention-and-archiving"></a><span data-ttu-id="1b90d-153">グループとチームの有効期限、保存、およびアーカイブ</span><span class="sxs-lookup"><span data-stu-id="1b90d-153">Group and team expiration, retention, and archiving</span></span>

<span data-ttu-id="1b90d-154">保持、有効期限ポリシーを設定するための追加要件を持つ組織もあり、チームおよびチームのデータをアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="1b90d-154">Your organization might have additional requirements for setting policies for expiration, retention, and archiving teams and teams data.</span></span> <span data-ttu-id="1b90d-155">自動的に保持するか、必要に応じて情報を削除するグループ、および保存ポリシーのライフ サイクルを管理するグループの有効期限ポリシーを構成することができ、チームをアーカイブすることができます (読み取り専用モードに設定する) チームのポイント ・ イン ・ タイム ・ ビューを保持するためのアクティブではないです。</span><span class="sxs-lookup"><span data-stu-id="1b90d-155">You can configure group expiration policies to automatically manage the lifecycle of the group and retention policies to preserve or delete information as needed, and you can archive teams (set them to read-only mode) to preserve a point-in-time view of a team that’s no longer active.</span></span>

|           |            |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="1b90d-156">意思決定ポイント</span><span class="sxs-lookup"><span data-stu-id="1b90d-156">Decision points</span></span>|<ul><li><span data-ttu-id="1b90d-157">組織はチームの有効期限を指定する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="1b90d-157">Does your organization require specifying an expiration date for teams?</span></span></li><li><span data-ttu-id="1b90d-158">組織に必要な特定のデータ ・ リテンション ・ ポリシーは、チームに適用するか。</span><span class="sxs-lookup"><span data-stu-id="1b90d-158">Does your organization require specific data retention policies be applied to teams?</span></span></li><li><span data-ttu-id="1b90d-159">組織は、読み取り専用状態でコンテンツを保持するためにチームを非アクティブにアーカイブする機能を必要とする予定ですか。</span><span class="sxs-lookup"><span data-stu-id="1b90d-159">Does your organization expect to require the ability to archive inactive teams to preserve the content in a read-only state?</span></span></li></ul>|
| ![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="1b90d-160">次のステップ</span><span class="sxs-lookup"><span data-stu-id="1b90d-160">Next steps</span></span>|<ul><li><span data-ttu-id="1b90d-161">チームの有効期限、データの保存、アーカイブに関する組織の要件を文書化します。</span><span class="sxs-lookup"><span data-stu-id="1b90d-161">Document your organization’s requirements for team expiration, data retention, and archiving.</span></span></li><li><span data-ttu-id="1b90d-162">チームの展開の一部としてこれらの要件を実装するために計画します。</span><span class="sxs-lookup"><span data-stu-id="1b90d-162">Plan to implement these requirements as part of your Teams rollout.</span></span></li><li><span data-ttu-id="1b90d-163">通信し、その動作のチームのユーザーに通知するポリシーを公開します。</span><span class="sxs-lookup"><span data-stu-id="1b90d-163">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

> [!TIP]
<span data-ttu-id="1b90d-164">組織の要件をキャプチャするのにには、次の表を使用します。</span><span class="sxs-lookup"><span data-stu-id="1b90d-164">Use the following table to capture your organization’s requirements.</span></span>
|<span data-ttu-id="1b90d-165">機能</span><span class="sxs-lookup"><span data-stu-id="1b90d-165">Capability</span></span> |<span data-ttu-id="1b90d-166">詳細</span><span class="sxs-lookup"><span data-stu-id="1b90d-166">Details</span></span> |<span data-ttu-id="1b90d-167">Azure AD プレミアム</span><span class="sxs-lookup"><span data-stu-id="1b90d-167">Azure AD Premium</span></span> <br><span data-ttu-id="1b90d-168">ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="1b90d-168">license required</span></span> |<span data-ttu-id="1b90d-169">意思決定</span><span class="sxs-lookup"><span data-stu-id="1b90d-169">Decision</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="1b90d-170">有効期限ポリシー</span><span class="sxs-lookup"><span data-stu-id="1b90d-170">Expiration policy</span></span> |<span data-ttu-id="1b90d-171">有効期限ポリシーを設定することにより、Office 365 のグループのライフ サイクルを管理します。</span><span class="sxs-lookup"><span data-stu-id="1b90d-171">Manage the lifecycle of Office 365 groups by setting an expiration policy.</span></span> |<span data-ttu-id="1b90d-172">P1</span><span class="sxs-lookup"><span data-stu-id="1b90d-172">P1</span></span> |<span data-ttu-id="1b90d-173">未定</span><span class="sxs-lookup"><span data-stu-id="1b90d-173">TBD</span></span>|
|<span data-ttu-id="1b90d-174">リテンション ・ ポリシー</span><span class="sxs-lookup"><span data-stu-id="1b90d-174">Retention policy</span></span> |<span data-ttu-id="1b90d-175">保持または、セキュリティとコンプライアンスの中心でチームのリテンション ・ ポリシーを設定することによって、特定の期間 (チームのチャネル メッセージ、チャネル ファイル) のデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="1b90d-175">Retain or delete data (Teams channel messages and channel files) for a specific time period by setting retention policies for Teams in the Security & compliance center.</span></span> <span data-ttu-id="1b90d-176">**注**: この機能を使用するには、Office 365 エンタープライズ E3 以上のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="1b90d-176">**Note**: Using this feature requires licensing of Office 365 Enterprise E3 or above.</span></span> |<span data-ttu-id="1b90d-177">なし</span><span class="sxs-lookup"><span data-stu-id="1b90d-177">No</span></span> |<span data-ttu-id="1b90d-178">未定</span><span class="sxs-lookup"><span data-stu-id="1b90d-178">TBD</span></span> |
|<span data-ttu-id="1b90d-179">アーカイブと復元</span><span class="sxs-lookup"><span data-stu-id="1b90d-179">Archive and restore</span></span> |<span data-ttu-id="1b90d-180">チームは、アクティブになっていませんが、参照を保持するか、将来的に再アクティブ化するときにアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="1b90d-180">Archive a team when it’s no longer active but you want to keep it around for reference or to reactivate in the future.</span></span> |<span data-ttu-id="1b90d-181">なし</span><span class="sxs-lookup"><span data-stu-id="1b90d-181">No</span></span> |<span data-ttu-id="1b90d-182">未定</span><span class="sxs-lookup"><span data-stu-id="1b90d-182">TBD</span></span> |

> [!Note]
> <span data-ttu-id="1b90d-183">グループの有効期限は、Azure AD プレミアム機能です。</span><span class="sxs-lookup"><span data-stu-id="1b90d-183">Group expiration is an Azure AD Premium feature.</span></span> <span data-ttu-id="1b90d-184">できるようにするには、この機能に、テナントは設定し、影響を受けるグループのメンバーを設定する管理者の Azure AD プレミアムとライセンスのサブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="1b90d-184">For this feature to be available, your tenant must have a subscription to Azure AD Premium and licenses for the administrator who configures the settings and the members of the affected groups.</span></span>

#### <a name="additional-information"></a><span data-ttu-id="1b90d-185">追加情報</span><span class="sxs-lookup"><span data-stu-id="1b90d-185">Additional information</span></span>

<span data-ttu-id="1b90d-186">これらの設定を実装する方法についての技術的なガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b90d-186">For technical guidance on how to implement these settings, see:</span></span>

-   <span data-ttu-id="1b90d-187">[Office 365 のグループの有効期限を設定](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)します。</span><span class="sxs-lookup"><span data-stu-id="1b90d-187">[Set up Office 365 groups expiration](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle).</span></span>

-   <span data-ttu-id="1b90d-188">[チーム ・ リテンション ・ ポリシーを設定](security-compliance-overview.md#retention-policies)します。</span><span class="sxs-lookup"><span data-stu-id="1b90d-188">[Set up Teams retention policies](security-compliance-overview.md#retention-policies).</span></span>

-   <span data-ttu-id="1b90d-189">[アーカイブまたはチームを復元](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)します。</span><span class="sxs-lookup"><span data-stu-id="1b90d-189">[Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>


## <a name="teams-feature-management"></a><span data-ttu-id="1b90d-190">チーム機能の管理</span><span class="sxs-lookup"><span data-stu-id="1b90d-190">Teams feature management</span></span>

<span data-ttu-id="1b90d-191">ガバナンスとチームのライフ サイクル管理のもう 1 つの重要な側面は、どのような機能、ユーザーがへのアクセスを制御する機能です。</span><span class="sxs-lookup"><span data-stu-id="1b90d-191">Another important aspect of governance and lifecycle management for Teams is the ability to control what features your users will have access to.</span></span> <span data-ttu-id="1b90d-192">メッセージング、会議、および Office 365 のテナントのレベルまたはユーザーごとのいずれかで、機能の呼び出しを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="1b90d-192">You can manage messaging, meeting, and calling features, either at the Office 365 tenant level or per-user.</span></span> 


|         |         |
|---------|---------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="1b90d-193">意思決定ポイント</span><span class="sxs-lookup"><span data-stu-id="1b90d-193">Decision points</span></span>|<ul><li><span data-ttu-id="1b90d-194">組織は、全体のテナントのチームの機能を制限する必要ですか。</span><span class="sxs-lookup"><span data-stu-id="1b90d-194">Does your organization require limiting Teams features for your entire tenant?</span></span></li><li><span data-ttu-id="1b90d-195">組織が特定のユーザーのチームの機能を制限する必要ですか。</span><span class="sxs-lookup"><span data-stu-id="1b90d-195">Does your organization require limiting Teams features for specific users?</span></span></li></ul>|
| ![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="1b90d-196">次のステップ</span><span class="sxs-lookup"><span data-stu-id="1b90d-196">Next steps</span></span>|<ul><li><span data-ttu-id="1b90d-197">テナントとユーザー レベルのチームの機能を制限するため、組織の要件を文書化します。</span><span class="sxs-lookup"><span data-stu-id="1b90d-197">Document your organization’s requirements for limiting Teams features at the tenant and user level.</span></span></li><li><span data-ttu-id="1b90d-198">チームの展開の一部として、特定の要件を実装するために計画します。</span><span class="sxs-lookup"><span data-stu-id="1b90d-198">Plan to implement your specific requirements as part of your Teams rollout.</span></span></li><li><span data-ttu-id="1b90d-199">通信し、その動作のチームのユーザーに通知するポリシーを公開します。</span><span class="sxs-lookup"><span data-stu-id="1b90d-199">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

### <a name="teams-feature-management-focus-areas"></a><span data-ttu-id="1b90d-200">チーム機能の管理の重点分野</span><span class="sxs-lookup"><span data-stu-id="1b90d-200">Teams feature management focus areas</span></span>

<span data-ttu-id="1b90d-201">チームでは、メッセージング、会議、呼び出し、およびライブ イベントの機能と詳細については、ポリシーを使用して制御するための詳細な機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="1b90d-201">Teams provides granular capabilities for controlling messaging, meeting, calling, and live event features and more, via policies.</span></span> <span data-ttu-id="1b90d-202">デフォルトで、または組織内で必要に応じてユーザーごと、すべてのユーザーに異なるポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="1b90d-202">Different policies can be applied to all users by default or per user as required by your organization.</span></span> 

<span data-ttu-id="1b90d-203">組織では、それらを実装する方法についての技術的なガイダンスを含む、すべての設定の詳細なリストは、以下の資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b90d-203">For detailed lists of all settings, including technical guidance on how to implement them for your organization, see the following articles:</span></span>

-   [<span data-ttu-id="1b90d-204">Office 365 組織でマイクロソフトのチーム機能を管理します。</span><span class="sxs-lookup"><span data-stu-id="1b90d-204">Manage Microsoft Teams features in your Office 365 organization</span></span>](enable-features-office-365.md)
-   [<span data-ttu-id="1b90d-205">新しいマイクロソフトのチームとビジネス管理センターの Skype に移行する際のチームを管理します。</span><span class="sxs-lookup"><span data-stu-id="1b90d-205">Manage Teams during the transition to the new Microsoft Teams and Skype for Business Admin Center</span></span>](manage-teams-skypeforbusiness-admin-center.md)
-   [<span data-ttu-id="1b90d-206">チームでミーティングのポリシーを管理します。</span><span class="sxs-lookup"><span data-stu-id="1b90d-206">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)


## <a name="security-and-compliance"></a><span data-ttu-id="1b90d-207">セキュリティとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="1b90d-207">Security and compliance</span></span>

<span data-ttu-id="1b90d-208">チームでは、高度なセキュリティおよびコンプライアンス機能を Office 365 の上に構築された、監査およびレポート作成、コンプライアンス ・ コンテンツの検索、電子的証拠開示、法的保持義務、および保存ポリシーをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1b90d-208">Teams is built on the advanced security and compliance capabilities of Office 365 and supports auditing and reporting, compliance content search, e-discovery, Legal Hold, and retention policies.</span></span> 

> [!Important]
> <span data-ttu-id="1b90d-209">組織は、コンプライアンスおよびセキュリティの要件は、[セキュリティとマイクロソフトのチームでのコンプライアンスの概要](security-compliance-overview.md)の資料では、このトピックに関する詳細な内容を確認してください。</span><span class="sxs-lookup"><span data-stu-id="1b90d-209">If your organization has compliance and security requirements, review the in-depth content provided about this topic in the article [Overview of security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->