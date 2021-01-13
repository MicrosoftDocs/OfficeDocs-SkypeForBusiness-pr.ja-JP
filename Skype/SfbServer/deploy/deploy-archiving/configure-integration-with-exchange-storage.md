---
title: Skype for Business Server の Exchange ストレージとの統合を構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: '概要: このトピックでは、Skype for Business Server で Exchange ストレージとの統合を構成する方法について説明します。'
ms.openlocfilehash: 05a0c65aaca54e469f30dd5e732565f6ec0bbb4b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825067"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a><span data-ttu-id="58a84-103">Skype for Business Server の Exchange ストレージとの統合を構成する</span><span class="sxs-lookup"><span data-stu-id="58a84-103">Configure integration with Exchange storage for Skype for Business Server</span></span>
 
<span data-ttu-id="58a84-104">**概要:** このトピックでは、Skype for Business Server で Exchange ストレージとの統合を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="58a84-104">**Summary:** Read this topic to learn how to configure integration with Exchange storage in Skype for Business Server.</span></span>
  
<span data-ttu-id="58a84-105">展開内のすべてのユーザーに Microsoft Exchange 統合を使用する場合は、ユーザーの Skype for Business Server アーカイブ ポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58a84-105">If you use Microsoft Exchange integration for all users in your deployment, you don't need to configure Skype for Business Server archiving policies for your users.</span></span> <span data-ttu-id="58a84-106">代わりに、Exchange In-Place 保持ポリシーを構成して、Exchange にホームのユーザーのメールボックスを保持In-Placeします。</span><span class="sxs-lookup"><span data-stu-id="58a84-106">Instead, you configure Exchange In-Place Hold policies to support archiving for users homed on Exchange, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="58a84-107">Exchange ストレージとの統合を構成する前に、「Skype for Business Server でのアーカイブの [計画」を参照してください](../../plan-your-deployment/archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="58a84-107">Before you configure integration with Exchange storage, read [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="58a84-108">Exchange In-Place保持ポリシーの詳細については、Exchange 製品ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="58a84-108">For details about Exchange In-Place Hold policies, see the Exchange product documentation.</span></span> 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="58a84-109">Microsoft Exchange ストレージとの統合を構成する</span><span class="sxs-lookup"><span data-stu-id="58a84-109">Configure integration with Microsoft Exchange storage</span></span>

1. <span data-ttu-id="58a84-110">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="58a84-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="58a84-111">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="58a84-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="58a84-112">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58a84-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="58a84-113">アーカイブ構成一覧で、適切なグローバル構成、サイト構成、またはプール構成の名前をクリックし、[**編集**]、[**詳細の表示**] の順にクリックして、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="58a84-113">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="58a84-114">Exchange ストレージとの統合を有効にするには **、[Microsoft Exchange 統合] チェック ボックスを** オンにします。</span><span class="sxs-lookup"><span data-stu-id="58a84-114">To enable integration with Exchange storage, select the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="58a84-115">Exchange ストレージとの統合を無効にするには、[Microsoft Exchange 統合] **チェック ボックスを** オフにします。</span><span class="sxs-lookup"><span data-stu-id="58a84-115">To disable integration with Exchange storage, clear the **Microsoft Exchange integration** check box.</span></span>
    
5. <span data-ttu-id="58a84-116">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58a84-116">Click **Commit**.</span></span>
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a><span data-ttu-id="58a84-117">Skype for Business Server と Microsoft Exchange が異なるフォレストに展開されている場合</span><span class="sxs-lookup"><span data-stu-id="58a84-117">When Skype for Business Server and Microsoft Exchange are deployed in different forests</span></span>

<span data-ttu-id="58a84-118">Microsoft Exchange 統合を使用し、Microsoft Exchange Server が Skype for Business Server と同じフォレストに展開されていない場合は、次の Exchange Active Directory 属性が Skype for Business Server が展開されているフォレストと同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58a84-118">If you use Microsoft Exchange integration and Microsoft Exchange Server is not deployed in the same forest as Skype for Business Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Skype for Business Server is deployed:</span></span>
  
- <span data-ttu-id="58a84-119">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="58a84-119">msExchUserHoldPolicies</span></span>
    
- <span data-ttu-id="58a84-120">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="58a84-120">proxyAddresses</span></span>
    
<span data-ttu-id="58a84-p102">これは複数値の属性です。この属性を同期するときは、値を置き換えるのではなく値をマージして、既存の値が失われないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="58a84-p102">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>
  

