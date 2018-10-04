---
title: Exchange の記憶域を持つ Skype のビジネス サーバーの統合を構成します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: '概要: は、Skype での Exchange の記憶域を持つビジネス サーバーの統合を構成する方法については、このトピックを読みます。'
ms.openlocfilehash: 35ef648a1076283f63752221a807da21bf4208ca
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370621"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a><span data-ttu-id="a531f-103">Exchange の記憶域を持つ Skype のビジネス サーバーの統合を構成します。</span><span class="sxs-lookup"><span data-stu-id="a531f-103">Configure integration with Exchange storage for Skype for Business Server</span></span>
 
<span data-ttu-id="a531f-104">**の概要:** Skype で Exchange の記憶域を持つビジネス サーバーの統合を構成する方法については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a531f-104">**Summary:** Read this topic to learn how to configure integration with Exchange storage in Skype for Business Server.</span></span>
  
<span data-ttu-id="a531f-105">配置内のすべてのユーザーの Microsoft Exchange の統合を使用する場合、ユーザーのアーカイブ ・ ポリシーをビジネス サーバー用 Skype を構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a531f-105">If you use Microsoft Exchange integration for all users in your deployment, you don't need to configure Skype for Business Server archiving policies for your users.</span></span> <span data-ttu-id="a531f-106">代わりに、インプレース保持に自分のメールボックスに、exchange の置かれているユーザー用にアーカイブをサポートするための Exchange インプレース保持ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="a531f-106">Instead, you configure Exchange In-Place Hold policies to support archiving for users homed on Exchange, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="a531f-107">Exchange ストレージ統合を構成する前に、 [Skype のビジネス サーバーでアーカイブするための計画](../../plan-your-deployment/archiving/archiving.md)を読み取る。</span><span class="sxs-lookup"><span data-stu-id="a531f-107">Before you configure integration with Exchange storage, read [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="a531f-108">Exchange インプレース保持ポリシーの詳細については、Exchange 製品のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a531f-108">For details about Exchange In-Place Hold policies, see the Exchange product documentation.</span></span> 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="a531f-109">Microsoft Exchange ストレージ統合を構成します。</span><span class="sxs-lookup"><span data-stu-id="a531f-109">Configure integration with Microsoft Exchange storage</span></span>

1. <span data-ttu-id="a531f-110">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a531f-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a531f-111">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="a531f-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="a531f-112">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a531f-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="a531f-113">アーカイブ構成の一覧から、適切なグローバル構成、サイト構成、またはプール構成の名前をクリックし、[**編集**]、[**詳細の表示**] の順にクリックし、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a531f-113">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="a531f-114">Exchange ストレージとの統合を有効にするには、 **Microsoft Exchange の統合**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="a531f-114">To enable integration with Exchange storage, select the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="a531f-115">Exchange ストレージとの統合を無効にするには、 **Microsoft Exchange の統合**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="a531f-115">To disable integration with Exchange storage, clear the **Microsoft Exchange integration** check box.</span></span>
    
5. <span data-ttu-id="a531f-116">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a531f-116">Click **Commit**.</span></span>
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a><span data-ttu-id="a531f-117">Business Server と Microsoft Exchange の Skype が別々 のフォレストに配置されるとき</span><span class="sxs-lookup"><span data-stu-id="a531f-117">When Skype for Business Server and Microsoft Exchange are deployed in different forests</span></span>

<span data-ttu-id="a531f-118">Microsoft Exchange の統合を使用するビジネス サーバーの Skype と同じフォレストに Microsoft Exchange Server が展開されない場合は、次の Exchange の Active Directory 属性がフォレストに同期されていることを確認してください、Skype のビジネス サーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="a531f-118">If you use Microsoft Exchange integration and Microsoft Exchange Server is not deployed in the same forest as Skype for Business Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Skype for Business Server is deployed:</span></span>
  
- <span data-ttu-id="a531f-119">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="a531f-119">msExchUserHoldPolicies</span></span>
    
- <span data-ttu-id="a531f-120">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="a531f-120">proxyAddresses</span></span>
    
<span data-ttu-id="a531f-p102">これは複数値の属性です。この属性を同期するときは、値を置き換えるのではなく値をマージして、既存の値が失われないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a531f-p102">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>
  

