---
title: Skype for Business Server と Exchange Server の統合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 795dc1c6-524f-4012-8b66-103b55198044
description: '概要: Exchange Server 2016 または Exchange Server 2013 および Skype for Business Server の統合手順を確認します。'
ms.openlocfilehash: 398ded1c138743c79de0e372b930dacef08fd94f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244044"
---
# <a name="integrate-skype-for-business-server-with-exchange-server"></a><span data-ttu-id="1d8d7-103">Skype for Business Server と Exchange Server の統合</span><span class="sxs-lookup"><span data-stu-id="1d8d7-103">Integrate Skype for Business Server with Exchange Server</span></span>

<span data-ttu-id="1d8d7-104">**概要:** Exchange Server 2013 以降と Skype for Business Server の統合手順を確認します。</span><span class="sxs-lookup"><span data-stu-id="1d8d7-104">**Summary:** Review integration steps for Exchange Server 2013 or later and Skype for Business Server.</span></span>

<span data-ttu-id="1d8d7-105">Exchange Server 2013 以降と Skype for Business Server は互換性があり、適切に統合されています。</span><span class="sxs-lookup"><span data-stu-id="1d8d7-105">Exchange Server 2013 or later and Skype for Business Server are compatible and integrate well.</span></span> <span data-ttu-id="1d8d7-106">たとえば、Skype for Business ユーザーのプレゼンス情報は、Microsoft Outlook で報告できます。同様に、Skype for Business では、ユーザーの Outlook の予定表にアクセスできます。ユーザーに会議がスケジュールされていることを通知し、会議中にユーザーのプレゼンスがビジー状態であることを示します。</span><span class="sxs-lookup"><span data-stu-id="1d8d7-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="1d8d7-107">Skype for Business Server (またはその逆) を実行するために Exchange Server を実行する必要はありませんが、2つの製品の間で両方のユーザーエクスペリエンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="1d8d7-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>

<span data-ttu-id="1d8d7-108">このドキュメントでは、Skype for Business Server および Exchange 2016 Server 2013 を統合する方法について説明しますが、これら2つの製品の初期設定と構成が既に行われていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="1d8d7-108">This documentation provides information on integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="1d8d7-109">Skype for Business Server の展開の詳細については、「 [skype For Business server のテクニカルセンター](https://go.microsoft.com/fwlink/p/?LinkId=246127)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d8d7-109">For details about deploying Skype for Business Server see the [Skype for Business Server Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span></span> <span data-ttu-id="1d8d7-110">Exchange Server の展開の詳細については、お使いの Exchange のバージョンの展開に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d8d7-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>

<span data-ttu-id="1d8d7-111">Skype for Business Server のオンプレミスインストールを Microsoft Exchange Online と統合する場合は、「[オンプレミスの skype For Business server と Outlook Web App との統合を構成](outlook-web-app.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d8d7-111">If you are integrating an on premises installation of Skype for Business Server with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span></span>

<span data-ttu-id="1d8d7-112">オンプレミスの Skype for business Online を Exchange Server と統合する場合は、「 [skype for Business online と Exchange online の間で OAuth を構成](oauth-with-online-and-on-premises.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d8d7-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="1d8d7-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1d8d7-113">In this section</span></span>

[<span data-ttu-id="1d8d7-114">Skype for Business Server および Exchange Server でパートナーアプリケーションを構成する</span><span class="sxs-lookup"><span data-stu-id="1d8d7-114">Configure partner applications in Skype for Business Server and Exchange Server</span></span>](configure-partner-applications.md)

[<span data-ttu-id="1d8d7-115">Exchange Server のアーカイブを使用するように Skype for Business Server を構成する</span><span class="sxs-lookup"><span data-stu-id="1d8d7-115">Configure Skype for Business Server to use Exchange Server archiving</span></span>](use-exchange-archiving.md)

[<span data-ttu-id="1d8d7-116">アーカイブされた Skype for Business データを検索するための SharePoint Server の構成</span><span class="sxs-lookup"><span data-stu-id="1d8d7-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)

[<span data-ttu-id="1d8d7-117">統合連絡先ストアを使用するための Skype for Business Server の構成</span><span class="sxs-lookup"><span data-stu-id="1d8d7-117">Configure Skype for Business Server to use the unified contact store</span></span>](use-the-unified-contact-store.md)

[<span data-ttu-id="1d8d7-118">Skype for Business Server で高解像度の写真を使用するように構成する</span><span class="sxs-lookup"><span data-stu-id="1d8d7-118">Configure the use of high-resolution photos in Skype for Business Server</span></span>](high-resolution-photos.md)

[<span data-ttu-id="1d8d7-119">Skype for Business Server ボイスメール用に Exchange Server ユニファイドメッセージングを構成する</span><span class="sxs-lookup"><span data-stu-id="1d8d7-119">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)

[<span data-ttu-id="1d8d7-120">Skype for Business Server と Microsoft Outlook Web App 2013 の統合</span><span class="sxs-lookup"><span data-stu-id="1d8d7-120">Integrating Skype for Business Server and Microsoft Outlook Web App 2013</span></span>](https://technet.microsoft.com/library/513d4cc7-aa87-4f68-b99d-d58b63bdf242.aspx)

[<span data-ttu-id="1d8d7-121">Skype for Business Server のクライアントコンピューターで個人用連絡先ストアを構成する</span><span class="sxs-lookup"><span data-stu-id="1d8d7-121">Configure the personal contacts store on client computers for Skype for Business Server</span></span>](personal-contacts-store.md)

## <a name="see-also"></a><span data-ttu-id="1d8d7-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d8d7-122">See also</span></span>

[<span data-ttu-id="1d8d7-123">Skype for Business と Exchange の統合の計画</span><span class="sxs-lookup"><span data-stu-id="1d8d7-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
