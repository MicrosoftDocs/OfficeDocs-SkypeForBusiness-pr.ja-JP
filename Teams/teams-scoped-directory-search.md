---
title: Microsoft Teams の範囲指定ディレクトリ検索を使用する
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Microsoft Teams の範囲指定ディレクトリ検索を使用して、ディレクトリのカスタマイズされたビューを提供する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1ede4b60878dbdd44edf369b0a3c1bb861ffe366
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094027"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="074fd-103">Microsoft Teams の範囲指定ディレクトリ検索を使用する</span><span class="sxs-lookup"><span data-stu-id="074fd-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="074fd-104">Microsoft Teams の範囲指定ディレクトリ検索を使用すると、組織は、ユーザーが組織内の他のユーザーを見つけて通信する方法を制御する仮想境界を作成できます。</span><span class="sxs-lookup"><span data-stu-id="074fd-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="074fd-105">Microsoft Teams を使用すると、組織はディレクトリのカスタム ビューをユーザーに提供できます。</span><span class="sxs-lookup"><span data-stu-id="074fd-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="074fd-106">Microsoft Teams では [、Information Barrier ポリシーを使用して](/microsoft-365/compliance/information-barriers) 、これらのカスタム ビューをサポートします。</span><span class="sxs-lookup"><span data-stu-id="074fd-106">Microsoft Teams uses [Information Barrier policies](/microsoft-365/compliance/information-barriers) to support these custom views.</span></span> <span data-ttu-id="074fd-107">ポリシーを有効にすると、他のユーザーの検索によって返される結果 (チャットの開始やチームへのメンバーの追加など) は、構成されたポリシーに従って範囲指定されます。</span><span class="sxs-lookup"><span data-stu-id="074fd-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="074fd-108">対象範囲検索が有効な場合、ユーザーはチームを検索または検出できますが、アクティブな Information Barrier ポリシーの許可に従って、これらのチームの既存のメンバーはユーザーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="074fd-108">Users will not be able to search or discover any teams when scoped search is in effect, but existing members in those teams can add users, as allowed by active Information Barrier policies.</span></span>

> [!NOTE]
> <span data-ttu-id="074fd-109">Exchange ハイブリッド環境では、この機能は Exchange Online メールボックスでのみ動作し、オンプレミスのメールボックスでは動作しません。</span><span class="sxs-lookup"><span data-stu-id="074fd-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="074fd-110">範囲指定されたディレクトリ検索を使用する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="074fd-110">When should you use scoped directory searches?</span></span>

<span data-ttu-id="074fd-111">範囲指定されたディレクトリ検索のメリットを受けるシナリオは、アドレス帳ポリシーのシナリオと似ています。</span><span class="sxs-lookup"><span data-stu-id="074fd-111">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="074fd-112">たとえば、次のような状況で、範囲指定されたディレクトリ検索を使用できます。</span><span class="sxs-lookup"><span data-stu-id="074fd-112">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="074fd-113">所属する組織において、テナント内に複数の会社があり、それらを切り離された状態で維持する場合。</span><span class="sxs-lookup"><span data-stu-id="074fd-113">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="074fd-114">所属する学校において、教職員と学生との間のチャットを制限する必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="074fd-114">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="074fd-115">アドレス帳ポリシーの使い方については、Exchange Online の [Information Barrier ポリシーを参照してください](/microsoft-365/compliance/information-barriers)。</span><span class="sxs-lookup"><span data-stu-id="074fd-115">To learn how to use address book policies, read [Information Barrier policies in Exchange Online](/microsoft-365/compliance/information-barriers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="074fd-116">アドレス帳ポリシーは、ディレクトリの観点からユーザーを仮想的に分離するだけのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="074fd-116">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="074fd-117">また、新しいアドレス帳ポリシーまたは更新されたアドレス帳ポリシーが適用される前に、既にキャッシュされているユーザー データは、最大 30 日間ユーザーが利用できます。</span><span class="sxs-lookup"><span data-stu-id="074fd-117">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="074fd-118">範囲指定されたディレクトリ検索を有効にする</span><span class="sxs-lookup"><span data-stu-id="074fd-118">Turn on scoped directory search</span></span>

1. <span data-ttu-id="074fd-119">Information Barrier ポリシーを使用して、組織を仮想サブグループに構成します。</span><span class="sxs-lookup"><span data-stu-id="074fd-119">Use Information Barrier policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="074fd-120">詳細については、「情報バリア [ポリシーの定義」を参照してください](/microsoft-365/compliance/information-barriers-policies)。</span><span class="sxs-lookup"><span data-stu-id="074fd-120">For more information, see [Define Information Barrier policies](/microsoft-365/compliance/information-barriers-policies).</span></span>

2. <span data-ttu-id="074fd-121">Microsoft Teams 管理センターで、組織全体の **設定 Teams の設定**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="074fd-121">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="074fd-122">[ **検索] の**[Exchange アドレス帳ポリシー **(ABP)** を使用する Teams のスコープ ディレクトリ検索] の横で、[オン] をオン **にします**。</span><span class="sxs-lookup"><span data-stu-id="074fd-122">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (ABP)**, turn the toggle **On**.</span></span>

    ![Microsoft Teams 管理センターでの範囲指定ディレクトリ検索](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> <span data-ttu-id="074fd-124">この変更は、複製に数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="074fd-124">This change can take a few hours to replicate.</span></span>