---
title: ユーザー Office 365 の電話システムに Skype で設置した PSTN 接続を持つサーバーで有効にビジネス
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
ms.audience: ITPro
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
description: 'このトピックでは、Office 365 の電話システムの設置の PSTN への接続を持つユーザーを有効にする方法について説明します。 このトピックの手順を実行する前に、以下を参照する必要があります: です。'
ms.openlocfilehash: 7427bf33c275d55b99c240aaf192d180c2d63945
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887403"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="62e35-104">ユーザー Office 365 の電話システムに Skype で設置した PSTN 接続を持つサーバーで有効にビジネス</span><span class="sxs-lookup"><span data-stu-id="62e35-104">Enable users for Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="62e35-105">このトピックでは、Office 365 の電話システムの設置の PSTN への接続を持つユーザーを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="62e35-105">This topic describes how to enable users for Phone System in Office 365 with on-premises PSTN connectivity.</span></span> <span data-ttu-id="62e35-106">このトピックの手順を実行する前に、以下を参照する必要があります: です。</span><span class="sxs-lookup"><span data-stu-id="62e35-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="62e35-107">ハイブリッド接続を設定する方法については、[サーバーのビジネスとオンライン ビジネスの Skype の Skype 間のハイブリッド接続を計画](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)し、[サーバーのビジネスとオンライン ビジネスの Skype の Skype 間のハイブリッド接続の展開](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62e35-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="62e35-108">展開の計画については、 [Skype のビジネス サーバーの PSTN への接続をオンプレミスと Office 365 の電話システムの計画](plan-phone-system-with-on-premises-pstn-connectivity.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62e35-108">To learn about planning your deployment, see [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="62e35-109">ライセンスおよび計画を含む、Office 365 の電話システムの詳細については、 [Skype をビジネスのための計画の PSTN の呼び出し](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62e35-109">To learn more about Phone System in Office 365, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a><span data-ttu-id="62e35-110">Office 365 の電話システムを設置した PSTN 接続を持つユーザーの移動</span><span class="sxs-lookup"><span data-stu-id="62e35-110">Moving users to Phone System in Office 365 with on-premises PSTN connectivity</span></span>

<span data-ttu-id="62e35-111">Skype をビジネス オンラインのユーザーを移動、する前に、ビジネスのサーバーまたは Lync Server 2013 では、Skype での社内ユーザーを有効にするを移動して、オンラインをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="62e35-111">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="62e35-112">詳細については、[サーバーのビジネスとオンライン ビジネスの Skype の Skype の間のハイブリッドの接続を計画](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)し、[設置型のエンタープライズ VoIP に対してユーザーを有効にする](enable-the-users-for-enterprise-voice-on-premises.md)の特別な考慮事項のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="62e35-112">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md).</span></span> 
  
<span data-ttu-id="62e35-113">すべてのユーザーは、オンプレミスの Active Directory で作成したし、Azure AD のコネクタのサポートされているバージョンを使用して Office 365 に同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62e35-113">All users must be created in Active Directory on premises and synchronized to Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="62e35-114">Azure AD で直接作成した Office 365 の電話システムのユーザーを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="62e35-114">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="62e35-115">設置型で、そのユーザー用に新しいアカウントを作成する必要があります Azure AD で作成されたユーザーに PSTN 接続を設置すると Office 365 の電話システムを有効にする場合は、AD は、アカウントの設置型を構成しを使用して、アカウントを同期Azure AD のコネクタ ツールのサポートされているバージョンです。</span><span class="sxs-lookup"><span data-stu-id="62e35-115">If you want to enable Phone System in Office 365 with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="62e35-116">Office 365 の電話システムの設置の PSTN への接続を持つユーザーを有効にして、オンライン ビジネスの Skype に移動して次の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="62e35-116">Enabling a user for Phone System in Office 365 with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="62e35-117">[設置型のエンタープライズ VoIP に対してユーザーを有効にします。](enable-the-users-for-enterprise-voice-on-premises.md)(実行、ユーザーは、ホームの設置型)。</span><span class="sxs-lookup"><span data-stu-id="62e35-117">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="62e35-118">[音声ルーティング ポリシーを割り当てる](assign-a-voice-routing-policy.md)(実行、ユーザーは、ホームの設置型)。</span><span class="sxs-lookup"><span data-stu-id="62e35-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="62e35-119">[同期ユーザーは、クラウドおよび割り当てのライセンス](synchronize-users-to-the-cloud-and-assign-licenses.md)(Office 365 を使用してを実行します。)</span><span class="sxs-lookup"><span data-stu-id="62e35-119">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="62e35-120">[オンプレミス ユーザーがオンライン ビジネスの Skype を移動します。](move-on-premises-users-to-skype-for-business-online.md)(Windows PowerShell の設置を使用していますが、Office 365 管理者の資格情報を使用して実行されます。)</span><span class="sxs-lookup"><span data-stu-id="62e35-120">[Move on-premises users to Skype for Business Online](move-on-premises-users-to-skype-for-business-online.md) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="62e35-121">[ユーザーのエンタープライズ VoIP のオンラインと電話のシステムでは、Office 365 のボイスメールを有効にします。](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md)(実行されるリモート PowerShell を使用する)。</span><span class="sxs-lookup"><span data-stu-id="62e35-121">[Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell).</span></span>
    

