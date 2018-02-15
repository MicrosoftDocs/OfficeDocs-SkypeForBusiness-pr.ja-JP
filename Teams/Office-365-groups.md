---
title: "Office 365 グループと Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Office 365 グループとグループ メンバーシップがどのように Microsoft Teams と連携しているかについて説明します。"
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0e21a776e9cb259b9a4e73a1bfc7df3e0b408a50
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2018
---
<a name="office-365-groups-and-microsoft-teams"></a><span data-ttu-id="5d7d7-103">Office 365 グループと Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5d7d7-103">Office 365 groups and Microsoft Teams</span></span>
=====================================

<span data-ttu-id="5d7d7-p101">Office 365 グループは Office 365 のクロスアプリケーションのメンバーシップ サービスです。基本的なレベルでは、Office 365 グループはメンバーのリストを含む Azure Active Directory のオブジェクトです。さらに、このオブジェクトには SharePoint チーム サイト、Yammer グループ、Exchange メールボックスのリソース、Planner、PowerBI、OneNote などの関連ワークロードとの疎結合も含まれています。Active Directory のその他のグループベースのセキュリティ オブジェクトと同様にグループにユーザーを追加したり、グループからユーザーを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="5d7d7-p101">Office 365 Groups is the cross-application membership service in Office 365. At the basic level, an Office 365 Group is an object in Azure Active Directory with a list of members and a loose coupling to related workloads including a SharePoint team site, Yammer Group, shared Exchange mailbox resources, Planner, PowerBI and OneNote. You can add or remove people to the Group just as you would any other group-based security object in Active Directory.</span></span>

<span data-ttu-id="5d7d7-107">Office 365 の管理者は Office 365 グループの定義やメンバーの追加を行うことができ、Exchange 共有メールボックス、SharePoint ドキュメント ライブラリなどの機能も利用することができます。グループについて詳しくは、「[Office 365 グループの概要](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5d7d7-107">An Office 365 administrator can define an Office 365 Group, add members, and benefit from features such as an Exchange shared mailbox, SharePoint document library, Yammer Group, etc. For more information about Groups visit: [Learn about Office 365 Groups](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).</span></span>

<a name="how-office-365-groups-work"></a><span data-ttu-id="5d7d7-108">Office 365 グループについて</span><span class="sxs-lookup"><span data-stu-id="5d7d7-108">How Office 365 groups work</span></span>
--------------------------

<span data-ttu-id="5d7d7-p102">Microsoft Teams のチームを作成することは、最終的には SharePoint ドキュメント ライブラリ、OneNote ノートブック、その他の Office 365 クラウド アプリケーションと関連付けられた Office 365 グループを作成することを意味します。チームを作成しているユーザーが既存の Office 365 パブリックまたはプライベート グループの所有者である場合は、Teams の機能をグループに追加できます。追加を行うと、チャット メッセージ、ドキュメント、OneNote、その他のオブジェクトが配置される既定の「全般」チャネルが作成されます。そのチャネルのドキュメント ライブラリを表示すると、チームのチャネルを表す「全般」フォルダーが表示されます。さらに重要な点は、ドキュメント ライブラリ内で独自のフォルダー構造を作成しても、それはチャネルとして Teams に**伝播されません**。現時点では、Teams から SharePoint にのみ伝播されます。</span><span class="sxs-lookup"><span data-stu-id="5d7d7-p102">When you create a Microsoft Team, on the backend, you’re creating an Office 365 Group along with the associated SharePoint document library, OneNote notebook, along with ties into other Office 365 cloud applications. If the person creating the Team is an owner of an existing Office 365 Public or Private Group, they can add Teams functionality to the Group. This creates one default “General” channel in which chat messages, documents, OneNote, and other objects reside. Viewing the document library for the channel will reveal the “General” folder representing the channel in the Team. More importantly, if you create your own folder structure within a document library **it does not propagate** to Teams as a channel; for now, it only flows from Teams into SharePoint.</span></span>




> [!NOTE]
> <span data-ttu-id="5d7d7-p103">Office 365 グループを削除すると、永続的な Outlook/OWA の会話や Teams 会議への招待状のメールボックス エイリアスが削除され、SharePoint サイトに削除のマークが付けられます。チームを削除した時点からそれが Outlook に反映されるまでに約 20 分かかります。Teams クライアントからチームを削除すると、そのチームのすべてのメンバーの表示からそのチームが即座に削除されます。Teams の機能を有効にしている Office 365 グループからメンバーを削除すると、削除したメンバーの Teams クライアントの表示からそのチームが削除されるまでに約 1 時間の遅延が発生します。</span><span class="sxs-lookup"><span data-stu-id="5d7d7-p103">Deleting an Office 365 Group will remove the mailbox alias for persistent Outlook/OWA conversations and Teams meeting invites, and mark the SharePoint site for deletion. It takes approximately 20 minutes between the removal of a Team and its effect on Outlook. Deleting a Team from the Teams client will remove it immediately from view to all who are members of the team. If you remove a member of an Office 365 Group which has had Teams functionality enabled on it, there could be a delay of approximately one hour before the Team is removed from view in the Teams client for the effected people who were removed.</span></span>

<a name="group-membership"></a><span data-ttu-id="5d7d7-118">グループ メンバーシップ</span><span class="sxs-lookup"><span data-stu-id="5d7d7-118">Group membership</span></span>
----------------

<span data-ttu-id="5d7d7-p104">ユーザーが利用できる機能は、グループ メンバーシップを入手した場所によって異なります。たとえば、チームのメンバーを削除すると、そのメンバーは Office 365 グループからも削除されます。グループから削除すると、即座にチームが削除され、Teams クライアントからチャネルが削除されます。Office 365 管理ポータルを使用してグループからメンバーを削除すると、そのメンバーは SharePoint Online ドキュメント ライブラリ、Yammer グループ、共有 OneNote といったその他のコラボレーション機能へのアクセスを失います。ただし、削除後もチームのチャット機能には約 1 時間アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5d7d7-p104">Depending on where you drive group membership from, depends on what features and capabilities your users will experience. For example, if you remove a member of a Team, they are removed from the Office 365 Group as well. Removal from the Group immediately removes the Team and channels from the Teams client. If you remove a person from a Group using the Office 365 Admin portal, they will no longer have access to the other collaborative aspects such as SharePoint Online document library, Yammer Group, or shared OneNote. However, they will still have access to the Team’s chat functionality for approximately one hour.</span></span>

<span data-ttu-id="5d7d7-p105">Teams の「メンバー管理」を行う場合、Teams クライアントを介して追加/削除機能を使用することで、適切なカスケード アクセス コントロールをその他の依存するクラウド アプリケーションに適用できます。さらに、ユーザーに整然としていない使用感が生じて、以前アクセスできていたリソースに、(特定のサービス コンポーネントへのアクセスが追加または取り消される次回の同期サイクルまで) 引き続きアクセスできるという印象を残さないようにします。</span><span class="sxs-lookup"><span data-stu-id="5d7d7-p105">Our guidance with respect to Teams ‘member management’ is to drive the add/remove functionality through the Teams client to ensure the correct cascading access control to other dependent cloud applications is applied. Additionally, you will avoid a disjointed experience leaving people with the impression they still have access to the resources they used to (until the next sync cycle either adds or revokes access to a particular component of the service).</span></span>
