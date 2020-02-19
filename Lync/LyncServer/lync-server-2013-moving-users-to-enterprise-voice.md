---
title: 'Lync Server 2013: エンタープライズ Voip へのユーザーの移動'
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
ms.openlocfilehash: 968e70e74cd129f05d4f39f626d9e21b1c3dc33a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42131150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="28c14-102">Lync Server 2013 でのエンタープライズ Voip へのユーザーの移動</span><span class="sxs-lookup"><span data-stu-id="28c14-102">Moving users to Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28c14-103">_**トピックの最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="28c14-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="28c14-104">既存の PBX テレフォニーインフラストラクチャからエンタープライズ Voip にユーザーを移動する場合、展開プロセスには、「 [Lync Server 2013 でのエンタープライズ voip の計画](lync-server-2013-planning-for-enterprise-voice.md)」で説明されている計画プロセスの一部ではないいくつかの手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="28c14-104">If you are moving users from an existing PBX telephony infrastructure to Enterprise Voice, the deployment process includes some steps that are not part of the planning process already described in [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span></span> <span data-ttu-id="28c14-105">以前に展開したエンタープライズ VoIP からのユーザー移行の詳細については、インストール メディアに含まれている「移行」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="28c14-105">For information about migrating users from an earlier Enterprise Voice deployment, see the migration documents that were included with your installation media.</span></span>

<span data-ttu-id="28c14-106">既存のテレフォニー インフラストラクチャからエンタープライズ VoIP にユーザーを移動するプロセスは、次のステップで構成されます。</span><span class="sxs-lookup"><span data-stu-id="28c14-106">The process of moving users from an existing telephony infrastructure to Enterprise Voice consists of the following steps:</span></span>

1.  <span data-ttu-id="28c14-107">主要電話番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="28c14-107">Designate primary phone numbers.</span></span>

2.  <span data-ttu-id="28c14-108">エンタープライズ VoIP に対してユーザーを有効化します。</span><span class="sxs-lookup"><span data-stu-id="28c14-108">Enable users for Enterprise Voice.</span></span>

3.  <span data-ttu-id="28c14-109">ユーザー向けのダイヤル プランを準備します。</span><span class="sxs-lookup"><span data-stu-id="28c14-109">Prepare dial plans for users.</span></span>

4.  <span data-ttu-id="28c14-110">ユーザーの音声ポリシーを計画します。</span><span class="sxs-lookup"><span data-stu-id="28c14-110">Plan user voice policies.</span></span>

5.  <span data-ttu-id="28c14-111">通話ルートを計画します。</span><span class="sxs-lookup"><span data-stu-id="28c14-111">Plan call routes.</span></span>

6.  <span data-ttu-id="28c14-112">エンタープライズ VoIP に対して有効化されたユーザーの通話を再ルーティングするように PBX または SIP トランクを構成します。</span><span class="sxs-lookup"><span data-stu-id="28c14-112">Configure PBX or SIP Trunk to reroute calls for users enabled for Enterprise Voice.</span></span>

7.  <span data-ttu-id="28c14-113">ユーザーを Exchange ユニファイドメッセージング (UM) に移動します (推奨)。</span><span class="sxs-lookup"><span data-stu-id="28c14-113">Move users to Exchange Unified Messaging (UM) (recommended).</span></span>

<span data-ttu-id="28c14-114">このトピックでは、これらの各ステップに必要な計画について説明します。</span><span class="sxs-lookup"><span data-stu-id="28c14-114">This topic describes the planning that is necessary for each of these steps.</span></span>

<div>

## <a name="step-1-designate-primary-phone-numbers"></a><span data-ttu-id="28c14-p102">ステップ 1. 主要電話番号を指定する</span><span class="sxs-lookup"><span data-stu-id="28c14-p102">Step 1. Designate primary phone numbers</span></span>

<span data-ttu-id="28c14-p103">エンタープライズ VoIP により、音声と他のメッセージング メディアが統合されます。着信通話がサーバーに到着すると、サーバーはその番号をユーザーの SIP URI にマッピングし、該当の SIP URI に関連付けられたすべてのクライアント エンドポイントに通話を分岐させます。このプロセスでは、各ユーザーが主要電話番号に関連付けられていることが必要になります。</span><span class="sxs-lookup"><span data-stu-id="28c14-p103">Enterprise Voice integrates voice with other messaging media, such that when an incoming call arrives at the server, the server maps the number to the user’s SIP-URI and then forks the call to all the client endpoints associated with that SIP-URI. This process requires that each user be associated with a primary phone number.</span></span>

<span data-ttu-id="28c14-119">主要電話番号の要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="28c14-119">A primary phone number must be:</span></span>

  - <span data-ttu-id="28c14-120">グローバルに一意であること。内線番号の場合は企業内で一意であること。</span><span class="sxs-lookup"><span data-stu-id="28c14-120">Globally unique or, in the case of internal extensions, unique in the enterprise.</span></span>

  - <span data-ttu-id="28c14-p104">企業が所有し、企業内でルーティングできること。個人用の番号を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="28c14-p104">Owned by and routable in the enterprise. Personal numbers should not be used.</span></span>

<span data-ttu-id="28c14-123">エンタープライズユーザーは、Active Directory ドメインサービスに2つ以上の電話番号を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="28c14-123">Enterprise users can have two or more telephone numbers listed for them in Active Directory Domain Services.</span></span> <span data-ttu-id="28c14-124">特定のユーザーに関連付けられたすべての電話番号は、Active Directory ユーザーとコンピューターのスナップインで、そのユーザーのプロパティ シートを使用して表示または変更できます。</span><span class="sxs-lookup"><span data-stu-id="28c14-124">All the telephone numbers associated with a particular user can be viewed or changed on the property sheet for that user in the Active Directory Users and Computers snap-in.</span></span>

<span data-ttu-id="28c14-p106">**[ユーザーのプロパティ]** ダイアログ ボックスの **[全般]** タブの **[電話番号]** ボックスには、ユーザーの主要な勤務先番号が表示されています。通常、この番号がユーザーの主要電話番号として指定されます。</span><span class="sxs-lookup"><span data-stu-id="28c14-p106">The **Telephone number** box on the **General** tab of the **User Properties** dialog box should contain the user’s main work number. This number will usually be designated as the user's Primary Phone Number.</span></span>

<span data-ttu-id="28c14-127">一部のユーザーが特殊な要件を持つ場合がありますが (すべての着信通話を管理スタッフ経由でルーティングすることを希望する役員など)、このような例外はその必要性が明確かつ重要であるものだけに限定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28c14-127">Some users may have special requirements (for example, an executive who wants all incoming calls routed through an administrative assistant), but such exceptions should be limited only to those where the need is clear and critical.</span></span>

<span data-ttu-id="28c14-128">主要電話番号を選択したら、その番号に対して次の処理を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="28c14-128">After a primary number is chosen, it must be:</span></span>

  - <span data-ttu-id="28c14-129">可能な限り、E.164 形式に正規化します。</span><span class="sxs-lookup"><span data-stu-id="28c14-129">Normalized to E.164 format, wherever possible.</span></span>

  - <span data-ttu-id="28c14-130">Active Directory の **msRTCSIP-line** 属性にコピーします。</span><span class="sxs-lookup"><span data-stu-id="28c14-130">Copied to the Active Directory **msRTCSIP-line** attribute.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="28c14-131"><STRONG>リモート通話コントロール (RCC) との共存</STRONG></span><span class="sxs-lookup"><span data-stu-id="28c14-131"><STRONG>Coexisting with remote call control (RCC)</STRONG></span></span><BR><span data-ttu-id="28c14-132">RCC は、Lync Server を使用して、デスクトップ PBX 電話を監視および制御する機能です。</span><span class="sxs-lookup"><span data-stu-id="28c14-132">RCC is the ability to use Lync Server to monitor and control a desktop PBX phone.</span></span> <span data-ttu-id="28c14-133">コントロールは、PBX へのゲートウェイとして機能するサーバー経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="28c14-133">Control is routed through the server, which acts as a gateway to the PBX.</span></span> <span data-ttu-id="28c14-134">RCC と エンタープライズ VoIP の両方に対してユーザーを構成することはできませんが、どちらの場合も、回線 URI 設定はユーザーの主要電話番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="28c14-134">Although you cannot configure a user for both RCC and Enterprise Voice, the Line URI setting designates a user’s primary phone number in either case.</span></span><BR><span data-ttu-id="28c14-135">既に PBX インフラストラクチャが存在し、一部のユーザーに引き続き使用させたい場合は、徐々にエンタープライズ VoIP を組織へ導入することができます。</span><span class="sxs-lookup"><span data-stu-id="28c14-135">If you have an existing PBX infrastructure that you want selected users to continue using, you can introduce Enterprise Voice incrementally into your organization.</span></span> <span data-ttu-id="28c14-136">この展開シナリオの詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-direct-sip-deployment-options.md">DIRECT SIP deployment options In Lync Server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28c14-136">For details about this deployment scenario, see <A href="lync-server-2013-direct-sip-deployment-options.md">Direct SIP deployment options in Lync Server 2013</A> in the Planning documentation.</span></span><BR><span data-ttu-id="28c14-137">以前のリリースでは、ユーザーに対して RCC とエンタープライズボイスの両方を有効にすることができましたが、デュアルフォーク用にユーザーを構成した場合に限り、着信呼び出しがユーザーの PBX 電話と Communicator を同時に呼び出す機能を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="28c14-137">In previous releases, you could enable both RCC and Enterprise Voice for a user, but only if you also configured the user for dual forking, a feature in which an incoming call will ring a user’s PBX phone and Communicator simultaneously.</span></span> <span data-ttu-id="28c14-138">Lync Server 2010 では、デュアルフォークはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="28c14-138">In Lync Server 2010, dual-forking is not supported.</span></span>

    
    </div>

<span data-ttu-id="28c14-139">**msRTCSIP-line** 属性を設定するには、次の 3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="28c14-139">There are three methods for populating the **msRTCSIP-line** attribute:</span></span>

  - <span data-ttu-id="28c14-140">Microsoft Identity Integration Server (推奨)</span><span class="sxs-lookup"><span data-stu-id="28c14-140">Microsoft Identity Integration Server (recommended)</span></span>

  - <span data-ttu-id="28c14-141">Lync Server コントロールパネルの [**ユーザー** ] ページ</span><span class="sxs-lookup"><span data-stu-id="28c14-141">The **Users** page in the Lync Server Control Panel</span></span>

<span data-ttu-id="28c14-142">多くの電話番号を処理する必要がある場合は、組織によって開発されたカスタムスクリプトを選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="28c14-142">Where many phone numbers must be processed, a script custom developed by your organization is the better choice.</span></span> <span data-ttu-id="28c14-143">組織が Active Directory ドメイン サービスで電話番号をどのように表しているかに応じて、スクリプトで主要電話番号を **msRTCSIP-line** 属性にコピーする前に E.164 形式に正規化することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="28c14-143">Depending on how your organization represents telephone numbers in Active Directory Domain Services, the script may have to normalize primary phone numbers to E.164 format before copying them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="28c14-144">組織が Active Directory ドメイン サービスにすべての電話番号を同じ形式で保持しており、さらにその形式が E.164 である場合、スクリプトでは各主要電話番号を **msRTCSIP-line** 属性に書き込むだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="28c14-144">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, and if that format is E.164, your script only needs to write each Primary Telephone Number to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="28c14-145">Active Directory ドメイン サービスにすべての電話番号を同じ形式で保持している場合でも、その形式が E.164 ではないときには、スクリプトで適切な正規化ルールを定義して主要電話番号を既存の形式から E.164 に変換してから、**msRTCSIP-line** 属性に書き込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="28c14-145">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, but that format is not E.164, your script should define an appropriate normalization rule to convert Primary Telephone Numbers from their existing format to E.164 before writing them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="28c14-146">組織が Active Directory ドメイン サービスで電話番号の標準形式を適用していない場合は、スクリプトで適切な正規化ルールを定義して主要電話番号をさまざまな形式から E.164 準拠に変換してから、**msRTCSIP-line** 属性に書き込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="28c14-146">If your organization does not enforce a standard format for telephone numbers in Active Directory Domain Services, your script should define appropriate normalization rules to convert Primary Phone Numbers from their various formats to E.164 compliance before writing the Primary Telephone Numbers to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="28c14-147">スクリプトでは、**msRTCSIP-line** 属性に主要電話番号を書き込む前に、各番号の前にプレフィックス **Tel:** を挿入することも必要となります。</span><span class="sxs-lookup"><span data-stu-id="28c14-147">Your script will also have to insert the prefix **Tel:** before each primary number before writing it to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="28c14-148">この属性で指定する番号に求められる形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="28c14-148">The expected format of the number specified in this attribute is:</span></span>

  - <span data-ttu-id="28c14-149">Tel: + 14255550100; ext = 50100。</span><span class="sxs-lookup"><span data-stu-id="28c14-149">Tel:+14255550100;ext=50100.</span></span>

  - <span data-ttu-id="28c14-150">Tel:5550100 (企業全体で一意の内線番号の場合)</span><span class="sxs-lookup"><span data-stu-id="28c14-150">Tel:5550100 (for unique enterprise wide extensions)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="28c14-151">アドレス帳サービス (ABS) によって実行される正規化では、Active Directory ドメイン サービス内で 各ユーザーの主要電話番号が置き換えられるわけではなく、正規化する必要性がなくなるわけでもありません。ABS は Active Directory ドメイン サービスにアクセスできないため、主要電話番号を <STRONG>msRTCSIP-line</STRONG> 属性にコピーできません。</span><span class="sxs-lookup"><span data-stu-id="28c14-151">The normalization performed by the Address Book Service (ABS) does not replace or otherwise eliminate the need to normalize each user's primary phone number in Active Directory Domain Services because ABS does not have access to Active Directory Domain Services and therefore cannot copy primary numbers to the <STRONG>msRTCSIP-line</STRONG> attribute.</span></span>

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a><span data-ttu-id="28c14-p111">ステップ 2. ユーザーをエンタープライズ VoIP に対して有効にする</span><span class="sxs-lookup"><span data-stu-id="28c14-p111">Step 2. Enable users for Enterprise Voice</span></span>

<span data-ttu-id="28c14-154">有効化するユーザーを特定する以外に、このステップを完了するために必要な特別な計画はありません。</span><span class="sxs-lookup"><span data-stu-id="28c14-154">Other than identifying which users are to be enabled, no special planning is required to complete this step.</span></span>

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a><span data-ttu-id="28c14-p112">ステップ 3. ユーザー向けのダイヤル プランを準備する</span><span class="sxs-lookup"><span data-stu-id="28c14-p112">Step 3. Prepare dial plans for users.</span></span>

<span data-ttu-id="28c14-p113">エンタープライズ VoIP に対して有効にされたユーザーは、ダイヤル プランがないと PSTN へ電話をかけることができません。ダイヤル プランとは、電話番号の承認と通話のルーティングを目的として、特定の場所、個々のユーザー、または連絡先オブジェクトの電話番号を 1 つの標準形式 (E.164) に変換する正規化ルールのセットに名前を付けたものです。正規化ルールは、さまざまな形式で表現された電話番号を指定された各場所、ユーザー、または連絡先オブジェクトにルーティングする方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="28c14-p113">Users who are enabled for Enterprise Voice will not be able to make calls to the PSTN without dial plans in place. A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing. Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span>

<span data-ttu-id="28c14-160">ダイヤルプランの準備の詳細については、「 [Lync Server 2013 のダイヤルプランと正規化ルール](lync-server-2013-dial-plans-and-normalization-rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28c14-160">For information about preparing dial plans, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span></span>

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a><span data-ttu-id="28c14-161">ステップ 4.</span><span class="sxs-lookup"><span data-stu-id="28c14-161">Step 4.</span></span> <span data-ttu-id="28c14-162">ユーザーの音声ポリシーを計画する</span><span class="sxs-lookup"><span data-stu-id="28c14-162">Plan user voice policies</span></span>

<span data-ttu-id="28c14-163">エンタープライズ VoIP に移動するユーザーについては、企業の電話から長距離通話や国際通話を利用する権利などの従来の PBX 上のユーザー クラス オブ サービス (CoS) 設定を VoIP ポリシーとして再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28c14-163">User class-of-service settings on a legacy PBX, such as the right to make long-distance or international calls from company phones, must be reconfigured as VoIP policies for users moved to Enterprise Voice.</span></span> <span data-ttu-id="28c14-164">エンタープライズ Voip のポリシーの計画と作成の詳細については、「 [Lync Server 2013 の音声ポリシー](lync-server-2013-voice-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28c14-164">For details about planning and creating policies for Enterprise Voice, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md).</span></span>

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a><span data-ttu-id="28c14-165">ステップ 5.</span><span class="sxs-lookup"><span data-stu-id="28c14-165">Step 5.</span></span> <span data-ttu-id="28c14-166">発信通話ルートを計画する</span><span class="sxs-lookup"><span data-stu-id="28c14-166">Plan outbound call routes</span></span>

<span data-ttu-id="28c14-167">通話ルートは、Lync Server がエンタープライズ Voip ユーザーによって送信される発信呼び出しを処理する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="28c14-167">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="28c14-168">ユーザーが番号をダイヤルすると、サーバーは、必要に応じて、ダイヤル文字列を E.164 形式に正規化し、一致する SIP URI があるかどうかを調べます。</span><span class="sxs-lookup"><span data-stu-id="28c14-168">When a user dials a number, the server, if necessary, normalizes the dial string to E.164 format and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="28c14-169">一致する SIP URI が見つからない場合は、番号に基づいて発信通話ルーティング ロジックが適用されます。</span><span class="sxs-lookup"><span data-stu-id="28c14-169">If the server is unable to make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="28c14-170">発信通話ルーティング ロジックを定義する最後のステップでは、ダイヤル プランごとの各相手電話番号に対して、個別の名前が付けられた通話ルートが作成されます。</span><span class="sxs-lookup"><span data-stu-id="28c14-170">The final step in defining that logic is creating a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="28c14-171">通話ルートの計画の詳細については、「 [Lync Server 2013 の音声ルート](lync-server-2013-voice-routes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28c14-171">For details about planning call routes, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a><span data-ttu-id="28c14-172">ステップ 6.</span><span class="sxs-lookup"><span data-stu-id="28c14-172">Step 6.</span></span> <span data-ttu-id="28c14-173">エンタープライズ VoIP に対して有効化されたユーザーの通話を再ルーティングするように PBX または SIP トランクを構成する</span><span class="sxs-lookup"><span data-stu-id="28c14-173">Configure PBX or SIP Trunk to reroute calls for Enterprise Voice users</span></span>

<span data-ttu-id="28c14-174">従来の PBX 接続または インターネット テレフォニー サービス プロバイダー (ITSP) への SIP トランク接続でこれまでホストされていたユーザーは、移動後も各自の電話番号を保持します。</span><span class="sxs-lookup"><span data-stu-id="28c14-174">Users who formerly were hosted on a traditional PBX or on a SIP Trunk connection to an Internet Telephony Service Provider (ITSP) retain their phone numbers after the move.</span></span> <span data-ttu-id="28c14-175">唯一の要件は、移行後に、エンタープライズ Voip ユーザーの着信呼び出しを仲介サーバーにルーティングするように PBX または SIP トランクを再構成する必要があることです。</span><span class="sxs-lookup"><span data-stu-id="28c14-175">The only requirement is that after the move, the PBX or SIP Trunk must be reconfigured to route incoming calls for Enterprise Voice users to the Mediation Server.</span></span>

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a><span data-ttu-id="28c14-p120">ステップ 7. ユーザーを Exchange ユニファイド メッセージングに移動する (推奨)</span><span class="sxs-lookup"><span data-stu-id="28c14-p120">Step 7. Move users to Exchange Unified Messaging (recommended)</span></span>

<span data-ttu-id="28c14-178">Exchange ユニファイド メッセージングへのユーザーの移動は、次の作業で構成されます。</span><span class="sxs-lookup"><span data-stu-id="28c14-178">Moving users to Exchange Unified Messaging consists of the following tasks:</span></span>

  - <span data-ttu-id="28c14-179">連携して動作するように Exchange ユニファイドメッセージングと Lync Server を構成します。</span><span class="sxs-lookup"><span data-stu-id="28c14-179">Configure Exchange Unified Messaging and Lync Server to work together.</span></span>

  - <span data-ttu-id="28c14-180">Exchange ユニファイド メッセージングの通話応答と Outlook Voice Access に対してユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="28c14-180">Enable users for Exchange Unified Messaging call answering and Outlook Voice Access.</span></span> <span data-ttu-id="28c14-181">Exchange ユニファイド メッセージング サーバーでこの作業を行います。</span><span class="sxs-lookup"><span data-stu-id="28c14-181">This task is performed on the Exchange Unified Messaging server.</span></span> <span data-ttu-id="28c14-182">詳細については、「Exchange Server 2010 TechNet [https://go.microsoft.com/fwlink/p/?linkID=139372](https://go.microsoft.com/fwlink/p/?linkid=139372)ライブラリ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28c14-182">For details, see the Exchange Server 2010 TechNet Library at [https://go.microsoft.com/fwlink/p/?linkID=139372](https://go.microsoft.com/fwlink/p/?linkid=139372).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

