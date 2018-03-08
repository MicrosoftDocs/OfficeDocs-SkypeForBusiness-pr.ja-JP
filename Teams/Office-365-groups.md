---
title: "Office 365 のグループと Microsoft チーム"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Office 365 のグループとグループ メンバーシップが Microsoft チームでどのように使用する方法について説明します。"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 429a11625bc41abd5414491e7e8f8a53a55c31bc
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="office-365-groups-and-microsoft-teams"></a><span data-ttu-id="b3215-103">Office 365 のグループと Microsoft チーム</span><span class="sxs-lookup"><span data-stu-id="b3215-103">Office 365 groups and Microsoft Teams</span></span>
=====================================

<span data-ttu-id="b3215-p101">Office 365 のグループは、Office 365 でアプリケーション間のメンバーシップ サービスです。基本的なレベルでは、Office 365 グループは、メンバーは、SharePoint チーム サイト、Yammer のグループを含む関連のワークロードに柔軟な結合のリストを含む Azure Active Directory のオブジェクトは、Exchange メールボックスのリソースのプランナー、くださいおよび OneNote を共有します。追加したり、Active Directory の他のグループに基づくセキュリティ オブジェクトと同様に、グループに人を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="b3215-p101">Office 365 Groups is the cross-application membership service in Office 365. At the basic level, an Office 365 Group is an object in Azure Active Directory with a list of members and a loose coupling to related workloads including a SharePoint team site, Yammer Group, shared Exchange mailbox resources, Planner, PowerBI and OneNote. You can add or remove people to the Group just as you would any other group-based security object in Active Directory.</span></span>

<span data-ttu-id="b3215-107">Office 365 管理者は、Office 365 グループを定義、メンバーを追加、および Exchange メールボックス、SharePoint ドキュメント ライブラリでの共有などの機能を活用 Yammer のグループなどです。グループの詳細については、以下を参照してください。: [Office 365 のグループについて説明](https://support.office.com/en-us/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)します。</span><span class="sxs-lookup"><span data-stu-id="b3215-107">An Office 365 administrator can define an Office 365 Group, add members, and benefit from features such as an Exchange shared mailbox, SharePoint document library, Yammer Group, etc. For more information about Groups visit: [Learn about Office 365 Groups](https://support.office.com/en-us/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).</span></span>

<a name="how-office-365-groups-work"></a><span data-ttu-id="b3215-108">Office 365 グループを操作する方法</span><span class="sxs-lookup"><span data-stu-id="b3215-108">How Office 365 groups work</span></span>
--------------------------

<span data-ttu-id="b3215-p102">バックエンドで Microsoft チームを作成するときに関連付けられている SharePoint ドキュメント ライブラリ、他の Office 365 クラウド アプリケーションにつながりと共に、OneNote のノートブックと Office 365 のグループを作成します。チームを作成するユーザーが既存の Office 365 のパブリックまたはプライベート グループの所有者である場合は、チームの機能グループに追加できます。これは、チャットのメッセージ、ドキュメント、OneNote、およびその他のオブジェクトが存在する 1 つの既定値「標準」チャネルを作成します。チャンネルのドキュメント ライブラリを表示すると、チームでチャンネルを表す「標準」フォルダーが表示されます。さらに、フォルダー、ドキュメント ライブラリ**それは反映されません**チーム チャネル; として内での構造を作成する場合ここでは、そののみフロー チームから SharePoint にします。</span><span class="sxs-lookup"><span data-stu-id="b3215-p102">When you create a Microsoft Team, on the backend, you’re creating an Office 365 Group along with the associated SharePoint document library, OneNote notebook, along with ties into other Office 365 cloud applications. If the person creating the Team is an owner of an existing Office 365 Public or Private Group, they can add Teams functionality to the Group. This creates one default “General” channel in which chat messages, documents, OneNote, and other objects reside. Viewing the document library for the channel will reveal the “General” folder representing the channel in the Team. More importantly, if you create your own folder structure within a document library **it does not propagate** to Teams as a channel; for now, it only flows from Teams into SharePoint.</span></span>




> [!NOTE]
> <span data-ttu-id="b3215-p103">Office 365 グループを削除する、永続的な Outlook/OWA 会話やチーム会議エイリアスのメールボックスへの招待を削除して、SharePoint サイトを削除します。チームの削除と Outlook では、その効果の約 20 分がかかります。チーム チーム クライアントから削除されますすぐにビューからチームのメンバーである [すべてにします。チームの機能を有効にした、Office 365 グループのメンバーを削除する場合はチームが削除されたユーザーは影響を受けるチーム クライアントでのビューから削除する前に約 1 時間の遅延の可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b3215-p103">Deleting an Office 365 Group will remove the mailbox alias for persistent Outlook/OWA conversations and Teams meeting invites, and mark the SharePoint site for deletion. It takes approximately 20 minutes between the removal of a Team and its effect on Outlook. Deleting a Team from the Teams client will remove it immediately from view to all who are members of the team. If you remove a member of an Office 365 Group which has had Teams functionality enabled on it, there could be a delay of approximately one hour before the Team is removed from view in the Teams client for the effected people who were removed.</span></span>

<a name="group-membership"></a><span data-ttu-id="b3215-118">グループ メンバーシップ</span><span class="sxs-lookup"><span data-stu-id="b3215-118">Group membership</span></span>
----------------

<span data-ttu-id="b3215-p104">どこからグループ メンバーシップをドライブ、によって、ユーザーが発生するどのような特長と機能かによって決まります。たとえば、チームのメンバーを削除する場合も、Office 365 グループから削除されます。すぐに、グループから削除は、チームを削除し、チームのクライアントからチャンネルします。場合は、Office 365 管理ポータルを使用して、グループからユーザーを削除すると、Yammer グループ、または共有の OneNote を SharePoint Online ドキュメント ライブラリなど、その他の共同作業環境の側面にアクセスできなくいるされます。ただし、それらが残りますチームのチャット機能へのアクセス (約 1 時間) します。</span><span class="sxs-lookup"><span data-stu-id="b3215-p104">Depending on where you drive group membership from, depends on what features and capabilities your users will experience. For example, if you remove a member of a Team, they are removed from the Office 365 Group as well. Removal from the Group immediately removes the Team and channels from the Teams client. If you remove a person from a Group using the Office 365 Admin portal, they will no longer have access to the other collaborative aspects such as SharePoint Online document library, Yammer Group, or shared OneNote. However, they will still have access to the Team’s chat functionality for approximately one hour.</span></span>

<span data-ttu-id="b3215-p105">チームのメンバーの管理] に関連するガイダンス ドライブに依存するクラウドの他のアプリケーションへの適切なカスケード アクセス制御が適用されることを確認するチーム クライアントで追加/削除機能です。さらに、引き続き (次の同期サイクルでは、追加か、またはサービスの特定のコンポーネントへのアクセスを取り消します) までに使ったリソースへのアクセス権があるという印象を切り離されたエクスペリエンスから離れることユーザーを避けられます。</span><span class="sxs-lookup"><span data-stu-id="b3215-p105">Our guidance with respect to Teams ‘member management’ is to drive the add/remove functionality through the Teams client to ensure the correct cascading access control to other dependent cloud applications is applied. Additionally, you will avoid a disjointed experience leaving people with the impression they still have access to the resources they used to (until the next sync cycle either adds or revokes access to a particular component of the service).</span></span>
