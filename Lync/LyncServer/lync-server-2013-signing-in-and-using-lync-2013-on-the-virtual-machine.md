---
title: 'Lync Server 2013: 仮想マシン上の Lync 2013 へのサインインと使用'
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
ms.openlocfilehash: 40c5c18c4e991c3b53e37e090e7f2d960a32f71c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732037"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a>仮想マシン上の Lync 2013 へのサインインと使用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-03_

VDI プラグインが有効になった後、ユーザーが Lync 2013 にサインインすると、次の手順が発生します。

1.  ユーザーは、仮想マシンで実行されている Lync 2013 クライアントに自分の資格情報を入力します。

2.  Lync は、VDI プラグインの可用性を検出した後、ユーザーに資格情報を再入力するように求めます。 このダイアログボックスでは、ユーザーが [**パスワードを保存**する] チェックボックスをオンにして、以降のサインインで資格情報を入力する必要がないようにすることをお勧めします。

3.  Lync は、VDI プラグインとのペアリングを開始します。 ペアリングが完了する前に、クライアントは Lync ステータスバーに2つのアイコンを表示します。 左下のアイコンは、オーディオデバイスが利用できないことを示し、右下の [点滅] アイコンは、次のように、VDI ペアリングが進行中であることを示します。
    
    ![成功したペアリングを示す Lync VDI アイコン](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "成功したペアリングを示す Lync VDI アイコン")  

4.  VDI ペアリングが成功すると、通話に使用されるオーディオ デバイスおよび VDI ペアリングが成功したことを示すアイコンに変わります。
    
    ![成功を示す Lync VDI ペアリングアイコン](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "成功を示す Lync VDI ペアリングアイコン")  

5.  Lync と VDI プラグインをペアリングした後、ユーザーはローカルコンピューターに接続されている Lync 互換デバイスで自分のプレゼンスを見ることができます。 これで、ユーザーは通常の方法で通話を発信して応答することができます。

</div>

<span> </span>

</div>

</div>

</div>

