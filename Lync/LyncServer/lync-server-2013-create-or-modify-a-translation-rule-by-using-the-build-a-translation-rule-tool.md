---
title: 翻訳ルールツールを使って翻訳ルールを作成または変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule by using the Build a Translation Rule tool
ms:assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412909(v=OCS.15)
ms:contentKeyID: 48185224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d45ca4e04146a175ec2782aa798ac27559fce495
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a><span data-ttu-id="6066c-102">Lync Server 2013 の翻訳ルールの作成ツールを使用して、翻訳ルールを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="6066c-102">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6066c-103">_**最終更新日:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="6066c-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="6066c-104">翻訳ルールを定義する場合は、次の手順に従います。**翻訳**ルールツールで一連の値を入力し、Lync Server コントロールパネルを有効にして、対応する照合パターンと翻訳ルールを生成することができます。</span><span class="sxs-lookup"><span data-stu-id="6066c-104">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="6066c-105">または、手動で正規表現を記述して一致パターンと変換ルールを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="6066c-105">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="6066c-106">詳細について[は、「Lync Server 2013 で翻訳ルールを手動で作成または変更](lync-server-2013-create-or-modify-a-translation-rule-manually.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6066c-106">For details, see [Create or modify a translation rule manually in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).</span></span>

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="6066c-107">変換ルールの構築ツールを使用してルールを定義するには</span><span class="sxs-lookup"><span data-stu-id="6066c-107">To define a rule by using the Build a Translation Rule tool</span></span>

1.  <span data-ttu-id="6066c-108">RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6066c-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="6066c-109">詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6066c-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="6066c-110">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6066c-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6066c-111">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6066c-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6066c-112">翻訳ルールの定義を開始するには、「 [Lync server 2013 でメディアバイパスを使用してトランクを構成](lync-server-2013-configure-a-trunk-with-media-bypass.md)する」を参照するか、「 [lync server 2013 でメディアをバイパスしないトランクを構成](lync-server-2013-configure-a-trunk-without-media-bypass.md)する」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="6066c-112">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="6066c-113">[**新しい変換ルール**] ページまたは [**変換ルールの編集**] ページの [**名前**] に、変換対象の番号パターンを説明する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6066c-113">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="6066c-114">(オプション) [**説明**] に、「**US International long-distance dialing**」などの変換ルールの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="6066c-114">(Optional) Under **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="6066c-115">ダイアログ ボックスの [**変換ルールの構築**] セクションの次のフィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="6066c-115">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>
    
      - <span data-ttu-id="6066c-116">[**開始番号**]: (オプション) パターンに一致させる番号の先頭の番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="6066c-116">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="6066c-117">たとえば、このフィールド**+** に「e.i」形式の数値 (+ で始まる) を入力します。</span><span class="sxs-lookup"><span data-stu-id="6066c-117">For example, enter **+** in this field to match numbers in E.164 format (which begin with +).</span></span>
    
      - <span data-ttu-id="6066c-p105">[**長さ**]: 一致パターンの桁数を指定し、パターンをこの長さと同じ桁数の番号に一致させるか、この長さ以上の番号に一致させるか、どの長さの番号にも一致させるかを選択します。たとえば、**11** と入力してドロップダウン リストで [**At least** ] を選択すると、最低でも 11 桁の長さの番号に一致します。</span><span class="sxs-lookup"><span data-stu-id="6066c-p105">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length. For example, enter **11** and select **At least** in the drop-down list to match numbers that are at least 11 digits in length.</span></span>
    
      - <span data-ttu-id="6066c-120">[**削除する番号**]: (オプション) 開始番号から削除する桁数を指定します。</span><span class="sxs-lookup"><span data-stu-id="6066c-120">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="6066c-121">たとえば、「 **1** 」と入力すると**+** 、番号の最初からが取り除かれます。</span><span class="sxs-lookup"><span data-stu-id="6066c-121">For example, enter **1** to strip out the **+** from the beginning of the number.</span></span>
    
      - <span data-ttu-id="6066c-p107">[**追加する番号**]: (オプション) 変換済みの番号の先頭に追加する番号を指定します。たとえば、ルール適用時、変換済みの番号の先頭に 011 を追加したい場合は、「**011**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="6066c-p107">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers. For example, enter **011** if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>
    
    <span data-ttu-id="6066c-p108">これらのフィールドに入力した値は、[**一致するパターン**] フィールドおよび [**変換ルール**] フィールドに反映されます。たとえば、上述の例の値を指定した場合、[**一致するパターン**] フィールドに設定される正規表現は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6066c-p108">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>
    
    <span data-ttu-id="6066c-126">**^\\+ (\\d{9}\\d +) $**</span><span class="sxs-lookup"><span data-stu-id="6066c-126">**^\\+(\\d{9}\\d+)$**</span></span>
    
    <span data-ttu-id="6066c-p109">[**変換ルール**] フィールドには、変換済みの番号の形式のパターンを指定します。このパターンには、次の 2 つのパーツがあります。</span><span class="sxs-lookup"><span data-stu-id="6066c-p109">The **Translation rule** field specifies a pattern for the format of translated numbers. This pattern has two parts:</span></span>
    
      - <span data-ttu-id="6066c-129">一致パターンの桁数を表す値 (**$1** など)</span><span class="sxs-lookup"><span data-stu-id="6066c-129">A value (for example, **$1**) that represents the number of digits in the matching pattern</span></span>
    
      - <span data-ttu-id="6066c-130">(オプション) [**追加する番号**] フィールドに入力することで先頭に追加できる値</span><span class="sxs-lookup"><span data-stu-id="6066c-130">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>
    
    <span data-ttu-id="6066c-131">上述の例の値を使用した場合、[**変換ルール**] フィールドに **011$1** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6066c-131">Using the preceding example values, **011$1** appears in the **Translation rule** field.</span></span>
    
    <span data-ttu-id="6066c-132">この変換ルールを適用すると、+441235551010 が 011441235551010 になります。</span><span class="sxs-lookup"><span data-stu-id="6066c-132">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

7.  <span data-ttu-id="6066c-133">[**OK**] をクリックして変換ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="6066c-133">Click **OK** to save the translation rule.</span></span>

8.  <span data-ttu-id="6066c-134">[**OK**] をクリックしてトランク構成を保存します。</span><span class="sxs-lookup"><span data-stu-id="6066c-134">Click **OK** to save the trunk configuration.</span></span>

9.  <span data-ttu-id="6066c-135">[**トランク構成**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6066c-135">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="6066c-136">変換ルールを作成または変更したときは必ず、[<STRONG>すべて確定</STRONG>] コマンドを実行して構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6066c-136">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="6066c-137">詳細については、「操作のドキュメントで「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 のボイスルーティング構成に保留中の変更を発行する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6066c-137">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6066c-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="6066c-138">See Also</span></span>


[<span data-ttu-id="6066c-139">Lync Server 2013 で翻訳ルールを手動で作成または変更する</span><span class="sxs-lookup"><span data-stu-id="6066c-139">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
[<span data-ttu-id="6066c-140">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6066c-140">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="6066c-141">Lync Server 2013 でメディアをバイパスせずにトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="6066c-141">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="6066c-142">Lync Server 2013 の音声ルーティング構成に保留中の変更を発行する</span><span class="sxs-lookup"><span data-stu-id="6066c-142">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="6066c-143">Lync Server 2013 のグローバルメディアバイパスオプション</span><span class="sxs-lookup"><span data-stu-id="6066c-143">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

