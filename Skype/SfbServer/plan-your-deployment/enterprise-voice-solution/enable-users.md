---
title: Skype for Business Server でユーザーの E9-1 を有効にする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 有効にするユーザー、およびローミングユーザーをサポートする方法など、Skype for Business Server エンタープライズボイスの E9 展開の場所ポリシーに必要な決定。
ms.openlocfilehash: 717b127a94fbac966476c681cfb7f6e81d91bde9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802957"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="21203-103">Skype for Business Server でユーザーの E9-1 を有効にする</span><span class="sxs-lookup"><span data-stu-id="21203-103">Enable users for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="21203-104">有効にするユーザー、およびローミングユーザーをサポートする方法など、Skype for Business Server エンタープライズボイスの E9 展開の場所ポリシーに必要な決定。</span><span class="sxs-lookup"><span data-stu-id="21203-104">Decisions necessary for the location policy for an E9-1-1 deployment in Skype for Business Server Enterprise Voice, including which users to enable and how to support roaming users.</span></span>
  
<span data-ttu-id="21203-105">顧客の登録中に、Skype for Business Server は位置情報ポリシーを使って、エンタープライズボイス対応ユーザーの E9 プロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="21203-105">During client registration, Skype for Business Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="21203-106">このポリシーには、E9-1-1 の実装方法を定義する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="21203-106">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="21203-107">たとえば、場所情報のポリシーには、緊急ダイヤルの文字列などの情報が含まれています。また、位置情報サービスで自動的に場所を指定しない場合は、その場所を手動で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21203-107">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="21203-108">位置情報ポリシーの完全な定義については、「 [Skype For Business Server の位置情報ポリシーの計画](location-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21203-108">For a complete definition of a location policy, see [Plan location policies for Skype for Business Server](location-policies.md).</span></span>
  
<span data-ttu-id="21203-109">Skype for Business Server は、サブネットに基づいてクライアントまたはグローバル、サイトごと、またはユーザーごとのポリシーに基づいてユーザーに位置情報ポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="21203-109">Skype for Business Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="21203-110">ユーザーを有効にする方法を決定するには、まず、次の情報を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21203-110">To help decide how you will enable users, you should first answer the following questions.</span></span>
  
 <span data-ttu-id="21203-111">**すべてのユーザーを有効にするか、またはエンタープライズの特定の地理的領域にサポートを限定するか。**</span><span class="sxs-lookup"><span data-stu-id="21203-111">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>
  
> <span data-ttu-id="21203-112">グローバルな場所ポリシーを使用することで、エンタープライズ内のすべてのユーザーに場所を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="21203-112">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="21203-113">ただし、Skype for Business Server ネットワークサイトに位置情報ポリシーを割り当て、サブネットをサイトに追加することによって、E9 のサポートをエンタープライズ内の選択した場所に対して制限することができます。また、サイトごとに E9 のルーティング動作を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="21203-113">However, by assigning a location policy to a Skype for Business Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span> 
    
 <span data-ttu-id="21203-114">**ユーザー ポリシーを使用して個々のユーザーを有効にするか。**</span><span class="sxs-lookup"><span data-stu-id="21203-114">**Do you plan to enable individual users through a user policy?**</span></span>
  
> <span data-ttu-id="21203-115">E9-1-1 サポートをカスタマイズする必要がある場合は、場所ポリシーを特定のユーザーまたは共通領域電話の連絡先オブジェクトに直接割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="21203-115">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>
    
 <span data-ttu-id="21203-116">**クライアントがネットワーク外を移動している場合、または定義されていないサブネットから接続されている場合、そのクライアントでも E9-1-1 を有効にするか。**</span><span class="sxs-lookup"><span data-stu-id="21203-116">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>
  
> <span data-ttu-id="21203-117">ユーザーにグローバル、サイト、またはユーザーごとの場所のポリシーが割り当てられている場合、クライアントが定義されたサブネット内に存在しない場合、または場所情報サービスによって場所が見つからない場合は、クライアントに場所を手動で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21203-117">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="21203-118">詳細については、「 [Skype For Business Server で場所を手動で取得するためのユーザーエクスペリエンスの定義](manually-acquiring-a-location.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21203-118">For details, see [Define the user experience for manually acquiring a location in Skype for Business Server](manually-acquiring-a-location.md).</span></span>
    

