---
title: 'Lync Server 2013: ホストボイスメールに対してユーザーを有効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for hosted voice mail
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413062(v=OCS.15)
ms:contentKeyID: 48185919
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7287f31a4dc0e43b0108ce666e9c65f51f75f2d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046660"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a><span data-ttu-id="494a7-102">Lync Server 2013 でホストボイスメールに対してユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="494a7-102">Enable users for hosted voice mail in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="494a7-103">_**トピックの最終更新日:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="494a7-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="494a7-104">手順に従い、hosted Exchange ユニファイドメッセージング (UM) サービスで Lync Server 2013 ユーザーのボイスメールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="494a7-104">Follow the procedure to enable Lync Server 2013 users for voice mail on a hosted Exchange Unified Messaging (UM) service.</span></span>

<span data-ttu-id="494a7-105">詳細については、「計画」のドキュメントの「 [Hosted Exchange user management In Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="494a7-105">For details, see [Hosted Exchange user management in Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="494a7-106">[Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser)コマンドレットの詳細については、「Lync Server Management Shell」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="494a7-106">For details about the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="494a7-107">ホストボイスメールに対して Lync Server 2013 ユーザーを有効にするには、そのユーザーアカウントに適用するホストボイスメールポリシーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="494a7-107">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to their user account must be deployed.</span></span> <span data-ttu-id="494a7-108">詳細については、「 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 のホストボイスメールポリシー</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="494a7-108">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a><span data-ttu-id="494a7-109">ホストボイスメールに対してユーザーを有効にするには</span><span class="sxs-lookup"><span data-stu-id="494a7-109">To enable users for hosted voice mail</span></span>

1.  <span data-ttu-id="494a7-110">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="494a7-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="494a7-111">ホストボイスメール用のユーザーアカウントを構成するには、Set-CsUser コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="494a7-111">Run the Set-CsUser cmdlet to configure the user account for hosted voice mail.</span></span> <span data-ttu-id="494a7-112">たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="494a7-112">For example, run:</span></span>
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    <span data-ttu-id="494a7-113">上述の例では、次のパラメーターが設定されます。</span><span class="sxs-lookup"><span data-stu-id="494a7-113">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="494a7-114">**HostedVoiceMail**では、ユーザーのボイスメール呼び出しを、ホストされた Exchange UM にルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="494a7-114">**HostedVoiceMail** enables a user’s voice mail calls to be routed to hosted Exchange UM.</span></span> <span data-ttu-id="494a7-115">また、Microsoft Lync 2013 に通知して、"ボイスメールの呼び出し" インジケーターを明るくします。</span><span class="sxs-lookup"><span data-stu-id="494a7-115">It also signals Microsoft Lync 2013 to light up the “call voice mail” indicator.</span></span>
    
      - <span data-ttu-id="494a7-p104">**Identity** により、変更するユーザー アカウントを指定しています。 Identity 値は、以下の形式のいずれかで指定できます。</span><span class="sxs-lookup"><span data-stu-id="494a7-p104">**Identity** specifies the user account to be modified. The Identity value can be specified using any of the following formats:</span></span>
        
          - <span data-ttu-id="494a7-118">ユーザーの SIP アドレス</span><span class="sxs-lookup"><span data-stu-id="494a7-118">The user's SIP address</span></span>
        
          - <span data-ttu-id="494a7-119">ユーザーの Active Directory ユーザー プリンシパル名</span><span class="sxs-lookup"><span data-stu-id="494a7-119">The user's Active Directory User-Principal-Name</span></span>
        
          - <span data-ttu-id="494a7-120">ユーザーのドメイン\\ログオン名 (たとえば、contoso\\kenmyer)</span><span class="sxs-lookup"><span data-stu-id="494a7-120">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
        
          - <span data-ttu-id="494a7-121">ユーザーの Active Directory ドメイン サービス表示名 (例: Ken Myer)。</span><span class="sxs-lookup"><span data-stu-id="494a7-121">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="494a7-122">Identity 値として表示名を使用する場合は、アスタリスク (\*) ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="494a7-122">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="494a7-123">たとえば、"\* smith" という id は、"smith" という文字列値で終わる表示名を持つすべてのユーザーを返します。</span><span class="sxs-lookup"><span data-stu-id="494a7-123">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="494a7-124">ユーザーの Active Directory SAM アカウント名は、フォレスト内で一意の名前とは限らないため、Identity 値として使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="494a7-124">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

