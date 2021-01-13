---
title: Skype for Business を使用してプライベート電話回線を計画する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: Skype for Business Server のプライベート (セカンダリ) 電話回線のエンタープライズ VoIP。
ms.openlocfilehash: 0ae62c4ee56a16583106c89b5ca1b190ee242e2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813597"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a><span data-ttu-id="e0080-103">Skype for Business を使用してプライベート電話回線を計画する</span><span class="sxs-lookup"><span data-stu-id="e0080-103">Plan for private telephone lines with Skype for Business</span></span>
 
<span data-ttu-id="e0080-104">Skype for Business Server のプライベート (セカンダリ) 電話回線のエンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="e0080-104">Planning for private (secondary) telephone lines in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="e0080-105">Skype for Business Server を使用すると、プライマリ電話回線に加えて、2 つ目のプライベート電話回線をユーザーに提供できます。</span><span class="sxs-lookup"><span data-stu-id="e0080-105">Skype for Business Server enables you to give users a second, private telephone line in addition to their primary telephone line.</span></span> <span data-ttu-id="e0080-106">プライベート電話回線は、多くの場合、役員や直接受信できる非公開の電話番号が必要なユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e0080-106">Private telephone lines are often assigned to executives and others who want an unlisted telephone number at which they can be reached directly.</span></span>
  
<span data-ttu-id="e0080-107">プライベート電話回線は、Skype for Business Server 管理シェルでのみ構成できます。</span><span class="sxs-lookup"><span data-stu-id="e0080-107">Private telephone lines can only be configured with the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="e0080-108">Skype for Business Server コントロール パネルを使用してプライベート電話回線を構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="e0080-108">You cannot configure private telephone lines with the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="e0080-109">プライベート電話回線は、Skype for Business Server の展開でのみ構成し、混在展開では構成しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0080-109">Private telephone lines should be configured only in deployments of Skype for Business Server and not in mixed deployments.</span></span>
  
## <a name="characteristics-of-private-telephone-lines"></a><span data-ttu-id="e0080-110">プライベート電話回線の特徴</span><span class="sxs-lookup"><span data-stu-id="e0080-110">Characteristics of Private Telephone Lines</span></span>

<span data-ttu-id="e0080-111">2 つ目のプライベート電話回線の概念は基本的に単純ですが、プライベート回線の特性と、ユーザーのプライマリ電話回線と類似する方法と異なる方法を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="e0080-111">Although the concept of a second, private telephone line is fundamentally simple, it is important to understand the characteristics of private lines and the ways in which they are similar to and different from users' primary telephone lines.</span></span>
  
### <a name="general-characteristics-of-private-telephone-lines"></a><span data-ttu-id="e0080-112">プライベート電話回線の一般的特徴</span><span class="sxs-lookup"><span data-stu-id="e0080-112">General Characteristics of Private Telephone Lines</span></span>

- <span data-ttu-id="e0080-113">ユーザーに割り当てることができるプライベート電話回線は 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="e0080-113">A user can have only one private telephone line.</span></span>
    
- <span data-ttu-id="e0080-114">プライベート電話回線が割り当てられたユーザーには、ボイス メール用メールボックスは 1 つのみ設定され、不在着信通知は 1 つの電子メール アドレスに通知されます。</span><span class="sxs-lookup"><span data-stu-id="e0080-114">A user with a private telephone line has only one voice mailbox and receives missed call notifications at a single email address.</span></span>
    
- <span data-ttu-id="e0080-115">プライベート電話回線が割り当てられたユーザーに、2 番目の SIP アドレスは割り当てられません。また、セカンダリのプライベート電話回線によって、ユーザーにネットワーク上の 2 番目のプレゼンス (2 番目のインスタント メッセージング ID など) は付与されません。</span><span class="sxs-lookup"><span data-stu-id="e0080-115">A user with a private telephone line does not have a second SIP address, and a second, private telephone line does not give a user a second presence on the network (such as a second instant messaging identity).</span></span> 
    
- <span data-ttu-id="e0080-116">プライベート電話回線は、内部設置型展開でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e0080-116">Private telephone lines are available for on-premises deployments only.</span></span> <span data-ttu-id="e0080-117">Skype for Business Server のホスト型展開では使用できません。</span><span class="sxs-lookup"><span data-stu-id="e0080-117">They are not available with hosted deployments of Skype for Business Server.</span></span>
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a><span data-ttu-id="e0080-118">プライベート電話回線とプライマリ電話回線の相違点</span><span class="sxs-lookup"><span data-stu-id="e0080-118">How Private Telephone Lines Differ from Primary Telephone Lines</span></span>

- <span data-ttu-id="e0080-119">プライベート電話回線の電話番号は、電話帳や Active Directory ドメイン サービスから得られる連絡先リストには表示されません。</span><span class="sxs-lookup"><span data-stu-id="e0080-119">The telephone numbers for private telephone lines do not appear in the telephone directories or Contacts lists that are derived from Active Directory Domain Services.</span></span>
    
- <span data-ttu-id="e0080-120">プライベート電話回線では、通話転送、チーム呼び出し、委任、チーム リング、グループ通話ピックアップ、応答グループ アプリケーションの機能は使用できません。</span><span class="sxs-lookup"><span data-stu-id="e0080-120">None of the following features are available with a private telephone line: call forwarding, team call, delegation, team ring, Group Call Pickup, and Response Group application.</span></span>
    
- <span data-ttu-id="e0080-121">プライベート電話回線の呼び出しには特別な呼び出し音が設定され、呼び出しのシステム通知により、プライベート番号に着信通話があることがユーザーに通知されます。</span><span class="sxs-lookup"><span data-stu-id="e0080-121">Calls to a private telephone line have a special ring, and the system notification for the call tells the user that the incoming call is on his or her private line.</span></span>
    
- <span data-ttu-id="e0080-p104">プライベート電話回線の呼び出しは、常に直接行われます。 "応答不可" ルールには従いません。</span><span class="sxs-lookup"><span data-stu-id="e0080-p104">Calls to the private telephone line always ring through. They do not follow "do not disturb" rules.</span></span>
    
- <span data-ttu-id="e0080-124">プライベート電話回線は着信のみで、発信通話に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e0080-124">Private telephone lines are inbound only and cannot be used to make outgoing calls.</span></span> <span data-ttu-id="e0080-125">プライベート電話回線を使用しているユーザーが通話を行う場合、その通話はユーザーのプライマリ電話回線から発信され、ユーザーの名前やユーザーのプライマリ電話番号を呼び出し元から隠すのではありません。</span><span class="sxs-lookup"><span data-stu-id="e0080-125">When a user with a private telephone line makes a call, the call originates from the user's primary telephone line and does not hide the user's name or the user's primary telephone number from the person called.</span></span>
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a><span data-ttu-id="e0080-126">プライベート電話回線とプライマリ電話回線の類似点</span><span class="sxs-lookup"><span data-stu-id="e0080-126">How Private Telephone Lines Are Similar to Primary Telephone Lines</span></span>

- <span data-ttu-id="e0080-127">プライベート電話回線の呼び出しで応答のなかったものは、プライマリ電話回線のものと同じボイス メール用受信ボックス (ボイス メールが有効になっている場合) にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="e0080-127">Unanswered calls to a private telephone line are routed to the same voice mail inbox as for the primary telephone line (if voice mail is enabled).</span></span>
    
- <span data-ttu-id="e0080-128">コール パークとコール ピックアップは、ユーザーのプライマリ電話回線とまったく同じ方法でプライベート電話回線で動作します。</span><span class="sxs-lookup"><span data-stu-id="e0080-128">Call park and call pickup work with private telephone lines in exactly the same manner as they do with the user's primary telephone line.</span></span>
    
- <span data-ttu-id="e0080-129">ユーザーのプライマリ電話回線で同時呼び出しを有効にすると、プライベート電話回線でも有効になります。</span><span class="sxs-lookup"><span data-stu-id="e0080-129">When simultaneous ringing is enabled on a user's primary telephone line, it is also enabled on the private telephone line.</span></span>
    
- <span data-ttu-id="e0080-130">プライベート電話回線の電話番号は、ユーザーのプライマリ電話回線の電話番号と同じ方法で通話詳細レコードに記録されますが、プライベート電話番号として表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0080-130">The telephone number for a private telephone line is recorded in the call detail record in the same manner as the telephone number for a user's primary telephone line, but with an indication that it is a private telephone number.</span></span>
    
- <span data-ttu-id="e0080-131">ユーザーがプライベート電話回線で通話に応答すると、その通話はユーザーのプライマリ電話回線での通話と同じように処理されます。</span><span class="sxs-lookup"><span data-stu-id="e0080-131">After a user answers a call on a private telephone line, the call is treated the same as a call on the user's primary telephone line.</span></span> <span data-ttu-id="e0080-132">たとえば、プライベート電話回線で通話を受信したユーザーが通話を転送したり、他のユーザーを電話会議に招待したりすると、そのユーザーの名前が Skype for Business に表示され、ユーザーのプライマリ電話回線の電話番号が発信者番号に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0080-132">For example, if a user who receives a call on a private telephone line forwards the call or invites others to a conference call, the user's name appears in Skype for Business, and the telephone number for the user's primary telephone line appears in caller ID.</span></span>
    
- <span data-ttu-id="e0080-133">ユーザーは、プライマリ電話回線と同じ方法で、プライベート電話回線からの通話を切り替える (応答する前に、携帯電話や自宅の電話などの別の宛先に通話をリダイレクトする) ことができます。</span><span class="sxs-lookup"><span data-stu-id="e0080-133">A user can deflect a call (redirect the call to another destination, such as a mobile phone or home phone, before answering) from the private telephone line in the same manner as with a primary telephone line.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e0080-134">プライベート番号の呼び出しが別の電話番号にルーティングされた場合、その別の電話番号でプライベート電話回線の電話番号を使用できるようになり、その番号のログを表示できます。</span><span class="sxs-lookup"><span data-stu-id="e0080-134">When a call to a private line is routed to an alternate telephone number, the telephone number for the private telephone line is made available to the alternate telephone number and can be displayed in the logs for that number.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="e0080-135">電話会議からプライベート電話回線への通話では、着信システム通知にプライベート回線は表示しません。</span><span class="sxs-lookup"><span data-stu-id="e0080-135">Calls from a conference to the private telephone line will not have a  *private-line*  indication in the incoming system notification.</span></span>
  
## <a name="administering-private-telephone-lines"></a><span data-ttu-id="e0080-136">プライベート電話回線の管理</span><span class="sxs-lookup"><span data-stu-id="e0080-136">Administering Private Telephone Lines</span></span>

<span data-ttu-id="e0080-p107">プライベート電話回線の作成および管理の技術的な側面に加えて、プライベート電話回線用の回線管理手順を設定する必要があります。これには、組織内のプライベート番号の対象ユーザー向けのポリシーの指定、それらのユーザーとその電話番号の一覧の作成および管理、役員のプライベート電話帳の作成、ユーザー トレーニングの調整、関連する作業などがあります。</span><span class="sxs-lookup"><span data-stu-id="e0080-p107">In addition to the technical aspects of creating and managing private telephone lines, you will need to establish administrative procedures for them. This includes determining policies for who in the organization is eligible for a private line, creating and maintaining lists of people and their telephone lines, possibly creating a private telephone directory for executives, arranging for user training, and related tasks.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e0080-p108">プライベート電話回線は、Active Directory にユーザー オブジェクトの msRTCSIP-PrivateLine 属性として格納されます。既定では、Authenticated Users グループのメンバーは、この属性に対して読み取りアクセスを持ちます。</span><span class="sxs-lookup"><span data-stu-id="e0080-p108">The private telephone line is stored in Active Directory as an msRTCSIP-PrivateLine attribute on the user object. By default any member of the Authenticated Users group has read access to this attribute.</span></span> 
  
### <a name="assigning-telephone-numbers"></a><span data-ttu-id="e0080-141">電話番号の割り当て</span><span class="sxs-lookup"><span data-stu-id="e0080-141">Assigning Telephone Numbers</span></span>

 <span data-ttu-id="e0080-142">プライベート電話回線を必要とする新規ユーザーのアカウントは、Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して、プライベート電話回線のないアカウントと同じ方法で作成されます。</span><span class="sxs-lookup"><span data-stu-id="e0080-142">Accounts for new users who need private telephone lines are created in the same manner as accounts without private telephone lines, using Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="e0080-143">Skype for Business Server 管理シェル で **Set-CsUser** コマンドレットを使用して、ユーザーのプライベート電話回線に電話番号を割り当てる (例: **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**)。</span><span class="sxs-lookup"><span data-stu-id="e0080-143">Use the **Set-CsUser** cmdlet in the Skype for Business Server Management Shell to assign a telephone number to a private telephone line for a user, for example, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span></span>
  
<span data-ttu-id="e0080-144">プライベート電話回線の電話番号は、3 ~ 15 の数字で、先頭に "TEL:" プレフィックスを付けする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0080-144">Telephone numbers for private telephone lines can be between 3 and 15 numbers in length and must be preceded with the "TEL:" prefix.</span></span> <span data-ttu-id="e0080-145">組織で市外局番や国/地域コードに Direct Inward Dialing を使用している場合、その市外局番や国/地域コードを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e0080-145">They can have any area code and any country/region code as long as your organization has direct inward dialing for that area code and country/region code.</span></span> 
  
<span data-ttu-id="e0080-146">コマンドレットと Skype for Business Server 管理シェルの詳細については、Skype for Business Server 管理シェルのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0080-146">For details about cmdlets and Skype for Business Server Management Shell, see the Skype for Business Server Management Shell documentation.</span></span>
  
### <a name="private-telephone-lines-in-mixed-deployments"></a><span data-ttu-id="e0080-147">混在環境におけるプライベート電話回線</span><span class="sxs-lookup"><span data-stu-id="e0080-147">Private Telephone Lines in Mixed Deployments</span></span>

<span data-ttu-id="e0080-148">プライベート電話回線は、Skype for Business Server または Lync Server 2013 の展開にのみ構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0080-148">Private telephone lines should be configured only for deployments of Skype for Business Server or Lync Server 2013.</span></span> <span data-ttu-id="e0080-149">以前のバージョンの Lync Server を実行しているサーバーがある展開では、以前のバージョンのユーザーがプライベート電話回線を呼び出しようとすると、サーバーがプライベート電話回線で番号の逆引き参照を実行できないので、通話のルーティングが失敗します。</span><span class="sxs-lookup"><span data-stu-id="e0080-149">In a deployment in which there are servers running earlier versions of Lync Server, when a user on earlier version attempts to call a private telephone line, routing of the call fails because the server cannot perform a reverse number lookup on a private telephone line.</span></span>
  

