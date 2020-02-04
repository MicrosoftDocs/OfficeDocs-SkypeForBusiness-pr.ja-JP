---
title: 'Lync Server 2013: hot desking を有効または無効にする'
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
ms.openlocfilehash: 7c56d7ae13be9afa3af7e4732242a86f4be4c458
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736037"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a>Lync Server 2013 でホット desking を有効または無効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-20_

一般的な市外電話は、*ホット卓上電話*として設定できます。 ホットデスク電話では、ユーザーは自分のユーザーアカウントにログオンして、ログオンした後、Lync Server の機能と自分のユーザープロファイル設定を使用できます。 ホット desking は、クライアントポリシーを使用して管理されます。ホット desking を有効または無効にするには、一般的なエリアの電話で使用されるクライアントポリシーを変更する必要があります。 共通のエリア電話に割り当てられている会議ポリシーを確認する方法の詳細については、「 [Lync Server 2013 で一般的な市外局番の情報を表示](lync-server-2013-view-common-area-phone-information.md)する」を参照してください。

電話のホット desキングを有効または無効にするには、**新しい-CSClientPolicy**コマンドレットの Enablehot desキングパラメーターを使用します。または、次のように**設定**します。 これらのコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行します。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>


<div>

## <a name="enabling-hot-desking"></a>ホット desking の有効化

  - 共通の市外局番に対してホット desking を有効にするには、その電話 (または電話の集合) に割り当てられているクライアントポリシーを変更する必要があります。
    
    変更する必要があるポリシーを特定した後、次の手順では、 **Set-CsClientPolicy**コマンドレットを使用して、Enableホット desキングパラメーターを True に設定します。 次に例を示します。
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - または、**新しい-CsClientPolicy**コマンドレットを使用して、ホット desking を有効にする新しいクライアントポリシーを作成することもできます。 次に例を示します。
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> このポリシーを作成したら、適切な共通エリアの電話に割り当てる必要があります。 詳細については、「 <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">Lync Server 2013 で共通の市外局番にポリシーを割り当てる</A>」を参照してください。



</div>

<div>

## <a name="disabling-hot-desking"></a>ホット desking の無効化

  - 一般的な市外電話のホット desking を無効にするには、 **Set-CsClientPolicy**コマンドレットの Enablehot desking パラメーターを既定値の False にリセットします。 次に例を示します。
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

詳細については、「[新しい-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)コマンドレット」および「 [csclientpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy)コマンドレット」のヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

