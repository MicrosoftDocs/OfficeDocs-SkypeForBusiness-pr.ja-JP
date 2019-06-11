---
title: 'Lync Server 2013: 共通の市外局番にポリシーを割り当てる'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign policies to a common area phone
ms:assetid: f0554fd1-b237-49b3-9eb4-26f4b91f5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994082(v=OCS.15)
ms:contentKeyID: 51803993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b792d6ae14ee13fd1d95761d2a0d6b0af7bbdfae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848806"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-policies-in-lync-server-2013-to-a-common-area-phone"></a>Lync Server 2013 で共通の市外局番にポリシーを割り当てる

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-20_

一般的なエリア電話のポリシーを作成した後 (詳細については、「 [Lync Server 2013 でボイスポリシーを作成し、PSTN 使用状況レコードを構成](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)する)」を参照してください。このポリシーは、Windows PowerShell と適切な許可 (Cs) を使って共通の市外局番に割り当てることができます。 **** コマンドレット。 これらのコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>


<div>

## <a name="assigning-a-policy-to-a-single-common-area-phone"></a>単一の一般的な市外局番にポリシーを割り当てる

  - 次のコマンドは、Id の建物14ロビーを持つ共通の市外局番に、ユーザーごとのボイスポリシー RedmondVoice を割り当てます。
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

</div>

<div>

## <a name="assigning-a-policy-to-multiple-common-area-phones"></a>複数の共通エリア電話にポリシーを割り当てる

  - この例では、組織で使用するために構成されているすべての共通エリア電話に、ユーザーごとのボイスポリシー RedmondVoice が割り当てられています。
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

</div>

詳細については、「 [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy)のヘルプトピック」を参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

