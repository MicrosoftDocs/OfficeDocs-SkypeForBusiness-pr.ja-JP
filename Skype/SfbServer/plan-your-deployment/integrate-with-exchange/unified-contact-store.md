---
title: ビジネス サーバーの Skype での統合連絡先ストアの計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 6/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d56e11be-43dd-45d4-8ac6-3adfb03f5d1a
description: '概要: ビジネスのサーバーで Exchange 2013 の Skype を統合するために計画するときにこのトピックを確認します。'
ms.openlocfilehash: c69e4990a77ec56ec74f1a1ac8d37c0c25872696
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907202"
---
# <a name="plan-for-unified-contact-store-in-skype-for-business-server-2015"></a><span data-ttu-id="a88f7-103">Skype for Business Server 2015 の統合連絡先ストアの計画</span><span class="sxs-lookup"><span data-stu-id="a88f7-103">Plan for unified contact store in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a88f7-104">**の概要:** ビジネスのサーバーで Exchange 2013 または 2016 の Skype を統合するために計画するときに、このトピックを確認します。</span><span class="sxs-lookup"><span data-stu-id="a88f7-104">**Summary:** Review this topic while planning to integrate Skype for Business Server with Exchange 2013 or 2016.</span></span>
  
<span data-ttu-id="a88f7-105">統合連絡先ストア、Microsoft Office 製品間で一貫性のある取引先担当者の経験を提供し、Exchange 2013 のすべての連絡先情報を格納するユーザーをできますが、ビジネス、Exchange、Outlook、Skype でグローバルに利用可能である情報では、、および Outlook Web Access。</span><span class="sxs-lookup"><span data-stu-id="a88f7-105">Unified contact store provides a consistent contact experience across Microsoft Office products, and enables users to store all contact information in Exchange 2013 but allows the information to be available globally across Skype for Business, Exchange, Outlook, and Outlook Web Access.</span></span>
  
## <a name="requirements-for-unified-contact-store"></a><span data-ttu-id="a88f7-106">統合連絡先ストアの要件</span><span class="sxs-lookup"><span data-stu-id="a88f7-106">Requirements for unified contact store</span></span>

<span data-ttu-id="a88f7-107">Skype のビジネス サーバーの統合連絡先ストアを実装します。</span><span class="sxs-lookup"><span data-stu-id="a88f7-107">To implement unified contact store in Skype for Business Server:</span></span>
  
- <span data-ttu-id="a88f7-108">ビジネス サーバーと Exchange 2013 または 2016 の Skype を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a88f7-108">You must be running Skype for Business Server and Exchange 2013 or 2016.</span></span>
    
- <span data-ttu-id="a88f7-109">ユーザーは、Skype からビジネス サーバーの Exchange 2013 または 2016、連絡先を移行するのにビジネス用の Skype を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a88f7-109">Users must use Skype for Business to migrate their contacts from Skype for Business Server to Exchange 2013 or 2016.</span></span>
    
- <span data-ttu-id="a88f7-110">ユーザーのメールボックスは、Exchange 2013 に移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a88f7-110">User mailboxes must be migrated to Exchange 2013.</span></span>
    
- <span data-ttu-id="a88f7-111">ビジネス サーバーと Exchange 2013 または 2016 の Skype 間で構成されているサーバーからサーバーへの認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="a88f7-111">You must have server-to-server authentication configured between Skype for Business Server and Exchange 2013 or 2016.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a88f7-112">ビジネス サーバーと Exchange 2013 または 2016 の Skype 間での認証の設定に関する詳細な要件[管理サーバーからサーバーへの認証 (OAuth) とビジネス サーバーの Skype のパートナーのアプリケーション](../../manage/authentication/server-to-server-and-partner-applications.md)操作で参照してください。ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="a88f7-112">For detailed requirements about setting up authentication between Skype for Business Server and Exchange 2013 or 2016, see [Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a88f7-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="a88f7-113">See also</span></span>

[<span data-ttu-id="a88f7-114">ビジネス サーバーの Skype での統合連絡先ストアを展開します。</span><span class="sxs-lookup"><span data-stu-id="a88f7-114">Deploy unified contact store in Skype for Business Server</span></span>](../../deploy/deploy-unified-contact-store.md)
