---
title: Skype for Business Server のオンプレミス PSTN 接続を備えた Office 365 の電話システムでユーザーを有効にする
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
description: このトピックでは、オンプレミスの PSTN 接続を備えた Office 365 の電話システムでユーザーを有効にする方法について説明します。 このトピックの手順を実行する前に、次の内容を確認する必要があります。
ms.openlocfilehash: 87dcafcfe0c5ce69bcdbcd9809d23cea80c234ba
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050189"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="462c4-104">Skype for Business Server のオンプレミス PSTN 接続を備えた Office 365 の電話システムでユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="462c4-104">Enable users for Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="462c4-105">このトピックでは、オンプレミスの PSTN 接続を備えた Office 365 の電話システムでユーザーを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="462c4-105">This topic describes how to enable users for Phone System in Office 365 with on-premises PSTN connectivity.</span></span> <span data-ttu-id="462c4-106">このトピックの手順を実行する前に、次の内容を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="462c4-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="462c4-107">ハイブリッド接続をセットアップする方法については、「skype [for Business server と skype for Business online の間のハイブリッド接続を計画](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)する」および「Skype For [Business server と Skype for business online 間のハイブリッド接続を展開](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="462c4-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="462c4-108">展開の計画については、「 [Plan Phone System In Office 365 with ON-PREMISES PSTN connectivity In Skype For Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="462c4-108">To learn about planning your deployment, see [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="462c4-109">ライセンスとプランを含む Office 365 の電話システムの詳細については、「 [Skype For business の PSTN 通話プラン](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="462c4-109">To learn more about Phone System in Office 365, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a><span data-ttu-id="462c4-110">オンプレミスの PSTN 接続を備えた Office 365 の電話システムへのユーザーの移動</span><span class="sxs-lookup"><span data-stu-id="462c4-110">Moving users to Phone System in Office 365 with on-premises PSTN connectivity</span></span>

<span data-ttu-id="462c4-111">ユーザーを Skype for Business Online に移行する前に、Skype for business Server または Lync Server 2013 でユーザーをオンプレミスで有効にしてから、それらをオンラインに移行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="462c4-111">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="462c4-112">詳細については、「 [Enable The Enterprise Voice on on-premises](enable-the-users-for-enterprise-voice-on-premises.md) (ユーザーがオンプレミスに所属している間に実行されます)」の「 [Skype for Business Server と Skype for business Online の間のハイブリッド接続を計画](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)する」および「特別な考慮事項」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="462c4-112">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span> 
  
<span data-ttu-id="462c4-113">すべてのユーザーをオンプレミスの Active Directory で作成し、サポートされているバージョンの Azure AD Connector を使用して Office 365 に同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="462c4-113">All users must be created in Active Directory on premises and synchronized to Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="462c4-114">Office 365 の電話システムでは、Azure AD で直接作成されたユーザーを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="462c4-114">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="462c4-115">Azure AD で作成したユーザーに対してオンプレミスの PSTN 接続を備えた Office 365 の電話システムを有効にするには、オンプレミスの AD でそのユーザーの新しいアカウントを作成し、オンプレミスのアカウントを構成して、を使用してアカウントを同期する必要があります。Azure AD コネクタツールのサポートされているバージョン。</span><span class="sxs-lookup"><span data-stu-id="462c4-115">If you want to enable Phone System in Office 365 with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="462c4-116">オンプレミスの PSTN 接続を使用して Office 365 の電話システムに対してユーザーを有効にし、それを Skype for Business Online に移動するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="462c4-116">Enabling a user for Phone System in Office 365 with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="462c4-117">[エンタープライズ voip オンプレミスのユーザーを有効](enable-the-users-for-enterprise-voice-on-premises.md)にします (ユーザーがオンプレミスに所属している間に実行されます)。</span><span class="sxs-lookup"><span data-stu-id="462c4-117">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="462c4-118">[音声ルーティングポリシーを割り当て](assign-a-voice-routing-policy.md)ます (ユーザーがオンプレミスに所属している間に実行されます)。</span><span class="sxs-lookup"><span data-stu-id="462c4-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="462c4-119">[ユーザーをクラウドに同期し、ライセンスを割り当て](synchronize-users-to-the-cloud-and-assign-licenses.md)ます (Office 365 を使用して実行します)。</span><span class="sxs-lookup"><span data-stu-id="462c4-119">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="462c4-120">オンプレミスの[ユーザーを Skype For Business Online に移動](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online)します (社内で Windows PowerShell を使用して実行しますが、Office 365 管理者の資格情報を使用します)。</span><span class="sxs-lookup"><span data-stu-id="462c4-120">[Move on-premises users to Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="462c4-121">Office 365 ボイスメール (リモート PowerShell を使用して実行される)[のエンタープライズ voip オンラインおよび電話システムでユーザーを有効に](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md)します。</span><span class="sxs-lookup"><span data-stu-id="462c4-121">[Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell.</span></span>
    

