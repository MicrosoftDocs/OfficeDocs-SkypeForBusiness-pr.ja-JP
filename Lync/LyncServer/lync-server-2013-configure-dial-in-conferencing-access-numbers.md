---
title: 'Lync Server 2013: ダイヤルイン会議アクセス番号の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure dial-in conferencing access numbers
ms:assetid: d8a18030-f318-43dd-834d-70e5014b5e8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398952(v=OCS.15)
ms:contentKeyID: 48185623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d42d8fbe6d3f507d0cadb7dc879b940191c04603
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a>Lync Server 2013 でのダイヤルイン会議アクセス番号の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2011-07-17_

ダイヤルイン会議を展開するときには、ユーザーが公衆交換電話網 (PSTN) からダイヤルして電話会議のオーディオ部分に参加するための電話番号を設定する必要があります。 それらのダイヤルイン アクセス番号は、ミーティングの招待状と [ダイヤルイン会議の設定] Web ページに表示されます。

ダイヤルイン アクセス番号を作成する前に、まずダイヤルイン会議の域を計画し、その地域のダイヤル プランを構成する必要があります。 地域の詳細については、計画ドキュメントの「 [Lync Server 2013 でのダイヤルイン会議の要件](lync-server-2013-dial-in-conferencing-requirements.md)」を参照してください。 ダイヤルイン会議のダイヤルプランの設定の詳細については、「 [Lync Server 2013 でダイヤルイン会議のダイヤルプランを構成する](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)」を参照してください。

<div>


> [!NOTE]  
> このアクセス番号の Active Directory ドメインサービス (AD&nbsp;DS) のレプリケーションが完了するまで、新しいダイヤルインアクセス番号を使用することはできません。 レプリケーションが完了するまでに数時間かかることがあります。



</div>

<div>


> [!NOTE]  
> ダイヤルイン アクセス番号を作成した後は、Active Directory の連絡先オブジェクトの表示名を変更し、ユーザーが正しいアクセス番号を識別しやすくすることができます。 表示名を変更するには、 <STRONG>CsDialInConferencingAccessNumber</STRONG>コマンドレットを使用します。 Active Directory のオブジェクトは手動で変更しないでください。 アクセス番号の変更について詳しくは、「 <STRONG>CsDialInConferencingAccessNumber</STRONG>コマンドレットの Lync Server 管理シェルドキュメント」をご覧ください。



</div>

<div>

## <a name="in-this-section"></a>このセクション中

[Lync Server 2013 でのダイヤルイン会議アクセス番号の作成または変更](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのダイヤルイン会議の要件](lync-server-2013-dial-in-conferencing-requirements.md)  


[Lync Server 2013 でのダイヤルイン会議のダイヤル プランの構成](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

