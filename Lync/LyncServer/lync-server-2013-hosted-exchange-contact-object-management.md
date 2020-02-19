---
title: 'Lync Server 2013: Hosted Exchange 連絡先オブジェクト管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange Contact object management
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412978(v=OCS.15)
ms:contentKeyID: 48185748
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 836fa74093e436d3a2f076f4896f0275d543e17e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135424"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a><span data-ttu-id="5d1aa-102">Lync Server 2013 での Hosted Exchange の連絡先オブジェクト管理</span><span class="sxs-lookup"><span data-stu-id="5d1aa-102">Hosted Exchange Contact object management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d1aa-103">_**トピックの最終更新日:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="5d1aa-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="5d1aa-104">横断設置型の展開では、自動応答番号およびサブスクライバー アクセス番号ごとに連絡先オブジェクトを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d1aa-104">You need to configure a Contact object for each auto-attendant number and subscriber access number in your cross-premises deployment.</span></span>

<span data-ttu-id="5d1aa-105">Hosted Exchange UM との統合では、ocsumutil.exe は Active Directory Exchange UM 設定に依存するため、ocsumutil.exe を使用して連絡先オブジェクトを管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="5d1aa-105">For integration with hosted Exchange UM, ocsumutil.exe cannot be used to manage Contact objects, because it depends on Active Directory Exchange UM settings.</span></span> <span data-ttu-id="5d1aa-106">クロスプレミスの展開では、Lync Server 2013 と hosted Exchange UM が異なるフォレストにインストールされ、それらの間に信頼はありません。</span><span class="sxs-lookup"><span data-stu-id="5d1aa-106">In a cross-premises deployment, Lync Server 2013 and hosted Exchange UM are installed in separate forests with no trust between them.</span></span> <span data-ttu-id="5d1aa-107">セキュリティ上の理由から、Lync Server 2013 管理者は、Exchange UM Active Directory 設定に直接アクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5d1aa-107">For security reasons, Lync Server 2013 administrators have no direct access to Exchange UM Active Directory settings.</span></span> <span data-ttu-id="5d1aa-108">そのため、Lync server 2013 と hosted Exchange UM サービスの2013両方からアクセスできる*共有 SIP アドレススペース*の連絡先オブジェクトを管理するための別のモデルが提供されています。</span><span class="sxs-lookup"><span data-stu-id="5d1aa-108">As a result, Lync Server 2013 provides a different model for managing Contact objects in a *shared SIP address space* that is accessible to both Lync Server 2013 and the hosted Exchange UM service.</span></span>

<div>

## <a name="hosted-contact-object-workflow"></a><span data-ttu-id="5d1aa-109">ホスト型連絡先オブジェクトのワークフロー</span><span class="sxs-lookup"><span data-stu-id="5d1aa-109">Hosted Contact Object Workflow</span></span>

<span data-ttu-id="5d1aa-110">以下では、Hosted Exchange のテナント管理者と協力して、連絡先オブジェクトを管理するための一般的な手順を示します。</span><span class="sxs-lookup"><span data-stu-id="5d1aa-110">The following are the general steps for working with your hosted Exchange tenant administrator to manage contact objects:</span></span>

1.  <span data-ttu-id="5d1aa-111">Exchange の管理者が、Exchange UM サブスクライバー アクセス連絡先オブジェクトおよび自動応答連絡先オブジェクトの電話番号を要求します。</span><span class="sxs-lookup"><span data-stu-id="5d1aa-111">The Exchange administrator requests phone numbers for the Exchange UM subscriber access and auto-attendant Contact objects.</span></span>

2.  <span data-ttu-id="5d1aa-112">Lync Server 2013 管理者は、各電話番号の連絡先オブジェクトを作成し、ホストボイスメールポリシーを各連絡先オブジェクトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5d1aa-112">The Lync Server 2013 administrator creates a Contact object for each phone number and assigns a hosted voice mail policy to each Contact object.</span></span>

3.  <span data-ttu-id="5d1aa-113">Lync Server 2013 管理者は、Exchange 管理者に電話番号を提供します。</span><span class="sxs-lookup"><span data-stu-id="5d1aa-113">The Lync Server 2013 administrator provides the phone numbers to the Exchange administrator.</span></span>

4.  <span data-ttu-id="5d1aa-114">Exchange 管理者は、自動応答およびサブスクライバー アクセス用の該当する Exchange UM ダイヤルプランに電話番号を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5d1aa-114">The Exchange administrator assigns the phone numbers to appropriate Exchange UM dial plans for auto attendants and subscriber access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5d1aa-115">オンプレミス展開の場合と同様に、連絡先オブジェクトに対して Lync Server 2013 ダイヤルプランの設定を構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5d1aa-115">There is no need to configure any Lync Server 2013 dial plan settings on the Contact objects as there is with on-premises deployments.</span></span>



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a><span data-ttu-id="5d1aa-116">ホスト型連絡先オブジェクトの構成</span><span class="sxs-lookup"><span data-stu-id="5d1aa-116">Configuring Hosted Contact Objects</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5d1aa-117">ホストされた Exchange UM に対して Lync Server 2013 連絡先オブジェクトを有効にする前に、それらに適用されるホストボイスメールポリシーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d1aa-117">Before Lync Server 2013 Contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="5d1aa-118">ここで展開するポリシーは、有効化する連絡先オブジェクトに適用するのであれば、そのスコープがグローバルなものでも、サイト レベルのものでも、ユーザー単位のものでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="5d1aa-118">The policy can be of global, site-level, or per-user scope, as long as it applies to the contact object you want to enable.</span></span> <span data-ttu-id="5d1aa-119">詳細については、「 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 のホストボイスメールポリシー</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d1aa-119">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="5d1aa-120">横断型展開でホスト型自動応答およびサブスクライバー アクセス連絡先オブジェクトを構成するには、次の各コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d1aa-120">To configure hosted auto-attendant and subscriber access Contact objects in a cross-premises deployment, you must use the following cmdlets:</span></span>

  - <span data-ttu-id="5d1aa-121">**New-CsExUmContact** は、ホスト型 UM 用の新しい連絡先オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="5d1aa-121">**New-CsExUmContact** creates a new Contact object for hosted UM.</span></span>

  - <span data-ttu-id="5d1aa-122">**Set-CsExUmContact** は、Hosted Exchange UM 用の既存の連絡先オブジェクトを変更します。</span><span class="sxs-lookup"><span data-stu-id="5d1aa-122">**Set-CsExUmContact** modifies an existing Contact object for hosted Exchange UM.</span></span>

<span data-ttu-id="5d1aa-123">次の例では、自動応答連絡先オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5d1aa-123">The following example creates an auto-attendant Contact object:</span></span>

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

<span data-ttu-id="5d1aa-124">この例では、SIP アドレスが sip:exumaa1@fabrikam.com の、新しい Exchange UM 連絡先オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5d1aa-124">This example creates a new Exchange UM Contact object with the SIP address sip:exumaa1@fabrikam.com.</span></span> <span data-ttu-id="5d1aa-125">Lync Server 2013 レジストラーサービスが実行されているプールの名前は RedmondPool.litwareinc.com です。</span><span class="sxs-lookup"><span data-stu-id="5d1aa-125">The name of the pool where the Lync Server 2013 Registrar service is running is RedmondPool.litwareinc.com.</span></span> <span data-ttu-id="5d1aa-126">この情報が保存される Active Directory 組織単位は、OU=ExUmContacts,DC=litwareinc,DC=com です。</span><span class="sxs-lookup"><span data-stu-id="5d1aa-126">The Active Directory organizational unit where this information will be stored is OU=ExUmContacts,DC=litwareinc,DC=com.</span></span> <span data-ttu-id="5d1aa-127">連絡先オブジェクトの電話番号は、2065554567 です。</span><span class="sxs-lookup"><span data-stu-id="5d1aa-127">The phone number of the Contact object is 2065554567.</span></span> <span data-ttu-id="5d1aa-128">オプションの -AutoAttendant $True パラメーターは、このオブジェクトが自動応答連絡先オブジェクトであることを指定しています。</span><span class="sxs-lookup"><span data-stu-id="5d1aa-128">The optional -AutoAttendant $True parameter specifies that this object is an auto-attendant Contact object.</span></span> <span data-ttu-id="5d1aa-129">-AutoAttendant パラメーターを False (既定) に設定すると、このオブジェクトがサブスクライバー アクセス連絡先オブジェクトであることが指定されます。</span><span class="sxs-lookup"><span data-stu-id="5d1aa-129">Setting the -AutoAttendant parameter to False (the default) specifies a subscriber access Contact object.</span></span>

<span data-ttu-id="5d1aa-130">新しい-CsExUmContact および Set-CsExUmContact コマンドレットの詳細については、「Lync Server Management Shell」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d1aa-130">For details about the New-CsExUmContact and Set-CsExUmContact cmdlets, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

