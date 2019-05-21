---
title: Skype for Business Server のオンプレミスの PSTN 接続を使用して、Office 365 で電話システムのユーザーを有効にする
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: このトピックでは、Office 365 の電話システムで、オンプレミスの PSTN 接続を使用してユーザーを有効にする方法について説明します。 このトピックの手順を実行する前に、次の内容を参照してください。
ms.openlocfilehash: c8870cce90963e3a8d4e42de008df3eee779e52a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287462"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="05d86-104">Skype for Business Server のオンプレミスの PSTN 接続を使用して、Office 365 で電話システムのユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="05d86-104">Enable users for Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="05d86-105">このトピックでは、Office 365 の電話システムで、オンプレミスの PSTN 接続を使用してユーザーを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="05d86-105">This topic describes how to enable users for Phone System in Office 365 with on-premises PSTN connectivity.</span></span> <span data-ttu-id="05d86-106">このトピックの手順を実行する前に、次の内容を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05d86-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="05d86-107">ハイブリッド接続のセットアップ方法については、「 [skype For Business server と skype for Business online の間のハイブリッド接続の計画](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)」と「Skype For [Business server と Skype for business online の間にハイブリッド接続を導入](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05d86-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="05d86-108">展開の計画については、「 [Skype For Business Server でオンプレミスの PSTN 接続を使用して Office 365 で電話システムを計画](plan-phone-system-with-on-premises-pstn-connectivity.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05d86-108">To learn about planning your deployment, see [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="05d86-109">ライセンスやプランなど、Office 365 の電話システムの詳細については、「 [Skype For business の PSTN 通話プラン](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05d86-109">To learn more about Phone System in Office 365, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a><span data-ttu-id="05d86-110">オンプレミスの PSTN 接続を使用して、Office 365 の電話システムにユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="05d86-110">Moving users to Phone System in Office 365 with on-premises PSTN connectivity</span></span>

<span data-ttu-id="05d86-111">ユーザーを Skype for business Online に移行する前に、Skype for Business Server または Lync Server 2013 でオンプレミスのユーザーを有効にして、それらをオンラインで移行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="05d86-111">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="05d86-112">詳細については、「 [skype For Business Server と skype For Business Online との間のハイブリッド接続の計画](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)」および「[エンタープライズ voip のユーザーを有効にする](enable-the-users-for-enterprise-voice-on-premises.md)(ユーザーのホームとして実行される)」の「特別な考慮事項」セクションを参照してください。オンプレミス)。</span><span class="sxs-lookup"><span data-stu-id="05d86-112">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span> 
  
<span data-ttu-id="05d86-113">すべてのユーザーは、オンプレミスの Active Directory で作成し、サポートされているバージョンの Azure AD コネクタを使用して Office 365 に同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05d86-113">All users must be created in Active Directory on premises and synchronized to Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="05d86-114">Azure AD で直接作成された Office 365 の電話システムのユーザーを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="05d86-114">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="05d86-115">Azure AD で作成されたユーザーのオンプレミスの PSTN 接続を使用して、Office 365 で電話システムを有効にするには、オンプレミスの AD でそのユーザーの新しいアカウントを作成し、そのアカウントをオンプレミスで構成して、次を使用してアカウントを同期する必要があります。サポートされている Azure AD コネクタツールのバージョン。</span><span class="sxs-lookup"><span data-stu-id="05d86-115">If you want to enable Phone System in Office 365 with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="05d86-116">Office 365 の電話システムでオンプレミスの PSTN 接続を有効にして、そのユーザーを Skype for Business Online に移行するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05d86-116">Enabling a user for Phone System in Office 365 with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="05d86-117">[オンプレミスのエンタープライズボイスのユーザーを有効にする](enable-the-users-for-enterprise-voice-on-premises.md)(ユーザーがオンプレミスでログオンしているときに実行されます)。</span><span class="sxs-lookup"><span data-stu-id="05d86-117">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="05d86-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (ユーザーがオンプレミスに所属している間に実行します)。</span><span class="sxs-lookup"><span data-stu-id="05d86-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="05d86-119">[ユーザーをクラウドと同期し、ライセンスを割り当てる](synchronize-users-to-the-cloud-and-assign-licenses.md)(Office 365 を使用して実行された場合)。</span><span class="sxs-lookup"><span data-stu-id="05d86-119">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="05d86-120">[オンプレミスユーザーを Skype For Business Online に移動する](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online)(オンプレミスの Windows PowerShell を使用して実行しましたが、Office 365 管理者の資格情報を使用します)。</span><span class="sxs-lookup"><span data-stu-id="05d86-120">[Move on-premises users to Skype for Business Online](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="05d86-121">[Office 365 でエンタープライズボイスオンラインおよび電話システムのユーザーを有効にする](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md)(リモート PowerShell を使用して実行されました。</span><span class="sxs-lookup"><span data-stu-id="05d86-121">[Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell.</span></span>
    

