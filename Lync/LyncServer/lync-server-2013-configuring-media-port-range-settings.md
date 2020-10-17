---
title: 'Lync Server 2013: メディアポート範囲設定の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring media port range settings
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48183723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e13e491037346d9c3186a8f15aada949c46ac8df
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502094"
---
# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a><span data-ttu-id="0c560-102">Lync Server 2013 でのメディアポート範囲設定の構成</span><span class="sxs-lookup"><span data-stu-id="0c560-102">Configuring media port range settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c560-103">_**トピックの最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="0c560-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="0c560-104">メディア ポート範囲の設定はクライアントのパフォーマンスに大きな影響を与える可能性があるため、構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="0c560-104">Media port range settings can significantly impact client performance and should be configured.</span></span> <span data-ttu-id="0c560-105">これらの設定は、Lync Server 管理シェルを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="0c560-105">You can configure these settings by using Lync Server Management Shell.</span></span>

### <a name="media-port-range-settings"></a><span data-ttu-id="0c560-106">メディア ポート範囲の設定</span><span class="sxs-lookup"><span data-stu-id="0c560-106">Media Port Range Settings</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c560-107">設定</span><span class="sxs-lookup"><span data-stu-id="0c560-107">Setting</span></span></th>
<th><span data-ttu-id="0c560-108">説明</span><span class="sxs-lookup"><span data-stu-id="0c560-108">Description</span></span></th>
<th><span data-ttu-id="0c560-109">Lync Server 管理シェルコマンドレット</span><span class="sxs-lookup"><span data-stu-id="0c560-109">Lync Server Management Shell cmdlet</span></span></th>
<th><span data-ttu-id="0c560-110">コマンドレット パラメーター</span><span class="sxs-lookup"><span data-stu-id="0c560-110">Cmdlet parameters</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c560-111">Portrange\ Enabled</span><span class="sxs-lookup"><span data-stu-id="0c560-111">Portrange\Enabled</span></span></p></td>
<td><p><span data-ttu-id="0c560-p102">サーバーから送信されたポート範囲が、クライアントでメディアと信号に使用される必要があるかどうかを指定します。 サブ値 MinMediaPort および MaxMediaPort と併用されます。</span><span class="sxs-lookup"><span data-stu-id="0c560-p102">Specifies whether the port ranges sent by the server should be used by the client for media and signaling. Used in conjunction with the subvalues MinMediaPort and MaxMediaPort.</span></span></p></td>
<td><p><span data-ttu-id="0c560-114"><strong>Get-csconferencingconfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="0c560-114"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="0c560-115">ClientMediaPortRangeEnabled</span><span class="sxs-lookup"><span data-stu-id="0c560-115">ClientMediaPortRangeEnabled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c560-116">Portrange\MinMediaPort</span><span class="sxs-lookup"><span data-stu-id="0c560-116">Portrange\MinMediaPort</span></span></p></td>
<td><p><span data-ttu-id="0c560-p103">メディアに使用する開始ポート番号を指定します。 MaxMediaPort と組み合わせて、ポート範囲を指定します。 推奨最小範囲は 40 ポートです。</span><span class="sxs-lookup"><span data-stu-id="0c560-p103">Specifies the starting port number to use for media. Combines with MaxMediaPort to specify the range of ports. The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="0c560-120"><strong>Get-csconferencingconfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="0c560-120"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="0c560-121">ClientMediaPort (クライアントのメディアに使用する開始ポート番号を表します。)</span><span class="sxs-lookup"><span data-stu-id="0c560-121">ClientMediaPort (represents the starting port number to use for client media)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c560-122">Portrange\MaxMediaPort</span><span class="sxs-lookup"><span data-stu-id="0c560-122">Portrange\MaxMediaPort</span></span></p></td>
<td><p><span data-ttu-id="0c560-p104">メディアに使用する最大ポート番号を指定します。 MinMediaPort と組み合わせて、ポート範囲を指定します。推奨最小範囲は 40 ポートです。</span><span class="sxs-lookup"><span data-stu-id="0c560-p104">Specifies the highest port number to use for media. Combines with MinMediaPort to specify the range of ports. The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="0c560-126"><strong>Get-csconferencingconfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="0c560-126"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="0c560-127">ClientMediaPortRange (クライアントのメディアに使用できるポートの合計数を示します。既定値は 40 です。)</span><span class="sxs-lookup"><span data-stu-id="0c560-127">ClientMediaPortRange (indicates the total number of ports available for client media; default is 40)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a><span data-ttu-id="0c560-128">メディア ポート範囲の設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="0c560-128">To Configure Media Port Range Settings</span></span>

1.  <span data-ttu-id="0c560-129">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c560-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="0c560-130">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="0c560-130">Run the following cmdlet:</span></span>
    
        Get-CsConferencingConfiguration
    
    <span data-ttu-id="0c560-131">このコマンドレットを実行すると、会議構成設定が戻されます。</span><span class="sxs-lookup"><span data-stu-id="0c560-131">This cmdlet returns the conferencing configuration settings.</span></span>

3.  <span data-ttu-id="0c560-132">変更するパラメーターと値を指定して、次のコマンドレットを実行します (このコマンドレットのパラメーターの詳細については、「Lync Server Management Shell」のドキュメントを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="0c560-132">Run the following cmdlet with the parameters and values you want to change (for details about the parameters for this cmdlet, see the Lync Server Management Shell documentation):</span></span>
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0c560-133">特定サイトの会議構成設定の追加セットを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0c560-133">You can create additional sets of conferencing configuration settings for specific sites.</span></span> <span data-ttu-id="0c560-134">サイト ID と共に <STRONG>New- CsConferencingConfiguration</STRONG> コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="0c560-134">Use the <STRONG>New- CsConferencingConfiguration</STRONG> cmdlet with a site identity.</span></span> <span data-ttu-id="0c560-135">サイトの新しい会議構成設定を作成すると、このサイト設定はグローバル設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="0c560-135">When you create new conferencing configuration settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="0c560-136">詳細については、Lync Server 管理シェルのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c560-136">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

