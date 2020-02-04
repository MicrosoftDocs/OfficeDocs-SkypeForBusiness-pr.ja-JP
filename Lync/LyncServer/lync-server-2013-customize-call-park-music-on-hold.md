---
title: 'Lync Server 2013: コールパークの保留中の音楽をカスタマイズする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Customize Call Park music on hold
ms:assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688031(v=OCS.15)
ms:contentKeyID: 49733621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 301625a36d23c69d02dfdcde8c4985def53630af
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="customize-call-park-music-on-hold-in-lync-server-2013"></a>通話パークをカスタマイズする Lync Server 2013 の保留中の音楽

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-10_

Lync Server 2013 に付属の既定の音楽ファイルの代わりに、自分の音楽ファイルを保留にして、音楽に使用することができます。 保留音をカスタマイズするには、**Set-CsCallParkServiceMusicOnHoldFile** コマンドレットを使用します。

<div>


> [!NOTE]  
> 保留中の音楽をカスタマイズして、複数のサイトで同じ音楽を使う場合は、通話パークアプリケーションを実行する各サイトの音楽ファイルを構成する必要があります。



</div>

<div>

## <a name="to-customize-the-music-file"></a>音楽ファイルをカスタマイズするには

1.  Lync Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 の委任セットアップの権限](lync-server-2013-delegate-setup-permissions.md)」で説明されているように、必要なユーザー権限を持つコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  次のコマンドレットを実行します。
    
        Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte[]>
    
    <div>
    

    > [!TIP]  
    > サービスを識別するには、<STRONG>Get-CsService</STRONG> コマンドレットを使用します。 詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsService">CsService</A>」を参照してください。

    
    </div>
    
    次の例は、soothingmusic.wma というファイルのコンテンツをバイト配列として取得し、変数に割り当てる方法を示しています。 次に音声ファイルをコール パークの保留音ファイルとして割り当てます。 詳細については、「 [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)」を参照してください。
    
        $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
        Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a

</div>

<div>

## <a name="see-also"></a>関連項目


[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

