---
title: Skype Room System のハイブリッド展開
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: ハイブリッド環境で Skype ルームのシステムを展開する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: 40cbcd7cd95b6a5dc7542f913fe7599bedc7eb85
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699673"
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="f9043-103">Skype Room System のハイブリッド展開</span><span class="sxs-lookup"><span data-stu-id="f9043-103">Skype Room System hybrid deployments</span></span>

<span data-ttu-id="f9043-104">ハイブリッド環境で Skype ルームのシステムを展開する方法の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9043-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="f9043-105">ハイブリッド展開</span><span class="sxs-lookup"><span data-stu-id="f9043-105">Hybrid deployments</span></span>

<span data-ttu-id="f9043-106">トポロジでは、Skype を持つビジネス サーバーおよび Exchange Online では、Exchange Online で Skype ルームのシステム リソースのメールボックスをホストする場合は、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f9043-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="f9043-107">またこのセクションでは、Exchange Online と Exchange Server の両方が展開されているハイブリッドのシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f9043-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="f9043-108">、例示目的でオンラインのドメインのドメインの設置と LyncSample.ccstp.net の LyncSample.com を使用します。</span><span class="sxs-lookup"><span data-stu-id="f9043-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="f9043-109">Exchange のオンラインでの準備の説明に従ってオンラインでの Exchange 管理シェルに接続することによって、Exchange 管理センター (LyncSample.ccsctp.net) でリソース メールボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="f9043-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
   ```
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    <span data-ttu-id="f9043-110">ログに記録する lrstest5@LyncSample.ccsctp.net を使用して OWA の接続を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f9043-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="f9043-111">Office 365 の Exchange 管理センターで、電子メールのアドレス lrstest5@LyncSample.com (prem のドメイン) を追加し、返信アドレスとして設定します。</span><span class="sxs-lookup"><span data-stu-id="f9043-111">In the Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="f9043-112">Prem で Active Directory のユーザー lrstest5@LyncSample.com を作成、lrstest5@LyncSample.com に電子メール アドレスの設定し、ターゲット アドレスを lrstest5@LyncSample.com に設定します。</span><span class="sxs-lookup"><span data-stu-id="f9043-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="f9043-113">ディレクトリの同期をトリガーし、同期が完了した後ことを確認ユーザーが AAD でマージする Office365 Exchange 管理センターでの受信者のリソースのプロパティを変更することがないこと。</span><span class="sxs-lookup"><span data-stu-id="f9043-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Office365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="f9043-114">Lrstest5@LyncSample.com を使用して OWA の接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="f9043-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="f9043-115">(以前のバージョンでは、することを確認、オンラインのドメインを使用して OWA 接続。)</span><span class="sxs-lookup"><span data-stu-id="f9043-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="f9043-p103">メールボックスを作成した後、Exchange Online 管理シェルで Set-CalendarProcessing を使用してメールボックスを構成できます。詳細については、単一フォレストのオンプレミス展開の手順 3 ～ 6 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9043-p103">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox. Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="f9043-118">Exchange Server および Exchange Online を使用して、ハイブリッド環境を使っている場合に、Exchange 管理シェルと有効にする RemoteMailbox の lrstest5@LyncSample.com ・ RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net ・ ルーム。</span><span class="sxs-lookup"><span data-stu-id="f9043-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="f9043-119">ディレクトリ同期をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="f9043-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="f9043-120">オンライン Exchange Skype ルームのシステム メールボックスをホストする場合は、Exchange 管理シェルの手順は必須ではありませんし、手順 6 に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="f9043-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="f9043-121">Skype のビジネス管理シェルの次のコマンドレットを実行して、ビジネスの Skype の Skype ルームのシステム アカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f9043-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="f9043-122">あれば Skype の Skype ではなくビジネス オンライン ビジネス サーバーの上記のシナリオは、Exchange リソース メールボックスをプロビジョニングした後、Skype のビジネスのオンライン提供、Skype で説明したようにビジネス アカウントを準備します。</span><span class="sxs-lookup"><span data-stu-id="f9043-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  

