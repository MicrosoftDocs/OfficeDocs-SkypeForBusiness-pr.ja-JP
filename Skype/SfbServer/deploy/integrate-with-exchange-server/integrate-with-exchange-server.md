---
title: Skype for Business Server 2015 と Exchange Server との統合
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 795dc1c6-524f-4012-8b66-103b55198044
description: '概要: ビジネス サーバー 2015 の 2016 の Exchange Server や Exchange Server 2013 と Skype の統合の手順を確認します。'
ms.openlocfilehash: c8cbecd6b78e3dc14ad2133a93d9fc2d1f6bb3d6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="integrate-skype-for-business-server-2015-with-exchange-server"></a><span data-ttu-id="568ec-103">Skype for Business Server 2015 と Exchange Server との統合</span><span class="sxs-lookup"><span data-stu-id="568ec-103">Integrate Skype for Business Server 2015 with Exchange Server</span></span>
 
<span data-ttu-id="568ec-104">**の概要:**2016 の Exchange Server や Exchange Server 2013 と Skype のビジネス サーバー 2015 の統合の手順を確認します。</span><span class="sxs-lookup"><span data-stu-id="568ec-104">**Summary:** Review integration steps for Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="568ec-105">2016 の Exchange Server や Exchange Server 2013 ビジネス サーバー 2015 の Skype は、互換性のあるし、も統合します。</span><span class="sxs-lookup"><span data-stu-id="568ec-105">Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015 are compatible and integrate well.</span></span> <span data-ttu-id="568ec-106">Skype のビジネス ユーザーのプレゼンス情報を報告して、Microsoft outlook で、同様に、ビジネスの Skype ユーザーの Outlook の予定表にアクセス、ユーザーが会議のスケジュールを持っていることを確認でき、会議中にビジーとしてユーザーのプレゼンスを表示します。</span><span class="sxs-lookup"><span data-stu-id="568ec-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="568ec-107">Skype ビジネス サーバー (またはその逆) の 2 つの製品まとめて実行するために Exchange Server を実行する必要はありませんが、互いに相手のユーザー エクスペリエンスを向上します。</span><span class="sxs-lookup"><span data-stu-id="568ec-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>
  
<span data-ttu-id="568ec-108">このドキュメントについての情報のビジネス サーバー 2015 2016 の Exchange Server や Exchange Server 2013 では、Skype を統合することですが、初期設定が想定しています. これら 2 つの製品の構成はすでに実行されています。</span><span class="sxs-lookup"><span data-stu-id="568ec-108">This documentation provides information on integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="568ec-109">Skype をビジネス サーバー 2015 の展開の詳細については、[ビジネス サーバー 2015 の技術センターの Skype](https://go.microsoft.com/fwlink/p/?LinkId=246127)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="568ec-109">For details about deploying Skype for Business Server 2015 see the [Skype for Business Server 2015 Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span></span> <span data-ttu-id="568ec-110">Exchange Server の展開の詳細については、お使いの Exchange の展開に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="568ec-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>
  
<span data-ttu-id="568ec-111">Microsoft Exchange Online でのビジネス サーバー 2015 の Skype の上の設置型インストールを統合する場合は、[設置型の Skype ビジネス サーバー 2015 と Outlook Web App の構成の統合](outlook-web-app.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="568ec-111">If you are integrating an on premises installation of Skype for Business Server 2015 with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](outlook-web-app.md).</span></span>
  
<span data-ttu-id="568ec-112">社内の Exchange Server のオンライン ビジネスの Skype を統合する場合は、 [Skype のオンライン ビジネスとの社内の Exchange との間の OAuth の構成](oauth-with-online-and-on-premises.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="568ec-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="568ec-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="568ec-113">In this section</span></span>

[<span data-ttu-id="568ec-114">ビジネス サーバー 2015 と Exchange Server の Skype のパートナーのアプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="568ec-114">Configure partner applications in Skype for Business Server 2015 and Exchange Server</span></span>](configure-partner-applications.md)
  
[<span data-ttu-id="568ec-115">Exchange Server のアーカイブを使用するサーバー 2015 のビジネス用の Skype を構成します。</span><span class="sxs-lookup"><span data-stu-id="568ec-115">Configure Skype for Business Server 2015 to use Exchange Server archiving</span></span>](use-exchange-archiving.md)
  
[<span data-ttu-id="568ec-116">ビジネス データのアーカイブされた Skype を検索する SharePoint サーバーの構成します。</span><span class="sxs-lookup"><span data-stu-id="568ec-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)
  
[<span data-ttu-id="568ec-117">統合連絡先ストアを使用するサーバー 2015 のビジネス用の Skype を構成します。</span><span class="sxs-lookup"><span data-stu-id="568ec-117">Configure Skype for Business Server 2015 to use the unified contact store</span></span>](use-the-unified-contact-store.md)
  
[<span data-ttu-id="568ec-118">ビジネス サーバー 2015 の Skype の高解像度の写真の使用を構成します。</span><span class="sxs-lookup"><span data-stu-id="568ec-118">Configure the use of high-resolution photos in Skype for Business Server 2015</span></span>](high-resolution-photos.md)
  
[<span data-ttu-id="568ec-119">ビジネス サーバー 2015 のボイス メール用 Skype の Exchange Server ユニファイド メッセージングを設定します。</span><span class="sxs-lookup"><span data-stu-id="568ec-119">Configure Exchange Server Unified Messaging for Skype for Business Server 2015 voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)
  
[<span data-ttu-id="568ec-120">ビジネス サーバー 2015 と Microsoft Outlook Web App の 2013年の Skype を統合します。</span><span class="sxs-lookup"><span data-stu-id="568ec-120">Integrating Skype for Business Server 2015 and Microsoft Outlook Web App 2013</span></span>](http://technet.microsoft.com/library/513d4cc7-aa87-4f68-b99d-d58b63bdf242.aspx)
  
[<span data-ttu-id="568ec-121">ビジネス サーバー 2015 の Skype のクライアント コンピューターの個人用連絡先ストアを構成します。</span><span class="sxs-lookup"><span data-stu-id="568ec-121">Configure the personal contacts store on client computers for Skype for Business Server 2015</span></span>](personal-contacts-store.md)
  
## <a name="see-also"></a><span data-ttu-id="568ec-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="568ec-122">See also</span></span>

#### 

[<span data-ttu-id="568ec-123">ビジネスとの交換用 Skype を統合しようとしてください。</span><span class="sxs-lookup"><span data-stu-id="568ec-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)

