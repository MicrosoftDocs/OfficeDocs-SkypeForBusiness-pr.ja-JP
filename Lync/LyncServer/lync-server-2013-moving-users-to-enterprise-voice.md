---
title: 'Lync Server 2013: エンタープライズ VoIP へのユーザーの移行'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving users to Enterprise Voice
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412758(v=OCS.15)
ms:contentKeyID: 48184958
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e92f0a7d71d42d8551a51028afec209e795941d5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="3e478-102">Lync Server 2013 でのエンタープライズ VoIP へのユーザーの移行</span><span class="sxs-lookup"><span data-stu-id="3e478-102">Moving users to Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e478-103">_**最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="3e478-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="3e478-104">既存の PBX テレフォニーインフラストラクチャからエンタープライズ Voip にユーザーを移動する場合、展開プロセスには、「 [Lync Server 2013 でのエンタープライズ voip の計画](lync-server-2013-planning-for-enterprise-voice.md)」で説明されている計画プロセスに含まれていないいくつかの手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3e478-104">If you are moving users from an existing PBX telephony infrastructure to Enterprise Voice, the deployment process includes some steps that are not part of the planning process already described in [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span></span> <span data-ttu-id="3e478-105">以前のエンタープライズ Voip 展開からユーザーを移行する方法については、インストールメディアに含まれている移行ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e478-105">For information about migrating users from an earlier Enterprise Voice deployment, see the migration documents that were included with your installation media.</span></span>

<span data-ttu-id="3e478-106">既存のテレフォニーインフラストラクチャからエンタープライズボイスにユーザーを移動するプロセスは、次の手順で構成されます。</span><span class="sxs-lookup"><span data-stu-id="3e478-106">The process of moving users from an existing telephony infrastructure to Enterprise Voice consists of the following steps:</span></span>

1.  <span data-ttu-id="3e478-107">主要な電話番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="3e478-107">Designate primary phone numbers.</span></span>

2.  <span data-ttu-id="3e478-108">エンタープライズ VoIP に対してユーザーを有効化します。</span><span class="sxs-lookup"><span data-stu-id="3e478-108">Enable users for Enterprise Voice.</span></span>

3.  <span data-ttu-id="3e478-109">ユーザー向けにダイヤルプランを準備します。</span><span class="sxs-lookup"><span data-stu-id="3e478-109">Prepare dial plans for users.</span></span>

4.  <span data-ttu-id="3e478-110">ユーザーの音声ポリシーを計画します。</span><span class="sxs-lookup"><span data-stu-id="3e478-110">Plan user voice policies.</span></span>

5.  <span data-ttu-id="3e478-111">通話ルートを計画します。</span><span class="sxs-lookup"><span data-stu-id="3e478-111">Plan call routes.</span></span>

6.  <span data-ttu-id="3e478-112">PBX または SIP トランクを構成して、エンタープライズ Voip を有効にしているユーザーの通話を再ルーティングします。</span><span class="sxs-lookup"><span data-stu-id="3e478-112">Configure PBX or SIP Trunk to reroute calls for users enabled for Enterprise Voice.</span></span>

7.  <span data-ttu-id="3e478-113">Exchange ユニファイドメッセージング (UM) にユーザーを移動する (推奨)</span><span class="sxs-lookup"><span data-stu-id="3e478-113">Move users to Exchange Unified Messaging (UM) (recommended).</span></span>

<span data-ttu-id="3e478-114">このトピックでは、これらの各手順に必要な計画について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e478-114">This topic describes the planning that is necessary for each of these steps.</span></span>

<div>

## <a name="step-1-designate-primary-phone-numbers"></a><span data-ttu-id="3e478-115">手順1</span><span class="sxs-lookup"><span data-stu-id="3e478-115">Step 1.</span></span> <span data-ttu-id="3e478-116">主要な電話番号を指定する</span><span class="sxs-lookup"><span data-stu-id="3e478-116">Designate primary phone numbers</span></span>

<span data-ttu-id="3e478-117">エンタープライズボイスは、音声を他のメッセージメディアと統合します。着信がサーバーに到着すると、サーバーはその番号をユーザーの SIP URI にマップし、その SIP URI に関連付けられているすべてのクライアントエンドポイントへの呼び出しをフォークします。</span><span class="sxs-lookup"><span data-stu-id="3e478-117">Enterprise Voice integrates voice with other messaging media, such that when an incoming call arrives at the server, the server maps the number to the user’s SIP-URI and then forks the call to all the client endpoints associated with that SIP-URI.</span></span> <span data-ttu-id="3e478-118">このプロセスでは、各ユーザーが通常の電話番号に関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e478-118">This process requires that each user be associated with a primary phone number.</span></span>

<span data-ttu-id="3e478-119">主要な電話番号は、次のようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e478-119">A primary phone number must be:</span></span>

  - <span data-ttu-id="3e478-120">グローバル一意または内部拡張の場合は、企業内で一意。</span><span class="sxs-lookup"><span data-stu-id="3e478-120">Globally unique or, in the case of internal extensions, unique in the enterprise.</span></span>

  - <span data-ttu-id="3e478-121">企業内での所有者とルーティング経路。</span><span class="sxs-lookup"><span data-stu-id="3e478-121">Owned by and routable in the enterprise.</span></span> <span data-ttu-id="3e478-122">個人番号は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="3e478-122">Personal numbers should not be used.</span></span>

<span data-ttu-id="3e478-123">エンタープライズユーザーは、Active Directory ドメインサービスで2つ以上の電話番号を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="3e478-123">Enterprise users can have two or more telephone numbers listed for them in Active Directory Domain Services.</span></span> <span data-ttu-id="3e478-124">特定のユーザーに関連付けられているすべての電話番号は、[Active Directory ユーザーとコンピューター] スナップインで、そのユーザーのプロパティシートで確認または変更することができます。</span><span class="sxs-lookup"><span data-stu-id="3e478-124">All the telephone numbers associated with a particular user can be viewed or changed on the property sheet for that user in the Active Directory Users and Computers snap-in.</span></span>

<span data-ttu-id="3e478-125">[**ユーザーのプロパティ**] ダイアログボックスの [**全般**] タブの [**電話番号**] ボックスには、ユーザーの主要作業番号が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e478-125">The **Telephone number** box on the **General** tab of the **User Properties** dialog box should contain the user’s main work number.</span></span> <span data-ttu-id="3e478-126">通常、この番号はユーザーのプライマリ電話番号として指定されます。</span><span class="sxs-lookup"><span data-stu-id="3e478-126">This number will usually be designated as the user's Primary Phone Number.</span></span>

<span data-ttu-id="3e478-127">一部のユーザーは、特別な要件がある場合があります (たとえば、すべての着信通話を管理アシスタント経由でルーティングする場合など)。ただし、そのような例外は、必要な情報が明らかで重要である場合にのみ制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e478-127">Some users may have special requirements (for example, an executive who wants all incoming calls routed through an administrative assistant), but such exceptions should be limited only to those where the need is clear and critical.</span></span>

<span data-ttu-id="3e478-128">1つ目の番号を選ぶと、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3e478-128">After a primary number is chosen, it must be:</span></span>

  - <span data-ttu-id="3e478-129">可能な限り、E-164 形式に正規化されます。</span><span class="sxs-lookup"><span data-stu-id="3e478-129">Normalized to E.164 format, wherever possible.</span></span>

  - <span data-ttu-id="3e478-130">Active Directory **msrtcsip-userenabled true line**属性にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="3e478-130">Copied to the Active Directory **msRTCSIP-line** attribute.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3e478-131"><STRONG>リモート通話コントロール (RCC) との共存</STRONG></span><span class="sxs-lookup"><span data-stu-id="3e478-131"><STRONG>Coexisting with remote call control (RCC)</STRONG></span></span><BR><span data-ttu-id="3e478-132">RCC は、Lync Server を使用して、デスクトップ PBX 携帯電話を監視および制御する機能です。</span><span class="sxs-lookup"><span data-stu-id="3e478-132">RCC is the ability to use Lync Server to monitor and control a desktop PBX phone.</span></span> <span data-ttu-id="3e478-133">コントロールはサーバー経由でルーティングされ、PBX へのゲートウェイとして機能します。</span><span class="sxs-lookup"><span data-stu-id="3e478-133">Control is routed through the server, which acts as a gateway to the PBX.</span></span> <span data-ttu-id="3e478-134">RCC とエンタープライズボイスの両方のユーザーを構成することはできませんが、[Line URI] の設定ではどちらの場合でも、ユーザーのプライマリ電話番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="3e478-134">Although you cannot configure a user for both RCC and Enterprise Voice, the Line URI setting designates a user’s primary phone number in either case.</span></span><BR><span data-ttu-id="3e478-135">選択したユーザーが引き続き使用できるようにする既存の PBX インフラストラクチャがある場合は、エンタープライズボイスを組織に段階的に導入することができます。</span><span class="sxs-lookup"><span data-stu-id="3e478-135">If you have an existing PBX infrastructure that you want selected users to continue using, you can introduce Enterprise Voice incrementally into your organization.</span></span> <span data-ttu-id="3e478-136">この展開シナリオの詳細については、計画ドキュメントの「 <A href="lync-server-2013-direct-sip-deployment-options.md">SIP 展開オプションと Lync Server 2013」</A>を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e478-136">For details about this deployment scenario, see <A href="lync-server-2013-direct-sip-deployment-options.md">Direct SIP deployment options in Lync Server 2013</A> in the Planning documentation.</span></span><BR><span data-ttu-id="3e478-137">以前のリリースでは、ユーザーに対して RCC とエンタープライズボイスの両方を有効にすることができます。ただし、デュアルフォーク用にユーザーを構成している場合のみ、着信時にユーザーの PBX 電話と Communicator が同時に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3e478-137">In previous releases, you could enable both RCC and Enterprise Voice for a user, but only if you also configured the user for dual forking, a feature in which an incoming call will ring a user’s PBX phone and Communicator simultaneously.</span></span> <span data-ttu-id="3e478-138">Lync Server 2010 では、デュアルフォーキングはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3e478-138">In Lync Server 2010, dual-forking is not supported.</span></span>

    
    </div>

<span data-ttu-id="3e478-139">**Msrtcsip-userenabled true**属性を設定するには、次の3つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="3e478-139">There are three methods for populating the **msRTCSIP-line** attribute:</span></span>

  - <span data-ttu-id="3e478-140">Microsoft Identity Integration Server (推奨)</span><span class="sxs-lookup"><span data-stu-id="3e478-140">Microsoft Identity Integration Server (recommended)</span></span>

  - <span data-ttu-id="3e478-141">Lync Server コントロールパネルの [**ユーザー** ] ページ</span><span class="sxs-lookup"><span data-stu-id="3e478-141">The **Users** page in the Lync Server Control Panel</span></span>

<span data-ttu-id="3e478-142">いくつかの電話番号を処理する必要があるので、組織によって開発されたスクリプトが適しています。</span><span class="sxs-lookup"><span data-stu-id="3e478-142">Where many phone numbers must be processed, a script custom developed by your organization is the better choice.</span></span> <span data-ttu-id="3e478-143">Active Directory ドメインサービスでの電話番号の表示方法によっては、スクリプトは、プライマリ電話番号を Msrtcsip-userenabled true 形式に正規化してから、それらを**line**属性にコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e478-143">Depending on how your organization represents telephone numbers in Active Directory Domain Services, the script may have to normalize primary phone numbers to E.164 format before copying them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="3e478-144">組織で Active Directory ドメインサービスのすべての電話番号を1つの形式で管理していて、その形式が E.i の場合、スクリプトでは、各主要な電話番号を Msrtcsip-userenabled true 属性に書き込むだけで**対応**する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e478-144">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, and if that format is E.164, your script only needs to write each Primary Telephone Number to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="3e478-145">組織で Active Directory ドメインサービスのすべての電話番号を1つの形式で管理しているが、その形式が E.i ではない場合、スクリプトでは、プライマリ電話番号を既存の形式から**msrtcsip-userenabled true**に変換する前に、対応する正規化ルールを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e478-145">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, but that format is not E.164, your script should define an appropriate normalization rule to convert Primary Telephone Numbers from their existing format to E.164 before writing them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="3e478-146">組織で Active Directory ドメインサービスの電話番号の標準形式を適用していない場合は、主要な電話番号を**msrtcsip-userenabled true line**属性に書き込む前に、主要な電話番号をさまざまな形式から e.i コンプライアンスに変換するために、スクリプトで適切な正規化ルールを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e478-146">If your organization does not enforce a standard format for telephone numbers in Active Directory Domain Services, your script should define appropriate normalization rules to convert Primary Phone Numbers from their various formats to E.164 compliance before writing the Primary Telephone Numbers to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="3e478-147">また、スクリプトでは、 **msrtcsip-userenabled true**属性に書き込む前に、各プライマリ番号の前に " **Tel** " というプレフィックスを挿入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e478-147">Your script will also have to insert the prefix **Tel:** before each primary number before writing it to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="3e478-148">この属性で指定する数値の予期される形式は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3e478-148">The expected format of the number specified in this attribute is:</span></span>

  - <span data-ttu-id="3e478-149">Tel: + 14255550100; ext = 50100</span><span class="sxs-lookup"><span data-stu-id="3e478-149">Tel:+14255550100;ext=50100.</span></span>

  - <span data-ttu-id="3e478-150">Tel: 5550100 (エンタープライズ規模の固有の拡張機能)</span><span class="sxs-lookup"><span data-stu-id="3e478-150">Tel:5550100 (for unique enterprise wide extensions)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3e478-151">アドレス帳サービス (ABS) によって実行される正規化によって、active Directory ドメインサービスへのアクセス権がなく、また、プライマリ番号を<STRONG>msrtcsip-userenabled true</STRONG>属性にコピーできないことが原因で、Active Directory ドメインサービスで各ユーザーの主要な電話番号を正規化する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="3e478-151">The normalization performed by the Address Book Service (ABS) does not replace or otherwise eliminate the need to normalize each user's primary phone number in Active Directory Domain Services because ABS does not have access to Active Directory Domain Services and therefore cannot copy primary numbers to the <STRONG>msRTCSIP-line</STRONG> attribute.</span></span>

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a><span data-ttu-id="3e478-152">手順2</span><span class="sxs-lookup"><span data-stu-id="3e478-152">Step 2.</span></span> <span data-ttu-id="3e478-153">エンタープライズ VoIP に対するユーザーの有効化</span><span class="sxs-lookup"><span data-stu-id="3e478-153">Enable users for Enterprise Voice</span></span>

<span data-ttu-id="3e478-154">有効にするユーザーを特定する以外に、この手順を完了するために特別な計画は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="3e478-154">Other than identifying which users are to be enabled, no special planning is required to complete this step.</span></span>

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a><span data-ttu-id="3e478-155">手順3</span><span class="sxs-lookup"><span data-stu-id="3e478-155">Step 3.</span></span> <span data-ttu-id="3e478-156">ユーザー向けにダイヤルプランを準備します。</span><span class="sxs-lookup"><span data-stu-id="3e478-156">Prepare dial plans for users.</span></span>

<span data-ttu-id="3e478-157">エンタープライズ Voip を有効にしているユーザーは、ダイヤルプランを使わずに PSTN に通話することはできません。</span><span class="sxs-lookup"><span data-stu-id="3e478-157">Users who are enabled for Enterprise Voice will not be able to make calls to the PSTN without dial plans in place.</span></span> <span data-ttu-id="3e478-158">ダイヤル プランとは、電話番号の承認と通話のルーティングを目的として、特定の場所、個々のユーザー、または連絡先オブジェクトの電話番号を 1 つの標準形式 (E.164) に変換する正規化ルールのセットに名前を付けたものです。</span><span class="sxs-lookup"><span data-stu-id="3e478-158">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span> <span data-ttu-id="3e478-159">正規化ルールは、さまざまな形式で表現された電話番号を指定された各場所、ユーザー、または連絡先オブジェクトにルーティングする方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="3e478-159">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span>

<span data-ttu-id="3e478-160">ダイヤルプランを準備する方法については、「 [Lync Server 2013 のダイヤルプランと正規化ルール](lync-server-2013-dial-plans-and-normalization-rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e478-160">For information about preparing dial plans, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span></span>

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a><span data-ttu-id="3e478-161">手順4。</span><span class="sxs-lookup"><span data-stu-id="3e478-161">Step 4.</span></span> <span data-ttu-id="3e478-162">ユーザーの音声ポリシーを計画する</span><span class="sxs-lookup"><span data-stu-id="3e478-162">Plan user voice policies</span></span>

<span data-ttu-id="3e478-163">会社の電話から長距離または国際通話を発信する権利など、従来の PBX でのユーザークラスの設定は、エンタープライズ voip に移行されたユーザーのために VoIP ポリシーとして再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e478-163">User class-of-service settings on a legacy PBX, such as the right to make long-distance or international calls from company phones, must be reconfigured as VoIP policies for users moved to Enterprise Voice.</span></span> <span data-ttu-id="3e478-164">エンタープライズ Voip のポリシーの計画と作成について詳しくは、「 [Lync Server 2013 の音声ポリシー](lync-server-2013-voice-policies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3e478-164">For details about planning and creating policies for Enterprise Voice, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md).</span></span>

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a><span data-ttu-id="3e478-165">手順5</span><span class="sxs-lookup"><span data-stu-id="3e478-165">Step 5.</span></span> <span data-ttu-id="3e478-166">発信通話ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="3e478-166">Plan outbound call routes</span></span>

<span data-ttu-id="3e478-167">通話ルートは、Lync Server がエンタープライズボイスユーザーによる発信通話をどのように処理するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3e478-167">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="3e478-168">ユーザーが番号をダイヤルすると、サーバーは、必要に応じて、ダイヤル文字列を E.i 形式に標準化し、SIP URI と一致させようとします。</span><span class="sxs-lookup"><span data-stu-id="3e478-168">When a user dials a number, the server, if necessary, normalizes the dial string to E.164 format and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="3e478-169">サーバーで一致させることができない場合は、その番号に基づいて発信呼び出しのルーティングロジックが適用されます。</span><span class="sxs-lookup"><span data-stu-id="3e478-169">If the server is unable to make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="3e478-170">ロジックを定義するための最後の手順では、各ダイヤルプランに記載されている宛先電話番号のセットごとに、個別の名前付き通話ルートを作成します。</span><span class="sxs-lookup"><span data-stu-id="3e478-170">The final step in defining that logic is creating a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="3e478-171">通話ルートの計画について詳しくは、「 [Lync Server 2013 のボイスルーティング](lync-server-2013-voice-routes.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3e478-171">For details about planning call routes, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a><span data-ttu-id="3e478-172">手順6</span><span class="sxs-lookup"><span data-stu-id="3e478-172">Step 6.</span></span> <span data-ttu-id="3e478-173">エンタープライズボイスユーザーの通話の経路を変更するために PBX または SIP トランクを構成する</span><span class="sxs-lookup"><span data-stu-id="3e478-173">Configure PBX or SIP Trunk to reroute calls for Enterprise Voice users</span></span>

<span data-ttu-id="3e478-174">以前は、従来の PBX または SIP トランクでインターネットテレフォニーサービスプロバイダ (ITSP) にホストされていたユーザーは、移動後も電話番号を維持します。</span><span class="sxs-lookup"><span data-stu-id="3e478-174">Users who formerly were hosted on a traditional PBX or on a SIP Trunk connection to an Internet Telephony Service Provider (ITSP) retain their phone numbers after the move.</span></span> <span data-ttu-id="3e478-175">唯一の要件として、移動後、PBX または SIP トランクを再構成して、エンタープライズ Voip ユーザーの着信通話を仲介サーバーにルーティングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e478-175">The only requirement is that after the move, the PBX or SIP Trunk must be reconfigured to route incoming calls for Enterprise Voice users to the Mediation Server.</span></span>

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a><span data-ttu-id="3e478-176">手順7</span><span class="sxs-lookup"><span data-stu-id="3e478-176">Step 7.</span></span> <span data-ttu-id="3e478-177">ユーザーを Exchange ユニファイドメッセージングに移行する (推奨)</span><span class="sxs-lookup"><span data-stu-id="3e478-177">Move users to Exchange Unified Messaging (recommended)</span></span>

<span data-ttu-id="3e478-178">Exchange ユニファイドメッセージングにユーザーを移行するには、次のタスクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3e478-178">Moving users to Exchange Unified Messaging consists of the following tasks:</span></span>

  - <span data-ttu-id="3e478-179">共同作業のために Exchange ユニファイドメッセージングと Lync Server を構成します。</span><span class="sxs-lookup"><span data-stu-id="3e478-179">Configure Exchange Unified Messaging and Lync Server to work together.</span></span>

  - <span data-ttu-id="3e478-180">ユーザーが Exchange ユニファイドメッセージングの通話応答と Outlook Voice Access を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3e478-180">Enable users for Exchange Unified Messaging call answering and Outlook Voice Access.</span></span> <span data-ttu-id="3e478-181">このタスクは、Exchange ユニファイドメッセージングサーバー上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="3e478-181">This task is performed on the Exchange Unified Messaging server.</span></span> <span data-ttu-id="3e478-182">詳細については、「Exchange Server 2010 TechNet [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372)ライブラリ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e478-182">For details, see the Exchange Server 2010 TechNet Library at [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

