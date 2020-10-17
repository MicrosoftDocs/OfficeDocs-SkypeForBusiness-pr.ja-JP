---
title: 'Lync Server 2013: トポロジビルダーでのトランクの変更'
description: 'Lync Server 2013: トポロジビルダーでトランクを変更します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a trunk in Topology Builder
ms:assetid: 81055a82-c6f8-47b2-9779-223b1d842f36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688110(v=OCS.15)
ms:contentKeyID: 49733709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f453997664dbe3048a7aa915732b4d95a932dd9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550483"
---
# <a name="modify-a-trunk-in-topology-builder-in-lync-server-2013"></a>Lync Server 2013 のトポロジビルダーでのトランクの変更

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

トランクの代替メディア IP アドレスおよび代替バイパス ID を変更するには、以下の手順に従います。

<div>

## <a name="to-modify-the-alternate-media-ip-address-of-a-trunk"></a>トランクの代替メディア IP アドレスを変更するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  Set-CsPstnGateway コマンドレットを実行し、Lync Server 管理シェルで Nm-server-w15-mgmtshell-short で alternatebypassid フィールドを変更します。
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -RepresentativeMediaIP <IP address>

</div>

<div>

## <a name="to-modify-the-alternate-bypassid-of-a-trunk"></a>トランクの代替バイパス ID を変更するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  Set-CsPstnGateway コマンドレットを実行し、Lync Server 管理シェルで Nm-server-w15-mgmtshell-short で alternatebypassid フィールドを変更します。
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -AlternateBypassID <identifier>

</div>

</div>

<span> </span>

</div>

</div>

</div>

