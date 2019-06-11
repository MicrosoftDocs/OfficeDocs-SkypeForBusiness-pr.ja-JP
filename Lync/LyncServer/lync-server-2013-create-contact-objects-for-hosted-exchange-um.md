---
title: 'Lync Server 2013: Hosted Exchange UM の連絡先オブジェクトの作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0ce65ed39e67068fcd57aba1177ecb72f553ccf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a><span data-ttu-id="cc24e-102">Lync Server 2013 での Hosted Exchange UM の連絡先オブジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="cc24e-102">Create contact objects for hosted Exchange UM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc24e-103">_**最終更新日:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="cc24e-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="cc24e-104">次の手順では、ホストされた Exchange ユニファイドメッセージング (UM) 用に自動応答 (AA) または加入者アクセス (SA) 連絡先オブジェクトを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cc24e-104">The following procedure explains how to create Auto Attendant (AA) or Subscriber Access (SA) contact objects for hosted Exchange Unified Messaging (UM).</span></span>

<span data-ttu-id="cc24e-105">詳細については、計画ドキュメントの「 [Lync Server 2013 での Hosted Exchange Contact object management](lync-server-2013-hosted-exchange-contact-object-management.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc24e-105">For details, see [Hosted Exchange Contact object management in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="cc24e-106">連絡先オブジェクトの構成の詳細については、次のコマンドレットの Lync Server 管理シェルに関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc24e-106">For details about configuring contact objects, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="cc24e-107">新規-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="cc24e-107">New-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [<span data-ttu-id="cc24e-108">Set-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="cc24e-108">Set-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="cc24e-109">Lync Server 2013 連絡先オブジェクトをホストされた Exchange UM に対して有効にする前に、それらに適用されるホストされたボイスメールポリシーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc24e-109">Before Lync Server 2013 contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="cc24e-110">詳細については、「 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 のホスト型ボイスメールポリシー</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc24e-110">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a><span data-ttu-id="cc24e-111">Hosted Exchange UM 用の AA または SA の連絡先オブジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="cc24e-111">To create AA or SA contact objects for hosted Exchange UM</span></span>

1.  <span data-ttu-id="cc24e-112">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc24e-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="cc24e-113">新しい-CsExUmContact コマンドレットを実行して、展開に必要な連絡先オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="cc24e-113">Run the New-CsExUmContact cmdlet to create any contact objects required for your deployment.</span></span> <span data-ttu-id="cc24e-114">たとえば、次のように実行して AA と SA の連絡先オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="cc24e-114">For example, run the following to create an AA and an SA contact object:</span></span>
    
       ```
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    <span data-ttu-id="cc24e-115">これらの例では、次のパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="cc24e-115">These examples set the following parameters:</span></span>
    
      - <span data-ttu-id="cc24e-116">**SipAddress**連絡先オブジェクトの SIP アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="cc24e-116">**SipAddress** specifies the SIP address of the contact object.</span></span> <span data-ttu-id="cc24e-117">これは、Active Directory ドメインサービスでユーザーまたは連絡先オブジェクトを構成するためにまだ使用されていないアドレスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc24e-117">This must be an address that has not already been used to configure a user or contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="cc24e-118">この値は、前の例で示した\<ように、"sip:*sip アドレス*\>" の形式になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc24e-118">This value must be in the format “sip:\<*SIP address*\>“ as shown in the previous examples.</span></span>
    
      - <span data-ttu-id="cc24e-119">**RegistrarPool**は、レジストラーサービスが実行されているプールの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="cc24e-119">**RegistrarPool** specifies the fully qualified domain name (FQDN) of the pool on which the Registrar service is running.</span></span>
        
        <div class=" ">
        

        > [!NOTE]  
        > <span data-ttu-id="cc24e-120">Lync server 2013 より前の Lync Server 2013 展開の一部であるプールに Exchange UM 連絡先オブジェクトを移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="cc24e-120">Exchange UM contact objects cannot be moved to pools that are part of Lync Server 2013 deployments prior to Lync Server 2013.</span></span>

        
        </div>
    
      - <span data-ttu-id="cc24e-121">**OU**この連絡先オブジェクトを配置する Active Directory の組織単位を指定します。</span><span class="sxs-lookup"><span data-stu-id="cc24e-121">**OU** specifies the Active Directory organizational unit where this contact object will be located.</span></span>
    
      - <span data-ttu-id="cc24e-122">**Displaynumber**連絡先オブジェクトの電話番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="cc24e-122">**DisplayNumber** specifies the telephone number of the contact object.</span></span> <span data-ttu-id="cc24e-123">各連絡先オブジェクトの電話番号は一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc24e-123">The phone number for each contact object must be unique.</span></span>
    
      - <span data-ttu-id="cc24e-124">**Autoattendant**連絡先オブジェクトが自動応答かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="cc24e-124">**AutoAttendant** specifies whether the Contact object is an Auto Attendant.</span></span> <span data-ttu-id="cc24e-125">自動応答では、発信者が電話システムを移動して、連絡を希望する当事者に連絡できるようにする一連の音声プロンプトが用意されています。</span><span class="sxs-lookup"><span data-stu-id="cc24e-125">Auto Attendant provides a set of voice prompts that allow callers to navigate the phone system and reach the party that they want to contact.</span></span> <span data-ttu-id="cc24e-126">このパラメーターの値が**False** (既定値) の場合、サブスクライバーアクセスの contact オブジェクトが示されます。</span><span class="sxs-lookup"><span data-stu-id="cc24e-126">A value of **False** (the default) for this parameter indicates a Subscriber Access contact object.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

