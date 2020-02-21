---
title: インスタントメッセージング (IM) のファイル転送と URL フィルターを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring file transfer and URL filtering for instant messaging (IM)
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48183440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0f9968b6154b281126430b87b7ae4ac98aa4b0a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a><span data-ttu-id="a710f-102">Lync Server 2013 でインスタントメッセージング (IM) 用のファイル転送および URL フィルターを構成する</span><span class="sxs-lookup"><span data-stu-id="a710f-102">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a710f-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a710f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a710f-104">インテリジェント IM フィルターツールは、ユーザーの利便性を最小限に抑えながら、最も一般的な形式のウイルスの蔓延に対して Lync Server 2013 の展開を保護するのに役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="a710f-104">The Intelligent IM Filter tool helps protect your Lync Server 2013 deployment against the spread of the most common forms of viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="a710f-105">インテリジェント IM フィルターを使用して、企業ファイアウォールの外側にある未知のエンドポイントから送信された、損害を与える可能性のある (または要求されていない) インスタント メッセージを禁止するようにフィルターを構成します。</span><span class="sxs-lookup"><span data-stu-id="a710f-105">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="a710f-106">フィルターを構成するには、禁止する対象 (特定のプレフィックスのハイパーリンクや、特定の拡張子のファイルを含むインスタント メッセージなど) を判断するための基準を指定します。</span><span class="sxs-lookup"><span data-stu-id="a710f-106">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks with specific prefixes and files with specific extensions.</span></span>

<span data-ttu-id="a710f-107">インテリジェント IM フィルターには、以下の機能があります。</span><span class="sxs-lookup"><span data-stu-id="a710f-107">Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="a710f-108">拡張 URL フィルター。</span><span class="sxs-lookup"><span data-stu-id="a710f-108">Enhanced URL filtering.</span></span>

  - <span data-ttu-id="a710f-109">拡張ファイル転送フィルター。</span><span class="sxs-lookup"><span data-stu-id="a710f-109">Enhanced file transfer filtering.</span></span>

<span data-ttu-id="a710f-110">インテリジェント IM フィルターの構成には、以下を含みます。</span><span class="sxs-lookup"><span data-stu-id="a710f-110">Configuring Intelligent IM Filter includes the following:</span></span>

  - <span data-ttu-id="a710f-111">URL フィルターの構成。</span><span class="sxs-lookup"><span data-stu-id="a710f-111">Configuring URL filtering.</span></span>

  - <span data-ttu-id="a710f-112">ファイル転送フィルターの構成。</span><span class="sxs-lookup"><span data-stu-id="a710f-112">Configuring file transfer filtering.</span></span>

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a><span data-ttu-id="a710f-113">インスタント メッセージ (IM) へのフィルター オプションの適用方法</span><span class="sxs-lookup"><span data-stu-id="a710f-113">How Filtering Options Are Applied to Instant Messages</span></span>

<span data-ttu-id="a710f-114">インテリジェント IM メッセージフィルターツールを展開する前に、Lync Server 2013 サーバー間でメッセージがルーティングされるときのフィルターオプションの適用方法を理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="a710f-114">Before you deploy the Intelligent IM Message Filter tool, you need to understand how filtering options are applied as messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="a710f-115">これらのサーバーが 1 つの組織内に配置されている場合も、組織の境界を越えて配置されている場合も、フィルター オプションが適用される方法は一貫しています。</span><span class="sxs-lookup"><span data-stu-id="a710f-115">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="a710f-116">カスタマイズされた通知、および警告テキストが、一貫した方法でメッセージに挿入され、サーバー間で送信されます。</span><span class="sxs-lookup"><span data-stu-id="a710f-116">This consistency applies to the way that the customized notice and warning texts are inserted into messages and sent across servers.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="a710f-117">インスタント メッセージ フィルターを使用すると、メッセージ中の URL を処理するために必要な CPU リソースの量が増加します。</span><span class="sxs-lookup"><span data-stu-id="a710f-117">The instant message filter increases the amount of CPU resources required to process URLs in a message.</span></span> <span data-ttu-id="a710f-118">この CPU 需要の増加は、Lync Server のパフォーマンスにも影響します。</span><span class="sxs-lookup"><span data-stu-id="a710f-118">This increase in CPU demand also affects the performance of Lync Server.</span></span>



</div>

<span data-ttu-id="a710f-119">Lync Server コントロールパネルの**IM およびプレゼンス**グループの**URL フィルター**ページを使用すると、一部またはすべてのハイパーリンクをブロックしたり、警告を構成したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="a710f-119">By using the **URL Filter** page in the **IM and Presence** group in Lync Server Control Panel, you can block some or all hyperlinks or configure a warning.</span></span> <span data-ttu-id="a710f-120">警告は、[**ハイパーリンク プレフィックス**] オプションの [**警告メッセージを送信する**] を選択している場合に、ハイパーリンクを含むインスタント メッセージの先頭に挿入されます。</span><span class="sxs-lookup"><span data-stu-id="a710f-120">The warning is inserted at the beginning of an instant message that contains a hyperlink when you choose the **Hyperlink prefix** option **Send warning message**.</span></span>

<span data-ttu-id="a710f-121">インスタント メッセージがサーバー間で転送される場合、次の一般的なガイドラインが適用されます。</span><span class="sxs-lookup"><span data-stu-id="a710f-121">When an instant message travels from one server to another, the following general guidelines apply:</span></span>

  - <span data-ttu-id="a710f-p105">サーバーでインスタント メッセージが禁止されている ([**URL フィルター**] ページの [**ファイル拡張子を含む URL を禁止する**] チェック ボックスがオンになっている、または [**ハイパーリンク プレフィックス**] オプションの [**ハイパーリンクを禁止する**] が選択されているため) 場合、クライアントにエラー メッセージが返されます。 後続のサーバーには、このインスタント メッセージは転送されません。</span><span class="sxs-lookup"><span data-stu-id="a710f-p105">If a server blocks an instant message (because you selected the **Block URLs with file extension** check box on the **URL Filter** page or because you chose the **Hyperlink prefix** option **Block hyperlinks**), an error message is returned to the client. Subsequent servers do not receive this instant message.</span></span>

  - <span data-ttu-id="a710f-p106">アクティブ ハイパーリンクが含まれるインスタント メッセージにあるサーバー (Server1) で警告が追加されても、このインスタント メッセージを受信する後続のサーバー (Server2) では、インスタント メッセージに含まれるこのアクティブ ハイパーリンクに基づいて別の処理を実行でき、インスタント メッセージの禁止または警告の追加を行うことができます。Server2 がこの URL について警告の追加のみを行うように構成されている場合は、Server1 によって事前に追加された警告は削除され、Server2 で構成された警告がインスタント メッセージの先頭に追加されます。</span><span class="sxs-lookup"><span data-stu-id="a710f-p106">If a server (Server1) adds a warning to an instant message that contains an active hyperlink, a subsequent server (Server2) that receives this instant message can still take a different action based on this active hyperlink present in the instant message and block the instant message or add a warning. If Server2 is configured only to add a warning for this URL, the earlier warning added by Server1 is removed, and the warning configured on Server2 is added to the beginning of the instant message.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="a710f-126">Lync Server 2013 を混在環境で実行している場合は、インテリジェント IM フィルターアプリケーションを使用するために必要な最低限のバージョンは Live Communications Server 2005 SP1 です。</span><span class="sxs-lookup"><span data-stu-id="a710f-126">If you are running Lync Server 2013 in a mixed environment, Live Communications Server 2005 with SP1 is the minimum version required to use the Intelligent IM Filter application.</span></span> <span data-ttu-id="a710f-127">インテリジェント IM フィルターは、SP1 が適用されていない Live Communications Server 2005 ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="a710f-127">The Intelligent IM Filter is not supported on Live Communications Server 2005 without SP1.</span></span>



</div>

<div>

## <a name="url-filtering"></a><span data-ttu-id="a710f-128">URL フィルター</span><span class="sxs-lookup"><span data-stu-id="a710f-128">URL Filtering</span></span>

<span data-ttu-id="a710f-p108">URL は、そのハイパーリンク プレフィックスに応じてフィルター処理されます。 次の例は、有効なプレフィックスです。</span><span class="sxs-lookup"><span data-stu-id="a710f-p108">URLs are filtered according to their hyperlink prefix. The following examples are valid prefixes:</span></span>

  - <span data-ttu-id="a710f-131">www\*。</span><span class="sxs-lookup"><span data-stu-id="a710f-131">www\*.</span></span>

  - <span data-ttu-id="a710f-132">転送.</span><span class="sxs-lookup"><span data-stu-id="a710f-132">ftp.</span></span>

  - <span data-ttu-id="a710f-133">プロトコル</span><span class="sxs-lookup"><span data-stu-id="a710f-133">http:</span></span>

<span data-ttu-id="a710f-p109">URL フィルター処理を実行するためにインスタント メッセージ フィルターを構成していない場合、インスタント メッセージに含まれるすべての URL がサーバーを介してそのまま渡されます。 URL フィルター処理を実行するためにインスタント メッセージ フィルターを構成している場合、インスタント メッセージ内の URL は、[**URL フィルターの編集**] または [**URL フィルターの新規作成**] ダイアログ ボックスで選択するオプションに応じてフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="a710f-p109">If you do not configure the instant message filter to perform any URL filtering, all URLs contained in instant messages are passed unmodified through the server. If you configure the instant message filter to perform URL filtering, URLs in instant messages are filtered according to the options that you select in the **Edit URL Filter** or **New URL Filter** dialog box.</span></span>

  - <span data-ttu-id="a710f-136">**[Url フィルター**   を有効にする] このオプションは、グローバル展開または選択したサイトの url フィルターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a710f-136">**Enable URL filter**   This option enables URL filtering for the global deployment or for the site that you select.</span></span>

  - <span data-ttu-id="a710f-137">**[ファイル拡張子**   を持つ url をブロックする] インスタントメッセージフィルターは、アクティブなイントラネットまたはインターネット URL で、[ファイル**フィルターの編集**] ダイアログボックスの [**ブロックするファイルの種類の拡張子**] の下に、拡張子が表示されているファイルが含まれているものをブロックします。</span><span class="sxs-lookup"><span data-stu-id="a710f-137">**Block URLs with file extension**   The instant message filter blocks any active intranet or Internet URL that contains a file with an extension listed under **File type extensions to block** in the **Edit File Filter** dialog box.</span></span> <span data-ttu-id="a710f-138">URL がブロックされると、送信者にエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a710f-138">When a URL is blocked, an error message is displayed to the sender.</span></span> <span data-ttu-id="a710f-139">このオプションを選択すると、[**ブロックするファイルの種類の拡張子**] で定義されているすべてのファイル拡張子について、他のすべてのフィルターオプションよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="a710f-139">When selected, this option takes precedence over all other filtering options for any file extensions defined under **File type extensions to block**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="a710f-140">ファイル拡張子のフィルター処理は、標準的なファイル名のみに制限されています。</span><span class="sxs-lookup"><span data-stu-id="a710f-140">Filtering of file extensions is limited to standard file names.</span></span> <span data-ttu-id="a710f-141">ファイル拡張子が他の名前に埋め込まれている場合は、フィルターが機能しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a710f-141">Filtering may not work with file extensions embedded in other names.</span></span>

    
    </div>

<span data-ttu-id="a710f-142">インスタント メッセージ会話でのハイパーリンクの処理方法を構成するには、[**ハイパーリンク プレフィックス**] で次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a710f-142">To configure how hyperlinks are handled in instant message conversations, select one of the following options under **Hyperlink prefix**:</span></span>

  - <span data-ttu-id="a710f-143">\*\*\*\*   サーバーを経由して送信されるメッセージ内の url にフィルターを適用しません。</span><span class="sxs-lookup"><span data-stu-id="a710f-143">**Do not filter**   URLs in messages are sent through the server.</span></span> <span data-ttu-id="a710f-144">このオプションを選択すると、[**許可] メッセージ**ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a710f-144">When you choose this option, the **Allow message** box appears.</span></span> <span data-ttu-id="a710f-145">[**許可] メッセージ**ボックスで、ハイパーリンクを含む各インスタントメッセージの先頭に挿入する通知を指定します。</span><span class="sxs-lookup"><span data-stu-id="a710f-145">In the **Allow message** box, specify the notice that you want to insert at the beginning of each instant message containing hyperlinks.</span></span> <span data-ttu-id="a710f-146">この通知は、65535文字以下で構成することができます。</span><span class="sxs-lookup"><span data-stu-id="a710f-146">This notice can consist of no more than 65535 characters.</span></span>

  - <span data-ttu-id="a710f-147">**[ハイパーリンク**   を禁止する] アクティブなハイパーリンクを含むインスタントメッセージの配信が Lync Server によってブロックされ、送信者にエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a710f-147">**Block hyperlinks**   Delivery of instant messages containing active hyperlinks is blocked by Lync Server, and an error message is displayed to the sender.</span></span>

  - <span data-ttu-id="a710f-148">**[警告メッセージ**   を送信する] インスタントメッセージ内でアクティブなハイパーリンクが許可されていますが、警告が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a710f-148">**Send warning message**   Lync Server permits active hyperlinks in instant messages, but it includes a warning.</span></span> <span data-ttu-id="a710f-149">このオプションを選択した場合は、[**警告メッセージ**] ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a710f-149">When you choose this option, the **Warning message** box appears.</span></span> <span data-ttu-id="a710f-150">[**警告メッセージ**] ボックスでは、有効なハイパーリンクを含むインスタント メッセージに添付する警告を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a710f-150">In the **Warning message** box, you must type the warning that you want to include with instant messages containing valid hyperlinks.</span></span> <span data-ttu-id="a710f-151">たとえば、この警告は、未知のリンクをクリックすることで発生する可能性のある危険の提示や、組織の関連ポリシーや要件への参照などを通知します。</span><span class="sxs-lookup"><span data-stu-id="a710f-151">For example, this warning might state the potential dangers of clicking an unknown link, or it might refer to your organization’s relevant policies and requirements.</span></span> <span data-ttu-id="a710f-152">この警告には、65,535 文字まで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a710f-152">The warning can be no more than 65535 characters.</span></span>

<span data-ttu-id="a710f-153">[**ハイパーリンクを禁止する**] または [**警告メッセージを送信する**] を選択する場合、次のオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a710f-153">If you select **Block hyperlinks** or **Send warning message**, the following options are available:</span></span>

  - <span data-ttu-id="a710f-154">**ローカルイントラネットのハイパーリンク**   を除外するインスタントメッセージフィルターはインターネットの url のみをブロックします。</span><span class="sxs-lookup"><span data-stu-id="a710f-154">**Exclude local intranet hyperlinks**   The instant message filter blocks only Internet URLs.</span></span> <span data-ttu-id="a710f-155">イントラネット内の場所の Url は、サーバーを通じて変更されずに渡されます。</span><span class="sxs-lookup"><span data-stu-id="a710f-155">URLs for locations within your intranet are passed unmodified through the server.</span></span> <span data-ttu-id="a710f-156">ただし、Lync Server を実行している個々のサーバーが渡すイントラネット Url は、イントラネットゾーンの一部と見なされるローカル web サイトの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="a710f-156">However, the intranet URLs that individual servers running Lync Server pass depend on which types of local websites are considered part of their intranet zone.</span></span> <span data-ttu-id="a710f-157">サーバーのイントラネットゾーン設定を確認するには、「 [Modify the DEFAULT URL filter In Lync server 2013](lync-server-2013-modify-the-default-url-filter.md)」の「Internet Explorer でイントラネット設定を構成するには」の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a710f-157">To check a server’s intranet zone settings, see the “To configure your intranet settings in Internet Explorer” procedure in [Modify the default URL filter in Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md).</span></span>

  - <span data-ttu-id="a710f-158">**[以下のハイパーリンクプレフィックス**   をフィルターする] 禁止するプレフィックスを選択するには、[**選択**] をクリックし、[**ハイパーリンクプレフィックスの選択**] で、プレフィックスを [**ハイパーリンク**プレフィックス] の一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="a710f-158">**Filter these hyperlink prefixes**   To choose which prefixes you want to block, click **Select**, and then, in **Select Hyperlink Prefix**, add the prefixes to the **Hyperlink prefixes** list.</span></span>
    
    <span data-ttu-id="a710f-159">**href** 以外のすべてのプレフィックスは、末尾がピリオドまたはコロンであるか、アスタリスクとそれに続くピリオドである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a710f-159">All prefixes except **href** must end with a period or a colon, or an asterisk followed by a period.</span></span> <span data-ttu-id="a710f-160">有効なプレフィックスには、アスタリスク (\*) を除く、有効な URL 文字のセット内の任意の文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a710f-160">Valid prefixes can contain any characters in the set of valid URL characters except the asterisk (\*).</span></span> <span data-ttu-id="a710f-161">有効な URL 文字のセットは次\# \*のとおりです。 +/\_ \` 0123456789 = @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^ ABCDEFGHIJKLMNOPQRSTUVWXYZ | ~</span><span class="sxs-lookup"><span data-stu-id="a710f-161">The set of valid URL characters is: \#\*+/0123456789=@ABCDEFGHIJKLMNOPQRSTUVWXYZ^\_\` abcdefghijklmnopqrstuvwxyz|~</span></span>

</div>

<div>

## <a name="file-transfer-filtering"></a><span data-ttu-id="a710f-162">ファイル転送フィルター処理</span><span class="sxs-lookup"><span data-stu-id="a710f-162">File Transfer Filtering</span></span>

<span data-ttu-id="a710f-p116">ファイル転送フィルター処理は、インスタント メッセージと会議の両方に影響します。 会議の場合、これらの設定は、Office Live Meeting 2007 クライアントの配布資料機能とマルチメディア再生機能に影響します。</span><span class="sxs-lookup"><span data-stu-id="a710f-p116">Filter transfer filtering affects both instant messages and conferences. For conferences, these settings affect the handout feature in the Office Live Meeting 2007 client and multimedia playback features.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="a710f-165">Lync Server では、ファイル転送設定オプションも提供されています。</span><span class="sxs-lookup"><span data-stu-id="a710f-165">Lync Server also offers file transfer setting options.</span></span> <span data-ttu-id="a710f-166">このサーバー側のオプションは、Lync Server で使用可能なクライアント側のコントロールに加えて提供されています。</span><span class="sxs-lookup"><span data-stu-id="a710f-166">This server-side option is offered in addition to the client-side controls available in Lync Server.</span></span>



</div>

<span data-ttu-id="a710f-p118">すべての種類のファイルについて、Office Live Meeting 2007 クライアントの配付資料機能の使用時、およびマルチメディア再生機能で、インスタント メッセージの会話中にファイル転送をフィルター処理できます。 次のオプションを設定して、ファイル転送を制御できます。</span><span class="sxs-lookup"><span data-stu-id="a710f-p118">You can filter file transfers during instant message conversations, when you are using the handout feature in the Office Live Meeting 2007 client, and for multimedia playback features for all file types. You can set the following options to control file transfers:</span></span>

  - <span data-ttu-id="a710f-169">**[ファイルフィルター**   を有効にする] このオプションは、グローバル展開または選択したサイトのファイルフィルターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a710f-169">**Enable file filter**   This option enables file filtering for the global deployment or for the site that you select.</span></span>
    
    <span data-ttu-id="a710f-170">ファイル フィルターを有効にすると、[**ファイル転送**] で次のオプションのうちの 1 つを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a710f-170">When you enable the file filter, you can choose one of the following options in **File transfer**:</span></span>
    
      - <span data-ttu-id="a710f-171">**特定のファイルの種類**   をブロックするブロックするファイル拡張子の一覧を指定して、サーバーによってフィルター処理されるファイル転送要求を指定します。</span><span class="sxs-lookup"><span data-stu-id="a710f-171">**Block specific file types**   You specify which file transfer requests are filtered by the server by specifying a list of file extensions to block.</span></span> <span data-ttu-id="a710f-172">リスト内のエントリには、すべての標準文字を含めることができ\*ますが、ワイルドカード文字 () は使用できません。</span><span class="sxs-lookup"><span data-stu-id="a710f-172">Entries in the list can contain all standard characters, but not the wildcard character (\*).</span></span> <span data-ttu-id="a710f-173">Office Live Meeting 2007 クライアントでは、配布資料機能は有効になっていますが、この拡張子を持つすべてのファイルをアップロードまたはダウンロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a710f-173">In the Office Live Meeting 2007 client the handout feature is enabled, but any file with this extension cannot be uploaded or downloaded.</span></span> <span data-ttu-id="a710f-174">[ **Url フィルター] タブ**に一覧表示されている url フィルターの設定について [**ファイル拡張子を持つ url をブロック**する] チェックボックスをオンにすると、url フィルターはこの同じ一覧を使用して、これらのファイル拡張子を含むアクティブなハイパーリンクをブロックします。</span><span class="sxs-lookup"><span data-stu-id="a710f-174">If you select the **Block URLs with file extension** check box on the settings for a URL filter listed on the **URL Filter** tab, the URL filter uses this same list to block active hyperlinks that contain any of these file extensions.</span></span> <span data-ttu-id="a710f-175">ブロックするファイルの種類を選択するには、[**選択**] をクリックし、[**ファイルの種類の選択**] で、選択したファイルの種類の**拡張子**の一覧にファイルの種類の拡張子を追加します。</span><span class="sxs-lookup"><span data-stu-id="a710f-175">To choose which file types you want to block, click **Select**, and then, in **Select File Type**, add the file type extensions to the **Selected file type extensions** list.</span></span>
    
      - <span data-ttu-id="a710f-176">**[すべて**   禁止] サーバーは、ファイル転送要求を含むすべてのインスタントメッセージを削除し、要求の送信者にエラーメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="a710f-176">**Block All**   The server drops all instant messages that contain file transfer requests and returns an error message to the sender of the request.</span></span> <span data-ttu-id="a710f-177">Office Live Meeting 2007 クライアントの配布資料機能は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="a710f-177">The handout feature in the Office Live Meeting 2007 client is disabled.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="a710f-p121">ファイル拡張子のフィルター処理は、標準的なファイル名のみに制限されています。 ファイル拡張子が他の名前に埋め込まれている場合は、フィルターが機能しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a710f-p121">Filtering of file extensions is limited to standard file names. Filtering may not work with file extensions embedded in other names.</span></span>



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a710f-180">このセクション中</span><span class="sxs-lookup"><span data-stu-id="a710f-180">In This Section</span></span>

  - [<span data-ttu-id="a710f-181">Lync Server 2013 での既定のファイル送信フィルターの変更</span><span class="sxs-lookup"><span data-stu-id="a710f-181">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [<span data-ttu-id="a710f-182">Lync Server 2013 で特定のサイトに対して新しいファイル転送フィルターを作成する</span><span class="sxs-lookup"><span data-stu-id="a710f-182">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [<span data-ttu-id="a710f-183">Lync Server 2013 で既定の URL フィルターを変更する</span><span class="sxs-lookup"><span data-stu-id="a710f-183">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)

  - [<span data-ttu-id="a710f-184">IM 会話でのハイパーリンクを処理するために Lync Server 2013 で新しい URL フィルターを作成する</span><span class="sxs-lookup"><span data-stu-id="a710f-184">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a710f-185">関連項目</span><span class="sxs-lookup"><span data-stu-id="a710f-185">See Also</span></span>


[<span data-ttu-id="a710f-186">Lync Server 2013 での IM およびプレゼンス設定の管理</span><span class="sxs-lookup"><span data-stu-id="a710f-186">Managing IM and presence settings in Lync Server 2013</span></span>](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

