---
title: Skype for Business Server で E9-1-1 のユーザーを有効にする
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Skype for Business Server エンタープライズ VoIP での E9-1-1 展開の場所ポリシーに必要な決定(有効にするユーザー、移動ユーザーをサポートする方法など)。
ms.openlocfilehash: 9a2ced694357b9225555a05c10e93a1006a771b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825747"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="4c9a8-103">Skype for Business Server で E9-1-1 のユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="4c9a8-103">Enable users for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="4c9a8-104">Skype for Business Server エンタープライズ VoIP での E9-1-1 展開の場所ポリシーに必要な決定(有効にするユーザー、移動ユーザーをサポートする方法など)。</span><span class="sxs-lookup"><span data-stu-id="4c9a8-104">Decisions necessary for the location policy for an E9-1-1 deployment in Skype for Business Server Enterprise Voice, including which users to enable and how to support roaming users.</span></span>
  
<span data-ttu-id="4c9a8-105">クライアントの登録時に、Skype for Business Server は場所ポリシーを使用して、ユーザーが有効なユーザーの E9-1-1 エンタープライズ VoIPを構成します。</span><span class="sxs-lookup"><span data-stu-id="4c9a8-105">During client registration, Skype for Business Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="4c9a8-106">このポリシーには、E9-1-1 の実装方法を定義する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4c9a8-106">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="4c9a8-107">たとえば、場所のポリシーには、緊急ダイヤル文字列などの情報や、場所情報サービスが自動的に提供しない場合に、ユーザーが場所を手動で入力する必要があるかどうかなどの情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4c9a8-107">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="4c9a8-108">場所ポリシーの完全な定義については、「Skype for Business Server の場所 [ポリシーを計画する」を参照してください](location-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="4c9a8-108">For a complete definition of a location policy, see [Plan location policies for Skype for Business Server](location-policies.md).</span></span>
  
<span data-ttu-id="4c9a8-109">Skype for Business Server は、場所ポリシーをサブネットに基づいてクライアントに割り当てるか、グローバル ポリシー、サイト単位、またはユーザー単位のポリシーに基づいてユーザーに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="4c9a8-109">Skype for Business Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="4c9a8-110">ユーザーを有効にする方法を決定するには、まず、次の情報を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c9a8-110">To help decide how you will enable users, you should first answer the following questions.</span></span>
  
 <span data-ttu-id="4c9a8-111">**すべてのユーザーを有効にするか、またはエンタープライズの特定の地理的領域にサポートを限定するか。**</span><span class="sxs-lookup"><span data-stu-id="4c9a8-111">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>
  
> <span data-ttu-id="4c9a8-112">グローバルな場所ポリシーを使用することで、エンタープライズ内のすべてのユーザーに場所を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4c9a8-112">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="4c9a8-113">ただし、場所ポリシーを Skype for Business Server ネットワーク サイトに割り当て、サブネットをサイトに追加することで、E9-1-1 のサポートを企業内の選択した場所に制限し、サイトごとに E9-1-1 ルーティング動作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4c9a8-113">However, by assigning a location policy to a Skype for Business Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span> 
    
 <span data-ttu-id="4c9a8-114">**ユーザー ポリシーを使用して個々のユーザーを有効にするか。**</span><span class="sxs-lookup"><span data-stu-id="4c9a8-114">**Do you plan to enable individual users through a user policy?**</span></span>
  
> <span data-ttu-id="4c9a8-115">E9-1-1 サポートをカスタマイズする必要がある場合は、場所ポリシーを特定のユーザーまたは共通領域電話の連絡先オブジェクトに直接割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4c9a8-115">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>
    
 <span data-ttu-id="4c9a8-116">**クライアントがネットワーク外を移動している場合、または定義されていないサブネットから接続されている場合、そのクライアントでも E9-1-1 を有効にするか。**</span><span class="sxs-lookup"><span data-stu-id="4c9a8-116">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>
  
> <span data-ttu-id="4c9a8-117">ユーザーにグローバル、サイト、またはユーザー単位の場所ポリシーが割り当てられている場合、クライアントが定義されたサブネット内にない場合や、場所情報サービスによって場所が見つからない場合は、ユーザーにクライアントに場所を手動で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c9a8-117">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="4c9a8-118">詳細については、「Skype for Business Server で場所を手動で取得するためのユーザー エクスペリエンスの定義 [」を参照してください](manually-acquiring-a-location.md)。</span><span class="sxs-lookup"><span data-stu-id="4c9a8-118">For details, see [Define the user experience for manually acquiring a location in Skype for Business Server](manually-acquiring-a-location.md).</span></span>
    

