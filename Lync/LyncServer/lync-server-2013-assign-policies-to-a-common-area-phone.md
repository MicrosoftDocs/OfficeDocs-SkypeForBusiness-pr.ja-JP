---
title: 'Lync Server 2013: 共通領域電話へのポリシーの割り当て'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign policies to a common area phone
ms:assetid: f0554fd1-b237-49b3-9eb4-26f4b91f5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994082(v=OCS.15)
ms:contentKeyID: 51803993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67ac175ea9aae83a56bd2706bee3c80418b99ea8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203323"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assign-policies-in-lync-server-2013-to-a-common-area-phone"></a>Lync Server 2013 のポリシーを共通領域電話に割り当てる

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-20_

共通領域電話のポリシーを作成した後 (詳細については、「 [create a voice policy and CONFIGURE PSTN usage records In Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)」を参照してください)、Windows PowerShell と適切な**付与/Cs**コマンドレットを使用して、ポリシーを共通領域電話に割り当てることができます。 これらのコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>


<div>

## <a name="assigning-a-policy-to-a-single-common-area-phone"></a>単一の共通領域電話へのポリシーの割り当て

  - 次のコマンドは、ユーザーごとの音声ポリシー RedmondVoice を、Identity を作成14ロビーの共通領域電話に割り当てます。
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

</div>

<div>

## <a name="assigning-a-policy-to-multiple-common-area-phones"></a>複数の共通領域電話へのポリシーの割り当て

  - この例では、ユーザーごとの音声ポリシー RedmondVoice は、組織での使用が構成されているすべての共通領域電話に割り当てられます。
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

</div>

詳細については、 [set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy)のヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

