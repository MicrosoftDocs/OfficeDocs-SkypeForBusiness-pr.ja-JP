---
title: 会議ディレクトリを移動する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d53e3183d781f527373ffcfb8573da9fbb52d41f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500304"
---
# <a name="move-conference-directories"></a>会議ディレクトリを移動する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-04_

プールを使用停止にする前に、Office Communications Server 2007 R2 プール内の会議ディレクトリごとに次の手順を実行する必要があります。

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>会議ディレクトリを Lync Server 2013 に移動するには

1.  Lync Server 管理シェルを開きます。

2.  組織の会議ディレクトリの ID を取得するには、次のコマンドを実行します。
    
        Get-CsConferenceDirectory
    
    このコマンドレットでは、組織のすべての会議ディレクトリが返されるので、使用停止にするプールのみに結果を絞り込んだ方がよい場合があります。たとえば、pool01.contoso.net という完全修飾ドメイン名 (FQDN) のプールを使用停止にする場合は、次のコマンドを実行します。
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    このコマンドレットでは、サービス ID に pool01.contoso.net という FQDN が含まれるすべての会議ディレクトリが返されます。

3.  会議ディレクトリを移動するには、プール内の会議ディレクトリごとに次のコマンドを実行します。
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    例:
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> 以下に示すようなエラーが発生することがあります。これは、Lync Server 管理シェルによって、Active Directory からの更新されたアクセス許可のセットが必要になることによって発生します。 エラーを解決するには、現在のウィンドウを閉じて、新しい Lync Server 管理シェルを開き、コマンドを再度実行します。



</div>

![Get-csconferencedirectory のエラー出力](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory のエラー出力")

</div>

</div>

<span> </span>

</div>

</div>

</div>

