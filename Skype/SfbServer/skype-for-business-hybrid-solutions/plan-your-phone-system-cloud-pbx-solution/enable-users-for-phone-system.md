---
title: Skype for Business Server でオンプレミス PSTN 接続を使用して電話システムのユーザーを有効にする
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: このトピックでは、オンプレミスの PSTN 接続を使用して電話システムのユーザーを有効にする方法について説明します。 このトピックの手順を実行する前に、次の内容を読む必要があります。
ms.openlocfilehash: 0a843b49546bfc5451197a3ef8ca48799c194731
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120869"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="a7f58-104">Skype for Business Server でオンプレミス PSTN 接続を使用して電話システムのユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="a7f58-104">Enable users for Phone System with on-premises PSTN connectivity in Skype for Business Server</span></span>

<span data-ttu-id="a7f58-105">このトピックでは、オンプレミスの PSTN 接続を使用して電話システムのユーザーを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a7f58-105">This topic describes how to enable users for Phone System with on-premises PSTN connectivity.</span></span> <span data-ttu-id="a7f58-106">このトピックの手順を実行する前に、次の内容を読む必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7f58-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="a7f58-107">ハイブリッド接続をセットアップする方法については [、「Skype for Business Server](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) と Skype for Business Online のハイブリッド接続を計画する」および [「Skype for](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)Business Server と Skype for Business Online のハイブリッド接続を展開する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7f58-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).</span></span>
    
- <span data-ttu-id="a7f58-108">展開の計画の詳細については、「Skype for Business Server でオンプレミス PSTN 接続を使用して電話システムを計画 [する」を参照してください](plan-phone-system-with-on-premises-pstn-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="a7f58-108">To learn about planning your deployment, see [Plan Phone System with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="a7f58-109">ライセンスとプランを含む電話システムの詳細については [、「SKYPE for Business の PSTN 通話プラン」を参照してください](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)。</span><span class="sxs-lookup"><span data-stu-id="a7f58-109">To learn more about Phone System, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
> [!Important]
> <span data-ttu-id="a7f58-110">Skype for Business Online は 2021 年 7 月 31 日に廃止され、その後サービスにアクセスできなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a7f58-110">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="a7f58-111">さらに、Skype for Business Server または Cloud Connector Edition と Skype for Business Online を介したオンプレミス環境間の PSTN 接続はサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a7f58-111">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="a7f58-112">直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。</span><span class="sxs-lookup"><span data-stu-id="a7f58-112">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a><span data-ttu-id="a7f58-113">オンプレミス PSTN 接続を使用してユーザーを電話システムに移動する</span><span class="sxs-lookup"><span data-stu-id="a7f58-113">Moving users to Phone System with on-premises PSTN connectivity</span></span>

<span data-ttu-id="a7f58-114">ユーザーを Skype for Business Online に移行する前に、Skype for Business Server または Lync Server 2013 でオンプレミスのユーザーを有効にしてから、それらをオンラインに移動してください。</span><span class="sxs-lookup"><span data-stu-id="a7f58-114">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="a7f58-115">詳細については [、「Skype for Business Server](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) と Skype for Business Online 間のハイブリッド接続を計画する」および「オンプレミスの [エンタープライズ VoIP](enable-the-users-for-enterprise-voice-on-premises.md) のユーザーを有効にする (ユーザーがオンプレミスに接続されている間に実行される)」の特別な考慮事項セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7f58-115">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span> 
  
<span data-ttu-id="a7f58-116">すべてのユーザーをオンプレミスの Active Directory で作成し、サポートされているバージョンの Azure AD Connector を使用して Microsoft 365 または Office 365 に同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7f58-116">All users must be created in Active Directory on premises and synchronized to Microsoft 365 or Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="a7f58-117">Azure 365 で直接作成された Office 365 で電話システムのユーザーを有効AD。</span><span class="sxs-lookup"><span data-stu-id="a7f58-117">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="a7f58-118">Azure AD で作成されたユーザーに対してオンプレミス PSTN 接続を使用して電話システムを有効にする場合は、オンプレミス AD でそのユーザーの新しいアカウントを作成し、オンプレミスでアカウントを構成し、サポートされているバージョンの Azure AD Connector ツールを使用してアカウントを同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7f58-118">If you want to enable Phone System with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="a7f58-119">オンプレミスの PSTN 接続を使用して電話システムのユーザーを有効にしてから、Skype for Business Online に移動するには、次の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="a7f58-119">Enabling a user for Phone System with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="a7f58-120">[ユーザーがオンプレミスにエンタープライズ VoIPを有効にする](enable-the-users-for-enterprise-voice-on-premises.md) (ユーザーがオンプレミスに設定されている間に実行されます)。</span><span class="sxs-lookup"><span data-stu-id="a7f58-120">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="a7f58-121">[音声ルーティング ポリシーを割り当てる](assign-a-voice-routing-policy.md) (ユーザーがオンプレミスに接続されている間に実行されます)。</span><span class="sxs-lookup"><span data-stu-id="a7f58-121">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="a7f58-122">[ユーザーをクラウドに同期し、ライセンスを割り当てる](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) (Office 365 を使用して実行)。</span><span class="sxs-lookup"><span data-stu-id="a7f58-122">[Synchronize users to the cloud and assign licenses](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) (performed using Office 365).</span></span>
    
- <span data-ttu-id="a7f58-123">[オンプレミス のユーザーを Skype for Business Online](../../../SfbHybrid/hybrid/move-users-from-on-premises-to-skype-for-business-online.md) に移動します (Windows PowerShellを使用して実行しますが、365 管理者の資格情報Office使用します)。</span><span class="sxs-lookup"><span data-stu-id="a7f58-123">[Move on-premises users to Skype for Business Online](../../../SfbHybrid/hybrid/move-users-from-on-premises-to-skype-for-business-online.md) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="a7f58-124">[オンラインおよび電話システムボイスエンタープライズ VoIPユーザーを有効にする](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (リモート PowerShell を使用して実行)。</span><span class="sxs-lookup"><span data-stu-id="a7f58-124">[Enable users for Enterprise Voice online and Phone System Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell.</span></span>
