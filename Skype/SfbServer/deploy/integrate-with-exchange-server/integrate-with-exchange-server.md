---
title: Skype for Business Server と Exchange Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 795dc1c6-524f-4012-8b66-103b55198044
description: '概要: Exchange Server 2016 または Exchange Server 2013 および Skype for Business Server の統合手順を確認します。'
ms.openlocfilehash: 6b5c63c0ad6783c11fd8fde25d1b00dc84d7e15a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833737"
---
# <a name="integrate-skype-for-business-server-with-exchange-server"></a><span data-ttu-id="33ea9-103">Skype for Business Server と Exchange Server</span><span class="sxs-lookup"><span data-stu-id="33ea9-103">Integrate Skype for Business Server with Exchange Server</span></span>

<span data-ttu-id="33ea9-104">**概要:** Exchange Server 2013 以降および Skype for Business Server の統合手順を確認します。</span><span class="sxs-lookup"><span data-stu-id="33ea9-104">**Summary:** Review integration steps for Exchange Server 2013 or later and Skype for Business Server.</span></span>

<span data-ttu-id="33ea9-105">Exchange Server 2013 以降と Skype for Business Server は互換性があり、うまく統合されています。</span><span class="sxs-lookup"><span data-stu-id="33ea9-105">Exchange Server 2013 or later and Skype for Business Server are compatible and integrate well.</span></span> <span data-ttu-id="33ea9-106">たとえば、Skype for Business のユーザー プレゼンス情報は Microsoft Outlook で報告できます。同様に、Skype for Business はユーザーの Outlook 予定表にアクセスし、ユーザーが会議がスケジュールされているのを確認し、会議中にユーザーのプレゼンスを取り込み中として表示できます。</span><span class="sxs-lookup"><span data-stu-id="33ea9-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="33ea9-107">Skype for Business Server を実行するために Exchange Server を実行する必要はありません (またはその逆)、2 つの製品を組み合わせてお互いにユーザー エクスペリエンスを向上させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="33ea9-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>

<span data-ttu-id="33ea9-108">このドキュメントでは、Skype for Business Server と Exchange Server 2016 または Exchange Server 2013 の統合について説明しますが、これら 2 つの製品の初期セットアップと構成は既に行っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="33ea9-108">This documentation provides information on integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="33ea9-109">Skype for Business Server の展開の詳細については [、Skype for Business Server Tech Center を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=246127)。</span><span class="sxs-lookup"><span data-stu-id="33ea9-109">For details about deploying Skype for Business Server see the [Skype for Business Server Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span></span> <span data-ttu-id="33ea9-110">アプリケーションの展開の詳細Exchange Server Exchange のバージョンの展開に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="33ea9-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>

<span data-ttu-id="33ea9-111">Skype for Business Server のオンプレミス インストールを Microsoft Exchange Online と統合する場合は、「Configure [integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33ea9-111">If you are integrating an on premises installation of Skype for Business Server with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span></span>

<span data-ttu-id="33ea9-112">Skype for Business Online とオンプレミスの Exchange Server を統合する場合は [、「Skype for Business Online](oauth-with-online-and-on-premises.md)とオンプレミスの Exchange の間で OAuth を構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33ea9-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="33ea9-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="33ea9-113">In this section</span></span>

[<span data-ttu-id="33ea9-114">Skype for Business Server および Exchange Server でパートナー アプリケーションを構成する</span><span class="sxs-lookup"><span data-stu-id="33ea9-114">Configure partner applications in Skype for Business Server and Exchange Server</span></span>](configure-partner-applications.md)

[<span data-ttu-id="33ea9-115">Skype for Business Server がアーカイブを使用Exchange Server構成する</span><span class="sxs-lookup"><span data-stu-id="33ea9-115">Configure Skype for Business Server to use Exchange Server archiving</span></span>](use-exchange-archiving.md)

[<span data-ttu-id="33ea9-116">アーカイブされた Skype for Business データを検索する SharePoint Server を構成する</span><span class="sxs-lookup"><span data-stu-id="33ea9-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)

[<span data-ttu-id="33ea9-117">統合連絡先ストアを使用するために Skype for Business Server を構成する</span><span class="sxs-lookup"><span data-stu-id="33ea9-117">Configure Skype for Business Server to use the unified contact store</span></span>](use-the-unified-contact-store.md)

[<span data-ttu-id="33ea9-118">Skype for Business Server で高解像度写真の使用を構成する</span><span class="sxs-lookup"><span data-stu-id="33ea9-118">Configure the use of high-resolution photos in Skype for Business Server</span></span>](high-resolution-photos.md)

[<span data-ttu-id="33ea9-119">Skype for Business Server Exchange Serverユニファイド メッセージングの構成</span><span class="sxs-lookup"><span data-stu-id="33ea9-119">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)

[<span data-ttu-id="33ea9-120">Skype for Business Server と Microsoft Outlook Web App 2013 の統合</span><span class="sxs-lookup"><span data-stu-id="33ea9-120">Integrating Skype for Business Server and Microsoft Outlook Web App 2013</span></span>](https://technet.microsoft.com/library/513d4cc7-aa87-4f68-b99d-d58b63bdf242.aspx)

[<span data-ttu-id="33ea9-121">Skype for Business Server のクライアント コンピューターで個人用連絡先ストアを構成する</span><span class="sxs-lookup"><span data-stu-id="33ea9-121">Configure the personal contacts store on client computers for Skype for Business Server</span></span>](personal-contacts-store.md)

## <a name="see-also"></a><span data-ttu-id="33ea9-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="33ea9-122">See also</span></span>

[<span data-ttu-id="33ea9-123">Skype for Business と Exchange の統合の計画</span><span class="sxs-lookup"><span data-stu-id="33ea9-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
