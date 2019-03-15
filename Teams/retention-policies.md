---
title: Microsoft Teams の保持ポリシー
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anach
description: リテンション ・ ポリシーをチームで管理する方法について説明します。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3c253569f642a8833d9bfad6677fe1a17624447
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2019
ms.locfileid: "30640979"
---
# <a name="retention-policies-in-microsoft-teams"></a><span data-ttu-id="c2815-103">Microsoft Teams の保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="c2815-103">Retention policies in Microsoft Teams</span></span>

<span data-ttu-id="c2815-104">チームの会話は、永続的な既定値が永久に保持されています。</span><span class="sxs-lookup"><span data-stu-id="c2815-104">Teams conversations are persistent and retained forever by default.</span></span> <span data-ttu-id="c2815-105">リテンション ・ ポリシーの導入により、管理者は、チームのチャットおよびチャネルのメッセージのセキュリティ & コンプライアンス センターで (保存と削除の両方) の保持ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="c2815-105">With the introduction of retention policies, admins can configure retention policies (both preservation and deletion) in the Security & Compliance Center for Teams chat and channel messages.</span></span> <span data-ttu-id="c2815-106">これにより、組織のコンプライアンス (つまり、保持ポリシーを特定の期間のデータを保持] または [特定の期間の後、責任と見なされる場合データ (つまり、削除ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="c2815-106">This helps organizations either retain data for compliance (namely, preservation policy) for a specific period or get rid of data (namely, deletion policy) if it is considered a liability after a specific period.</span></span> <span data-ttu-id="c2815-107">チーム ・ リテンション ・ ポリシーは、データを削除するときはチーム サービスすべて永続的なデータ ストレージの場所から削除されますを確認します。</span><span class="sxs-lookup"><span data-stu-id="c2815-107">Teams retention policies ensure that when you delete data, it is removed from all permanent data storage locations on the Teams service.</span></span> 

<span data-ttu-id="c2815-108">チーム ・ リテンション ・ ポリシーを管理するには、Office 365 のセキュリティ &**データの管理**下にあるコンプライアンス センターで設定およびコマンドレットを使用 > **保存**します。</span><span class="sxs-lookup"><span data-stu-id="c2815-108">To manage Teams retention policies, use the settings and cmdlets in the Office 365 Security & Compliance Center under **Data Governance** > **Retention**.</span></span>

<span data-ttu-id="c2815-109">チーム ・ リテンション ・ ポリシーはサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c2815-109">Teams retention policies do support:</span></span> 
    
- <span data-ttu-id="c2815-110">保存: 指定された期間のチームのデータを保持して、何もしません。</span><span class="sxs-lookup"><span data-stu-id="c2815-110">Preservation: Keep Teams data for a specified duration and then do nothing</span></span>
- <span data-ttu-id="c2815-111">保存とし、[削除: 指定した期間のチームのデータを保持し、削除</span><span class="sxs-lookup"><span data-stu-id="c2815-111">Preservation and then delete: Keep Teams data for a specified duration and then delete</span></span>
- <span data-ttu-id="c2815-112">削除: 指定した期間の後のチームのデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="c2815-112">Deletion: Delete Teams data after a specified duration</span></span>

<span data-ttu-id="c2815-113">チーム ・ リテンション ・ ポリシーをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c2815-113">Teams retention policies do not yet support:</span></span>

- <span data-ttu-id="c2815-114">チャットのチームとチームのチャネル メッセージの場所に高度な保存ポリシーが適用されません。</span><span class="sxs-lookup"><span data-stu-id="c2815-114">Advanced retention policies don't apply to Teams chat and Teams channel message locations</span></span>
- <span data-ttu-id="c2815-115">30 日以内の期間</span><span class="sxs-lookup"><span data-stu-id="c2815-115">Duration of fewer than 30 days</span></span>

<span data-ttu-id="c2815-116">管理者は、チームのプライベート チャット (チャットが 1:1 または 1 対多) とチャネルのメッセージをチームの別の保存ポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="c2815-116">Admins can set up separate retention policies for Teams private chats (1:1 or 1:Many chats) and Teams channel messages.</span></span> <span data-ttu-id="c2815-117">多くの場合、組織は複数のチャネル メッセージは、複数のプロジェクトに関連する会話は、通常よりも負債としてプライベート チャット データを検討してください。</span><span class="sxs-lookup"><span data-stu-id="c2815-117">In many cases, organizations consider private chat data as more of a liability than channel messages, which are usually more project-related conversations.</span></span> <span data-ttu-id="c2815-118">セキュリティ & コンプライアンス センターでは、**データ ・ ガバナンス**のポリシーを設定します > **保存**します。</span><span class="sxs-lookup"><span data-stu-id="c2815-118">Set up these policies in the Security & Compliance Center, **Data governance** > **Retention**.</span></span> <span data-ttu-id="c2815-119">**チャネルのメッセージをチーム**と**チームのチャット**をオンにし、(もは次の図に示すように) これらの場所の保存ポリシーを定義し、します。</span><span class="sxs-lookup"><span data-stu-id="c2815-119">Turn on **Teams channel messages** and **Teams chats** and then define retention policies for these locations (also shown in the diagram below).</span></span> 

<span data-ttu-id="c2815-120">**チームのメッセージのチャネル**を有効にするとき、チームはこのポリシーを適用するを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c2815-120">When you turn on **Teams channel messages**, you can specify Teams to which this policy will apply.</span></span> <span data-ttu-id="c2815-121">たとえば、X、Y、および Z は、チームの管理者ことができます 1 年間でこれらのチームを個別に選択)、削除ポリシーを設定、チームの残りの部分に 3 年間の削除ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="c2815-121">For example, for teams X, Y, and Z, the admin can set the deletion policies for 1 year (by selecting those teams individually), and apply a 3-year deletion policy to the rest of the teams.</span></span> 

<span data-ttu-id="c2815-122">特定のユーザーを選択し、一意の保持ポリシーを適用することによって**チームのチャット**の同じことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c2815-122">You can do the same thing for **Teams chats** by selecting specific users and applying unique retention policies.</span></span> 

![Exchange と SharePoint への Teams データのワークフローの図。](media/Retention-Policies.png)


> [!IMPORTANT]
> <span data-ttu-id="c2815-124">チャネル メッセージの場所のチームとチーム チャットの場所は、Exchange Online のメールボックス (メールボックスをユーザーとグループ) に格納されているチームの会話にしか対応します。</span><span class="sxs-lookup"><span data-stu-id="c2815-124">The Teams channel message locations and Teams chats locations only address the Teams conversations stored in Exchange Online mailboxes (user and group mailboxes).</span></span> <span data-ttu-id="c2815-125">メッセージは、すべての関連する記憶域、つまりメールボックス、基板、およびチャット サービスから削除されます。</span><span class="sxs-lookup"><span data-stu-id="c2815-125">The messages are deleted from all relevant storage locations, namely the mailboxes, substrate, and chat service.</span></span> 
> 
> <span data-ttu-id="c2815-126">ビジネスおよび SharePoint の OneDrive に保存されている、チームのファイルの保存ポリシーを管理するために、リテンション ・ ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="c2815-126">To manage retention policies for Teams files, which are stored in OneDrive for Business and SharePoint, use their retention policies.</span></span>

<span data-ttu-id="c2815-127">仕様では、削除チーム ファイルのポリシーを構成して SharePoint Online OneDrive の事業所です。</span><span class="sxs-lookup"><span data-stu-id="c2815-127">By design, deletion policies for Teams files are configured through SharePoint Online and OneDrive for Business locations.</span></span> <span data-ttu-id="c2815-128">その結果、ポリシーがそれらのメッセージは削除する前に、チーム チャットやチャネルのメッセージで参照されているファイルを削除できなかったことができます。</span><span class="sxs-lookup"><span data-stu-id="c2815-128">As a result, it's possible that a policy could delete a file referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="c2815-129">この例では、ファイルは表示されますチームのメッセージが、ファイルをクリックすると、(に起こる場合も、ポリシーがない場合はファイルが SharePoint Online またはビジネスのための OneDrive から手動で削除する場合)、"ファイルが見つかりません"というエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2815-129">In this case, the file will still show up in the Teams message, but if you click the file, you'll get a "File not found" error (this could also happen in the absence of a policy, if someone manually deletes a file from SharePoint Online or OneDrive for Business).</span></span>

<span data-ttu-id="c2815-130">Office 365 用のリテンション ・ ポリシーの構成の詳細については、[保存ポリシーの概要](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2815-130">For detailed information about configuring retention policies for Office 365, read [Overview of retention policies](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
 
