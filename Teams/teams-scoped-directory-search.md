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
description: スコープを指定したディレクトリMicrosoft Teamsを使用して、ディレクトリのカスタマイズされたビューを提供する方法について学習します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1048b6451163cd7b0cdbcd3f52e48c6b0f4811d1
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717798"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="dd64a-103">Microsoft Teams の範囲指定ディレクトリ検索を使用する</span><span class="sxs-lookup"><span data-stu-id="dd64a-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="dd64a-104">Microsoft Teamsを使用すると、組織は仮想境界を作成して、ユーザーが組織内の他のユーザーを見つけて通信する方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="dd64a-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="dd64a-105">Microsoft Teams、組織はディレクトリのカスタム ビューをユーザーに提供できます。</span><span class="sxs-lookup"><span data-stu-id="dd64a-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="dd64a-106">Microsoft Teamsポリシー[を使用して、これらの](/microsoft-365/compliance/information-barriers)カスタム ビューをサポートします。</span><span class="sxs-lookup"><span data-stu-id="dd64a-106">Microsoft Teams uses [Information Barrier policies](/microsoft-365/compliance/information-barriers) to support these custom views.</span></span> <span data-ttu-id="dd64a-107">ポリシーが有効になると、他のユーザーの検索によって返される結果 (チャットの開始やチームへのメンバーの追加など) は、構成されたポリシーに従って範囲指定されます。</span><span class="sxs-lookup"><span data-stu-id="dd64a-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="dd64a-108">スコープ検索が有効な場合、ユーザーはチームを検索または検出できますが、アクティブな Information Barrier ポリシーで許可されているユーザーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="dd64a-108">Users will not be able to search or discover any teams when scoped search is in effect, but existing members in those teams can add users, as allowed by active Information Barrier policies.</span></span>

> [!NOTE]
> <span data-ttu-id="dd64a-109">ハイブリッドExchange場合、この機能はオンプレミスのメールボックスではなく、Exchange Online メールボックスでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="dd64a-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

<span data-ttu-id="dd64a-110">「アドレス帳[ポリシー」も参照Exchange Online。](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)</span><span class="sxs-lookup"><span data-stu-id="dd64a-110">See also [Address book policies in Exchange Online](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="dd64a-111">スコープ指定されたディレクトリ検索を使用する必要が生じ</span><span class="sxs-lookup"><span data-stu-id="dd64a-111">When should you use scoped directory searches?</span></span>

<span data-ttu-id="dd64a-112">範囲指定されたディレクトリ検索のメリットを得るシナリオは、アドレス帳ポリシーのシナリオと似ています。</span><span class="sxs-lookup"><span data-stu-id="dd64a-112">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="dd64a-113">たとえば、次のような状況で、範囲指定されたディレクトリ検索を使用できます。</span><span class="sxs-lookup"><span data-stu-id="dd64a-113">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="dd64a-114">所属する組織において、テナント内に複数の会社があり、それらを切り離された状態で維持する場合。</span><span class="sxs-lookup"><span data-stu-id="dd64a-114">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="dd64a-115">所属する学校において、教職員と学生との間のチャットを制限する必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="dd64a-115">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="dd64a-116">アドレス帳ポリシーを使用する方法については、次の記事の「Information Barrier policies (情報バリア ポリシー [)」をExchange Online。](/microsoft-365/compliance/information-barriers)</span><span class="sxs-lookup"><span data-stu-id="dd64a-116">To learn how to use address book policies, read [Information Barrier policies in Exchange Online](/microsoft-365/compliance/information-barriers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd64a-117">アドレス帳ポリシーは、ディレクトリの観点からのユーザーの仮想的な分離のみを提供します。</span><span class="sxs-lookup"><span data-stu-id="dd64a-117">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="dd64a-118">また、新しいアドレス帳ポリシーまたは更新されたアドレス帳ポリシーを適用する前に、既にキャッシュされているユーザー データは、最大 30 日間ユーザーが使用できる状態が維持されます。</span><span class="sxs-lookup"><span data-stu-id="dd64a-118">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="dd64a-119">スコープを指定したディレクトリ検索を有効にする</span><span class="sxs-lookup"><span data-stu-id="dd64a-119">Turn on scoped directory search</span></span>

1. <span data-ttu-id="dd64a-120">Information Barrier ポリシーを使用して、組織を仮想サブグループに構成します。</span><span class="sxs-lookup"><span data-stu-id="dd64a-120">Use Information Barrier policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="dd64a-121">詳細については、「情報バリア ポリシー [の定義」を参照してください](/microsoft-365/compliance/information-barriers-policies)。</span><span class="sxs-lookup"><span data-stu-id="dd64a-121">For more information, see [Define Information Barrier policies](/microsoft-365/compliance/information-barriers-policies).</span></span>

2. <span data-ttu-id="dd64a-122">管理センター Microsoft Teams、[組織全体の設定] を選択し **、[** 設定  >  **] Teamsします**。</span><span class="sxs-lookup"><span data-stu-id="dd64a-122">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="dd64a-123">[**検索]** で、[アドレス帳ポリシー **(ABP)** Teamsを使用して Exchange ディレクトリ検索をスコープする] の横にある [オン] トグルを **オンにします**。</span><span class="sxs-lookup"><span data-stu-id="dd64a-123">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (ABP)**, turn the toggle **On**.</span></span>

    ![管理センターでのスコープMicrosoft Teams検索](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> <span data-ttu-id="dd64a-125">この変更は、レプリケートに数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dd64a-125">This change can take a few hours to replicate.</span></span>
