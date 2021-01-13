---
title: Skype Room System のハイブリッド展開
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: このトピックでは、ハイブリッド環境に Skype Room System を展開する方法について説明します。
ms.openlocfilehash: 47be9204155a1ff6cf6e8d9dfa67723a370fec26
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805897"
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="2ea01-103">Skype Room System のハイブリッド展開</span><span class="sxs-lookup"><span data-stu-id="2ea01-103">Skype Room System hybrid deployments</span></span>

<span data-ttu-id="2ea01-104">このトピックでは、ハイブリッド環境に Skype Room System を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ea01-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="2ea01-105">ハイブリッド展開</span><span class="sxs-lookup"><span data-stu-id="2ea01-105">Hybrid deployments</span></span>

<span data-ttu-id="2ea01-106">トポロジに Skype for Business Server と Exchange Online が含まれますが、Exchange Online で Skype Room System リソース メールボックスをホストする場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2ea01-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="2ea01-107">このセクションでは、Exchange Online と Exchange Online の両方を展開するハイブリッド Exchange Serverします。</span><span class="sxs-lookup"><span data-stu-id="2ea01-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="2ea01-108">説明を目的として、オンプレミス ドメインLyncSample.com、オンライン ドメインのLyncSample.ccstp.netを使用します。</span><span class="sxs-lookup"><span data-stu-id="2ea01-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="2ea01-109">「Exchange Online プロビジョニング」の説明に従って Exchange Online 管理シェルに接続して、Exchange 管理センター (LyncSample.ccsctp.net) でリソース メールボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="2ea01-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    <span data-ttu-id="2ea01-110">OWA 接続を確認するには、lrstest5@LyncSample.ccsctp.netを使用します。</span><span class="sxs-lookup"><span data-stu-id="2ea01-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="2ea01-111">Microsoft 365 または Office 365 Exchange 管理センターで、電子メール アドレス lrstest5@LyncSample.com (オンプレム ドメイン) を追加し、返信アドレスとして設定します。</span><span class="sxs-lookup"><span data-stu-id="2ea01-111">In the Microsoft 365 or Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="2ea01-112">事前に Active Directory ユーザー アカウントを作成lrstest5@LyncSample.com電子メール アドレスを lrstest5@LyncSample.com に設定し、ターゲット アドレスを lrstest5@LyncSample.com。</span><span class="sxs-lookup"><span data-stu-id="2ea01-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="2ea01-113">ディレクトリ同期をトリガーし、同期が完了したら、ユーザーが AAD にマージされ、Microsoft 365 または Office 365 Exchange 管理センターで受信者のリソースのプロパティを変更できない点を確認します。</span><span class="sxs-lookup"><span data-stu-id="2ea01-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Microsoft 365 or Office 365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="2ea01-114">次のコマンドを使用して OWA 接続lrstest5@LyncSample.com。</span><span class="sxs-lookup"><span data-stu-id="2ea01-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="2ea01-115">(以前は、オンライン ドメインを使用して OWA 接続を確認しました。)</span><span class="sxs-lookup"><span data-stu-id="2ea01-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="2ea01-116">メールボックスを作成した後、Exchange Online 管理シェルSet-CalendarProcessingを使用してメールボックスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="2ea01-116">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox.</span></span> <span data-ttu-id="2ea01-117">詳細については、「Single Forest On-prem Deployments」の手順 3 . ~ 6. を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ea01-117">Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="2ea01-118">Exchange Server と Exchange Online を使用するハイブリッド環境がある場合は、Exchange 管理シェルに移動し、-RemoteRoutingAddress Enable-RemoteMailbox lrstest5@LyncSample.com -Room lrstest5@LyncSample.mail.ccsctp.netに移動します。</span><span class="sxs-lookup"><span data-stu-id="2ea01-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="2ea01-119">その後、ディレクトリ同期をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="2ea01-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="2ea01-120">Exchange Online で Skype Room System メールボックスをホストする場合、これらの Exchange 管理シェルの手順は必要ありません。手順 6 に進みます。</span><span class="sxs-lookup"><span data-stu-id="2ea01-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="2ea01-121">Skype for Business 管理シェルで次のコマンドレットを実行して、Skype for Business の Skype Room System アカウントを有効にする。</span><span class="sxs-lookup"><span data-stu-id="2ea01-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="2ea01-122">上記のシナリオで Skype for Business Server ではなく Skype for Business Online を使用している場合は、Exchange リソース メールボックスのプロビジョニング後に、Skype for Business Online プロビジョニングの説明に従って Skype for Business アカウントをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="2ea01-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  

