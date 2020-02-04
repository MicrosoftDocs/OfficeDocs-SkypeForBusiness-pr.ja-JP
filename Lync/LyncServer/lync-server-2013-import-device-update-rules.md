---
title: 'Lync Server 2013: デバイス更新ルールをインポートする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import Device Update rules
ms:assetid: 919e9c87-912b-4bc9-92e7-5998fc2e0bf0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994056(v=OCS.15)
ms:contentKeyID: 51803967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 872f729584f14011d18920a676c32205d38c7f62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-device-update-rules-in-lync-server-2013"></a>Lync Server 2013 でデバイス更新ルールをインポートする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

デバイス更新ルールをインポートするには、Windows PowerShell と**インポート-CsDeviceUpdate**コマンドレットを使用する必要があります。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。

<div>


> [!NOTE]  
> リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。



</div>

<div>


<div>

## <a name="to-import-device-update-rules-to-a-single-web-server"></a>デバイス更新ルールを1つの web サーバーにインポートするには

  - 次のコマンドは、デバイス更新ルールを Web サーバー atl-cs-001.litwareinc.com にインポートします。
    
        Import-CsDeviceUpdate -Identity "service:WebServer:atl-cs-001.litwareinc.com" -FileName C:\Updates\UCUpdates.cab

</div>

<div>

## <a name="to-import-device-update-rules-to-all-your-web-servers"></a>すべての web サーバーにデバイス更新ルールをインポートするには

  - この例では、デバイス更新ルールは、組織に展開されているすべての Web サーバーにインポートされます。 このコマンドが動作するためには\\ \\、\\フォルダーの atl-fs-001.litwareinc.com の更新が共有され、すべての Web サーバーで利用できるようになっている必要があります。
    
        Get-CsService -WebServer | ForEach-Object {Import-CsDeviceUpdate -Identity $_.Identity -FileName \\atl-fs-001.litwareinc.com\Updates\UCUpdates.cab}

</div>

詳細については、「[インポート-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate)コマンドレット」のヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのデバイス更新ルールに関する情報を確認する](lync-server-2013-view-information-about-device-update-rules.md)  
[Lync Server 2013 でデバイス更新ルールを承認する](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

