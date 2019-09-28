---
title: Microsoft Teams の範囲指定ディレクトリ検索を使用する
author: LolaJacobsen
ms.author: lolaj
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
- Teams_ITAdmin_Help
description: Microsoft Teams のスコープ指定ディレクトリ検索を使用して、ディレクトリのカスタマイズされたビューを提供する方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e3b95e9d8de04abc6299a52a27cf07d95365a4f
ms.sourcegitcommit: 1721acdd507591d16a4e766b390b997979d985e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "37305801"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="0be78-103">Microsoft Teams の範囲指定ディレクトリ検索を使用する</span><span class="sxs-lookup"><span data-stu-id="0be78-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="0be78-104">Microsoft Teams 範囲指定ディレクトリ検索を使用すると、組織は、ユーザーが組織内の他のユーザーを検索して通信する方法を制御する仮想境界を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="0be78-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="0be78-105">Microsoft Teams を使用すると、組織はディレクトリのカスタムビューをユーザーに提供できます。</span><span class="sxs-lookup"><span data-stu-id="0be78-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="0be78-106">Microsoft Teams では、これらのカスタムビューをサポートするために[Exchange アドレス帳ポリシー](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)が使用されています。</span><span class="sxs-lookup"><span data-stu-id="0be78-106">Microsoft Teams uses [Exchange address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) to support these custom views.</span></span> <span data-ttu-id="0be78-107">ポリシーを有効にすると、他のユーザーの検索結果 (チャットの開始やチームへのメンバーの追加など) は、構成されたポリシーに従って範囲設定されます。</span><span class="sxs-lookup"><span data-stu-id="0be78-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="0be78-108">スコープ指定された検索が有効になっている場合、ユーザーはチームを検索または検出できません。</span><span class="sxs-lookup"><span data-stu-id="0be78-108">Users will not be able to search or discover teams when scoped search is in effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="0be78-109">Exchange ハイブリッド環境では、この機能は Exchange Online のメールボックスでのみ機能し、オンプレミスのメールボックスには使用できません。</span><span class="sxs-lookup"><span data-stu-id="0be78-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="0be78-110">スコープディレクトリ検索を使用する場合</span><span class="sxs-lookup"><span data-stu-id="0be78-110">When should you use scoped directory searches?</span></span>

<span data-ttu-id="0be78-111">スコープを指定したディレクトリ検索を利用するシナリオは、アドレス帳ポリシーのシナリオと似ています。</span><span class="sxs-lookup"><span data-stu-id="0be78-111">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="0be78-112">たとえば、次のような場合には、スコープ指定されたディレクトリ検索を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="0be78-112">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="0be78-113">所属する組織において、テナント内に複数の会社があり、それらを切り離された状態で維持する場合。</span><span class="sxs-lookup"><span data-stu-id="0be78-113">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="0be78-114">所属する学校において、教職員と学生との間のチャットを制限する必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="0be78-114">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="0be78-115">アドレス帳ポリシーの使用方法については、「 [Exchange Online のアドレス帳ポリシー](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0be78-115">To learn how to use address book policies, read [Address book policies in Exchange Online](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0be78-116">アドレス帳ポリシーは、ディレクトリの観点からのユーザーの仮想的な分離のみを提供します。</span><span class="sxs-lookup"><span data-stu-id="0be78-116">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="0be78-117">ユーザーは、完全なメールアドレスを提供して、他のユーザーとの通信を開始することができます。</span><span class="sxs-lookup"><span data-stu-id="0be78-117">Users can still initiate communications with others by providing complete email addresses.</span></span> <span data-ttu-id="0be78-118">また、新規または更新されたアドレス帳ポリシーを適用する前に、既にキャッシュされていたすべてのユーザーデータは、最大30日間はユーザーに対して利用可能になることに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0be78-118">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="0be78-119">スコープディレクトリ検索を有効にする</span><span class="sxs-lookup"><span data-stu-id="0be78-119">Turn on scoped directory search</span></span>

1. <span data-ttu-id="0be78-120">アドレス帳ポリシーを使用して、組織を仮想サブグループに構成します。</span><span class="sxs-lookup"><span data-stu-id="0be78-120">Use address book policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="0be78-121">詳細については、「[アドレス帳ポリシーの手順](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0be78-121">For more information, see [Procedures for address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span></span>

2. <span data-ttu-id="0be78-122">Microsoft Teams 管理センターで、[**組織全体の設定** > **チームの設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0be78-122">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="0be78-123">[**検索**] の [ **Exchange アドレス帳ポリシー (apb) を使用して Teams で検索**する] の横にある [オン **] に切り替えます。**</span><span class="sxs-lookup"><span data-stu-id="0be78-123">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (APB)**, turn the toggle **On**.</span></span>

    ![Microsoft Teams 管理センターでのスコープディレクトリ検索](media/teams-scoped-directory-search-image1.png)



