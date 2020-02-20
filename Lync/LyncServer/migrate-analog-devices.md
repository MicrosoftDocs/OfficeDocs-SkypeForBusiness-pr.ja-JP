---
title: アナログデバイスを移行する
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
ms.openlocfilehash: daa85bae73df45fe8252973a3bf4d4e0690ec4a1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-analog-devices"></a>アナログデバイスを移行する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-16_

Lync Server は、アナログデバイスのサポートを提供します。 具体的には、アナログ音声電話とアナログ FAX 電話がアナログ デバイスとしてサポートされます。 Lync Server 環境でのアナログデバイスの使用をサポートするために、認定ゲートウェイを構成することができます。 Lync Server 2010 から Lync Server 2013 に移行した後、アナログデバイスに関連付けられている連絡先オブジェクトも移行する必要があります。 Lync server 管理シェルを使用して、まず Lync Server 2010 のアナログデバイスに関連付けられているすべての連絡先オブジェクトを取得し、そのオブジェクトを Lync Server 2013 プールに移動します。

<div>

## <a name="to-migrate-analog-devices"></a>アナログ デバイスを移行するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  コマンドラインで、次のように入力します。
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  すべての連絡先オブジェクトが Lync Server 2013 プールに移動されたことを確認します。 コマンドラインで、次のように入力します。
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  すべての連絡先オブジェクトが Lync Server 2013 プールに関連付けられていることを確認します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

