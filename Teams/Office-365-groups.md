---
title: Office 365 グループと Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: Office 365 グループとグループ メンバーシップがどのように Microsoft Teams と連携しているかについて説明します。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f16a99f00add1e93bfdf4cde29f4b75f384a296
ms.sourcegitcommit: cacd16f596460c1400dd514437794afd04bddadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2018
---
<a name="office-365-groups-and-microsoft-teams"></a><span data-ttu-id="00747-103">Office 365 グループと Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="00747-103">Office 365 groups and Microsoft Teams</span></span>
=====================================

<span data-ttu-id="00747-p101">Office 365 グループは Office 365 のクロスアプリケーションのメンバーシップ サービスです。基本的なレベルでは、Office 365 グループはメンバーのリストを含む Azure Active Directory のオブジェクトです。さらに、このオブジェクトには SharePoint チーム サイト、Yammer グループ、Exchange メールボックスのリソース、Planner、PowerBI、OneNote などの関連ワークロードとの疎結合も含まれています。Active Directory のその他のグループベースのセキュリティ オブジェクトと同様にグループにユーザーを追加したり、グループからユーザーを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="00747-p101">Office 365 Groups is the cross-application membership service in Office 365. At the basic level, an Office 365 Group is an object in Azure Active Directory with a list of members and a loose coupling to related workloads including a SharePoint team site, Yammer Group, shared Exchange mailbox resources, Planner, PowerBI and OneNote. You can add or remove people to the Group just as you would any other group-based security object in Active Directory.</span></span>

<span data-ttu-id="00747-107">Office 365 の管理者は Office 365 グループの定義やメンバーの追加を行うことができ、Exchange 共有メールボックス、SharePoint ドキュメント ライブラリなどの機能も利用することができます。グループについて詳しくは、「[Office 365 グループの概要](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="00747-107">An Office 365 administrator can define an Office 365 Group, add members, and benefit from features such as an Exchange shared mailbox, SharePoint document library, Yammer Group, etc. For more information about Groups visit: [Learn about Office 365 Groups](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).</span></span>

<a name="how-office-365-groups-work"></a><span data-ttu-id="00747-108">Office 365 グループについて</span><span class="sxs-lookup"><span data-stu-id="00747-108">How Office 365 groups work</span></span>
--------------------------

<span data-ttu-id="00747-p102">Microsoft Teams のチームを作成することは、最終的には SharePoint ドキュメント ライブラリ、OneNote ノートブック、その他の Office 365 クラウド アプリケーションと関連付けられた Office 365 グループを作成することを意味します。チームを作成しているユーザーが既存の Office 365 パブリックまたはプライベート グループの所有者である場合は、Teams の機能をグループに追加できます。追加を行うと、チャット メッセージ、ドキュメント、OneNote、その他のオブジェクトが配置される既定の「全般」チャネルが作成されます。そのチャネルのドキュメント ライブラリを表示すると、チームのチャネルを表す「全般」フォルダーが表示されます。さらに重要な点は、ドキュメント ライブラリ内で独自のフォルダー構造を作成しても、それはチャネルとして Teams に**伝播されません**。現時点では、Teams から SharePoint にのみ伝播されます。</span><span class="sxs-lookup"><span data-stu-id="00747-p102">When you create a Microsoft Team, on the backend, you’re creating an Office 365 Group along with the associated SharePoint document library, OneNote notebook, along with ties into other Office 365 cloud applications. If the person creating the Team is an owner of an existing Office 365 Public or Private Group, they can add Teams functionality to the Group. This creates one default “General” channel in which chat messages, documents, OneNote, and other objects reside. Viewing the document library for the channel will reveal the “General” folder representing the channel in the Team. More importantly, if you create your own folder structure within a document library **it does not propagate** to Teams as a channel; for now, it only flows from Teams into SharePoint.</span></span>




> [!NOTE]
> <span data-ttu-id="00747-p103">Office 365 グループを削除すると、永続的な Outlook/OWA の会話や Teams 会議への招待状のメールボックス エイリアスが削除され、SharePoint サイトに削除のマークが付けられます。チームを削除した時点からそれが Outlook に反映されるまでに約 20 分かかります。Teams クライアントからチームを削除すると、そのチームのすべてのメンバーの表示からそのチームが即座に削除されます。Teams の機能を有効にしている Office 365 グループからメンバーを削除すると、削除したメンバーの Teams クライアントの表示からそのチームが削除されるまでに約 1 時間の遅延が発生します。</span><span class="sxs-lookup"><span data-stu-id="00747-p103">Deleting an Office 365 Group will remove the mailbox alias for persistent Outlook/OWA conversations and Teams meeting invites, and mark the SharePoint site for deletion. It takes approximately 20 minutes between the removal of a Team and its effect on Outlook. Deleting a Team from the Teams client will remove it immediately from view to all who are members of the team. If you remove a member of an Office 365 Group which has had Teams functionality enabled on it, there could be a delay of approximately one hour before the Team is removed from view in the Teams client for the effected people who were removed.</span></span>

<a name="group-membership"></a><span data-ttu-id="00747-118">グループ メンバーシップ</span><span class="sxs-lookup"><span data-stu-id="00747-118">Group membership</span></span>
----------------

<span data-ttu-id="00747-119">グループの機能と、ユーザーのための機能は、グループのメンバーシップからのドライブの場所によって異なります。</span><span class="sxs-lookup"><span data-stu-id="00747-119">Group features and capabilities for your users depends on where you drive group membership from.</span></span> <span data-ttu-id="00747-120">たとえば、チームのメンバーを削除する場合は同様に、Office 365 グループから削除されます。</span><span class="sxs-lookup"><span data-stu-id="00747-120">For example, if you remove a member of a team, they are removed from the Office 365 Group as well.</span></span> <span data-ttu-id="00747-121">グループからの削除は、すぐにチームを削除し、チームのクライアントからのチャネルします。</span><span class="sxs-lookup"><span data-stu-id="00747-121">Removal from the Group immediately removes the Team and channels from the Teams client.</span></span> <span data-ttu-id="00747-122">Office 365 管理ポータルを使用してグループからユーザーを削除する場合は、他の共同作業の側面へのアクセス、Yammer グループ、または共有の OneNote の SharePoint Online のドキュメント ライブラリなど。</span><span class="sxs-lookup"><span data-stu-id="00747-122">If you remove a person from a Group using the Office 365 Admin portal, they will no longer have access to the other collaborative aspects such as SharePoint Online document library, Yammer Group, or shared OneNote.</span></span> <span data-ttu-id="00747-123">ただし、それらがまだチームのチャット機能へのアクセスを約 1 時間です。</span><span class="sxs-lookup"><span data-stu-id="00747-123">However, they will still have access to the Team’s chat functionality for approximately one hour.</span></span>

<span data-ttu-id="00747-124">チーム メンバーを管理するためのベストプラクティス: を追加し、他の依存するクラウド アプリケーションを正しいカスケード アクセス制御が適用されることを確認するのにはチームのクライアントからメンバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="00747-124">Best practice for managing Teams members: Add and remove members from the Teams client to ensure the correct cascading access control to other dependent cloud applications is applied.</span></span> <span data-ttu-id="00747-125">さらに、切り離された経験したままの人まで次の同期サイクルは、追加、またはサービスの特定のコンポーネントへのアクセス権を取り消します) するために使用するリソースへのアクセスがまだあるという印象を回避します。</span><span class="sxs-lookup"><span data-stu-id="00747-125">Additionally, you will avoid a disjointed experience leaving people with the impression they still have access to the resources they used to (until the next sync cycle either adds or revokes access to a particular component of the service).</span></span> <span data-ttu-id="00747-126">かどうかを追加または削除を行うチームのクライアント以外のチーム メンバー (Office 365 の管理者センター、Azure AD を使用して、または Exchange のオンライン PowerShell)、チームに反映させるには、最大で 1 時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="00747-126">If you DO add or remove team members outside of the Teams client (by using Office 365 Admin Center, Azure AD, or Exchange Online PowerShell), it sometimes takes up to one hour for changes to be reflected in Teams.</span></span>
