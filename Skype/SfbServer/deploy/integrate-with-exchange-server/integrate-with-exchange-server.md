---
title: Skype for Business Server とビジネス サーバーを統合Exchange Server
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
description: '概要: 2016 年または 2016 年Exchange Server 2013 年Exchange Server Skype for Business Server の統合手順を確認します。'
ms.openlocfilehash: b19aa73e62b12674551690b716144fb67b4cd715
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104853"
---
# <a name="integrate-skype-for-business-server-with-exchange-server"></a><span data-ttu-id="a0239-103">Skype for Business Server とビジネス サーバーを統合Exchange Server</span><span class="sxs-lookup"><span data-stu-id="a0239-103">Integrate Skype for Business Server with Exchange Server</span></span>

<span data-ttu-id="a0239-104">**概要:** 2013 以降のExchange Server Skype for Business Server の統合手順を確認します。</span><span class="sxs-lookup"><span data-stu-id="a0239-104">**Summary:** Review integration steps for Exchange Server 2013 or later and Skype for Business Server.</span></span>

<span data-ttu-id="a0239-105">Exchange Server 2013 以降と Skype for Business Server は互換性があり、統合も可能です。</span><span class="sxs-lookup"><span data-stu-id="a0239-105">Exchange Server 2013 or later and Skype for Business Server are compatible and integrate well.</span></span> <span data-ttu-id="a0239-106">たとえば、Skype for Business ユーザープレゼンス情報は、Microsoft Outlook で報告できます。同様に、Skype for Business はユーザーの Outlook 予定表にアクセスし、ユーザーが会議がスケジュールされているのを確認し、会議中にユーザーのプレゼンスをビジー状態として表示できます。</span><span class="sxs-lookup"><span data-stu-id="a0239-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="a0239-107">Skype for Business Server (またはその逆) を実行するために、Exchange Serverを実行する必要はありません。ただし、2 つの製品は互いにユーザー エクスペリエンスを強化します。</span><span class="sxs-lookup"><span data-stu-id="a0239-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>

<span data-ttu-id="a0239-108">このドキュメントでは、Skype for Business Server と Exchange Server 2016 または Exchange Server 2013 の統合に関する情報を提供しますが、これら 2 つの製品の初期セットアップと構成は既に行っている前提です。</span><span class="sxs-lookup"><span data-stu-id="a0239-108">This documentation provides information on integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="a0239-109">Skype for Business Server の展開の詳細については [、「Skype for Business Server Tech Center」を参照してください](../../../Hub/index.yml)。</span><span class="sxs-lookup"><span data-stu-id="a0239-109">For details about deploying Skype for Business Server see the [Skype for Business Server Tech Center](../../../Hub/index.yml).</span></span> <span data-ttu-id="a0239-110">展開方法の詳細についてはExchange Serverバージョンの Exchange の展開ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0239-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>

<span data-ttu-id="a0239-111">Skype for Business Server のオンプレミス インストールを Microsoft Exchange Online と統合する場合は [、「Configure integration between on-premises Skype for Business Server](outlook-web-app.md)と Outlook Web App」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0239-111">If you are integrating an on premises installation of Skype for Business Server with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span></span>

<span data-ttu-id="a0239-112">Skype for Business Online とオンプレミスの Exchange Serverを統合する場合は、「Configure OAuth between Skype for Business Online と [Exchange on premises」を参照してください](oauth-with-online-and-on-premises.md)。</span><span class="sxs-lookup"><span data-stu-id="a0239-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="a0239-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a0239-113">In this section</span></span>

[<span data-ttu-id="a0239-114">Skype for Business Server および Skype でパートナー アプリケーションを構成Exchange Server</span><span class="sxs-lookup"><span data-stu-id="a0239-114">Configure partner applications in Skype for Business Server and Exchange Server</span></span>](configure-partner-applications.md)

[<span data-ttu-id="a0239-115">Skype for Business Server でアーカイブを使用Exchange Server構成する</span><span class="sxs-lookup"><span data-stu-id="a0239-115">Configure Skype for Business Server to use Exchange Server archiving</span></span>](use-exchange-archiving.md)

[<span data-ttu-id="a0239-116">アーカイブされた Skype for Business データを検索する SharePoint Server を構成する</span><span class="sxs-lookup"><span data-stu-id="a0239-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)

[<span data-ttu-id="a0239-117">統合連絡先ストアを使用する Skype for Business Server の構成</span><span class="sxs-lookup"><span data-stu-id="a0239-117">Configure Skype for Business Server to use the unified contact store</span></span>](use-the-unified-contact-store.md)

[<span data-ttu-id="a0239-118">Skype for Business Server での高解像度写真の使用を構成する</span><span class="sxs-lookup"><span data-stu-id="a0239-118">Configure the use of high-resolution photos in Skype for Business Server</span></span>](high-resolution-photos.md)

[<span data-ttu-id="a0239-119">Skype Exchange Serverユニファイド メッセージングの構成</span><span class="sxs-lookup"><span data-stu-id="a0239-119">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)

<span data-ttu-id="a0239-120">[Skype for Business Server と 2013 Microsoft Outlook Web Appの統合](/previous-versions/office/communications/jj688055(v=ocs.16))</span><span class="sxs-lookup"><span data-stu-id="a0239-120">[Integrating Skype for Business Server and Microsoft Outlook Web App 2013](/previous-versions/office/communications/jj688055(v=ocs.16))</span></span>

[<span data-ttu-id="a0239-121">Skype for Business Server のクライアント コンピューター上の個人用連絡先ストアを構成する</span><span class="sxs-lookup"><span data-stu-id="a0239-121">Configure the personal contacts store on client computers for Skype for Business Server</span></span>](personal-contacts-store.md)

## <a name="see-also"></a><span data-ttu-id="a0239-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0239-122">See also</span></span>

[<span data-ttu-id="a0239-123">Skype for Business と Exchange の統合の計画</span><span class="sxs-lookup"><span data-stu-id="a0239-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)