---
title: Skype Room System のハイブリッド展開
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: このトピックでは、ハイブリッド環境で Skype Room System を展開する方法について説明します。
ms.openlocfilehash: 80e7efaf5fe3705e052d40606ea5944527d43a61
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774958"
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="72f27-103">Skype Room System のハイブリッド展開</span><span class="sxs-lookup"><span data-stu-id="72f27-103">Skype Room System hybrid deployments</span></span>

<span data-ttu-id="72f27-104">このトピックでは、ハイブリッド環境で Skype Room System を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="72f27-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="72f27-105">ハイブリッド展開</span><span class="sxs-lookup"><span data-stu-id="72f27-105">Hybrid deployments</span></span>

<span data-ttu-id="72f27-106">トポロジで Skype for Business Server と Exchange Online を使用していて、Exchange Online で Skype Room System リソースメールボックスをホストする場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="72f27-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="72f27-107">またこのセクションでは、Exchange Online と Exchange Server の両方が展開されているハイブリッドのシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="72f27-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="72f27-108">ここでは、LyncSample.com を使って、オンプレミスのドメインとオンラインドメインの LyncSample.ccstp.net を使用しています。</span><span class="sxs-lookup"><span data-stu-id="72f27-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="72f27-109">「Exchange Online のプロビジョニング」で説明されているように、exchange Online Management shell に接続して、exchange 管理センター (LyncSample.ccsctp.net) でリソースメールボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="72f27-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
   ```
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    <span data-ttu-id="72f27-110">Lrstest5@LyncSample.ccsctp.net を使用してログインするには、OWA の接続を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="72f27-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="72f27-111">Office 365 Exchange 管理センターで、メールアドレス lrstest5@LyncSample.com (オンプレミスドメイン) を追加して、それを返信アドレスとして設定します。</span><span class="sxs-lookup"><span data-stu-id="72f27-111">In the Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="72f27-112">オンプレミスの Active Directory ユーザー lrstest5@LyncSample.com を作成し、メールアドレスを lrstest5@LyncSample.com に設定して、ターゲットアドレスを lrstest5@LyncSample.com に設定します。</span><span class="sxs-lookup"><span data-stu-id="72f27-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="72f27-113">同期が完了した後、同期が完了したら、ユーザーが AAD に統合されたことを確認し、Office365 Exchange 管理センターで受信者のリソースのプロパティを変更できないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="72f27-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Office365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="72f27-114">Lrstest5@LyncSample.com を使用して OWA 接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="72f27-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="72f27-115">(以前は、オンラインドメインを使用して OWA 接続を確認していること)。</span><span class="sxs-lookup"><span data-stu-id="72f27-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="72f27-p103">メールボックスを作成した後、Exchange Online 管理シェルで Set-CalendarProcessing を使用してメールボックスを構成できます。詳細については、単一フォレストのオンプレミス展開の手順 3 ～ 6 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72f27-p103">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox. Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="72f27-118">Exchange Server と Exchange Online のハイブリッド環境を使用している場合は、Exchange 管理シェルに移動して、[Box lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="72f27-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="72f27-119">次に、ディレクトリ同期をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="72f27-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="72f27-120">Exchange Online で Skype Room システムメールボックスをホストする場合、これらの Exchange 管理シェルの手順は必要ありません。手順6に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="72f27-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="72f27-121">Skype for business の管理シェルで次のコマンドレットを実行して、skype for Business の Skype Room System アカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="72f27-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="72f27-122">上記のシナリオで Skype for Business Server の代わりに Skype for business Online を使用している場合は、Exchange リソースメールボックスをプロビジョニングした後、「Skype for Business Online のプロビジョニング」で説明されているように、Skype for Business アカウントをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="72f27-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  

