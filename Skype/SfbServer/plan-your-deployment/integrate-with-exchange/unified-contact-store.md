---
title: Skype for Business Server での統合連絡先ストアの計画
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 6/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d56e11be-43dd-45d4-8ac6-3adfb03f5d1a
description: '概要: Skype for Business Server と Exchange 2013 の統合を計画する場合は、このトピックを確認してください。'
ms.openlocfilehash: 3ce06118f8225e78c5c84a8f9124e4815f79d593
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816257"
---
# <a name="plan-for-unified-contact-store-in-skype-for-business-server-2015"></a><span data-ttu-id="742f0-103">Skype for Business Server 2015 での統合連絡先ストアの計画</span><span class="sxs-lookup"><span data-stu-id="742f0-103">Plan for unified contact store in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="742f0-104">**概要:** Skype for Business Server と Exchange 2013 または 2016 の統合を計画する場合は、このトピックを確認してください。</span><span class="sxs-lookup"><span data-stu-id="742f0-104">**Summary:** Review this topic while planning to integrate Skype for Business Server with Exchange 2013 or 2016.</span></span>
  
<span data-ttu-id="742f0-105">統合連絡先ストアは、Microsoft Office 製品間で一貫した連絡先エクスペリエンスを提供し、ユーザーは Exchange 2013 のすべての連絡先情報を保存できますが、Skype for Business、Exchange、Outlook、および Outlook Web Access 全体でグローバルに情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="742f0-105">Unified contact store provides a consistent contact experience across Microsoft Office products, and enables users to store all contact information in Exchange 2013 but allows the information to be available globally across Skype for Business, Exchange, Outlook, and Outlook Web Access.</span></span>
  
## <a name="requirements-for-unified-contact-store"></a><span data-ttu-id="742f0-106">統合連絡先ストアの要件</span><span class="sxs-lookup"><span data-stu-id="742f0-106">Requirements for unified contact store</span></span>

<span data-ttu-id="742f0-107">Skype for Business Server に統合連絡先ストアを実装するには:</span><span class="sxs-lookup"><span data-stu-id="742f0-107">To implement unified contact store in Skype for Business Server:</span></span>
  
- <span data-ttu-id="742f0-108">Skype for Business Server と Exchange 2013 または 2016 を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="742f0-108">You must be running Skype for Business Server and Exchange 2013 or 2016.</span></span>
    
- <span data-ttu-id="742f0-109">ユーザーは、Skype for Business Server から Exchange 2013 または 2016 に連絡先を移行するために Skype for Business を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="742f0-109">Users must use Skype for Business to migrate their contacts from Skype for Business Server to Exchange 2013 or 2016.</span></span>
    
- <span data-ttu-id="742f0-110">ユーザー メールボックスは Exchange 2013 に移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="742f0-110">User mailboxes must be migrated to Exchange 2013.</span></span>
    
- <span data-ttu-id="742f0-111">Skype for Business Server と Exchange 2013 または 2016 の間にサーバー間認証を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="742f0-111">You must have server-to-server authentication configured between Skype for Business Server and Exchange 2013 or 2016.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="742f0-112">Skype for Business Server と Exchange 2013 または 2016 の間の認証のセットアップに関する詳細な要件については、「操作」のドキュメントの「Skype for Business Server でのサーバー間認証 [(OAuth)](../../manage/authentication/server-to-server-and-partner-applications.md) およびパートナー アプリケーションの管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="742f0-112">For detailed requirements about setting up authentication between Skype for Business Server and Exchange 2013 or 2016, see [Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="742f0-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="742f0-113">See also</span></span>

[<span data-ttu-id="742f0-114">Skype for Business Server での統合連絡先ストアの展開</span><span class="sxs-lookup"><span data-stu-id="742f0-114">Deploy unified contact store in Skype for Business Server</span></span>](../../deploy/deploy-unified-contact-store.md)
