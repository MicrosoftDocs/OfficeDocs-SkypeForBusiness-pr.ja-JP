---
title: Microsoft Teams の保持ポリシー
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: prvijay
description: アイテム保持ポリシーを管理する方法と、それらをチームで管理する方法について説明します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f2f3cc0c74b85d0b243dd8fefcd6bce1f2451fae
ms.sourcegitcommit: 6b73b89f29a0eabbd9cdedf995d5325291594bac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2019
ms.locfileid: "37018814"
---
# <a name="retention-policies-in-microsoft-teams"></a><span data-ttu-id="bfe27-103">Microsoft Teams の保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="bfe27-103">Retention policies in Microsoft Teams</span></span>

<span data-ttu-id="bfe27-104">チームの会話は永続的であり、既定では無期限に保持されます。</span><span class="sxs-lookup"><span data-stu-id="bfe27-104">Teams conversations are persistent and retained forever by default.</span></span> <span data-ttu-id="bfe27-105">アイテム保持ポリシーを導入すると、管理者は、チームチャットとチャネルメッセージのセキュリティ & コンプライアンスセンターで保持ポリシー (保持と削除の両方) を構成できます。</span><span class="sxs-lookup"><span data-stu-id="bfe27-105">With the introduction of retention policies, admins can configure retention policies (both preservation and deletion) in the Security & Compliance Center for Teams chat and channel messages.</span></span> <span data-ttu-id="bfe27-106">これにより、組織は、特定の期間のコンプライアンス (つまり、保持ポリシー) のデータを保持するか、または特定の期間後に法的義務と見なされる場合は、データ (つまり、削除ポリシー) を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="bfe27-106">This helps organizations either retain data for compliance (namely, preservation policy) for a specific period or get rid of data (namely, deletion policy) if it is considered a liability after a specific period.</span></span> <span data-ttu-id="bfe27-107">チームアイテム保持ポリシーを使用すると、データを削除したときに、Teams サービス上のすべての永続的データストレージの場所から削除されます。</span><span class="sxs-lookup"><span data-stu-id="bfe27-107">Teams retention policies ensure that when you delete data, it is removed from all permanent data storage locations on the Teams service.</span></span> 

<span data-ttu-id="bfe27-108">Teams のアイテム保持ポリシーを管理するには、[**データガバナンス** > の**保持**] の下にある Office 365 セキュリティ & コンプライアンスセンターの設定とコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="bfe27-108">To manage Teams retention policies, use the settings and cmdlets in the Office 365 Security & Compliance Center under **Data Governance** > **Retention**.</span></span>

<span data-ttu-id="bfe27-109">Teams のアイテム保持ポリシーは、次の機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="bfe27-109">Teams retention policies do support:</span></span> 
    
- <span data-ttu-id="bfe27-110">保持: チームのデータを指定した期間だけ保持し、何もしないようにします。</span><span class="sxs-lookup"><span data-stu-id="bfe27-110">Preservation: Keep Teams data for a specified duration and then do nothing</span></span>
- <span data-ttu-id="bfe27-111">保存して削除する: 指定した期間だけチームのデータを保持してから削除します。</span><span class="sxs-lookup"><span data-stu-id="bfe27-111">Preservation and then delete: Keep Teams data for a specified duration and then delete</span></span>
- <span data-ttu-id="bfe27-112">削除: 指定した期間後に Teams のデータを削除する</span><span class="sxs-lookup"><span data-stu-id="bfe27-112">Deletion: Delete Teams data after a specified duration</span></span>

<span data-ttu-id="bfe27-113">Teams アイテム保持ポリシーはまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bfe27-113">Teams retention policies do not yet support:</span></span>

- <span data-ttu-id="bfe27-114">高度なアイテム保持ポリシーが Teams のチャットおよび Teams チャネルのメッセージの場所に適用されない</span><span class="sxs-lookup"><span data-stu-id="bfe27-114">Advanced retention policies don't apply to Teams chat and Teams channel message locations</span></span>
- <span data-ttu-id="bfe27-115">30日未満の期間</span><span class="sxs-lookup"><span data-stu-id="bfe27-115">Duration of fewer than 30 days</span></span>

<span data-ttu-id="bfe27-116">管理者は、Teams のプライベートチャット (1:1 または 1: 多くのチャット) と Teams チャネルメッセージに個別のアイテム保持ポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="bfe27-116">Admins can set up separate retention policies for Teams private chats (1:1 or 1:Many chats) and Teams channel messages.</span></span> <span data-ttu-id="bfe27-117">多くの場合、組織はチャネルメッセージよりも負債の多い方法としてプライベートチャットデータを検討していますが、通常はプロジェクト関連の会話がより多くなります。</span><span class="sxs-lookup"><span data-stu-id="bfe27-117">In many cases, organizations consider private chat data as more of a liability than channel messages, which are usually more project-related conversations.</span></span> <span data-ttu-id="bfe27-118">セキュリティ & コンプライアンスセンター、**データガバナンス** > の**保持**で、これらのポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="bfe27-118">Set up these policies in the Security & Compliance Center, **Data governance** > **Retention**.</span></span> <span data-ttu-id="bfe27-119">**チームチャネルメッセージ**と**チームチャット**をオンにしてから、これらの場所のアイテム保持ポリシーを定義します (以下の図を参照)。</span><span class="sxs-lookup"><span data-stu-id="bfe27-119">Turn on **Teams channel messages** and **Teams chats** and then define retention policies for these locations (also shown in the diagram below).</span></span> 

<span data-ttu-id="bfe27-120">**Teams チャネルのメッセージ**を有効にすると、このポリシーを適用するチームを指定できます。</span><span class="sxs-lookup"><span data-stu-id="bfe27-120">When you turn on **Teams channel messages**, you can specify Teams to which this policy will apply.</span></span> <span data-ttu-id="bfe27-121">たとえば、teams X、Y、Z の場合、管理者は1年間の削除ポリシーを設定でき (それらのチームを個別に選択)、残りのチームに3年の削除ポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="bfe27-121">For example, for teams X, Y, and Z, the admin can set the deletion policies for 1 year (by selecting those teams individually), and apply a 3-year deletion policy to the rest of the teams.</span></span> 

<span data-ttu-id="bfe27-122">**チームチャット**では、特定のユーザーを選択して固有のアイテム保持ポリシーを適用することで、同じことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bfe27-122">You can do the same thing for **Teams chats** by selecting specific users and applying unique retention policies.</span></span> 

![Exchange と SharePoint への Teams データのワークフローの図。](media/Retention-Policies.png)


> [!IMPORTANT]
> <span data-ttu-id="bfe27-124">チームチャネルのメッセージの場所とチームのチャットの場所は、Exchange Online メールボックス (ユーザーとグループのメールボックス) に保存されているチームの会話にのみ対応しています。</span><span class="sxs-lookup"><span data-stu-id="bfe27-124">The Teams channel message locations and Teams chats locations only address the Teams conversations stored in Exchange Online mailboxes (user and group mailboxes).</span></span> <span data-ttu-id="bfe27-125">メッセージは、関連するすべての保存場所 (メールボックス、サブサイト、チャットサービスなど) から削除されます。</span><span class="sxs-lookup"><span data-stu-id="bfe27-125">The messages are deleted from all relevant storage locations, namely the mailboxes, substrate, and chat service.</span></span> 
> 
> <span data-ttu-id="bfe27-126">OneDrive for Business と SharePoint に保存されている Teams ファイルのアイテム保持ポリシーを管理するには、アイテム保持ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="bfe27-126">To manage retention policies for Teams files, which are stored in OneDrive for Business and SharePoint, use their retention policies.</span></span>

<span data-ttu-id="bfe27-127">デザインにより、Teams ファイルの削除ポリシーは、SharePoint Online と OneDrive for business の場所を通じて構成されます。</span><span class="sxs-lookup"><span data-stu-id="bfe27-127">By design, deletion policies for Teams files are configured through SharePoint Online and OneDrive for Business locations.</span></span> <span data-ttu-id="bfe27-128">そのため、ポリシーでは、チームチャットまたはチャネルメッセージで参照されているファイルを削除してから、それらのメッセージを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="bfe27-128">As a result, it's possible that a policy could delete a file referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="bfe27-129">この場合、ファイルは Teams メッセージに表示されますが、ファイルをクリックすると、"ファイルが見つかりませんでした" というエラーが表示されます (これは、他のユーザーが SharePoint Online または OneDrive for business からファイルを手動で削除した場合にも、ポリシーがない場合に発生する可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="bfe27-129">In this case, the file will still show up in the Teams message, but if you click the file, you'll get a "File not found" error (this could also happen in the absence of a policy, if someone manually deletes a file from SharePoint Online or OneDrive for Business).</span></span>

<span data-ttu-id="bfe27-130">Office 365 のアイテム保持ポリシーの構成の詳細については、「[アイテム保持ポリシーの概要」](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfe27-130">For detailed information about configuring retention policies for Office 365, read [Overview of retention policies](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
 
