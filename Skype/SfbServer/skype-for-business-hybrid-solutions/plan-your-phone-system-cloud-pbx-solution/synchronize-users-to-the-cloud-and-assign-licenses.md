---
title: ユーザーとクラウドを同期してライセンスを割り当てる
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/3/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 3a8176fc-47ee-4809-ba2f-d8b8090c1cf3
description: Office 365 にユーザーを実際に移動するには、前に、まず、クラウドに同期される、ライセンスを割り当てることを確認します。 この操作には、Office 365 管理センターを使用します。
ms.openlocfilehash: 7f7e10a6367a7ebb134ea5f9e82ce205998640f2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="synchronize-users-to-the-cloud-and-assign-licenses"></a><span data-ttu-id="1a283-104">ユーザーとクラウドを同期してライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="1a283-104">Synchronize users to the cloud and assign licenses</span></span>
 
<span data-ttu-id="1a283-105">Office 365 にユーザーを実際に移動するには、前に、まず、クラウドに同期される、ライセンスを割り当てることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1a283-105">Before actually moving the user to Office 365, you must first confirm that they are synchronized to the cloud, and assign them a license.</span></span> <span data-ttu-id="1a283-106">この操作には、Office 365 管理センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1a283-106">To do this, you use the Office 365 Admin Center.</span></span>
  
### <a name="to-confirm-that-a-user-is-synchronized-with-office-365"></a><span data-ttu-id="1a283-107">ユーザーが Office 365 と同期していることを確認するのには</span><span class="sxs-lookup"><span data-stu-id="1a283-107">To confirm that a user is synchronized with Office 365</span></span>

1. <span data-ttu-id="1a283-108">Office 365 の管理ページを開きます (https://portal.office.com)。</span><span class="sxs-lookup"><span data-stu-id="1a283-108">Open the Office 365 Admin Center (https://portal.office.com).</span></span>
    
2. <span data-ttu-id="1a283-109">左側のナビゲーション ウィンドウで、[**ユーザー**]、[**アクティブなユーザー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a283-109">On the left navigation pane, click **Users** and then **Active Users**.</span></span>
    
3. <span data-ttu-id="1a283-110">[**ユーザーの検索**] をクリックして、ユーザーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a283-110">Click **Search for a User**, and type the name of the user.</span></span>
    
4. <span data-ttu-id="1a283-111">ユーザーが表示されており、そのステータスが [**Active Directory と同期済み**] であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1a283-111">Confirm that you see the user, and that their status is **Synched with Active Directory**.</span></span>
    
    <span data-ttu-id="1a283-112">ユーザーがまだ同期されていない場合は、3 時間以内に次の自動同期が実行されます。</span><span class="sxs-lookup"><span data-stu-id="1a283-112">If the user is not yet synchronized, the next automatic synchronization should happen within three hours.</span></span> <span data-ttu-id="1a283-113">または、すぐに同期を強制する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1a283-113">Or you could force a synchronization sooner.</span></span> <span data-ttu-id="1a283-114">詳細については、[ディレクトリ同期の強制](https://msdn.microsoft.com/en-us/library/azure/JJ151771.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a283-114">For more information, see [Force Directory Synchronization](https://msdn.microsoft.com/en-us/library/azure/JJ151771.aspx).</span></span>
    
## <a name="to-assign-the-license"></a><span data-ttu-id="1a283-115">ライセンスを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="1a283-115">To assign the license</span></span>

<span data-ttu-id="1a283-116">Office 365 のライセンスを割り当てるには、[ユーザーの PBX をクラウドのライセンスを割り当てまたは割り当て解除](https://support.office.com/article/Assign-or-unassign-a-Cloud-PBX-license-for-a-user-36c6d5a6-5ea8-4c44-9f18-fea33d5a847e)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a283-116">To assign the license in Office 365, see [Assign or unassign a Cloud PBX license for a user](https://support.office.com/article/Assign-or-unassign-a-Cloud-PBX-license-for-a-user-36c6d5a6-5ea8-4c44-9f18-fea33d5a847e).</span></span>
  

