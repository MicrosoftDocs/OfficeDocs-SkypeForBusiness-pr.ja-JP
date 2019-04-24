---
title: Skype をビジネス サーバーを Exchange Server との統合します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 795dc1c6-524f-4012-8b66-103b55198044
description: '概要: は、2016 の Exchange Server や Exchange Server 2013 と Skype のビジネス サーバーの統合の手順を確認します。'
ms.openlocfilehash: d08bf95894febb224e88cc1c40dce1f693b99704
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32210145"
---
# <a name="integrate-skype-for-business-server-with-exchange-server"></a><span data-ttu-id="d27d8-103">Skype をビジネス サーバーを Exchange Server との統合します。</span><span class="sxs-lookup"><span data-stu-id="d27d8-103">Integrate Skype for Business Server with Exchange Server</span></span>

<span data-ttu-id="d27d8-104">**の概要:** ビジネスのサーバーの Exchange Server 2013 またはそれ以降の統合手順を実行し、Skype を確認します。</span><span class="sxs-lookup"><span data-stu-id="d27d8-104">**Summary:** Review integration steps for Exchange Server 2013 or later and Skype for Business Server.</span></span>

<span data-ttu-id="d27d8-105">2013 またはそれ以降の Exchange Server Skype ビジネス サーバーの互換性と統合します。</span><span class="sxs-lookup"><span data-stu-id="d27d8-105">Exchange Server 2013 or later and Skype for Business Server are compatible and integrate well.</span></span> <span data-ttu-id="d27d8-106">Skype のビジネス ユーザーのプレゼンス情報を報告して、Microsoft outlook で、同様に、ビジネスの Skype ユーザーの Outlook の予定表にアクセス、ユーザーが会議のスケジュールを持っていることを確認でき、会議中にビジーとしてユーザーのプレゼンスを表示します。</span><span class="sxs-lookup"><span data-stu-id="d27d8-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="d27d8-107">Skype ビジネス サーバー (またはその逆) の 2 つの製品まとめて実行するために Exchange Server を実行する必要はありませんが、互いに相手のユーザー エクスペリエンスを向上します。</span><span class="sxs-lookup"><span data-stu-id="d27d8-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>

<span data-ttu-id="d27d8-108">このドキュメントでは、ビジネス サーバーと Exchange Server 2016 または Exchange Server 2013 では、Skype を統合することに関する情報を提供ですが、初期設定と、これら 2 つの製品の構成はすでに実行されています。</span><span class="sxs-lookup"><span data-stu-id="d27d8-108">This documentation provides information on integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="d27d8-109">Skype をビジネスのサーバーの展開の詳細については、 [Skype](https://go.microsoft.com/fwlink/p/?LinkId=246127)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d27d8-109">For details about deploying Skype for Business Server see the [Skype for Business Server Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span></span> <span data-ttu-id="d27d8-110">Exchange Server の展開の詳細については、お使いの Exchange の展開に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d27d8-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>

<span data-ttu-id="d27d8-111">ビジネスのサーバーで Microsoft Exchange Online の Skype の上の設置型インストールを統合する場合は、[設置型の Skype ビジネス サーバーおよび Outlook Web App の構成の統合](outlook-web-app.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d27d8-111">If you are integrating an on premises installation of Skype for Business Server with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span></span>

<span data-ttu-id="d27d8-112">社内の Exchange Server のオンライン ビジネスの Skype を統合する場合は、 [Skype のオンライン ビジネスとの社内の Exchange との間の OAuth の構成](oauth-with-online-and-on-premises.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d27d8-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d27d8-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d27d8-113">In this section</span></span>

[<span data-ttu-id="d27d8-114">ビジネス サーバーと Exchange Server の Skype のパートナーのアプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="d27d8-114">Configure partner applications in Skype for Business Server and Exchange Server</span></span>](configure-partner-applications.md)

[<span data-ttu-id="d27d8-115">Skype ビジネス サーバーで Exchange Server のアーカイブを使用するを構成します。</span><span class="sxs-lookup"><span data-stu-id="d27d8-115">Configure Skype for Business Server to use Exchange Server archiving</span></span>](use-exchange-archiving.md)

[<span data-ttu-id="d27d8-116">アーカイブされた Skype for Business データを検索するための SharePoint Server の構成</span><span class="sxs-lookup"><span data-stu-id="d27d8-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)

[<span data-ttu-id="d27d8-117">統合連絡先ストアを使用するための Skype for Business Server の構成</span><span class="sxs-lookup"><span data-stu-id="d27d8-117">Configure Skype for Business Server to use the unified contact store</span></span>](use-the-unified-contact-store.md)

[<span data-ttu-id="d27d8-118">ビジネス サーバー用の Skype の高解像度の写真の使用を構成します。</span><span class="sxs-lookup"><span data-stu-id="d27d8-118">Configure the use of high-resolution photos in Skype for Business Server</span></span>](high-resolution-photos.md)

[<span data-ttu-id="d27d8-119">ビジネス サーバーのボイス メール用 Skype の Exchange Server ユニファイド メッセージングを設定します。</span><span class="sxs-lookup"><span data-stu-id="d27d8-119">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)

[<span data-ttu-id="d27d8-120">ビジネス サーバーと Microsoft Outlook Web App の 2013年の Skype を統合します。</span><span class="sxs-lookup"><span data-stu-id="d27d8-120">Integrating Skype for Business Server and Microsoft Outlook Web App 2013</span></span>](https://technet.microsoft.com/library/513d4cc7-aa87-4f68-b99d-d58b63bdf242.aspx)

[<span data-ttu-id="d27d8-121">ビジネス サーバーのクライアント コンピューターで Skype の連絡先ストアを構成します。</span><span class="sxs-lookup"><span data-stu-id="d27d8-121">Configure the personal contacts store on client computers for Skype for Business Server</span></span>](personal-contacts-store.md)

## <a name="see-also"></a><span data-ttu-id="d27d8-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="d27d8-122">See also</span></span>

[<span data-ttu-id="d27d8-123">Skype for Business と Exchange の統合の計画</span><span class="sxs-lookup"><span data-stu-id="d27d8-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
