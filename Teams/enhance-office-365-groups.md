---
title: 既存の Office 365 グループを Microsoft Teams で強化する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: 配布リストをチームに取り込んだり、メール対応セキュリティ グループを追加したりなどの操作を行うことで、Microsoft Teams を介して Office 365 グループを強化する方法について説明します。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 95112a3a3e4aea4fee68507fea4c366dac1da2da
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2019
ms.locfileid: "30463525"
---
<a name="enhance-existing-office-365-groups-with-microsoft-teams"></a><span data-ttu-id="2c79e-103">既存の Office 365 グループを Microsoft Teams で強化する</span><span class="sxs-lookup"><span data-stu-id="2c79e-103">Enhance Existing Office 365 groups with Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="2c79e-p101">Microsoft Teams ユーザーは、Microsoft Teams の機能を使って既存の Office 365 グループを強化することができます。Office 365 のパブリック グループでは、そのメンバー数が 2500 人以下の場合にグループを強化できます。</span><span class="sxs-lookup"><span data-stu-id="2c79e-p101">Microsoft Teams users can enhance an existing Office 365 Group with Microsoft Teams functionality. When looking at enhancing a public Office 365 Group, users can do that if the number of members is equal to or less than 2500.</span></span>

<span data-ttu-id="2c79e-106">これを行うには、ユーザーはマイクロソフトのチームのクライアントからの新しいチームの作成の流れを通過する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c79e-106">To do this, users should go through the flow of creating a new team from the Microsoft Teams client.</span></span> <span data-ttu-id="2c79e-107">画面の下部にある**既存の Office 365 グループからチームを作成する**] を選択し、マイクロソフトのチームを強化するために使用する既存のグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="2c79e-107">Select **Create a team from an existing Office 365 group** at the bottom of the screen and then choose the existing group that you want to enhance with Microsoft Teams.</span></span> <span data-ttu-id="2c79e-108">既存のグループのメンバーがメンバーとして追加するチームに自動的にします。</span><span class="sxs-lookup"><span data-stu-id="2c79e-108">Existing group members will be added as members to the team automatically.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2c79e-109">マイクロソフト チームは、既存のグループを強化するために Office 365 のグループの所有者のみの権限し、そのグループには、2500 未満のユーザーが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c79e-109">Only Office 365 Group owners have permission to enhance an existing group  with Microsoft Teams, and that group must contain less than 2500 users.</span></span> <span data-ttu-id="2c79e-110">拡張されたチームも一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="2c79e-110">Teams that have already been enhanced will not show up in the list.</span></span>
>
><span data-ttu-id="2c79e-111">**既存の Office 365 グループからチームを作成する**] オプションは、これらの条件が満たされていない限り、使用できません。</span><span class="sxs-lookup"><span data-stu-id="2c79e-111">The **Create a team from an existing Office 365 group** option will not be available unless these conditions have been met.</span></span>


<span data-ttu-id="2c79e-p104">ユーザーは配布リストをチームに取り込むこともできます。それを行うと、配布リストのメンバーがチームに追加されます。この処理は一度のみ実行されるため、その後に配布リスト内のグループ メンバーの変更があった場合でもチームには反映されません。</span><span class="sxs-lookup"><span data-stu-id="2c79e-p104">Users can also invite a distribution list to a team, and the members of that distribution list will be added to the team. This is a one-time sync, and later changes in group membership in the distribution list will not be replicated to Teams.</span></span> 

![配布リストとそのメンバーのチームへの取り込みを示す一連のスクリーンショット。](media/Enhance_Existing_Office_365_groups_with_Microsoft_Teams_image2.png)

<span data-ttu-id="2c79e-p105">チームのメンバーとして、メール対応のセキュリティ グループを追加することもできます。ただし、後でセキュリティ グループにさらに多くのメンバーを追加しても、それらのメンバーはチームに自動追加されません。新しいメンバーをチームに個別に追加するか、セキュリティ グループをチームに再追加する必要があります。(セキュリティ グループを再追加する場合は、重複を削除してメンバーが一度だけ追加されるようにします。)</span><span class="sxs-lookup"><span data-stu-id="2c79e-p105">You can also add mail-enabled security groups as members of a team. But, if you later add more members to the security group, those members are not automatically added to the team. You must add the new members separately or re-add the security group to the team. (If you re-add the security group, deduplication makes sure members are added only once.)</span></span>

<span data-ttu-id="2c79e-p106">Office 365 グループでのプライバシー設定には、**パブリックとプライベート**の 2 種類があります。これらのグループの種類は両方とも、Microsoft Teams で有効にすることができますが、セルフ サービスの場合ではこれらの種類の間に多少の違いがあります。</span><span class="sxs-lookup"><span data-stu-id="2c79e-p106">There are two types of privacy settings with Office 365 groups, **public and private**. Whereas both group types can be enabled for Microsoft Teams, there is a slight difference when it comes to self-service.</span></span>

-   <span data-ttu-id="2c79e-121">ユーザーはパブリック グループを検索して、チーム所有者の承認なしで自由に参加できます。</span><span class="sxs-lookup"><span data-stu-id="2c79e-121">Users can search for public groups and can join by themselves without a need for team owner’s approval.</span></span>

-   <span data-ttu-id="2c79e-122">プライベート グループは検索できません。ユーザーはチーム所有者からメンバーとして追加されない限り参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="2c79e-122">Private groups are not searchable, and users cannot join unless a team owner add them as a member.</span></span>

<span data-ttu-id="2c79e-p107">Microsoft Teams で新しいチームを作成すると、既存のプライベート  グループの所有者は、グループのメンバーシップを使って新しいチームを作成することができます。ユーザーは、既存の SharePoint ファイル (タブの追加) や OneNote ファイル (ファイルの結合) を追加できます。</span><span class="sxs-lookup"><span data-stu-id="2c79e-p107">When creating a new team in Microsoft Teams, an owner of an existing private Office 365 group has an option to use the membership in the Office 365 group to create the team. Users can add their existing SharePoint and OneNote files by adding a tab for SharePoint and merging OneNote files.</span></span>
