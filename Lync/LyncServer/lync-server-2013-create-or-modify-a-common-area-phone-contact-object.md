---
title: 'Lync Server 2013: 共通領域電話の連絡先オブジェクトを作成または変更する'
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
ms.openlocfilehash: 83d2eb58df1e5c83f23fdb1d31ba73b408d107a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="e664b-102">Lync Server 2013 で共通領域電話の連絡先オブジェクトを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="e664b-102">Create or modify a common area phone Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e664b-103">_**トピックの最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="e664b-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="e664b-104">すべての共通領域電話に対して Active Directory ドメインサービスの連絡先オブジェクトを作成するには、 **move-cscommonareaphone**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e664b-104">To create Active Directory Domain Services contact objects for all your common area phones, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="e664b-105">このコマンドレットでは、共通領域電話で使用する新しい連絡先オブジェクトを作成するか、既存の連絡先オブジェクトを新しい共通領域電話に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="e664b-105">This cmdlet can either create new contact objects for use with common area phones, or it can associate existing contact objects with a new common area phone.</span></span> <span data-ttu-id="e664b-106">共通領域電話に関連付けられている連絡先オブジェクトのプロパティを変更するには、 **move-cscommonareaphone**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e664b-106">To modify the properties of the contact objects associated with common area phones, use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="e664b-107">**Move-cscommonareaphone**のオプションのパラメーターを使用すると、連絡先の Active Directory 表示名や電話に関連付けられている回線 Uri (Uniform resource Identifier) などのアイテムを変更し、Lync Server で使用するアカウントを有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e664b-107">Optional parameters for **Set-CsCommonAreaPhone** enable you to change items, such as the contact’s Active Directory display name or the line Uniform Resource Identifier (URI) associated with the phone, and enable and disable the account for use with Lync Server.</span></span> <span data-ttu-id="e664b-108">使用可能なすべての変更の詳細については、「 [move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone)」のパラメータセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e664b-108">For details about all the available modifications, see the Parameters section at [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone).</span></span> <span data-ttu-id="e664b-109">**Move-cscommonareaphone**パラメーターの詳細については、「 [move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e664b-109">For details about **New-CsCommonAreaPhone** parameters, see [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).</span></span>

<span data-ttu-id="e664b-110">これら2つのコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="e664b-110">You can run these two cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e664b-111">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="e664b-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a><span data-ttu-id="e664b-112">共通領域電話の連絡先オブジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="e664b-112">Creating a common area phone contact object</span></span>

  - <span data-ttu-id="e664b-113">新しい共通領域電話の連絡先オブジェクトを作成するには、 **move-cscommonareaphone**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e664b-113">To create a new common area phone contact object, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="e664b-114">連絡先オブジェクトを作成するときには、少なくとも次の情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e664b-114">At a minimum, you must supply the following information when creating a contact object:</span></span>
    
      - <span data-ttu-id="e664b-115">**Lineuri**: 共通領域電話に割り当てられた電話番号です。</span><span class="sxs-lookup"><span data-stu-id="e664b-115">**LineUri**: The telephone number assigned to the common area phone.</span></span> <span data-ttu-id="e664b-116">電話番号を指定するときは、e.164 形式を使用する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e664b-116">Note that you must use the E.164 format when specifying the phone number.</span></span>
    
      - <span data-ttu-id="e664b-117">**RegistrarPool**: 連絡先オブジェクトをホストするレジストラープールの完全修飾ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="e664b-117">**RegistrarPool**: The fully qualified domain name (FQDN) of the Registrar pool that will host the contact object.</span></span>
    
      - <span data-ttu-id="e664b-118">**OU**: 連絡先オブジェクトを作成する Active Directory コンテナーの識別名。</span><span class="sxs-lookup"><span data-stu-id="e664b-118">**OU**: Distinguished name of the Active Directory container where the contact object will be created.</span></span>
    
    <span data-ttu-id="e664b-119">また、Active Directory ドメインサービスの表示名を指定することもお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e664b-119">We also recommend that you provide an Active Directory Domain Services display name.</span></span> <span data-ttu-id="e664b-120">それ以外の場合は、電話 Id を指定するために GUID を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e664b-120">Otherwise, you will need to use a GUID to specify the phone Identity.</span></span> <span data-ttu-id="e664b-121">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e664b-121">For example:</span></span>
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a><span data-ttu-id="e664b-122">共通領域電話の連絡先オブジェクトを変更する</span><span class="sxs-lookup"><span data-stu-id="e664b-122">Modifying a common area phone contact object</span></span>

  - <span data-ttu-id="e664b-123">既存の共通領域電話のプロパティを変更するには、連絡先オブジェクトで**move-cscommonareaphone**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e664b-123">To modify the properties of an existing common area phone, contact object use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="e664b-124">たとえば、次のコマンドは、共通領域電話の SIP アドレスを DisplayName ロビーで構成します。</span><span class="sxs-lookup"><span data-stu-id="e664b-124">For example, this command configures the SIP address for the common area phone with the DisplayName Lobby:</span></span>
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

<span data-ttu-id="e664b-125">詳細については、 [move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone)コマンドレットおよび[move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e664b-125">For details, see the Help topics for the [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) cmdlet and the [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

