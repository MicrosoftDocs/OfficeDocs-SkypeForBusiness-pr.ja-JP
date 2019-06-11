---
title: 会議ディレクトリを移動する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ba7480e3454d338d9d6f2ff521c09e26b4f17c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a>会議ディレクトリを移動する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-04_

プールを解除する前に、Office Communications Server 2007 R2 プールの各会議ディレクトリに対して、次の手順を実行する必要があります。

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>会議ディレクトリを Lync Server 2013 に移動するには

1.  Lync Server 管理シェルを開きます。

2.  組織内の会議ディレクトリの id を取得するには、次のコマンドを実行します。
    
        Get-CsConferenceDirectory
    
    このコマンドレットでは、組織内のすべての会議ディレクトリが返されるため、使用停止するプールのみに結果を制限することができます。 たとえば、完全修飾ドメイン名 (FQDN) pool01.contoso.net を使ってプールを撤去する場合は、次のようにします。
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    このコマンドレットは、サービス ID に FQDN pool01.contoso.net が含まれているすべての会議ディレクトリを返します。

3.  会議ディレクトリを移動するには、プール内の各会議ディレクトリに対して次の操作を実行します。
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    次に例を示します。
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> 次のようなエラーが表示されることがあります。これは、Lync Server 管理シェルで、Active Directory に対するアクセス許可の更新されたセットが必要であることが原因で発生する可能性があります。 エラーを解決するには、現在のウィンドウを閉じて、新しい Lync Server 管理シェルを開き、コマンドをもう一度実行します。



</div>

![CsConferenceDirectory の移動エラーの出力](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "CsConferenceDirectory の移動エラーの出力")

</div>

</div>

<span> </span>

</div>

</div>

</div>

