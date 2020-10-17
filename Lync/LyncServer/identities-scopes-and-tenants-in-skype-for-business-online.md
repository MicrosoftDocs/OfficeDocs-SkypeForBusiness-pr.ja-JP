---
title: Skype for Business Online の id、スコープ、およびテナント
description: Skype for Business Online の id、スコープ、およびテナント。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00ab84c3ca83dea2e328315ae7e616ad7830c227
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552513"
---
# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a><span data-ttu-id="6b3ae-103">Skype for Business Online の id、スコープ、およびテナント</span><span class="sxs-lookup"><span data-stu-id="6b3ae-103">Identities, scopes, and tenants in Skype for Business Online</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b3ae-104">_**トピックの最終更新日:** 2015-03-09_</span><span class="sxs-lookup"><span data-stu-id="6b3ae-104">_**Topic Last Modified:** 2015-03-09_</span></span>

<span data-ttu-id="6b3ae-105">Skype for Business Online を管理するために使用されている Windows PowerShell コマンドレットの多くは、管理しようとしているアイテムについて明確にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-105">Many of the Windows PowerShell cmdlets used to manage Skype for Business Online require you to be very specific about the item that you are trying to manage.</span></span> <span data-ttu-id="6b3ae-106">たとえば、 [Csuser acp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) コマンドレットを実行するときは、管理するユーザーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-106">For example, when you run the [Set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) cmdlet, you must indicate which user you are trying to manage.</span></span> <span data-ttu-id="6b3ae-107">これは、理にかなっています。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-107">This makes sense.</span></span> <span data-ttu-id="6b3ae-108">コマンドレットに管理するユーザーアカウントを特に指定しない限り、ユーザーの電話会議情報をどのユーザーに対して変更する必要があるか **は、このコマンドレットに** はわかりません。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-108">Unless you specifically tell the cmdlet which user account to manage, the **Set-CsUserAcp** cmdlet has no idea which user’s audio conferencing information should be modified.</span></span> <span data-ttu-id="6b3ae-109">このため、 **Set-CsUserAcp** コマンドレットを実行するたびに、identity パラメーターを含める必要があります。その後に、変更するユーザーアカウントの id を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-109">For this reason, each time you run the **Set-CsUserAcp** cmdlet, you’ll need to include the Identity parameter, followed by the Identity of the user account to be modified:</span></span>

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

<span data-ttu-id="6b3ae-110">用語 *id* が常にユーザーアカウントの id を参照している場合、混乱が生じることはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-110">If the term *Identity* always referred to the Identity of a user account, there would be little cause for confusion.</span></span> <span data-ttu-id="6b3ae-111">ユーザー (ユーザー、連絡先など) を扱う場合、Id は個別のユーザーを参照します。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-111">When you are dealing with people (users, contacts, and so on), Identities refer to the individual users themselves.</span></span> <span data-ttu-id="6b3ae-112">ただし、ユーザーアカウント以外のアイテムにも Id があります。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-112">However, items other than user accounts also have Identities.</span></span> <span data-ttu-id="6b3ae-113">Skype for Business Online サービスのコンポーネント (ポリシー、構成設定など) を処理している場合は、用語 Id は、多少異なるものになります。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-113">When you are dealing with components of the Skype for Business Online service—policies, configuration settings, and so on—the term Identity means something slightly different.</span></span> <span data-ttu-id="6b3ae-114">たとえば、次のコマンドを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-114">For example, consider this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="6b3ae-115">この例では、Id "global" は会議の構成設定の範囲を参照します。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-115">In this case, the Identity "global" refers to the scope of the meeting configuration settings.</span></span> <span data-ttu-id="6b3ae-116">*Scope* は、管理の球体を指定するために Skype For business Online (および Lync Server) で使用される用語です。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-116">*Scope* is a term used in Skype for Business Online (and in Lync Server) to designate spheres of management.</span></span> <span data-ttu-id="6b3ae-117">既定では、ポリシーと設定は常にグローバルスコープになります。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-117">By default, policies and settings always have a global scope.</span></span> <span data-ttu-id="6b3ae-118">最初に Skype for Business Online アカウントをセットアップすると、グローバルなポリシーと設定のコレクション (グローバルな会議の構成設定、グローバル外部アクセスポリシー、グローバルなダイヤルプランなど) が既定で作成されます。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-118">When you first set up your Skype for Business Online account you'll have, by default, a collection of global policies and settings—global meeting configuration settings, a global external access policy, a global dial plan, and so on.</span></span>

<span data-ttu-id="6b3ae-119">これらのグローバルポリシーと設定は、Microsoft Lync Server 2010 で導入されました。すべてのユーザーとすべてのコンポーネントを常に管理することができるようにします。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-119">These global policies and settings were introduced in Microsoft Lync Server 2010 to help ensure that all users and all components would always, in some way, be managed.</span></span> <span data-ttu-id="6b3ae-120">これは、Microsoft Office Communicator 2007 R2 では必ずしも当てはまりません。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-120">This was not necessarily true in Microsoft Office Communicator 2007 R2.</span></span> <span data-ttu-id="6b3ae-121">システムにアクセスした方法によっては、ほぼ管理されていない状態になる可能性があります (多くの場合、グループポリシーをユーザーアカウントに適用できないため)。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-121">Depending on how you accessed the system, you could potentially end up in a largely unmanaged state (typically, because Group Policy could not be applied to your user account).</span></span> <span data-ttu-id="6b3ae-122">一方、Lync Server と Skype for Business Online では、管理されていないものはありません。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-122">In contrast, in Lync Server and in Skype for Business Online, nothing is ever left unmanaged.</span></span> <span data-ttu-id="6b3ae-123">これは、他のすべての代わりに、グローバルポリシーと設定が常に適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-123">This is because, in lieu of anything else, global policies and settings will always be enforced.</span></span>

<span data-ttu-id="6b3ae-124">「Else」とは何を意味していますか?</span><span class="sxs-lookup"><span data-stu-id="6b3ae-124">What do we mean by "in lieu of anything else"?</span></span> <span data-ttu-id="6b3ae-125">Skype for Business Online の場合、 *タグのスコープ*または管理の球体でポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-125">Well, in the case of Skype for Business Online, it’s possible to create policies at the *tag scope*, or sphere of management.</span></span> <span data-ttu-id="6b3ae-126">タグスコープ ( *ユーザーごとのスコープ*とも呼ばれる) で作成されたポリシーは、グローバルスコープで作成されたポリシーより優先されます。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-126">Policies created at the tag scope (also known as *the per-user scope*) take priority over policies created at the global scope.</span></span> <span data-ttu-id="6b3ae-127">言い換えると、ユーザーごとのポリシーは常にグローバルポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-127">In other words, a per-user policy will always take precedence over a global policy.</span></span> <span data-ttu-id="6b3ae-128">たとえば、2つの外部ユーザーアクセスポリシーがあるとします。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-128">For example, you might have two external user access policies.</span></span> <span data-ttu-id="6b3ae-129">グローバルポリシーにより、ユーザーは、パブリックインスタントメッセージング (IM) プロバイダー (Windows Live など) のアカウントを持つユーザーと通信することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-129">The global policy prohibits users from communicating with people who have accounts on public instant messaging (IM) providers, such as Windows Live.</span></span> <span data-ttu-id="6b3ae-130">ユーザーごとのポリシーである AllowPublicIMCommunication は、パブリック IM プロバイダーとの通信を可能にします。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-130">The per-user policy, AllowPublicIMCommunication, allows communication with public IM providers.</span></span>

<span data-ttu-id="6b3ae-131">また、Ken Myer と Pilar Ackerman という2人のユーザーがいる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-131">You might also have two users: Ken Myer and Pilar Ackerman.</span></span> <span data-ttu-id="6b3ae-132">Ken Myer には、ユーザーごとのポリシーが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-132">Ken Myer has been assigned the per-user policy.</span></span> <span data-ttu-id="6b3ae-133">Pilar Ackerman にはユーザーごとのポリシーが割り当てられていません。つまり、彼女はグローバル外部アクセスポリシーによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-133">Pilar Ackerman has not been assigned a per-user policy; that is, she is managed by the global external access policy.</span></span> <span data-ttu-id="6b3ae-134">次の表は、パブリック IM プロバイダーと通信できるユーザー (ある場合) を示しています。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-134">The following table shows which user (if any) can communicate with public IM providers:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6b3ae-135">ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="6b3ae-135">Policy Settings</span></span></th>
<th><span data-ttu-id="6b3ae-136">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="6b3ae-136">Ken Myer</span></span></th>
<th><span data-ttu-id="6b3ae-137">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="6b3ae-137">Pilar Ackerman</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6b3ae-138">パブリック IM プロバイダーのグローバルポリシー設定</span><span class="sxs-lookup"><span data-stu-id="6b3ae-138">Global policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="6b3ae-139">いいえ</span><span class="sxs-lookup"><span data-stu-id="6b3ae-139">No</span></span></p></td>
<td><p><span data-ttu-id="6b3ae-140">いいえ</span><span class="sxs-lookup"><span data-stu-id="6b3ae-140">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b3ae-141">パブリック IM プロバイダーのユーザーごとのポリシー設定</span><span class="sxs-lookup"><span data-stu-id="6b3ae-141">Per-user policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="6b3ae-142">必要</span><span class="sxs-lookup"><span data-stu-id="6b3ae-142">Yes</span></span></p></td>
<td><p><span data-ttu-id="6b3ae-143">いいえ</span><span class="sxs-lookup"><span data-stu-id="6b3ae-143">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b3ae-144">ユーザーがパブリック IM プロバイダーと通信できる</span><span class="sxs-lookup"><span data-stu-id="6b3ae-144">User can communicate with public IM providers</span></span></p></td>
<td><p><span data-ttu-id="6b3ae-145">必要</span><span class="sxs-lookup"><span data-stu-id="6b3ae-145">Yes</span></span></p></td>
<td><p><span data-ttu-id="6b3ae-146">いいえ</span><span class="sxs-lookup"><span data-stu-id="6b3ae-146">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6b3ae-147">ご覧のとおり、Ken Myer はパブリック IM プロバイダーと通信することができます。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-147">As you can see, Ken Myer is allowed to communicate with public IM providers.</span></span> <span data-ttu-id="6b3ae-148">これは、ユーザーごとに割り当てられたポリシーの設定がグローバルポリシーの設定より優先されるためです。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-148">This is because the settings in the per-user policy assigned to him override the settings in the global policy.</span></span> <span data-ttu-id="6b3ae-149">Pilar Ackerman はパブリック IM プロバイダーと通信できません。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-149">Pilar Ackerman cannot communicate with public IM providers.</span></span> <span data-ttu-id="6b3ae-150">これは、グローバルポリシーによって管理されているため、グローバルポリシーによってそのような通信が禁止されるためです。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-150">This is because she is managed by the global policy, and the global policy prohibits such communications.</span></span>

<span data-ttu-id="6b3ae-151">Microsoft サポートによって、ユーザーごとのポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-151">Per-user policies must be created for you by Microsoft Support.</span></span> <span data-ttu-id="6b3ae-152">ポリシーが作成されたら、適切な **付与** されたコマンドレット (たとえば、 [get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)) を使用して、ポリシーをユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-152">After the policies are created, you can then assign them to users by using the appropriate **Grant-Cs** cmdlet (for example, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)).</span></span> <span data-ttu-id="6b3ae-153">ポリシーの Id は常にタグ **プレフィックス**で始まるため、ユーザーごとのポリシーは簡単に識別できます。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-153">Per-user policies are easy to identify because the policy Identity always begins with the tag **prefix**.</span></span> <span data-ttu-id="6b3ae-154">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-154">For example:</span></span>

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> <span data-ttu-id="6b3ae-155">タグ <STRONG>プレフィックス</STRONG> の日付は、Lync Server 2010 の早期の開発日に戻されます。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-155">The tag <STRONG>prefix</STRONG> dates back to the early development days of Lync Server 2010.</span></span> <span data-ttu-id="6b3ae-156">このような場合、ユーザーごとのポリシーは <EM>タグポリシー</EM> と呼ばれ、タグの <STRONG>プレフィックス</STRONG>によって識別されていました。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-156">In those days, per-user policies were referred to as <EM>tag policies</EM> and were identified by the tag <STRONG>prefix</STRONG>.</span></span> <span data-ttu-id="6b3ae-157">これらのポリシーは、 <EM>ユーザーごとのポリシー</EM>としてより正確に参照されるようになり、タグの範囲は <EM>ユーザー単位のスコープ</EM>としてより正確に参照されます。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-157">These policies are now more accurately referred to as <EM>per-user policies</EM>, and the tag scope is more accurately referred to as the <EM>per-user scope</EM>.</span></span> <span data-ttu-id="6b3ae-158">ただし、技術的な理由から、タグの <STRONG>プレフィックス</STRONG> は変更されていません。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-158">However, for technical reasons, the tag <STRONG>prefix</STRONG> was never changed.</span></span>



</div>

<span data-ttu-id="6b3ae-159">Skype for Business Online および Windows PowerShell の使用時に使用されるもう1つの重要な用語は *テナント*です。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-159">Another key term used when working with Skype for Business Online and Windows PowerShell is *tenant*.</span></span> <span data-ttu-id="6b3ae-160">Skype for Business Online アカウントをセットアップすると、新しい展開には、次のようなグローバル一意識別子 (GUID) を持つテナント ID 番号が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-160">When you set up a Skype for Business Online account, your new deployment is assigned a tenant ID number, which is a globally unique identifier (GUID) similar to this:</span></span>

    bf19b7db-6960-41e5-a139-2aa373474354

<span data-ttu-id="6b3ae-161">いくつかの Skype for Business Online コマンドレットでは、コマンドレットを実行するたびに、テナント ID を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-161">A few of the Skype for Business Online cmdlets require you to enter the tenant ID whenever you run the cmdlet.</span></span> <span data-ttu-id="6b3ae-162">テナント ID は、1つのテナントにログオンしている場合でも、1つのテナントに対してのみ入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-162">You must enter the tenant ID even if you have logged on to, and only have, one tenant.</span></span> <span data-ttu-id="6b3ae-163">さいわい、テナント ID を記憶する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-163">Fortunately, you do not have to memorize the tenant ID.</span></span> <span data-ttu-id="6b3ae-164">テナント ID は、次の Windows PowerShell コマンドを実行することによって、いつでも取得できます。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-164">You can retrieve your tenant ID at any time by running the following Windows PowerShell command:</span></span>

    Get-CsTenant | Select-Object TenantId

<span data-ttu-id="6b3ae-165">当然ですが、グローバルスコープとユーザーごとのスコープ (またはタグのスコープ) の違いについては、半分の戦いに過ぎません。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-165">Of course, knowing things such as the difference between the global scope and the per-user scope (or the tag scope) is only half the battle.</span></span> <span data-ttu-id="6b3ae-166">また、どのような場合でも、これらの範囲を使用できるかどうかを知ることが重要です。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-166">It’s also important to know when (or even if) you can use these scopes.</span></span> <span data-ttu-id="6b3ae-167">Identity と tenant パラメーターにも同じことが当てはまります。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-167">The same is true for Identities and the tenant parameter.</span></span> <span data-ttu-id="6b3ae-168">次のトピックでは、さまざまな Skype for Business Online コマンドレットが Id、範囲、およびテナントパラメーターを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b3ae-168">The following topics describe how the different Skype for Business Online cmdlets use Identities, scopes, and the tenant parameter:</span></span>

  - [<span data-ttu-id="6b3ae-169">グローバルスコープのみを使用する Skype for Business Online のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="6b3ae-169">Cmdlets in Skype for Business Online that use only the global scope</span></span>](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [<span data-ttu-id="6b3ae-170">グローバルスコープとタグスコープを使用する Skype for Business Online のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="6b3ae-170">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [<span data-ttu-id="6b3ae-171">ユーザー id を使用する Skype for Business Online のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="6b3ae-171">Cmdlets in Skype for Business Online that use a user identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [<span data-ttu-id="6b3ae-172">ユーザー id とタグスコープを使用する Skype for Business Online のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="6b3ae-172">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [<span data-ttu-id="6b3ae-173">テナントパラメーターを使用する Skype for Business Online のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="6b3ae-173">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [<span data-ttu-id="6b3ae-174">電話会議プロバイダーの id を使用する Skype for Business Online のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="6b3ae-174">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [<span data-ttu-id="6b3ae-175">スコープまたは id を使用しない Skype for Business Online のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="6b3ae-175">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

