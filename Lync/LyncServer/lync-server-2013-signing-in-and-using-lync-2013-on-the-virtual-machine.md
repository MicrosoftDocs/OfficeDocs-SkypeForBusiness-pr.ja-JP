---
title: 'Lync Server 2013: 仮想マシンでの Lync 2013 のサインインと使用'
description: 'Lync Server 2013: 仮想マシンで Lync 2013 にサインインして使用します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Signing in and using Lync 2013 on the virtual machine
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204948(v=OCS.15)
ms:contentKeyID: 48184318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad9a92d450fb9d60aed70617089d95280528892f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555683"
---
# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a>仮想マシンでの Lync 2013 のサインインと使用

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-03_

VDI プラグインを有効にした後、ユーザーが Lync 2013 にサインインすると、次の手順が実行されます。

1.  ユーザーは、仮想マシン上で実行されている Lync 2013 クライアントに自分の資格情報を入力します。

2.  Lync は、VDI プラグインの可用性を検出した後、ユーザーに資格情報を再入力するように求めるメッセージを表示します。 このダイアログボックスでは、[ **パスワードを保存** する] チェックボックスをオンにすることをお勧めします。これにより、ユーザーは、以降のサインイン時に資格情報を入力する必要がなくなります。

3.  Lync は、VDI プラグインとのペアリングを開始します。 ペアリングが完了する前に、クライアントは Lync ステータスバーに2つのアイコンを表示します。 次に示す左下のアイコンは利用可能なオーディオ デバイスがないことを示し、右下の点滅するアイコンは VDI ペアリングが進行中であることを示します。
    
    ![ペアリングが成功したことを示す Lync VDI アイコン](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "ペアリングが成功したことを示す Lync VDI アイコン")  

4.  VDI ペアリングが成功すると、通話に使用されるオーディオ デバイスおよび VDI ペアリングが成功したことを示すアイコンに変わります。
    
    ![成功を示す Lync VDI ペアリングアイコン](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "成功を示す Lync VDI ペアリングアイコン")  

5.  Lync を VDI プラグインと組み合わせて使用すると、ユーザーは、ローカルコンピューターに接続されている Lync 互換デバイスでプレゼンスを確認できます。 これで、ユーザーは通常どおり通話を行うことができます。

</div>

<span> </span>

</div>

</div>

</div>

