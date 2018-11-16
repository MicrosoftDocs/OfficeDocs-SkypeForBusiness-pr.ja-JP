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
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5becca716ad4790cc0b156dd15895e66fea7d836
ms.sourcegitcommit: f0dec487e2893a171c7e701bfcf598076f5245b7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "26539042"
---
# <a name="plan-for-governance-in-teams"></a><span data-ttu-id="1f4c2-103">チームの管理のための計画</span><span class="sxs-lookup"><span data-stu-id="1f4c2-103">Plan for governance in Teams</span></span>

<span data-ttu-id="1f4c2-104">チームは、組織が必要な場合があります、管理機能を実装するためのツールの豊富なセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-104">Teams provides a rich set of tools to implement any governance capabilities your organization might require.</span></span> <span data-ttu-id="1f4c2-105">この資料では、IT プロフェッショナルが、ガバナンス、およびそれらに対応する方法についての要件を確認するのには、正しい質問をガイドします。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-105">This article guides IT pros to ask the right questions to determine their requirements for governance, and how to meet them.</span></span> 

> [!Tip] 
> <span data-ttu-id="1f4c2-106">マイクロソフトのチームでの管理の詳細については、次のセッションを見る:[管理、管理、およびマイクロソフトのチームでのライフ サイクル](https://aka.ms/teams-governance)</span><span class="sxs-lookup"><span data-stu-id="1f4c2-106">Watch the following session to learn about more about Governance in Microsoft Teams: [Governance, management and lifecycle in Microsoft Teams](https://aka.ms/teams-governance)</span></span>

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a><span data-ttu-id="1f4c2-107">グループとチームの作成、名前付け、分類、およびゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="1f4c2-107">Group and team creation, naming, classification, and guest access</span></span>

<span data-ttu-id="1f4c2-108">組織は、チームの名前し分類方法、来園者をチームのメンバーとして追加するか、およびチームを作成できるユーザーを厳密な制御を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-108">Your organization might require that you implement strict controls on how teams are named and classified, whether guests can be added as team members, and who can create teams.</span></span> <span data-ttu-id="1f4c2-109">Azure Active Directory (AD の Azure) を使用して、これらの各領域を設定できます。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-109">You can configure each of these areas by using Azure Active Directory (Azure AD).</span></span> 

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="1f4c2-110">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="1f4c2-110">Decision points</span></span>|<ul><li><span data-ttu-id="1f4c2-111">組織はチームの特定の命名規則を必要とするか。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-111">Does your organization require a specific naming convention for teams?</span></span></li><li><span data-ttu-id="1f4c2-112">チーム作成者にチームを組織に固有の分類を割り当てる機能が必要ですか。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-112">Do team creators need the ability to assign organization-specific classifications to teams?</span></span></li><li><span data-ttu-id="1f4c2-113">チーム別のチームにゲストを追加する機能を制限する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-113">Do you need to restrict the ability to add guests to teams on a per-team basis?</span></span></li><li><span data-ttu-id="1f4c2-114">組織は、チームを作成できるユーザーを制限することを必要ですか。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-114">Does your organization require limiting who can create teams?</span></span></li></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="1f4c2-115">次のステップ</span><span class="sxs-lookup"><span data-stu-id="1f4c2-115">Next steps</span></span>|<ul><li><span data-ttu-id="1f4c2-116">チームの作成、名前付け、分類、およびゲスト アクセスのため、組織の要件を文書化します。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-116">Document your organization’s requirements for team creation, naming, classification, and guest access.</span></span></li><li><span data-ttu-id="1f4c2-117">チームの展開の一部としてこれらの要件を実装するために計画します。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-117">Plan to implement these requirements as a part of your Teams rollout.</span></span></li><li><span data-ttu-id="1f4c2-118">通信し、その動作のチームのユーザーに通知するポリシーを公開します。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-118">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

> [!TIP]
> <span data-ttu-id="1f4c2-119">組織の要件をキャプチャするのにには、次の表を使用します。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-119">Use the following table to capture your organization’s requirements.</span></span>
> 
> |<span data-ttu-id="1f4c2-120">機能</span><span class="sxs-lookup"><span data-stu-id="1f4c2-120">Capability</span></span> |<span data-ttu-id="1f4c2-121">詳細</span><span class="sxs-lookup"><span data-stu-id="1f4c2-121">Details</span></span> |<span data-ttu-id="1f4c2-122">Azure AD プレミアム</span><span class="sxs-lookup"><span data-stu-id="1f4c2-122">Azure AD Premium</span></span> <br> <span data-ttu-id="1f4c2-123">ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="1f4c2-123">license required</span></span> |<span data-ttu-id="1f4c2-124">意思決定</span><span class="sxs-lookup"><span data-stu-id="1f4c2-124">Decision</span></span> |
> |---------|---------|---------|---------|
> |<span data-ttu-id="1f4c2-125">チームの名前付けポリシー</span><span class="sxs-lookup"><span data-stu-id="1f4c2-125">Team naming policy</span></span> | <span data-ttu-id="1f4c2-126">プレフィックス、サフィックスに基づく、カスタム ブロックの単語を使用します。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-126">Use Prefix-Suffix–based, Custom Blocked Words.</span></span> |<span data-ttu-id="1f4c2-127">P1</span><span class="sxs-lookup"><span data-stu-id="1f4c2-127">P1</span></span> |<span data-ttu-id="1f4c2-128">未定</span><span class="sxs-lookup"><span data-stu-id="1f4c2-128">TBD</span></span> |
> |<span data-ttu-id="1f4c2-129">チーム分類</span><span class="sxs-lookup"><span data-stu-id="1f4c2-129">Team classification</span></span> |<span data-ttu-id="1f4c2-130">分類をチームに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-130">Assign classifications to teams.</span></span> |<span data-ttu-id="1f4c2-131">P1</span><span class="sxs-lookup"><span data-stu-id="1f4c2-131">P1</span></span> |<span data-ttu-id="1f4c2-132">未定</span><span class="sxs-lookup"><span data-stu-id="1f4c2-132">TBD</span></span> |
> |<span data-ttu-id="1f4c2-133">チームのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="1f4c2-133">Team guest access</span></span> |<span data-ttu-id="1f4c2-134">許可するか、来園者がチームに追加されることを防止します。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-134">Allow or prevent guests from being added to teams.</span></span> |<span data-ttu-id="1f4c2-135">なし</span><span class="sxs-lookup"><span data-stu-id="1f4c2-135">No</span></span> |<span data-ttu-id="1f4c2-136">未定</span><span class="sxs-lookup"><span data-stu-id="1f4c2-136">TBD</span></span> |
> |<span data-ttu-id="1f4c2-137">チームの作成</span><span class="sxs-lookup"><span data-stu-id="1f4c2-137">Team creation</span></span> |<span data-ttu-id="1f4c2-138">管理者のチームの作成を制限します。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-138">Limit team creation to administrators.</span></span> |<span data-ttu-id="1f4c2-139">なし</span><span class="sxs-lookup"><span data-stu-id="1f4c2-139">No</span></span> |<span data-ttu-id="1f4c2-140">未定</span><span class="sxs-lookup"><span data-stu-id="1f4c2-140">TBD</span></span>|
> |<span data-ttu-id="1f4c2-141">チームの作成</span><span class="sxs-lookup"><span data-stu-id="1f4c2-141">Team creation</span></span> |<span data-ttu-id="1f4c2-142">セキュリティ グループのメンバーにチームの作成を制限します。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-142">Limit team creation to security group members.</span></span> |<span data-ttu-id="1f4c2-143">P1</span><span class="sxs-lookup"><span data-stu-id="1f4c2-143">P1</span></span> |<span data-ttu-id="1f4c2-144">未定</span><span class="sxs-lookup"><span data-stu-id="1f4c2-144">TBD</span></span>|
> 
> [!NOTE]
> <span data-ttu-id="1f4c2-145">[学ぶ必要があるライセンスの詳細については、これらのポリシーを設定し、どのような](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)事前の計画に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-145">To help you plan ahead, [learn more about setting these policies and what licenses they require](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings).</span></span>
> 
> [!NOTE]
> <span data-ttu-id="1f4c2-146">グループとチームの作成を制限することと、多くの Office 365 サービスは、サービスが機能するためにグループを作成することを必要とするために、ユーザーの生産性が低下することが。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-146">Limiting group and team creation can slow your users’ productivity, because many Office 365 services require that groups be created for the service to function.</span></span> <span data-ttu-id="1f4c2-147">詳細についてに移動し、 [Office 365 のグループを作成したユーザーを制御する理由](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)を展開します。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-147">For additional information, navigate to and expand [Why control who creates Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why).</span></span>


#### <a name="additional-information"></a><span data-ttu-id="1f4c2-148">追加情報</span><span class="sxs-lookup"><span data-stu-id="1f4c2-148">Additional information</span></span>

<span data-ttu-id="1f4c2-149">お客様の要件を決定した後は、Azure AD コントロールを使用して実装できます。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-149">After you’ve determined your requirements, you can implement them by using Azure AD controls.</span></span> <span data-ttu-id="1f4c2-150">これらの設定を実装する方法についての技術的なガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-150">For technical guidance on how to implement these settings, see:</span></span>

-   <span data-ttu-id="1f4c2-151">[Azure Active Directory グループの設定を構成するコマンドレット](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)です。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-151">[Azure Active Directory cmdlets for configuring group settings](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets).</span></span>

-   <span data-ttu-id="1f4c2-152">[Azure Active Directory 内の Office 365 のグループの名前付けポリシーを適用します](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-152">[Enforce a naming policy for Office 365 groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy).</span></span>

-   <span data-ttu-id="1f4c2-153">[Office 365 のグループ ポリシーに名前を付ける](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-153">[Office 365 Groups naming policy](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>


## <a name="group-and-team-expiration-retention-and-archiving"></a><span data-ttu-id="1f4c2-154">グループとチームの有効期限、保存、およびアーカイブ</span><span class="sxs-lookup"><span data-stu-id="1f4c2-154">Group and team expiration, retention, and archiving</span></span>

<span data-ttu-id="1f4c2-155">保持、有効期限ポリシーを設定するための追加要件を持つ組織もあり、チームおよびチームのデータをアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-155">Your organization might have additional requirements for setting policies for expiration, retention, and archiving teams and teams data.</span></span> <span data-ttu-id="1f4c2-156">自動的に保持するか、必要に応じて情報を削除するグループ、および保存ポリシーのライフ サイクルを管理するグループの有効期限ポリシーを構成することができ、チームをアーカイブすることができます (読み取り専用モードに設定する) チームのポイント ・ イン ・ タイム ・ ビューを保持するためのアクティブではないです。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-156">You can configure group expiration policies to automatically manage the lifecycle of the group and retention policies to preserve or delete information as needed, and you can archive teams (set them to read-only mode) to preserve a point-in-time view of a team that’s no longer active.</span></span>

|           |            |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="1f4c2-157">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="1f4c2-157">Decision points</span></span>|<ul><li><span data-ttu-id="1f4c2-158">組織はチームの有効期限を指定する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-158">Does your organization require specifying an expiration date for teams?</span></span></li><li><span data-ttu-id="1f4c2-159">組織に必要な特定のデータ ・ リテンション ・ ポリシーは、チームに適用するか。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-159">Does your organization require specific data retention policies be applied to teams?</span></span></li><li><span data-ttu-id="1f4c2-160">組織は、読み取り専用状態でコンテンツを保持するためにチームを非アクティブにアーカイブする機能を必要とする予定ですか。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-160">Does your organization expect to require the ability to archive inactive teams to preserve the content in a read-only state?</span></span></li></ul>|
| ![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="1f4c2-161">次のステップ</span><span class="sxs-lookup"><span data-stu-id="1f4c2-161">Next steps</span></span>|<ul><li><span data-ttu-id="1f4c2-162">チームの有効期限、データの保存、アーカイブに関する組織の要件を文書化します。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-162">Document your organization’s requirements for team expiration, data retention, and archiving.</span></span></li><li><span data-ttu-id="1f4c2-163">チームの展開の一部としてこれらの要件を実装するために計画します。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-163">Plan to implement these requirements as part of your Teams rollout.</span></span></li><li><span data-ttu-id="1f4c2-164">通信し、その動作のチームのユーザーに通知するポリシーを公開します。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-164">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

> [!TIP]
> <span data-ttu-id="1f4c2-165">組織の要件をキャプチャするのにには、次の表を使用します。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-165">Use the following table to capture your organization’s requirements.</span></span>
> 
> |<span data-ttu-id="1f4c2-166">機能</span><span class="sxs-lookup"><span data-stu-id="1f4c2-166">Capability</span></span> |<span data-ttu-id="1f4c2-167">詳細</span><span class="sxs-lookup"><span data-stu-id="1f4c2-167">Details</span></span> |<span data-ttu-id="1f4c2-168">Azure AD プレミアム</span><span class="sxs-lookup"><span data-stu-id="1f4c2-168">Azure AD Premium</span></span> <br><span data-ttu-id="1f4c2-169">ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="1f4c2-169">license required</span></span> |<span data-ttu-id="1f4c2-170">意思決定</span><span class="sxs-lookup"><span data-stu-id="1f4c2-170">Decision</span></span> |
> |---------|---------|---------|---------|
> |<span data-ttu-id="1f4c2-171">有効期限ポリシー</span><span class="sxs-lookup"><span data-stu-id="1f4c2-171">Expiration policy</span></span> |<span data-ttu-id="1f4c2-172">有効期限ポリシーを設定することにより、Office 365 のグループのライフ サイクルを管理します。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-172">Manage the lifecycle of Office 365 groups by setting an expiration policy.</span></span> |<span data-ttu-id="1f4c2-173">P1</span><span class="sxs-lookup"><span data-stu-id="1f4c2-173">P1</span></span> |<span data-ttu-id="1f4c2-174">未定</span><span class="sxs-lookup"><span data-stu-id="1f4c2-174">TBD</span></span>|
> |<span data-ttu-id="1f4c2-175">リテンション ・ ポリシー</span><span class="sxs-lookup"><span data-stu-id="1f4c2-175">Retention policy</span></span> |<span data-ttu-id="1f4c2-176">保持または、セキュリティとコンプライアンスの中心でチームのリテンション ・ ポリシーを設定することによって、特定の期間 (チームのチャネル メッセージ、チャネル ファイル) のデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-176">Retain or delete data (Teams channel messages and channel files) for a specific time period by setting retention policies for Teams in the Security & compliance center.</span></span> <span data-ttu-id="1f4c2-177">**注**: この機能を使用するには、Office 365 エンタープライズ E3 以上のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-177">**Note**: Using this feature requires licensing of Office 365 Enterprise E3 or above.</span></span> |<span data-ttu-id="1f4c2-178">なし</span><span class="sxs-lookup"><span data-stu-id="1f4c2-178">No</span></span> |<span data-ttu-id="1f4c2-179">未定</span><span class="sxs-lookup"><span data-stu-id="1f4c2-179">TBD</span></span> |
> |<span data-ttu-id="1f4c2-180">アーカイブと復元</span><span class="sxs-lookup"><span data-stu-id="1f4c2-180">Archive and restore</span></span> |<span data-ttu-id="1f4c2-181">チームは、アクティブになっていませんが、参照を保持するか、将来的に再アクティブ化するときにアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-181">Archive a team when it’s no longer active but you want to keep it around for reference or to reactivate in the future.</span></span> |<span data-ttu-id="1f4c2-182">なし</span><span class="sxs-lookup"><span data-stu-id="1f4c2-182">No</span></span> |<span data-ttu-id="1f4c2-183">未定</span><span class="sxs-lookup"><span data-stu-id="1f4c2-183">TBD</span></span> |
> 
> [!Note]
> <span data-ttu-id="1f4c2-184">グループの有効期限は、Azure AD プレミアム機能です。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-184">Group expiration is an Azure AD Premium feature.</span></span> <span data-ttu-id="1f4c2-185">できるようにするには、この機能に、テナントは設定し、影響を受けるグループのメンバーを設定する管理者の Azure AD プレミアムとライセンスのサブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-185">For this feature to be available, your tenant must have a subscription to Azure AD Premium and licenses for the administrator who configures the settings and the members of the affected groups.</span></span>

#### <a name="additional-information"></a><span data-ttu-id="1f4c2-186">追加情報</span><span class="sxs-lookup"><span data-stu-id="1f4c2-186">Additional information</span></span>

<span data-ttu-id="1f4c2-187">これらの設定を実装する方法についての技術的なガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-187">For technical guidance on how to implement these settings, see:</span></span>

-   <span data-ttu-id="1f4c2-188">[Office 365 のグループの有効期限を設定](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)します。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-188">[Set up Office 365 groups expiration](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle).</span></span>

-   <span data-ttu-id="1f4c2-189">[チーム ・ リテンション ・ ポリシーを設定](retention-policies.md)します。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-189">[Set up Teams retention policies](retention-policies.md).</span></span>

-   <span data-ttu-id="1f4c2-190">[アーカイブまたはチームを復元](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)します。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-190">[Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>


## <a name="teams-feature-management"></a><span data-ttu-id="1f4c2-191">チーム機能の管理</span><span class="sxs-lookup"><span data-stu-id="1f4c2-191">Teams feature management</span></span>

<span data-ttu-id="1f4c2-192">ガバナンスとチームのライフ サイクル管理のもう 1 つの重要な側面は、どのような機能、ユーザーがへのアクセスを制御する機能です。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-192">Another important aspect of governance and lifecycle management for Teams is the ability to control what features your users will have access to.</span></span> <span data-ttu-id="1f4c2-193">メッセージング、会議、および Office 365 のテナントのレベルまたはユーザーごとのいずれかで、機能の呼び出しを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-193">You can manage messaging, meeting, and calling features, either at the Office 365 tenant level or per-user.</span></span> 


|         |         |
|---------|---------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="1f4c2-194">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="1f4c2-194">Decision points</span></span>|<ul><li><span data-ttu-id="1f4c2-195">組織は、全体のテナントのチームの機能を制限する必要ですか。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-195">Does your organization require limiting Teams features for your entire tenant?</span></span></li><li><span data-ttu-id="1f4c2-196">組織が特定のユーザーのチームの機能を制限する必要ですか。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-196">Does your organization require limiting Teams features for specific users?</span></span></li></ul>|
| ![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="1f4c2-197">次のステップ</span><span class="sxs-lookup"><span data-stu-id="1f4c2-197">Next steps</span></span>|<ul><li><span data-ttu-id="1f4c2-198">テナントとユーザー レベルのチームの機能を制限するため、組織の要件を文書化します。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-198">Document your organization’s requirements for limiting Teams features at the tenant and user level.</span></span></li><li><span data-ttu-id="1f4c2-199">チームの展開の一部として、特定の要件を実装するために計画します。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-199">Plan to implement your specific requirements as part of your Teams rollout.</span></span></li><li><span data-ttu-id="1f4c2-200">通信し、その動作のチームのユーザーに通知するポリシーを公開します。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-200">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

### <a name="teams-feature-management-focus-areas"></a><span data-ttu-id="1f4c2-201">チーム機能の管理の重点分野</span><span class="sxs-lookup"><span data-stu-id="1f4c2-201">Teams feature management focus areas</span></span>

<span data-ttu-id="1f4c2-202">チームでは、メッセージング、会議、呼び出し、およびライブ イベントの機能と詳細については、ポリシーを使用して制御するための詳細な機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-202">Teams provides granular capabilities for controlling messaging, meeting, calling, and live event features and more, via policies.</span></span> <span data-ttu-id="1f4c2-203">デフォルトで、または組織内で必要に応じてユーザーごと、すべてのユーザーに異なるポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-203">Different policies can be applied to all users by default or per user as required by your organization.</span></span> 

<span data-ttu-id="1f4c2-204">組織では、それらを実装する方法についての技術的なガイダンスを含む、すべての設定の詳細なリストは、以下の資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-204">For detailed lists of all settings, including technical guidance on how to implement them for your organization, see the following articles:</span></span>

-   [<span data-ttu-id="1f4c2-205">Office 365 組織でマイクロソフトのチーム機能を管理します。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-205">Manage Microsoft Teams features in your Office 365 organization</span></span>](enable-features-office-365.md)
-   [<span data-ttu-id="1f4c2-206">新しいマイクロソフトのチームとビジネス管理センターの Skype に移行する際のチームを管理します。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-206">Manage Teams during the transition to the new Microsoft Teams and Skype for Business Admin Center</span></span>](manage-teams-skypeforbusiness-admin-center.md)
-   [<span data-ttu-id="1f4c2-207">チームでミーティングのポリシーを管理します。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-207">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)


## <a name="security-and-compliance"></a><span data-ttu-id="1f4c2-208">セキュリティとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="1f4c2-208">Security and compliance</span></span>

<span data-ttu-id="1f4c2-209">チームでは、高度なセキュリティおよびコンプライアンス機能を Office 365 の上に構築された、監査およびレポート作成、コンプライアンス ・ コンテンツの検索、電子的証拠開示、法的保持義務、および保存ポリシーをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-209">Teams is built on the advanced security and compliance capabilities of Office 365 and supports auditing and reporting, compliance content search, e-discovery, Legal Hold, and retention policies.</span></span> 

> [!Important]
> <span data-ttu-id="1f4c2-210">組織は、コンプライアンスおよびセキュリティの要件は、[セキュリティとマイクロソフトのチームでのコンプライアンスの概要](security-compliance-overview.md)の資料では、このトピックに関する詳細な内容を確認してください。</span><span class="sxs-lookup"><span data-stu-id="1f4c2-210">If your organization has compliance and security requirements, review the in-depth content provided about this topic in the article [Overview of security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
