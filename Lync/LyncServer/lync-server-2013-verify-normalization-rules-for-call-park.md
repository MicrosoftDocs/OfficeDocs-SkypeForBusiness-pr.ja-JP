---
title: 'Lync Server 2013: コールパークの正規化ルールの確認'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify normalization rules for Call Park
ms:assetid: deaa170f-041e-45cb-8eab-f02931ab541e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398981(v=OCS.15)
ms:contentKeyID: 48185646
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dda9fe8d3e0ca9ebc4dec96a8e878fe36576fd41
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113290"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a>Lync Server 2013 でのコールパークの正規化ルールの確認

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-11_

コールパークオービットを正規化することはできません。 オービット番号が正規化されていないことを確認するには、ダイヤルプランを確認してください。 オービットが正規化されないようにするために追加の正規化ルールを作成する必要がある場合は、「 [create a dial plan In Lync Server 2013](lync-server-2013-create-a-dial-plan.md) 」の手順に従って新しい正規化ルールを定義します。これにより、**一致するパターン**でオービット範囲と**変換パターン**が **$1**になります。 たとえば、コールパークオービット範囲が7000–7999の場合、**照合するパターン**は **^ (\\7 d{3}) $** 、**変換パターン**は **$1**になります。

<div>


> [!IMPORTANT]  
> ダイヤルプランの既定の正規化ルールに<STRONG>^ (\d *)</STRONG>が含まれていないことを確認してください。 それ以外の場合、コールパーク正規化ルールは実行されません。



</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でダイヤルプランを作成する](lync-server-2013-create-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

