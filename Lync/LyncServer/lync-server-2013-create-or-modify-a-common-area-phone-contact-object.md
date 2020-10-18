---
title: 'Lync Server 2013: 共通領域電話の連絡先オブジェクトを作成または変更する'
description: 'Lync Server 2013: 共通領域電話の連絡先オブジェクトを作成または変更します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a common area phone Contact object
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994083(v=OCS.15)
ms:contentKeyID: 51803995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adc5ede23f495a63b2d556b556817d4171a08723
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578233"
---
# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="2e0d8-103">Lync Server 2013 で共通領域電話の連絡先オブジェクトを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="2e0d8-103">Create or modify a common area phone Contact object in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e0d8-104">_**トピックの最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="2e0d8-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="2e0d8-105">すべての共通領域電話に対して Active Directory ドメインサービスの連絡先オブジェクトを作成するには、 **move-cscommonareaphone** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-105">To create Active Directory Domain Services contact objects for all your common area phones, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="2e0d8-106">このコマンドレットでは、共通領域電話で使用する新しい連絡先オブジェクトを作成するか、既存の連絡先オブジェクトを新しい共通領域電話に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-106">This cmdlet can either create new contact objects for use with common area phones, or it can associate existing contact objects with a new common area phone.</span></span> <span data-ttu-id="2e0d8-107">共通領域電話に関連付けられている連絡先オブジェクトのプロパティを変更するには、 **move-cscommonareaphone** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-107">To modify the properties of the contact objects associated with common area phones, use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="2e0d8-108">**Move-cscommonareaphone**のオプションのパラメーターを使用すると、連絡先の Active Directory 表示名や電話に関連付けられている回線 Uri (Uniform resource Identifier) などのアイテムを変更し、Lync Server で使用するアカウントを有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-108">Optional parameters for **Set-CsCommonAreaPhone** enable you to change items, such as the contact’s Active Directory display name or the line Uniform Resource Identifier (URI) associated with the phone, and enable and disable the account for use with Lync Server.</span></span> <span data-ttu-id="2e0d8-109">使用可能なすべての変更の詳細については、「 [move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone)」のパラメータセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-109">For details about all the available modifications, see the Parameters section at [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone).</span></span> <span data-ttu-id="2e0d8-110">**Move-cscommonareaphone**パラメーターの詳細については、「 [move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-110">For details about **New-CsCommonAreaPhone** parameters, see [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).</span></span>

<span data-ttu-id="2e0d8-111">これら2つのコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-111">You can run these two cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2e0d8-112">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-112">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a><span data-ttu-id="2e0d8-113">共通領域電話の連絡先オブジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="2e0d8-113">Creating a common area phone contact object</span></span>

  - <span data-ttu-id="2e0d8-114">新しい共通領域電話の連絡先オブジェクトを作成するには、 **move-cscommonareaphone** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-114">To create a new common area phone contact object, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="2e0d8-115">連絡先オブジェクトを作成するときには、少なくとも次の情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-115">At a minimum, you must supply the following information when creating a contact object:</span></span>
    
      - <span data-ttu-id="2e0d8-116">**Lineuri**: 共通領域電話に割り当てられた電話番号です。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-116">**LineUri**: The telephone number assigned to the common area phone.</span></span> <span data-ttu-id="2e0d8-117">電話番号を指定するときは、e.164 形式を使用する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-117">Note that you must use the E.164 format when specifying the phone number.</span></span>
    
      - <span data-ttu-id="2e0d8-118">**RegistrarPool**: 連絡先オブジェクトをホストするレジストラープールの完全修飾ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-118">**RegistrarPool**: The fully qualified domain name (FQDN) of the Registrar pool that will host the contact object.</span></span>
    
      - <span data-ttu-id="2e0d8-119">**OU**: 連絡先オブジェクトを作成する Active Directory コンテナーの識別名。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-119">**OU**: Distinguished name of the Active Directory container where the contact object will be created.</span></span>
    
    <span data-ttu-id="2e0d8-120">また、Active Directory ドメインサービスの表示名を指定することもお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-120">We also recommend that you provide an Active Directory Domain Services display name.</span></span> <span data-ttu-id="2e0d8-121">それ以外の場合は、電話 Id を指定するために GUID を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-121">Otherwise, you will need to use a GUID to specify the phone Identity.</span></span> <span data-ttu-id="2e0d8-122">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-122">For example:</span></span>
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a><span data-ttu-id="2e0d8-123">共通領域電話の連絡先オブジェクトを変更する</span><span class="sxs-lookup"><span data-stu-id="2e0d8-123">Modifying a common area phone contact object</span></span>

  - <span data-ttu-id="2e0d8-124">既存の共通領域電話のプロパティを変更するには、連絡先オブジェクトで **move-cscommonareaphone** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-124">To modify the properties of an existing common area phone, contact object use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="2e0d8-125">たとえば、次のコマンドは、共通領域電話の SIP アドレスを DisplayName ロビーで構成します。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-125">For example, this command configures the SIP address for the common area phone with the DisplayName Lobby:</span></span>
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

<span data-ttu-id="2e0d8-126">詳細については、 [move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) コマンドレットおよび [move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e0d8-126">For details, see the Help topics for the [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) cmdlet and the [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

