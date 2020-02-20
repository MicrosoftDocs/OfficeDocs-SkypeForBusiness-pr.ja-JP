---
title: 変換ルールの構築ツールを使用して変換ルールを作成または変更する
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
ms.openlocfilehash: 8c529a83a85cd9ffbed0aa0b5e9a741e6c3a7815
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a><span data-ttu-id="3b7e3-102">Lync Server 2013 で変換ルールの構築ツールを使用して変換ルールを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="3b7e3-102">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b7e3-103">_**トピックの最終更新日:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="3b7e3-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="3b7e3-104">[**変換ルールの構築**] ツールに値のセットを入力し、Lync Server コントロールパネルを有効にして対応する一致パターンと変換ルールを生成することによって、変換ルールを定義するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3b7e3-104">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="3b7e3-105">または、手動で正規表現を記述して一致パターンと変換ルールを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="3b7e3-105">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="3b7e3-106">詳細については、「 [Lync Server 2013 で変換ルールを手動で作成または変更する](lync-server-2013-create-or-modify-a-translation-rule-manually.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b7e3-106">For details, see [Create or modify a translation rule manually in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).</span></span>

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="3b7e3-107">変換ルールの構築ツールを使用してルールを定義するには</span><span class="sxs-lookup"><span data-stu-id="3b7e3-107">To define a rule by using the Build a Translation Rule tool</span></span>

1.  <span data-ttu-id="3b7e3-108">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3b7e3-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="3b7e3-109">詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b7e3-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="3b7e3-110">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3b7e3-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3b7e3-111">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b7e3-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3b7e3-112">変換ルールの定義を開始するには、「 [lync server 2013 でのメディアバイパスを使用](lync-server-2013-configure-a-trunk-with-media-bypass.md)したトランクの構成」の手順10まで、または「 [lync server 2013 でのメディアバイパスを使用しないトランクの構成](lync-server-2013-configure-a-trunk-without-media-bypass.md)」の手順9に記載されている手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3b7e3-112">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="3b7e3-113">[**新しい変換ルール**] ページまたは [**変換ルールの編集**] ページの [**名前**] に、変換対象の番号パターンを説明する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="3b7e3-113">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="3b7e3-114">(オプション) [**説明**] に、「**米国長距離国際電話ダイヤル**」などの変換ルールの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="3b7e3-114">(Optional) Under **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="3b7e3-115">ダイアログ ボックスの [**変換ルールの構築**] セクションの次のフィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="3b7e3-115">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>
    
      - <span data-ttu-id="3b7e3-116">[**開始番号**]: (オプション) パターンに一致させる番号の先頭の番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="3b7e3-116">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="3b7e3-117">たとえば、このフィールド**+** に「e.164」形式の番号 (+ で始まる) を入力します。</span><span class="sxs-lookup"><span data-stu-id="3b7e3-117">For example, enter **+** in this field to match numbers in E.164 format (which begin with +).</span></span>
    
      - <span data-ttu-id="3b7e3-p105">[**長さ**]: 一致パターンの桁数を指定し、パターンをこの長さと同じ桁数の番号に一致させるか、この長さ以上の番号に一致させるか、どの長さの番号にも一致させるかを選択します。 たとえば、**[11]** と入力してドロップダウン リストで **[最少]** を選択すると、最低でも 11 桁の長さの番号に一致されます。</span><span class="sxs-lookup"><span data-stu-id="3b7e3-p105">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length. For example, enter **11** and select **At least** in the drop-down list to match numbers that are at least 11 digits in length.</span></span>
    
      - <span data-ttu-id="3b7e3-120">[**削除する番号**]: (オプション) 開始番号から削除する桁数を指定します。</span><span class="sxs-lookup"><span data-stu-id="3b7e3-120">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="3b7e3-121">たとえば、「 **1** 」と入力して**+** 、を番号の先頭から削除します。</span><span class="sxs-lookup"><span data-stu-id="3b7e3-121">For example, enter **1** to strip out the **+** from the beginning of the number.</span></span>
    
      - <span data-ttu-id="3b7e3-p107">[**追加する番号**]: (オプション) 変換済みの番号の先頭に追加する番号を指定します。 たとえば、ルール適用時、変換済みの番号の先頭に 011 を追加したい場合は、「**011**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="3b7e3-p107">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers. For example, enter **011** if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>
    
    <span data-ttu-id="3b7e3-p108">これらのフィールドに入力した値は、[**一致するパターン**] フィールドおよび [**変換ルール**] フィールドに反映されます。 たとえば、上述の例の値を指定した場合、[**一致するパターン**] フィールドに設定される正規表現は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3b7e3-p108">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>
    
    <span data-ttu-id="3b7e3-126">**^\\+ (\\d{9}\\d +) $**</span><span class="sxs-lookup"><span data-stu-id="3b7e3-126">**^\\+(\\d{9}\\d+)$**</span></span>
    
    <span data-ttu-id="3b7e3-p109">[**変換ルール**] フィールドには、変換済みの番号の形式のパターンを指定します。 このパターンには、次の 2 つのパーツがあります。</span><span class="sxs-lookup"><span data-stu-id="3b7e3-p109">The **Translation rule** field specifies a pattern for the format of translated numbers. This pattern has two parts:</span></span>
    
      - <span data-ttu-id="3b7e3-129">一致パターンの桁数を表す値 (**$1** など)</span><span class="sxs-lookup"><span data-stu-id="3b7e3-129">A value (for example, **$1**) that represents the number of digits in the matching pattern</span></span>
    
      - <span data-ttu-id="3b7e3-130">(オプション) [**追加する番号**] フィールドに入力することで先頭に追加できる値</span><span class="sxs-lookup"><span data-stu-id="3b7e3-130">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>
    
    <span data-ttu-id="3b7e3-131">上述の例の値を使用した場合、[**変換ルール**] フィールドに **011$1** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b7e3-131">Using the preceding example values, **011$1** appears in the **Translation rule** field.</span></span>
    
    <span data-ttu-id="3b7e3-132">この変換ルールを適用すると、+441235551010 が 011441235551010 になります。</span><span class="sxs-lookup"><span data-stu-id="3b7e3-132">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

7.  <span data-ttu-id="3b7e3-133">[**OK**] をクリックして変換ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="3b7e3-133">Click **OK** to save the translation rule.</span></span>

8.  <span data-ttu-id="3b7e3-134">[**OK**] をクリックしてトランク構成を保存します。</span><span class="sxs-lookup"><span data-stu-id="3b7e3-134">Click **OK** to save the trunk configuration.</span></span>

9.  <span data-ttu-id="3b7e3-135">[**トランク構成**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b7e3-135">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="3b7e3-136">変換ルールを作成または変更したときは必ず、[<STRONG>すべて確定</STRONG>] コマンドを実行して構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b7e3-136">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="3b7e3-137">詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b7e3-137">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3b7e3-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b7e3-138">See Also</span></span>


[<span data-ttu-id="3b7e3-139">Lync Server 2013 で変換ルールを手動で作成または変更する</span><span class="sxs-lookup"><span data-stu-id="3b7e3-139">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
[<span data-ttu-id="3b7e3-140">Lync Server 2013 でメディアバイパスを使用してトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="3b7e3-140">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="3b7e3-141">Lync Server 2013 でメディアバイパスを使用せずにトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="3b7e3-141">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="3b7e3-142">Lync Server 2013 で保留中の変更を音声ルーティング構成に公開する</span><span class="sxs-lookup"><span data-stu-id="3b7e3-142">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="3b7e3-143">Lync Server 2013 のグローバルメディアバイパスオプション</span><span class="sxs-lookup"><span data-stu-id="3b7e3-143">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

