---
title: 'Lync Server 2013: クライアントコンピューター上の個人用連絡先ストアの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the personal contacts store on client computers
ms:assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721922(v=OCS.15)
ms:contentKeyID: 49733857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e035c360d339b48157969c75a1702beff03da634
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a>Lync Server 2013 のクライアントコンピューターでの個人用連絡先ストアの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-02-05_

Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 を統合する場合は、Microsoft Lync 2010 を実行しているすべてのクライアントコンピューターで個人連絡先ストアを構成することをお勧めします。 特に、Exchange を個人連絡先ストアとして使用するように Lync を構成し、同時にユーザーがその決定を上書きできないようにする必要があります。 これを行うには、各クライアントコンピューターでレジストリ値を作成して構成します。

これは、Lync 2013 を実行しているコンピューターでは必要ありません。

ある 1 台のコンピューターでこの値を構成するには、次の手順を実行します。

1.  クライアントコンピューターで、[**スタート**] をクリックし、[**実行**] をクリックします。

2.  [**実行**] ダイアログボックスで、「regedit」と入力し、enter キーを押します。

3.  レジストリエディターで、[ **HKEY\_LOCAL\_MACHINE**] を展開し、[**ソフトウェア**]、[**ポリシー**]、[ **Microsoft**]、[ **Communicator**] の順に展開します。

4.  [ **Communicator**] を右クリックし、[**新規**] をポイントして、[ **DWORD (32 ビット)**] の値をクリックします。

5.  新しい値が作成されたら、「 **」と入力し、** enter キーを押して、値の名前を変更します。

6.  PersonalContactStoreOverride の値が 0 に設定されていることを確認し、レジストリ エディタを閉じます。

複数のコンピューターでこれと同じ変更をする必要がある場合は、カスタム グループ ポリシー オブジェクトを作成します。 詳細については、「」の[https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?linkid=268543)グループポリシーのドキュメントを参照してください。

</div>

<span> </span>

</div>

</div>

</div>

