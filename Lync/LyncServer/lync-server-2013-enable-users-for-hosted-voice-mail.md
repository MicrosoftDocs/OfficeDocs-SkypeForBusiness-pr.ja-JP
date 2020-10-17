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
ms.openlocfilehash: 5c0975f6be3d78ec7634859b26e7ed35e7efee5a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501034"
---
# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a><span data-ttu-id="c6852-102">Lync Server 2013 でホストボイスメールに対してユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="c6852-102">Enable users for hosted voice mail in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6852-103">_**トピックの最終更新日:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="c6852-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="c6852-104">手順に従い、hosted Exchange ユニファイドメッセージング (UM) サービスで Lync Server 2013 ユーザーのボイスメールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c6852-104">Follow the procedure to enable Lync Server 2013 users for voice mail on a hosted Exchange Unified Messaging (UM) service.</span></span>

<span data-ttu-id="c6852-105">詳細については、「計画」のドキュメントの「 [Hosted Exchange user management In Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6852-105">For details, see [Hosted Exchange user management in Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="c6852-106">[Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser)コマンドレットの詳細については、「Lync Server Management Shell」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6852-106">For details about the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c6852-107">ホストボイスメールに対して Lync Server 2013 ユーザーを有効にするには、そのユーザーアカウントに適用するホストボイスメールポリシーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6852-107">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to their user account must be deployed.</span></span> <span data-ttu-id="c6852-108">詳細については、「 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 のホストボイスメールポリシー</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6852-108">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a><span data-ttu-id="c6852-109">ホストボイスメールに対してユーザーを有効にするには</span><span class="sxs-lookup"><span data-stu-id="c6852-109">To enable users for hosted voice mail</span></span>

1.  <span data-ttu-id="c6852-110">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6852-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c6852-111">Set-CsUser コマンドレットを実行して、ホストボイスメールのユーザーアカウントを構成します。</span><span class="sxs-lookup"><span data-stu-id="c6852-111">Run the Set-CsUser cmdlet to configure the user account for hosted voice mail.</span></span> <span data-ttu-id="c6852-112">たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="c6852-112">For example, run:</span></span>
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    <span data-ttu-id="c6852-113">上述の例では、次のパラメーターが設定されます。</span><span class="sxs-lookup"><span data-stu-id="c6852-113">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="c6852-114">**HostedVoiceMail** では、ユーザーのボイスメール呼び出しを、ホストされた Exchange UM にルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="c6852-114">**HostedVoiceMail** enables a user’s voice mail calls to be routed to hosted Exchange UM.</span></span> <span data-ttu-id="c6852-115">また、Microsoft Lync 2013 に通知して、"ボイスメールの呼び出し" インジケーターを明るくします。</span><span class="sxs-lookup"><span data-stu-id="c6852-115">It also signals Microsoft Lync 2013 to light up the “call voice mail” indicator.</span></span>
    
      - <span data-ttu-id="c6852-p104">**Identity** により、変更するユーザー アカウントを指定しています。 Identity 値は、以下の形式のいずれかで指定できます。</span><span class="sxs-lookup"><span data-stu-id="c6852-p104">**Identity** specifies the user account to be modified. The Identity value can be specified using any of the following formats:</span></span>
        
          - <span data-ttu-id="c6852-118">ユーザーの SIP アドレス</span><span class="sxs-lookup"><span data-stu-id="c6852-118">The user's SIP address</span></span>
        
          - <span data-ttu-id="c6852-119">ユーザーの Active Directory ユーザー プリンシパル名</span><span class="sxs-lookup"><span data-stu-id="c6852-119">The user's Active Directory User-Principal-Name</span></span>
        
          - <span data-ttu-id="c6852-120">ユーザーのドメイン \\ ログオン名 (たとえば、contoso \\ kenmyer)</span><span class="sxs-lookup"><span data-stu-id="c6852-120">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
        
          - <span data-ttu-id="c6852-121">ユーザーの Active Directory ドメイン サービス表示名 (例: Ken Myer)。</span><span class="sxs-lookup"><span data-stu-id="c6852-121">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="c6852-122">Display-Name を Identity 値として使用する場合は、アスタリスク ( \* ) ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6852-122">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="c6852-123">たとえば、"smith" という Id は、" \* smith" という文字列値で終わる Display-Name を持つすべてのユーザーを返します。</span><span class="sxs-lookup"><span data-stu-id="c6852-123">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c6852-124">ユーザーの Active Directory SAM アカウント名は、フォレスト内で一意の名前とは限らないため、Identity 値として使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="c6852-124">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

