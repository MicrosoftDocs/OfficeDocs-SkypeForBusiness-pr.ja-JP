---
title: Skype for Business Server の統合連絡先ストアの計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 6/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d56e11be-43dd-45d4-8ac6-3adfb03f5d1a
description: '概要: Skype for Business Server と Exchange 2013 との統合を計画しているときに、このトピックを確認してください。'
ms.openlocfilehash: 4548773c382b4295ddfbfa141f18f0df8ba367ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297394"
---
# <a name="plan-for-unified-contact-store-in-skype-for-business-server-2015"></a><span data-ttu-id="dd8f0-103">Skype for Business Server 2015 の統合連絡先ストアの計画</span><span class="sxs-lookup"><span data-stu-id="dd8f0-103">Plan for unified contact store in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="dd8f0-104">**概要:** Skype for Business Server を Exchange 2013 または2016に統合する計画中に、このトピックを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dd8f0-104">**Summary:** Review this topic while planning to integrate Skype for Business Server with Exchange 2013 or 2016.</span></span>
  
<span data-ttu-id="dd8f0-105">統合連絡先ストアでは、Microsoft Office 製品全体で一貫した連絡先エクスペリエンスを提供し、ユーザーは Exchange 2013 ですべての連絡先情報を保存できますが、情報は Skype for Business、Exchange、Outlook でグローバルに利用できます。、Outlook Web Access などがあります。</span><span class="sxs-lookup"><span data-stu-id="dd8f0-105">Unified contact store provides a consistent contact experience across Microsoft Office products, and enables users to store all contact information in Exchange 2013 but allows the information to be available globally across Skype for Business, Exchange, Outlook, and Outlook Web Access.</span></span>
  
## <a name="requirements-for-unified-contact-store"></a><span data-ttu-id="dd8f0-106">統合連絡先ストアの要件</span><span class="sxs-lookup"><span data-stu-id="dd8f0-106">Requirements for unified contact store</span></span>

<span data-ttu-id="dd8f0-107">Skype for Business Server でユニファイド連絡先ストアを実装するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="dd8f0-107">To implement unified contact store in Skype for Business Server:</span></span>
  
- <span data-ttu-id="dd8f0-108">Skype for Business Server および Exchange 2013 または2016を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd8f0-108">You must be running Skype for Business Server and Exchange 2013 or 2016.</span></span>
    
- <span data-ttu-id="dd8f0-109">ユーザーは skype for Business を使用して、Skype for Business Server から Exchange 2013 または2016に連絡先を移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd8f0-109">Users must use Skype for Business to migrate their contacts from Skype for Business Server to Exchange 2013 or 2016.</span></span>
    
- <span data-ttu-id="dd8f0-110">ユーザーのメールボックスは Exchange 2013 に移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd8f0-110">User mailboxes must be migrated to Exchange 2013.</span></span>
    
- <span data-ttu-id="dd8f0-111">Skype for Business Server と Exchange 2013 または2016の間にサーバー間認証が構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd8f0-111">You must have server-to-server authentication configured between Skype for Business Server and Exchange 2013 or 2016.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dd8f0-112">Skype for Business Server と Exchange 2013 または2016の間の認証のセットアップの詳細については、「 [skype For Business server でのサーバー間認証 (OAuth) とパートナーアプリケーションの管理](../../manage/authentication/server-to-server-and-partner-applications.md)」を参照してください。documentation.</span><span class="sxs-lookup"><span data-stu-id="dd8f0-112">For detailed requirements about setting up authentication between Skype for Business Server and Exchange 2013 or 2016, see [Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dd8f0-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd8f0-113">See also</span></span>

[<span data-ttu-id="dd8f0-114">Skype for Business Server にユニファイド連絡先ストアを展開する</span><span class="sxs-lookup"><span data-stu-id="dd8f0-114">Deploy unified contact store in Skype for Business Server</span></span>](../../deploy/deploy-unified-contact-store.md)
