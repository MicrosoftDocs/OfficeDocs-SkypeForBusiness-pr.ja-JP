---
title: 'Lync Server 2013: 一般的なエリア電話の連絡先オブジェクトを作成または変更する'
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
ms.openlocfilehash: 1e9e7ddf1a4911b9afb3428531911223f62ea723
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758111"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="24dc6-102">Lync Server 2013 で一般的なエリア電話の連絡先オブジェクトを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="24dc6-102">Create or modify a common area phone Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24dc6-103">_**トピックの最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="24dc6-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="24dc6-104">共通するすべての携帯電話の Active Directory ドメインサービス連絡先オブジェクトを作成するには、 **CsCommonAreaPhone**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="24dc6-104">To create Active Directory Domain Services contact objects for all your common area phones, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="24dc6-105">このコマンドレットは、一般的なエリア携帯電話で使用する新しい連絡先オブジェクトを作成するか、既存の連絡先オブジェクトを新しい一般的な市外局番に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="24dc6-105">This cmdlet can either create new contact objects for use with common area phones, or it can associate existing contact objects with a new common area phone.</span></span> <span data-ttu-id="24dc6-106">一般的な市外局番に関連付けられた連絡先オブジェクトのプロパティを変更するには、 **CsCommonAreaPhone**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="24dc6-106">To modify the properties of the contact objects associated with common area phones, use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="24dc6-107">**CsCommonAreaPhone**のオプションパラメーターを使用すると、連絡先の Active Directory 表示名や電話に関連付けられている行の Uniform resource IDENTIFIER (URI) などの項目を変更し、Lync Server で使用するアカウントを有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="24dc6-107">Optional parameters for **Set-CsCommonAreaPhone** enable you to change items, such as the contact’s Active Directory display name or the line Uniform Resource Identifier (URI) associated with the phone, and enable and disable the account for use with Lync Server.</span></span> <span data-ttu-id="24dc6-108">使用可能なすべての変更の詳細については、「 [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone)」の「パラメーター」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="24dc6-108">For details about all the available modifications, see the Parameters section at [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone).</span></span> <span data-ttu-id="24dc6-109">**新規 CsCommonAreaPhone**パラメーターの詳細については、「 [CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24dc6-109">For details about **New-CsCommonAreaPhone** parameters, see [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).</span></span>

<span data-ttu-id="24dc6-110">これら2つのコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="24dc6-110">You can run these two cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="24dc6-111">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="24dc6-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a><span data-ttu-id="24dc6-112">一般的なエリア電話の連絡先オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="24dc6-112">Creating a common area phone contact object</span></span>

  - <span data-ttu-id="24dc6-113">新しい共通エリア電話連絡先オブジェクトを作成するには、 **CsCommonAreaPhone**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="24dc6-113">To create a new common area phone contact object, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="24dc6-114">連絡先オブジェクトの作成時には、少なくとも次の情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24dc6-114">At a minimum, you must supply the following information when creating a contact object:</span></span>
    
      - <span data-ttu-id="24dc6-115">**Lineuri**: 一般的な市外局番に割り当てられている電話番号。</span><span class="sxs-lookup"><span data-stu-id="24dc6-115">**LineUri**: The telephone number assigned to the common area phone.</span></span> <span data-ttu-id="24dc6-116">電話番号を指定するときは、必ず164形式を使用する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="24dc6-116">Note that you must use the E.164 format when specifying the phone number.</span></span>
    
      - <span data-ttu-id="24dc6-117">**RegistrarPool**: 連絡先オブジェクトをホストするレジストラープールの完全修飾ドメイン名 (FQDN) です。</span><span class="sxs-lookup"><span data-stu-id="24dc6-117">**RegistrarPool**: The fully qualified domain name (FQDN) of the Registrar pool that will host the contact object.</span></span>
    
      - <span data-ttu-id="24dc6-118">**OU**: 連絡先オブジェクトを作成する Active Directory コンテナーの識別名。</span><span class="sxs-lookup"><span data-stu-id="24dc6-118">**OU**: Distinguished name of the Active Directory container where the contact object will be created.</span></span>
    
    <span data-ttu-id="24dc6-119">Active Directory ドメインサービスの表示名も指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="24dc6-119">We also recommend that you provide an Active Directory Domain Services display name.</span></span> <span data-ttu-id="24dc6-120">それ以外の場合は、電話 Id を指定するために GUID を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24dc6-120">Otherwise, you will need to use a GUID to specify the phone Identity.</span></span> <span data-ttu-id="24dc6-121">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="24dc6-121">For example:</span></span>
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a><span data-ttu-id="24dc6-122">一般的なエリア電話の連絡先オブジェクトを変更する</span><span class="sxs-lookup"><span data-stu-id="24dc6-122">Modifying a common area phone contact object</span></span>

  - <span data-ttu-id="24dc6-123">既存の一般的な市外局番のプロパティを変更するには、 **CsCommonAreaPhone**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="24dc6-123">To modify the properties of an existing common area phone, contact object use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="24dc6-124">たとえば、次のコマンドは、共通エリア電話の SIP アドレスを DisplayName ロビーで構成します。</span><span class="sxs-lookup"><span data-stu-id="24dc6-124">For example, this command configures the SIP address for the common area phone with the DisplayName Lobby:</span></span>
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

<span data-ttu-id="24dc6-125">詳細については、 [CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone)コマンドレットと[CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="24dc6-125">For details, see the Help topics for the [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) cmdlet and the [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

