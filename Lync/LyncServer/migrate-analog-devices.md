---
title: アナログ デバイスの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e809db03cf098bea07f57673ddcbfc019e15f299
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762975"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-analog-devices"></a>アナログ デバイスの移行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-16_

Lync Server は、アナログデバイスのサポートを提供します。 特に、サポートされているアナログデバイスはアナログオーディオ電話とアナログ fax マシンです。 Lync Server 環境でのアナログデバイスの使用をサポートするために、修飾ゲートウェイを構成することができます。 Lync Server 2010 から Lync Server 2013 に移行した後、アナログデバイスに関連付けられた連絡先オブジェクトも移行する必要があります。 Lync server 管理シェルを使用して、Lync Server 2010 アナログデバイスに関連付けられたすべての連絡先オブジェクトを取得してから、それらのオブジェクトを Lync Server 2013 プールに移動します。

<div>

## <a name="to-migrate-analog-devices"></a>アナログデバイスを移行するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  コマンド ラインで次を入力します。
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  すべての連絡先オブジェクトが Lync Server 2013 プールに移動されていることを確認します。 コマンド ラインで次を入力します。
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  すべての連絡先オブジェクトが Lync Server 2013 プールと関連付けられていることを確認します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

