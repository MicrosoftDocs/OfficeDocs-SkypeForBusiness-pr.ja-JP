---
title: 'Lync Server 2013: hot desking を有効または無効にする'
description: 'Lync Server 2013: hot desking を有効または無効にします。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable hot desking
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994057(v=OCS.15)
ms:contentKeyID: 51803968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fd22c9bf51078324cfe5e215bd154503c2d9b57
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552433"
---
# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a>Lync Server 2013 の [ホット desking] を有効または無効にする

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-20_

共通領域電話を *ホットデスク電話*としてセットアップすることができます。 ホットデスク電話を使用すると、ユーザーは自分のユーザーアカウントにログオンし、ログオンした後、Lync Server 機能と独自のユーザープロファイル設定を使用できます。 Hot desking はクライアントポリシーを使用して管理されます。ホット desking を有効または無効にするには、共通領域電話で使用されるクライアントポリシーを変更する必要があります。 共通領域電話に割り当てられている電話会議ポリシーを確認する方法の詳細については、「 [Lync Server 2013 で共通領域電話情報を表示](lync-server-2013-view-common-area-phone-information.md)する」を参照してください。

次に示すように、 **新しい-CSClientPolicy** コマンドレットまたは **Set-csclientpolicy** コマンドレットの enablehot desキングパラメーターを使用して、電話のホット desキングを有効または無効にします。 これらのコマンドレットは、Lync Server 2013 管理シェルから実行するか、Windows PowerShell のリモートセッションから実行します。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>


<div>

## <a name="enabling-hot-desking"></a>ホット desking の有効化

  - 共通領域電話のホット desking を有効にするには、その電話に割り当てられているクライアントポリシー (または電話のコレクション) を変更する必要があります。
    
    変更する必要があるポリシーを特定したら、次の手順では、 **Set-CsClientPolicy** コマンドレットを使用して Enableホット desキングパラメーターを True に設定します。 以下に例を示します。
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - 別の方法として、 **新しい-CsClientPolicy** コマンドレットを使用して、hot desking を有効にする新しいクライアントポリシーを作成することもできます。 以下に例を示します。
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> このポリシーを作成したら、適切な共通領域電話に割り当てる必要があります。 詳細については、「 <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">Lync Server 2013 のポリシーを共通領域電話に割り当てる</A>」を参照してください。



</div>

<div>

## <a name="disabling-hot-desking"></a>Hot desking の無効化

  - 共通領域電話のホット desking を無効にするには、 **Set-CsClientPolicy** コマンドレットの Enablehot desking パラメーターを既定値の False にリセットします。 以下に例を示します。
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

詳細については、「 [新しい-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) コマンドレット」および「 [Set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) コマンドレット」のヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

