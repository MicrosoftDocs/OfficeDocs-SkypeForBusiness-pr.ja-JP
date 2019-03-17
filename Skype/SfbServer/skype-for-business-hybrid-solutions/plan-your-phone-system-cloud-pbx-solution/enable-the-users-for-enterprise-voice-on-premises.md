---
title: 設置型のエンタープライズ VoIP のユーザーを有効にします。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
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
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: 電話システムを使用して、Office 365 (クラウド PBX) でユーザーが、最初にエンタープライズ VoIP を有効にして、電話番号を割り当てる必要があります。 これを行う設置型展開で、ユーザーのホームでも、設置型の展開を使用しています。
ms.openlocfilehash: 8d00120b0b0fd74baed1ceb003a46cfc2468d502
ms.sourcegitcommit: 7ca7f5cd38742b6a1967bd792113348dfe689850
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "30657448"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="9dbfb-104">設置型のエンタープライズ VoIP のユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="9dbfb-104">Enable the users for Enterprise Voice on premises</span></span>
 
<span data-ttu-id="9dbfb-105">電話システムを使用して、Office 365 (クラウド PBX) でユーザーが、最初にエンタープライズ VoIP を有効にして、電話番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dbfb-105">For a user to use Phone System in Office 365 (Cloud PBX), you must first enable them for Enterprise Voice and assign them a phone number.</span></span> <span data-ttu-id="9dbfb-106">これを行う設置型展開で、ユーザーのホームでも、設置型の展開を使用しています。</span><span class="sxs-lookup"><span data-stu-id="9dbfb-106">You do this using your on-premises deployment while the user is still homed in the on-premises deployment.</span></span>
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a><span data-ttu-id="9dbfb-107">設置型のエンタープライズ VoIP に対してユーザーを有効にすると、電話番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="9dbfb-107">To enable a user for Enterprise Voice on premises and assign a phone number</span></span>

1. <span data-ttu-id="9dbfb-108">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9dbfb-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="9dbfb-109">スタート メニューかデスクトップ ショートカットを使用して、Skype for Business Server のコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9dbfb-109">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="9dbfb-110">また、ブラウザー ウィンドウを開いて管理 URL を入力し、Skype for Business Server のコントロール パネルを開くこともできます。</span><span class="sxs-lookup"><span data-stu-id="9dbfb-110">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="9dbfb-111">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9dbfb-111">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="9dbfb-112">[**ユーザーの検索**] ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か先頭の部分の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9dbfb-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="9dbfb-113">テーブルでは、エンタープライズ VoIP を有効にするオンライン ビジネスのユーザー アカウントの Skype をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9dbfb-113">In the table, click the Skype for Business Online user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="9dbfb-114">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9dbfb-114">On the **Edit** menu, click **Show Details**.</span></span>
    
7. <span data-ttu-id="9dbfb-115">[**テレフォニー**] の [**エンタープライズ VoIP**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9dbfb-115">Under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="9dbfb-p103">[**回線 URI**] をクリックし、正規化された一意の電話番号 (たとえば、tel:+14255550200) を入力して、[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9dbfb-p103">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200). Then click **Commit**.</span></span>
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="9dbfb-118">設置型のエンタープライズ VoIP に対してユーザーを有効にするときに特別な考慮事項</span><span class="sxs-lookup"><span data-stu-id="9dbfb-118">Special considerations when enabling users for Enterprise Voice on premises</span></span>

<span data-ttu-id="9dbfb-119">場合によっては、エンタープライズ VoIP でユーザーを有効にする方法を変更して、ユーザーが正常に発信および受信できることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dbfb-119">In some cases, you may need to modify the way you enable users for Enterprise Voice to make sure that they can successfully make and receive calls.</span></span> <span data-ttu-id="9dbfb-120">次の条件を満たす、展開内のユーザーがある場合は場合、は、エンタープライズ VoIP に対してユーザーを有効にするのには含まれている手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9dbfb-120">If you have users in your deployment that meet the following conditions, perform the steps included to enable the user for Enterprise Voice.</span></span>
  
- <span data-ttu-id="9dbfb-121">設置型で、ユーザーが作成されたかどうかは AD とは、Skype のビジネスやエンタープライズ VoIP に有効にすることがなく、オンライン ビジネスの Skype と同期し、LineURI 設定、影響を受けるユーザーごとの値を置き換えるには、次のコマンドレットを実行する必要はありません <c0 > <b1></b1> 、環境の実際の値とします。</span><span class="sxs-lookup"><span data-stu-id="9dbfb-121">If a user is created in your on-premises AD and then synchronized with Skype for Business Online without being enabled for Skype for Business or for Enterprise Voice and do not have a LineURI set, run the following cmdlets for each affected user, replacing the values in \< \> with actual values for your environment:</span></span>
    
  ```
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="9dbfb-122">ユーザー設置型では、ビジネス用の Skype は既に有効になってくださいが、エンタープライズ VoIP を有効になっているかいたビジネス オンラインの Skype を移動する前に、LineURI を割り当てられている場合、は、ユーザーごとに次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="9dbfb-122">If a user is already enabled for Skype for Business on premises, but was not enabled for Enterprise Voice or assigned a LineURI before being moved to Skype for Business Online, run the following cmdlet for each user:</span></span>
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="9dbfb-123">ユーザーは、社内のビジネスのための Skype で既に有効になってが有効になっていないエンタープライズ VoIP を LineURI を既に割り当てられている場合でも、影響を受けるユーザーごとに次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="9dbfb-123">If a user is already enabled in Skype for Business on premises but not enabled for Enterprise Voice, even if already assigned a LineURI, run the following cmdlet for each affected user:</span></span>
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


