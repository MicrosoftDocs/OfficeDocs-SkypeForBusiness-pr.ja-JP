---
title: 'Lync Server 2013: メディアポート範囲の設定を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring media port range settings
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48183723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 300bec82443e1d2929df63a808cbe17c5bd6f9fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a><span data-ttu-id="06fa1-102">Lync Server 2013 でメディアポート範囲設定を構成する</span><span class="sxs-lookup"><span data-stu-id="06fa1-102">Configuring media port range settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06fa1-103">_**最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="06fa1-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="06fa1-104">メディアポート範囲の設定は、クライアントのパフォーマンスに大きな影響を与え、構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06fa1-104">Media port range settings can significantly impact client performance and should be configured.</span></span> <span data-ttu-id="06fa1-105">Lync Server 管理シェルを使用して、これらの設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="06fa1-105">You can configure these settings by using Lync Server Management Shell.</span></span>

### <a name="media-port-range-settings"></a><span data-ttu-id="06fa1-106">メディアポート範囲の設定</span><span class="sxs-lookup"><span data-stu-id="06fa1-106">Media Port Range Settings</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="06fa1-107">設定</span><span class="sxs-lookup"><span data-stu-id="06fa1-107">Setting</span></span></th>
<th><span data-ttu-id="06fa1-108">説明</span><span class="sxs-lookup"><span data-stu-id="06fa1-108">Description</span></span></th>
<th><span data-ttu-id="06fa1-109">Lync Server Management Shell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="06fa1-109">Lync Server Management Shell cmdlet</span></span></th>
<th><span data-ttu-id="06fa1-110">コマンドレットのパラメーター</span><span class="sxs-lookup"><span data-stu-id="06fa1-110">Cmdlet parameters</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06fa1-111">Portrange\ Enabled</span><span class="sxs-lookup"><span data-stu-id="06fa1-111">Portrange\Enabled</span></span></p></td>
<td><p><span data-ttu-id="06fa1-112">サーバーによって送信されるポート範囲を、メディアとシグナリングのクライアントで使うかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="06fa1-112">Specifies whether the port ranges sent by the server should be used by the client for media and signaling.</span></span> <span data-ttu-id="06fa1-113">Subvalues MinMediaPort と MaxMediaPort と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="06fa1-113">Used in conjunction with the subvalues MinMediaPort and MaxMediaPort.</span></span></p></td>
<td><p><span data-ttu-id="06fa1-114"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="06fa1-114"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="06fa1-115">ClientMediaPortRangeEnabled</span><span class="sxs-lookup"><span data-stu-id="06fa1-115">ClientMediaPortRangeEnabled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06fa1-116">Portrange\MinMediaPort</span><span class="sxs-lookup"><span data-stu-id="06fa1-116">Portrange\MinMediaPort</span></span></p></td>
<td><p><span data-ttu-id="06fa1-117">メディアに使用する開始ポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="06fa1-117">Specifies the starting port number to use for media.</span></span> <span data-ttu-id="06fa1-118">MaxMediaPort と組み合わせて、ポートの範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="06fa1-118">Combines with MaxMediaPort to specify the range of ports.</span></span> <span data-ttu-id="06fa1-119">推奨される最小範囲は、40ポートです。</span><span class="sxs-lookup"><span data-stu-id="06fa1-119">The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="06fa1-120"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="06fa1-120"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="06fa1-121">ClientMediaPort (クライアントメディアに使用する開始ポート番号を表します)</span><span class="sxs-lookup"><span data-stu-id="06fa1-121">ClientMediaPort (represents the starting port number to use for client media)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06fa1-122">Portrange\MaxMediaPort</span><span class="sxs-lookup"><span data-stu-id="06fa1-122">Portrange\MaxMediaPort</span></span></p></td>
<td><p><span data-ttu-id="06fa1-123">メディアに使用する最大のポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="06fa1-123">Specifies the highest port number to use for media.</span></span> <span data-ttu-id="06fa1-124">MinMediaPort と組み合わせて、ポートの範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="06fa1-124">Combines with MinMediaPort to specify the range of ports.</span></span> <span data-ttu-id="06fa1-125">推奨される最小範囲は、40ポートです。</span><span class="sxs-lookup"><span data-stu-id="06fa1-125">The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="06fa1-126"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="06fa1-126"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="06fa1-127">ClientMediaPortRange (クライアントメディアで利用できるポートの合計数を示します。既定は 40)</span><span class="sxs-lookup"><span data-stu-id="06fa1-127">ClientMediaPortRange (indicates the total number of ports available for client media; default is 40)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a><span data-ttu-id="06fa1-128">メディアポート範囲の設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="06fa1-128">To Configure Media Port Range Settings</span></span>

1.  <span data-ttu-id="06fa1-129">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="06fa1-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="06fa1-130">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="06fa1-130">Run the following cmdlet:</span></span>
    
        Get-CsConferencingConfiguration
    
    <span data-ttu-id="06fa1-131">このコマンドレットは会議の構成設定を返します。</span><span class="sxs-lookup"><span data-stu-id="06fa1-131">This cmdlet returns the conferencing configuration settings.</span></span>

3.  <span data-ttu-id="06fa1-132">変更するパラメーターと値を使用して、次のコマンドレットを実行します (このコマンドレットのパラメーターの詳細については、「Lync Server 管理シェルドキュメント」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="06fa1-132">Run the following cmdlet with the parameters and values you want to change (for details about the parameters for this cmdlet, see the Lync Server Management Shell documentation):</span></span>
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="06fa1-133">特定のサイトの会議構成設定の追加のセットを作成できます。</span><span class="sxs-lookup"><span data-stu-id="06fa1-133">You can create additional sets of conferencing configuration settings for specific sites.</span></span> <span data-ttu-id="06fa1-134">サイト id を使用して<STRONG>CsConferencingConfiguration</STRONG>コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="06fa1-134">Use the <STRONG>New- CsConferencingConfiguration</STRONG> cmdlet with a site identity.</span></span> <span data-ttu-id="06fa1-135">サイトの新しい会議構成設定を作成する場合、サイトの設定はグローバル設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="06fa1-135">When you create new conferencing configuration settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="06fa1-136">詳細については、「Lync Server 管理シェルのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06fa1-136">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

