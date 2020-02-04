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
ms.openlocfilehash: c63e9952abab192e7f8f4a71e97a660d2798d3b9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739067"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a><span data-ttu-id="3720e-102">Lync Server 2013 の Hosted Exchange 連絡先オブジェクト管理</span><span class="sxs-lookup"><span data-stu-id="3720e-102">Hosted Exchange Contact object management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3720e-103">_**最終更新日:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="3720e-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="3720e-104">クロスプレミスの展開で、自動応答の番号とサブスクライバーのアクセス番号ごとに、連絡先オブジェクトを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3720e-104">You need to configure a Contact object for each auto-attendant number and subscriber access number in your cross-premises deployment.</span></span>

<span data-ttu-id="3720e-105">ホストされた Exchange UM との統合のために、Active Directory の Exchange UM 設定によって異なるため、連絡先オブジェクトを管理するために ocsumutil を使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="3720e-105">For integration with hosted Exchange UM, ocsumutil.exe cannot be used to manage Contact objects, because it depends on Active Directory Exchange UM settings.</span></span> <span data-ttu-id="3720e-106">クロスプレミスの展開では、Lync Server 2013 とホストされた Exchange UM は別々のフォレストにインストールされ、それらの間に信頼はありません。</span><span class="sxs-lookup"><span data-stu-id="3720e-106">In a cross-premises deployment, Lync Server 2013 and hosted Exchange UM are installed in separate forests with no trust between them.</span></span> <span data-ttu-id="3720e-107">セキュリティ上の理由から、Lync Server 2013 管理者は Exchange UM Active Directory の設定に直接アクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3720e-107">For security reasons, Lync Server 2013 administrators have no direct access to Exchange UM Active Directory settings.</span></span> <span data-ttu-id="3720e-108">このため、Lync Server 2013 には、Lync Server 2013 とホストされている Exchange UM サービスの両方からアクセスできる*共有 SIP アドレス空間*の連絡先オブジェクトを管理するための別のモデルが用意されています。</span><span class="sxs-lookup"><span data-stu-id="3720e-108">As a result, Lync Server 2013 provides a different model for managing Contact objects in a *shared SIP address space* that is accessible to both Lync Server 2013 and the hosted Exchange UM service.</span></span>

<div>

## <a name="hosted-contact-object-workflow"></a><span data-ttu-id="3720e-109">ホステッド連絡先オブジェクトワークフロー</span><span class="sxs-lookup"><span data-stu-id="3720e-109">Hosted Contact Object Workflow</span></span>

<span data-ttu-id="3720e-110">ホストされた Exchange テナント管理者と協力して連絡先オブジェクトを管理する一般的な手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3720e-110">The following are the general steps for working with your hosted Exchange tenant administrator to manage contact objects:</span></span>

1.  <span data-ttu-id="3720e-111">Exchange 管理者は、Exchange UM サブスクライバーアクセスと自動応答の連絡先オブジェクトの電話番号を要求します。</span><span class="sxs-lookup"><span data-stu-id="3720e-111">The Exchange administrator requests phone numbers for the Exchange UM subscriber access and auto-attendant Contact objects.</span></span>

2.  <span data-ttu-id="3720e-112">Lync Server 2013 管理者は、電話番号ごとに連絡先オブジェクトを作成し、ホストされたボイスメールポリシーを各連絡先オブジェクトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3720e-112">The Lync Server 2013 administrator creates a Contact object for each phone number and assigns a hosted voice mail policy to each Contact object.</span></span>

3.  <span data-ttu-id="3720e-113">Lync Server 2013 管理者は、Exchange 管理者に電話番号を提供します。</span><span class="sxs-lookup"><span data-stu-id="3720e-113">The Lync Server 2013 administrator provides the phone numbers to the Exchange administrator.</span></span>

4.  <span data-ttu-id="3720e-114">Exchange 管理者は、自動応答と加入者アクセスの適切な Exchange UM ダイヤルプランに電話番号を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3720e-114">The Exchange administrator assigns the phone numbers to appropriate Exchange UM dial plans for auto attendants and subscriber access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3720e-115">オンプレミスの展開があるため、連絡先オブジェクトの Lync Server 2013 ダイヤルプランの設定を構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3720e-115">There is no need to configure any Lync Server 2013 dial plan settings on the Contact objects as there is with on-premises deployments.</span></span>



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a><span data-ttu-id="3720e-116">ホステッド連絡先オブジェクトの構成</span><span class="sxs-lookup"><span data-stu-id="3720e-116">Configuring Hosted Contact Objects</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3720e-117">Lync Server 2013 連絡先オブジェクトをホストされた Exchange UM に対して有効にする前に、それらに適用されるホストされたボイスメールポリシーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3720e-117">Before Lync Server 2013 Contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="3720e-118">有効にする連絡先オブジェクトに適用される限り、ポリシーはグローバル、サイトレベル、またはユーザーごとのスコープにすることができます。</span><span class="sxs-lookup"><span data-stu-id="3720e-118">The policy can be of global, site-level, or per-user scope, as long as it applies to the contact object you want to enable.</span></span> <span data-ttu-id="3720e-119">詳細については、「 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 のホスト型ボイスメールポリシー</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3720e-119">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="3720e-120">クロスプレミスの展開でホストされた自動応答とサブスクライバーアクセスの連絡先オブジェクトを構成するには、次のコマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3720e-120">To configure hosted auto-attendant and subscriber access Contact objects in a cross-premises deployment, you must use the following cmdlets:</span></span>

  - <span data-ttu-id="3720e-121">**新しい-CsExUmContact**は、ホストされた UM 用の新しい連絡先オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="3720e-121">**New-CsExUmContact** creates a new Contact object for hosted UM.</span></span>

  - <span data-ttu-id="3720e-122">**Set-CsExUmContact**は、ホストされた Exchange UM の既存の連絡先オブジェクトを変更します。</span><span class="sxs-lookup"><span data-stu-id="3720e-122">**Set-CsExUmContact** modifies an existing Contact object for hosted Exchange UM.</span></span>

<span data-ttu-id="3720e-123">次の例では、自動応答の連絡先オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="3720e-123">The following example creates an auto-attendant Contact object:</span></span>

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

<span data-ttu-id="3720e-124">この例では、SIP アドレス sip:exumaa1@fabrikam.com を使用して、新しい Exchange UM 連絡先オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="3720e-124">This example creates a new Exchange UM Contact object with the SIP address sip:exumaa1@fabrikam.com.</span></span> <span data-ttu-id="3720e-125">Lync Server 2013 レジストラーサービスを実行しているプールの名前は、RedmondPool.litwareinc.com です。</span><span class="sxs-lookup"><span data-stu-id="3720e-125">The name of the pool where the Lync Server 2013 Registrar service is running is RedmondPool.litwareinc.com.</span></span> <span data-ttu-id="3720e-126">この情報が保存される Active Directory の組織単位は、OU = ExUmContacts、DC = litwareinc、DC = com です。</span><span class="sxs-lookup"><span data-stu-id="3720e-126">The Active Directory organizational unit where this information will be stored is OU=ExUmContacts,DC=litwareinc,DC=com.</span></span> <span data-ttu-id="3720e-127">連絡先オブジェクトの電話番号は2065554567です。</span><span class="sxs-lookup"><span data-stu-id="3720e-127">The phone number of the Contact object is 2065554567.</span></span> <span data-ttu-id="3720e-128">オプション-AutoAttendant $True パラメーターは、このオブジェクトが自動応答の連絡先オブジェクトであることを指定します。</span><span class="sxs-lookup"><span data-stu-id="3720e-128">The optional -AutoAttendant $True parameter specifies that this object is an auto-attendant Contact object.</span></span> <span data-ttu-id="3720e-129">-AutoAttendant パラメーターを False に設定する (既定) サブスクライバーアクセスの連絡先オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="3720e-129">Setting the -AutoAttendant parameter to False (the default) specifies a subscriber access Contact object.</span></span>

<span data-ttu-id="3720e-130">新しい-CsExUmContact と Set-CsExUmContact コマンドレットの詳細については、「Lync Server 管理シェルのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3720e-130">For details about the New-CsExUmContact and Set-CsExUmContact cmdlets, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

