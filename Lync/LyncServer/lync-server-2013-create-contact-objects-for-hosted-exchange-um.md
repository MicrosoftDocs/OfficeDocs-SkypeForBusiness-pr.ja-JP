---
title: 'Lync Server 2013: hosted Exchange UM の連絡先オブジェクトの作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c783a79c6d3ed3cd0af47d53d136a47585cb94d0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a><span data-ttu-id="b05d0-102">Lync Server 2013 で hosted Exchange UM の連絡先オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="b05d0-102">Create contact objects for hosted Exchange UM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b05d0-103">_**トピックの最終更新日:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="b05d0-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="b05d0-104">次の手順では、Hosted Exchange ユニファイド メッセージング (UM) の自動応答 (AA) またはサブスクライバー アクセス (SA) の連絡先オブジェクトを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b05d0-104">The following procedure explains how to create Auto Attendant (AA) or Subscriber Access (SA) contact objects for hosted Exchange Unified Messaging (UM).</span></span>

<span data-ttu-id="b05d0-105">詳細については、「計画」のドキュメントの「 [Hosted Exchange Contact object management In Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b05d0-105">For details, see [Hosted Exchange Contact object management in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="b05d0-106">連絡先オブジェクトの構成の詳細については、以下のコマンドレットの Lync Server Management Shell のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b05d0-106">For details about configuring contact objects, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="b05d0-107">New-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="b05d0-107">New-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [<span data-ttu-id="b05d0-108">Set-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="b05d0-108">Set-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="b05d0-109">ホストされた Exchange UM に対して Lync Server 2013 連絡先オブジェクトを有効にする前に、それらに適用されるホストボイスメールポリシーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b05d0-109">Before Lync Server 2013 contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="b05d0-110">詳細については、「 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 のホストボイスメールポリシー</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b05d0-110">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a><span data-ttu-id="b05d0-111">Hosted Exchange UM の AA または SA の連絡先オブジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="b05d0-111">To create AA or SA contact objects for hosted Exchange UM</span></span>

1.  <span data-ttu-id="b05d0-112">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b05d0-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b05d0-p102">New-CsExUmContact コマンドレットを実行して、展開に必要な連絡先オブジェクトを作成します。 たとえば、AA および SA の連絡先オブジェクトを作成するには、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="b05d0-p102">Run the New-CsExUmContact cmdlet to create any contact objects required for your deployment. For example, run the following to create an AA and an SA contact object:</span></span>
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    <span data-ttu-id="b05d0-115">これらの例は、次のパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="b05d0-115">These examples set the following parameters:</span></span>
    
      - <span data-ttu-id="b05d0-116">**SipAddress** は、連絡先オブジェクトの SIP アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b05d0-116">**SipAddress** specifies the SIP address of the contact object.</span></span> <span data-ttu-id="b05d0-117">これは、Active Directory ドメイン サービスでユーザーまたは連絡先オブジェクトを構成するために以前使用したことのないアドレスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b05d0-117">This must be an address that has not already been used to configure a user or contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="b05d0-118">この値は、前の例で示され\<ているように、「sip:*sip アドレス*\>」の形式にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b05d0-118">This value must be in the format “sip:\<*SIP address*\>“ as shown in the previous examples.</span></span>
    
      - <span data-ttu-id="b05d0-119">**RegistrarPool** は、レジストラー サービスが実行されているプールの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="b05d0-119">**RegistrarPool** specifies the fully qualified domain name (FQDN) of the pool on which the Registrar service is running.</span></span>
        
        <div class=" ">
        

        > [!NOTE]  
        > <span data-ttu-id="b05d0-120">Lync Server 2013 の前に、Lync Server 2013 展開の一部であるプールに Exchange UM 連絡先オブジェクトを移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="b05d0-120">Exchange UM contact objects cannot be moved to pools that are part of Lync Server 2013 deployments prior to Lync Server 2013.</span></span>

        
        </div>
    
      - <span data-ttu-id="b05d0-121">**OU** は、この連絡先オブジェクトの配置先となる Active Directory 組織単位を指定します。</span><span class="sxs-lookup"><span data-stu-id="b05d0-121">**OU** specifies the Active Directory organizational unit where this contact object will be located.</span></span>
    
      - <span data-ttu-id="b05d0-p104">**DisplayNumber** は、連絡先オブジェクトの電話番号を指定します。 各連絡先オブジェクトの電話番号は一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b05d0-p104">**DisplayNumber** specifies the telephone number of the contact object. The phone number for each contact object must be unique.</span></span>
    
      - <span data-ttu-id="b05d0-p105">**AutoAttendant** は、連絡先オブジェクトを自動応答にするかどうかを指定します。 発信者は自動応答の音声案内セットを利用することで、電話システムを通して、希望する相手先に連絡することができます。 このパラメーターに **False** (既定値) の値が設定されている場合、それはサブスクライバー アクセスの連絡先オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="b05d0-p105">**AutoAttendant** specifies whether the Contact object is an Auto Attendant. Auto Attendant provides a set of voice prompts that allow callers to navigate the phone system and reach the party that they want to contact. A value of **False** (the default) for this parameter indicates a Subscriber Access contact object.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

